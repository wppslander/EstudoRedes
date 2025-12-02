#MTCNA #Fundamentos #Identificacao

O **Hostname** (Nome de Host) é um rótulo (label) legível por humanos atribuído a um dispositivo em uma rede. Ele serve para identificar a máquina de uma forma mais amigável do que um endereço numérico ([[IPv4]] ou [[IPv6]]).

### Estrutura

*   **Simples**: Apenas o nome da máquina (ex: `pc-dani`, `srv-arquivos`). Usado principalmente em redes locais pequenas (LAN).
*   **FQDN (Fully Qualified Domain Name)**: O nome completo que especifica a posição exata do host na hierarquia do [[DNS]].
    *   Estrutura: `[Hostname].[Domínio]`
    *   Exemplo: `server1.google.com` (Onde `server1` é o hostname e `google.com` é o domínio).

### Resolução de Nomes

Computadores não entendem nomes, eles entendem números (IPs). Para acessar um host pelo nome, é necessário um mecanismo de tradução:
1.  **Hosts File** (`/etc/hosts`): Um arquivo de texto local no computador que faz o mapeamento manual (ex: `192.168.1.10  meu-servidor`).
2.  **[[DNS]]**: O sistema dinâmico e global que traduz nomes para IPs.

### Curiosidade: Hostname e DHCP
Quando um dispositivo solicita um IP via [[DHCP]], ele geralmente envia seu Hostname no pacote de requisição (`DHCP Request`). Isso permite que o servidor DHCP (ou o Roteador) registre aquele nome, facilitando a identificação de quem está conectado na rede.
