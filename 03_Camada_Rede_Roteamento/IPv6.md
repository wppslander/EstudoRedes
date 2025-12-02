#MTCNA #Redes #IPv6

O **IPv6** (Internet Protocol version 6) é a versão mais recente do protocolo de internet, desenvolvida para substituir o [[IPv4]] devido ao esgotamento de endereços. Ele opera na [[Camada de Rede]] e traz melhorias significativas em segurança, eficiência de roteamento e capacidade de endereçamento.

### Estrutura do Endereço

Diferente do IPv4 (32 bits), o IPv6 utiliza endereços de **128 bits**. Isso permite um número astronômico de endereços únicos ($2^{128}$), o suficiente para garantir que cada dispositivo na Terra tenha trilhões de endereços próprios.

Os endereços são representados em **[[Hexadecimal]]**, divididos em 8 grupos de 4 dígitos hexadecimais, separados por dois pontos (`:`).
*   Exemplo: `2001:0db8:85a3:0000:0000:8a2e:0370:7334`

### Regras de Abreviação

Para facilitar a leitura, existem regras para encurtar os endereços:
1.  **Omissão de zeros à esquerda**: `0db8` pode ser escrito como `db8`.
2.  **Compactação de zeros (Double Colon `::`)**: Uma sequência contínua de grupos de zeros pode ser substituída por `::`, mas apenas uma vez por endereço.
    *   O exemplo acima ficaria: `2001:db8:85a3::8a2e:370:7334`.

### Tipos de Endereçamento

O IPv6 elimina o conceito de Broadcast e utiliza três tipos principais de comunicação:

1.  **Unicast**: Um para Um. Identifica uma interface única. Um pacote enviado a um endereço unicast é entregue apenas àquela interface.
2.  **Multicast**: Um para Muitos. Identifica um grupo de interfaces. Um pacote enviado é entregue a todas as interfaces do grupo.
3.  **Anycast**: Um para o Mais Próximo. Identifica um grupo de interfaces, mas o pacote é entregue apenas à interface mais próxima (em termos de distância de roteamento).

### Melhorias em relação ao IPv4

*   **Cabeçalho Simplificado**: O cabeçalho do IPv6 tem um tamanho fixo e menos campos que o do IPv4, facilitando o processamento pelos [[Roteador]]es.
*   **Sem necessidade de [[NAT]]**: Com a abundância de endereços, cada dispositivo pode ter um endereço global único, restaurando a conectividade fim-a-fim.
*   **Autoconfiguração (SLAAC)**: Dispositivos podem gerar seus próprios endereços IPv6 automaticamente ao se conectarem a uma rede, sem necessidade de um servidor [[DHCP]] (embora o DHCPv6 também exista).
*   **Segurança Nativa**: O suporte a IPsec (segurança de IP) foi projetado como parte mandatória da arquitetura do IPv6 (embora sua implementação prática varie).

### Resumo

O IPv6 é essencial para o futuro da Internet, permitindo a expansão contínua de dispositivos conectados e oferecendo uma arquitetura de rede mais eficiente e moderna.
