Em cada grupo de [[Link Aggregation|agregação de links]], o compartilhamento de carga baseado em fluxo é realizado. O tráfego do mesmo fluxo de dados trafega pela mesma porta, enquanto o tráfego de diferentes fluxos de dados pode trafegar por diferentes portas-membro.

Os fluxos de dados são identificados com base em um campo de pacote ou em um conjunto de campos de pacote. Normalmente, os endereços MAC de origem e destino são usados para identificar os fluxos de tráfego da [[Camada Interface de Rede|Camada 2]] e os endereços IP de origem e destino são usados para identificar os fluxos de tráfego da [[Camada de Rede|Camada 3]].

![[BalanceamentodeCarga.png]]

Suponha que o endereço [[MAC]] de origem seja usado no SWA na figura acima. Os quadros do PCA e do PCB serão identificados como pertencentes a fluxos de dados diferentes e poderão ser transmitidos por meio de portas diferentes. Da mesma forma, o SWB também transmite os fluxos de dados de retorno por dois links separadamente.