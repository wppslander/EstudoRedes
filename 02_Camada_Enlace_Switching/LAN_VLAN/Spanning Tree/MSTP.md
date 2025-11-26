Tanto o [[STP]] quanto o [[RSTP]] usam "uma única instancia do [[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/Spanning Tree/Spanning Tree]]", o que significa que, em uma rede multi-[[VLAN]] com switching, todas as VLANs devem compartilhar uma [[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/Spanning Tree/Spanning Tree|árvore de spanning]] comum e, portanto, ter a mesma topologia. Em um link de tronco, o tráfego é encaminhado ou bloqueado independentemente da [[VLAN]] à qual pertence.

![[MSTP.png]]

Conforme mostrado na figura acima, a porta que conecta SWB a SWA é bloqueada após o cálculo da árvore de abrangência com STP ou RSTP. Como resultado, todo o tráfego do PCA para o servidor é transmitido pelo caminho SWB -> SWC -> SWA, enquanto o caminho entre SWB e SWA fica ocioso.

Como uma [[VLAN]] é essencialmente uma rede comutada de [[Camada Interface de Rede|camada 2]] independente, a execução do cálculo do spanning tree por VLAN para evitar loops em cada VLAN é uma abordagem mais eficiente em um ambiente com várias VLANs. Para isso, foi elaborado o protocolo IEEE 802.1s Multiple Spanning Tree Protocol ([[MSTP]]), que foi posteriormente incorporado ao padrão 802.1Q-2003.

O MSTP permite que você configure "várias instâncias de [[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/Spanning Tree/Spanning Tree]]” em uma rede, com cada instância mapeada para várias [[VLAN]]s e mantendo uma instância spanning tree independente. Isso evita o desperdício de recursos na manutenção de uma instância spanning tree separada para cada VLAN e, ao mesmo tempo, permite que VLANs diferentes tenham topologias de spanning tree diferentes. Como resultado, uma porta pode permitir o tráfego de algumas VLANs e bloquear o tráfego de outras VLANs, dependendo do resultado do cálculo do spanning tree em cada instância.


| ![[MSTP2.png]] |
| -------------- |
A figura acima mostra como o tráfego de diferentes VLANs é compartilhado entre diferentes links. O PCA pertence à VLAN 10, que é mapeada para a instância A, e o PCB pertence à VLAN 20, que é mapeada para a instância B. Como o link entre SWB e SWA está ativo na instância A, os quadros de dados do PCA para o servidor trafegam pelo link. Da mesma forma, o tráfego do PCB para o servidor percorre o link entre SWC e SWA.

