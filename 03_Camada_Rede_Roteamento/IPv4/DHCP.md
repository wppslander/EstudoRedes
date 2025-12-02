#MTCNA #Redes #DHCP

O **DHCP** (Dynamic Host Configuration Protocol) é um protocolo de gerenciamento de rede utilizado para automatizar o processo de configuração de dispositivos em redes IP. Ele opera na **Camada de Aplicação** (Modelo OSI), mas é fundamental para o funcionamento da [[Camada de Rede]].

> **Nota**: Este artigo foca no **DHCPv4** (para IPv4). O IPv6 possui uma versão separada chamada DHCPv6, embora frequentemente utilize o método SLAAC.

### Como Funciona (Processo DORA)

A comunicação DHCP ocorre tipicamente em quatro etapas, conhecidas pelo acrônimo **DORA**:

1.  **D**iscover (Descoberta): O cliente envia um pacote de [[Broadcast]] na rede procurando por um servidor DHCP disponível.
2.  **O**ffer (Oferta): O servidor DHCP recebe a solicitação e responde (geralmente em unicast ou broadcast, dependendo da implementação) oferecendo um endereço [[IP]] disponível.
3.  **R**equest (Requisição): O cliente aceita a oferta e solicita formalmente aquele endereço ao servidor.
4.  **A**cknowledge (Confirmação): O servidor confirma o aluguel (lease) do endereço IP e fornece os parâmetros finais (Máscara, Gateway, DNS).

### Pools de DHCP

Um **Pool** (conjunto) define o intervalo de endereços IP que o servidor DHCP pode distribuir aos clientes.
*   **Intervalo (Range)**: Define o IP inicial e final (ex: `192.168.88.10` a `192.168.88.254`).
*   **Exclusões**: É comum excluir os primeiros IPs do pool para uso estático (servidores, impressoras, roteadores) para evitar [[Conflito de IP]].
*   **Lease Time**: O tempo que um cliente pode usar o IP antes de precisar renová-lo. Pools para redes Wi-Fi públicas geralmente têm *lease times* curtos (ex: 1 hora) para liberar IPs rapidamente, enquanto redes corporativas usam tempos maiores (ex: 24 horas).

### Saturação e Domínios de Broadcast

Um erro comum no design de redes é criar **Pools DHCP gigantescos** (ex: um /16 com 65.000 IPs) em uma única [[VLAN]].

Isso cria um **Domínio de [[Broadcast]]** massivo. Como o DHCP (e o [[ARP]]) dependem pesadamente de tráfego de broadcast, as consequências físicas e lógicas são severas:
1.  **Saturação da Camada 1**: O meio físico (cabos, ondas de rádio) fica ocupado transmitindo broadcasts inuteis, reduzindo a largura de banda disponível para dados reais.
2.  **Consumo de CPU**: Cada dispositivo na rede precisa processar cada pacote de broadcast para saber se é para ele. Em uma rede com milhares de hosts, isso pode travar dispositivos mais simples.
3.  **Tempestades de Broadcast**: Um loop ou dispositivo defeituoso pode derrubar toda a rede facilmente.

**Solução**: Segmentar a rede em várias [[VLAN]]s menores (subnetting), cada uma com seu próprio escopo DHCP menor.

### Problemas Comuns: O "Rogue DHCP"

Um dos problemas mais críticos e comuns em redes locais é a presença de **múltiplos servidores DHCP** no mesmo domínio de [[Broadcast]].

#### O Cenário
Isso acontece frequentemente quando um usuário conecta acidentalmente um roteador doméstico (com o servidor DHCP ativado) na rede corporativa através de uma de suas portas LAN, em vez da porta WAN.

#### A Consequência
Como o processo de descoberta (DHCP Discover) é feito via Broadcast, todos os servidores DHCP na rede recebem a solicitação.
*   **Corrida**: O cliente aceitará a configuração do servidor que responder primeiro (o [[Oferta|Offer]] mais rápido).
*   **Perda de Conectividade**: Se o cliente aceitar o IP do roteador "pirata" (Rogue), ele receberá um Gateway incorreto.
*   **Conflito de IP**: O roteador pirata pode distribuir IPs que já estão em uso por outros dispositivos.

### Soluções e Mitigação

Para evitar esse caos, utiliza-se um recurso de segurança de Camada 2 chamado **DHCP Snooping** em [[Switch]]es gerenciáveis.

*   **DHCP Snooping**: O administrador define quais portas do switch são "Confiáveis" (Trusted) - onde está o servidor DHCP legítimo - e quais são "Não Confiáveis" (Untrusted). O switch bloqueia ofertas DHCP vindas de portas não confiáveis.
