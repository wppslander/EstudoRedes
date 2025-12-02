#MTCNA #IPv4 #Redes

Além das Classes (A, B, C) e dos endereços Privados, o protocolo IPv4 reserva intervalos de endereços para funções específicas de manutenção, teste e comunicação especial. Estes endereços **nunca** devem ser atribuídos manualmente a um dispositivo em uma rede de produção normal.

### 1. Loopback (`127.0.0.0/8`)
*   **Intervalo**: `127.0.0.1` a `127.255.255.254`
*   **Endereço mais famoso**: `127.0.0.1` (Localhost).
*   **Função**: Usado para que o computador se comunique consigo mesmo.
*   **Utilidade**:
    *   Testar se a pilha TCP/IP do sistema operacional está funcionando corretamente, independente da placa de rede física ou cabos.
    *   Acessar serviços (como servidores Web ou Bancos de Dados) rodando na própria máquina.
    *   Qualquer pacote enviado para `127.x.x.x` nunca sai do computador; ele "dá a volta" (loops back) na camada de software.

### 2. Rota Padrão / Endereço "Desconhecido" (`0.0.0.0`)
Este endereço tem significados diferentes dependendo do contexto:

*   **Como Origem (Source)**:
    *   Usado por um dispositivo que **ainda não tem um IP**.
    *   Exemplo: Quando um computador liga e envia um **DHCP Discover**, ele diz "Eu sou `0.0.0.0` enviando para `255.255.255.255`".
*   **Como Destino (Rota Padrão)**:
    *   Representa "Qualquer Rede" ou "O resto do mundo".
    *   Nos roteadores, a rota `0.0.0.0/0` é a **Rota Default**. Significa: "Se você não sabe para onde enviar este pacote, envie por aqui (geralmente para o provedor de internet)".

### 3. Broadcast Limitado (`255.255.255.255`)
*   **Função**: Envia dados para **TODOS** os dispositivos na mesma rede local (mesmo domínio de broadcast).
*   **Diferença do Broadcast de Rede**:
    *   Broadcast de Rede (ex: `192.168.1.255`): Destinado a todos na sub-rede 192.168.1.0.
    *   Broadcast Limitado (`255.255.255.255`): Destinado a "quem estiver me ouvindo neste cabo agora".
*   **Regra de Ouro**: Roteadores **NUNCA** encaminham pacotes destinados a `255.255.255.255`. Eles morrem na interface local.

### 4. Link-Local / APIPA (`169.254.0.0/16`)
*   **Intervalo**: `169.254.0.1` a `169.254.255.254`
*   **Função**: Atribuição Automática de IP Privado (APIPA).
*   **Cenário**: Se o seu computador (Windows/Linux) está configurado para obter IP via [[DHCP]], mas **não consegue encontrar o servidor**, ele se auto-atribui um endereço neste intervalo.
*   **Sintoma**: Se você ver um IP começando com `169.254...`, significa que o DHCP falhou e você está sem conectividade com a rede externa.

### 5. Redes de Documentação (`192.0.2.0/24`, `198.51.100.0/24`, `203.0.113.0/24`)
*   Reservados especificamente para serem usados em exemplos de livros, manuais e aulas (como esta!), para evitar que autores usem IPs reais que possam pertencer a empresas.
