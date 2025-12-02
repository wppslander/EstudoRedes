#MTCNA #Redes #IGMP

O **IGMP** (Internet Group Management Protocol) é um protocolo da [[Camada de Rede]] utilizado por hosts e [[Roteador]]es [[IPv4]] para gerenciar a participação de grupos de multicast. Ele permite que um host informe um roteador de que deseja receber tráfego de um grupo de multicast específico, otimizando o uso da largura de banda ao enviar dados apenas para os interessados.

### Multicast e IGMP

Em redes IP, o multicast é uma forma eficiente de comunicação "um para muitos", onde um remetente envia um único fluxo de dados para múltiplos receptores simultaneamente. O IGMP é o protocolo chave que permite que os hosts "assine" (join) ou "cancele a assinatura" (leave) desses grupos de multicast.

### Como o IGMP Funciona

1.  **Report de Membros (Membership Report)**: Quando um host deseja receber tráfego de um grupo de multicast, ele envia uma mensagem de "Membership Report" (ou "Join Message") para o roteador local.
2.  **Consultas de Membros (Membership Queries)**: Os roteadores enviam periodicamente "Membership Queries" para a rede local para descobrir quais grupos de multicast ainda têm membros ativos naquela sub-rede.
3.  **Saída de Grupo (Leave Group Message)**: Quando um host não deseja mais receber tráfego de um grupo de multicast, ele pode enviar uma mensagem "Leave Group" para o roteador.

### Versões do IGMP

Existem três versões principais do IGMP:

*   **IGMPv1 (RFC 1112)**: A versão original, que permite aos hosts se juntarem a um grupo de multicast.
*   **IGMPv2 (RFC 2236)**: Adicionou a capacidade para os hosts explicitamente "sair" de um grupo de multicast, acelerando o processo de otimização de tráfego.
*   **IGMPv3 (RFC 3376)**: Introduziu o "Source-Specific Multicast (SSM)", permitindo que os hosts especifiquem de qual fonte (servidor) desejam receber o tráfego multicast, oferecendo maior controle e segurança.

### Importância

O IGMP é crucial para aplicações que dependem de multicast, como streaming de vídeo, teleconferências e jogos online, garantindo que o tráfego de dados seja entregue apenas aos destinatários que o solicitaram, conservando os recursos da rede.
