Uma trunk port permite a passagem de quadros de "várias" [[VLAN]]s. Ele não manipula tags de [[VLAN]] para quadros de quaisquer [[VLAN]]s, exceto aquelas com o [[PVID]].
Ao encaminhar um quadro com etiqueta [[PVID]] de saída, a porta do tronco retira a etiqueta. Ao receber um quadro sem tag de entrada, a porta do tronco marca o quadro com o [[PVID]].

As trunk ports são normalmente usadas para conectar [[switch]]es.

![[trunkport.png]]

A figura acima mostra como as tags de [[VLAN]] são manipuladas quando os [[switch]]es encaminham o tráfego entre PCA e PCC e entre PCB e PCD.

Quando um quadro [[Ethernet]] do PCA chega à access port GigabitEthernet 1/0/1 do SWA, o SWA marca o quadro com o [[PVID]] da GigabitEthernet 1/0/1, [[VLAN]] 10, por exemplo, e encaminha o quadro marcado para fora da trunk port GigabitEthernet 1/0/24 para o SWB. O SWB examina o endereço [[MAC]] de destino e a tag de [[VLAN]] do quadro e, em seguida, o entrega à porta GigabitEthernet 1/0/1. Como o [[PVID]] da porta GigabitEthernet 1/0/1 é [[VLAN]] 10, o SWB retira a tag de [[VLAN]] e encaminha o quadro sem tag para o PCC.

Vejamos como um quadro enviado da PCB para a PCD é processado. A access port GigabitEthernet 1/0/2 no SWA marca o quadro com [[PVID]] 20 e o envia para a trunk port de saída GigabitEthernet 1/0/24. Como o [[PVID]] da porta tronco é a [[VLAN]] 20, o quadro é enviado com a tag removida. Quando o quadro sem tag chega à porta GigabitEthernet 1/0/24 do SWB, o SWB marca o quadro com a VLAN 20 (o PVID do ponto) e o envia para a porta GigabitEthernet 1/0/2. Como o [[PVID]] do ponto GigabitEthernet 1/0/2 é [[VLAN]] 20, o SWB retira a tag de [[VLAN]] e encaminha o quadro sem tag para o PCD.