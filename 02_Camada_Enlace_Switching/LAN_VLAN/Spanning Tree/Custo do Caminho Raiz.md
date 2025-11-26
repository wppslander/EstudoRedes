![[CustoCaminhoRaiz.png]]

Cada enlace tem um custo de caminho de raiz. Para o [[root bridge]], o custo do caminho raiz é zero. Para aqueles que não são root bridge, é a soma de todos os custos do caminho da porta no caminho de menor custo até o [[root bridge]].

Normalmente, o custo do caminho de uma porta é determinado por sua largura de banda física. Quanto maior a largura de banda, menor o custo do caminho da porta.

O IEEE 802.1d e o IEEE 802.1t definem os custos de caminho padrão para links (portas) [[Ethernet]] que operam a taxas diferentes em modos diferentes. A Intelbras otimiza o esquema de custo de caminho para melhor uso em redes reais, conforme mostrado abaixo. Para obter detalhes, consulte a documentação padrão relacionada e os manuais dos produtos.

![[CustoDoCaminho.png]]

Por padrão, os [[switch]]es Intelbras calculam os custos do caminho da porta com base no padrão proprietário da Intelbras. Você pode alterar manualmente o custo do caminho de uma porta conforme necessário para afetar o cálculo de do [[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/Spanning Tree/Spanning Tree]].

