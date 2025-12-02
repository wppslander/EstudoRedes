#MTCNA #Redes #RARP

O **RARP** (Reverse Address Resolution Protocol) é um protocolo da [[Camada de Rede]] que realiza a função inversa do [[ARP]]. Enquanto o ARP traduz um endereço IP conhecido em um endereço MAC físico, o RARP permite que um host físico, como um computador sem disco rígido (diskless workstation), descubra seu próprio endereço IP a partir de seu endereço MAC.

### Funcionamento

1.  **Solicitação**: Ao inicializar, o dispositivo cliente (que conhece seu próprio endereço MAC, mas não seu IP) envia um pacote de broadcast RARP na rede local.
2.  **Servidor RARP**: Um servidor RARP configurado na rede recebe a solicitação. Ele consulta uma tabela que mapeia endereços MAC físicos para endereços IP correspondentes.
3.  **Resposta**: Se o servidor encontrar uma entrada correspondente, ele envia uma resposta unicast de volta ao cliente contendo o endereço IP designado.

### Limitações e Obsolescência

O RARP foi amplamente utilizado no passado, mas possui limitações significativas:
*   **Baixo Nível**: Opera em um nível muito baixo e não fornece informações adicionais de configuração, como máscara de sub-rede ou gateway padrão.
*   **Dependência de Servidor**: Exige um servidor RARP em cada segmento de rede físico, pois as solicitações RARP (broadcast de camada 2) não são roteadas.

Devido a essas limitações, o RARP foi substituído por protocolos mais modernos e robustos, como o **BOOTP** (Bootstrap Protocol) e, posteriormente, o **[[DHCP]]** (Dynamic Host Configuration Protocol), que fornecem uma configuração de rede completa.
