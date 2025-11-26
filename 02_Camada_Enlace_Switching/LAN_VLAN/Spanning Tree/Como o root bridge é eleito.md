Cada [[switch]] em uma "[[WLAN]]]]" tem um bridge ID exclusivo, que consiste na priority bridge + endereço [[MAC]] da caixa. Os valores de prioridade da [[bridge]] são numéricos, sendo que um número menor representa uma prioridade melhor. Quando duas bridge IDs são comparadas, a que tiver a prioridade mais alta vence. Se elas usarem a mesma prioridade, a que tiver o valor de endereço [[MAC]] mais baixo será a vencedora.

![[rootbridgeeleito.png]]

Inicialmente, cada [[switch]] habilitado para [[STP]] na rede assume que é o [[Root Bridge]]. Ao trocar [[BPDU]]s de configuração, os [[switch]]es comparam seus root IDs e elegem aquele com o root ID mais baixo como o [[Root Bridge]]. Depois que da convergência do [[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/Spanning Tree/Spanning Tree]], o [[Root Bridge]] gera e envia [[BPDU]]s de configuração regularmente e os outros dispositivos apenas encaminham esses [[BPDU]]s. Esse mecanismo garante a estabilidade topológica.

No cenário apresentado acima, a SWA é eleita a ponte raiz porque tem o bridge ID mais baixo.

