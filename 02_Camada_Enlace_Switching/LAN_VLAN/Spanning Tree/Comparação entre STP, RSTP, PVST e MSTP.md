
| Características                               | STP | RSTP | PVST | MSTP |
| --------------------------------------------- | --- | ---- | ---- | ---- |
| Resolve falhas de loops e permite redundância | SIm | Sim  | Sim  | Sim  |
| Convergência Rápida                           | Não | Sim  | Sim  | Sim  |
| Permite Balancear a Carga                     | Não | Não  | Sim  | Sim  |
O [[STP]] pode formar uma instancia de [[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/Spanning Tree/Spanning Tree]] sem [[loop]] na rede de comutação e, portanto, resolver a falha de loop e obter redundância.

Com base nas funções do [[STP]], o [[RSTP]] proporciona uma convergência mais rápida, permitindo que a [[root port]] entre rapidamente no estado de forwarding, adotando o mecanismo de handshake e definindo o ponto de borda.

O [[MSTP]] e o [[PVST]] formam várias instâncias de spanning tree em um ambiente grande e com várias [[VLAN]]s, para fornecer com eficiência o balanceamento de carga de várias VLANs.

A compatibilidade entre o modo [[PVST]] e outros modos é a seguinte:  
• Para portas de acesso: O modo [[PVST]] é compatível com outros modos em qualquer VLAN.  
• Para pons tronco ou portas híbridas: O modo PVST é compatível com outros modos somente na VLAN 1.

O [[MSTP]] é compatível com o [[STP]] e o [[RSTP]]. Os pacotes STP e RSTP podem ser identificados por dispositivos que executam o [[MSTP]] e aplicados ao cálculo do [[spanning tree]]

Além disso, os cinco estados de porta usados no [[STP]] são reduzidos a três no [[RSTP]] e no [[MSTP]], conforme mostrado Abaixo:

![[MSTP3.png]]
