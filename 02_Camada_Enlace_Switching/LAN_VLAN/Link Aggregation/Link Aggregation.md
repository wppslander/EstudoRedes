O link aggregation, ou agregação de link é uma tecnologia comum para aumentar a largura de banda e melhorar a confiabilidade em uma rede [[Ethernet]].  
Este capítulo descreve como a agregação de links funciona para obter maior largura de banda e compartilhamento de carga e como configurar e manter a agregação de links nos [[switch]]es Intelbras.

![[LinkAggregation.png]]

Benefícios

A agregação de links atribui várias portas [[Ethernet]] físicas em um grupo de agregação lógico. Para cada grupo de agregação de links, é criada uma interface agregada. Para as entidades da camada superior que usam o serviço de agregação de links, os links físicos agregados parecem um único link lógico e o tráfego de dados é transmitido pela interface agregada. A agregação de links oferece os seguintes benefícios:

• Maior largura de banda: em cada grupo de agregação de links, o tráfego é distribuído entre as portas membros de acordo com um algoritmo de domínio. Assim, a agregação de links aumenta a velocidade do link além dos limites de uma única porta.

• Maior confiabilidade do link: As portas membros em um grupo de agregação de links fazem backup dinâmico umas das outras. Quando uma porta membro falha, seu tráfego é automaticamente transferido para outras portas membros.