#MTCNA #MTCSWE

A tecnologia de rede local virtual (VLAN) foi introduzida para limitar as transmissões em uma [[WLAN]]]] comutada. Ela divide uma [[WLAN]]]] em vários domínios de [[Broadcast]] independentes da Camada 2, denominados VLANs. Cada VLAN é um domínio [[broadcast]], os quadros são trocados somente entre portas atribuídas à mesma VLAN.

Visão geral de [[VLAN]]

[[Broadcast]]

Embora os switches em uma rede "[[Ethernet]]" dividam uma "[[WLAN]]]] em domínios de visão menores, eles não dividem o domínio de broadcast. Todas as portas em uma Ethernet comutada ainda estão no mesmo domínio de broadcast e os quadros de transmissão de um PC podem ser recebidos por todos os PCs na [[WLAN]]]]. Assim, os recursos limitados da rede são ocupados por tráfego de transmissão inútil.

Conforme mostrado na figura acima, os quadros de transmissão dos quatro PCs são todos transmitidos na[[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/WLAN_RedeSemFio/WLAN]]. Se a taxa de quadros de transmissão de cada PC for de 100 kbps, a taxa total de quadros de transmissão dos quatro PCs será de 400 kbps, o que representa 0,4% da largura de banda total em um link de 100 Mbps. Se houver 400 PCs na[[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/WLAN_RedeSemFio/WLAN]], a taxa de tráfego de broadcast ocupará 40 Mbps, 40% da largura de banda total do link. Ocupado com um tráfego de broadcast excessivo, um dispositivo ou [[host]]]] de rede ficará mais lento e, por fim, apresentará problemas.

Para melhorar o desempenho de uma [[WLAN]]]], as transmissões devem ser isoladas.

![[Imagens/Vlan1.png]]

Uma maneira de limitar as transmissões de [[Broadcast]] é implementar [[Roteador]]es. As interfaces de um [[Roteador]] formam limites entre os domínios de broadcast e terminam os quadros de broadcast. Um roteador não envia transmissões de broadcast recebidas em uma interface para outras interfaces, conforme mostrado na figura ao lado.

No entanto, o preço dos [[Roteador]]es é mais alto. Além disso, o desempenho de encaminhamento da maioria dos roteadores de baixo e médio porte não é tão alto quanto o de um [[Switch]], pois eles realizam encaminhamento de software em vez de encaminhamento de hardware. Isso pode criar gargalos de desempenho na rede.

Uma maneira de limitar as transmissões de broadcast é implementar roteadores. As interfaces de um roteador formam limites entre os domínios de broadcast e terminam os quadros de broadcast. Um roteador não envia transmissões de broadcast recebidas em uma interface para outras interfaces, conforme mostrado na figura abaixo.

![[Imagens/Vlan2.png]]

Divisão de domínios de [[Broadcast]] com [[Switch]]

O uso da tecnologia VLAN nos [[Switch]]es é uma maneira mais econômica de isolar as transmissões do que os [[roteadores]]. A tecnologia VLAN divide uma [[WLAN]]]] em [[WLAN]]]]s lógicas menores, sendo cada uma delas um domínio de [[broadcast]]. Enquanto os dispositivos na mesma VLAN podem se comunicar como se estivessem em uma[[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/WLAN_RedeSemFio/WLAN]], os dispositivos em diferentes VLANs são isolados na [[Camada Interface de Rede|Camada 2]]. Para permitir a comunicação entre VLANs, são necessários roteadores ou switches de [[Camada de Rede|camada 3]]. Dessa forma, os quadros de transmissão são confinados em uma VLAN. Atualmente, a maioria dos [[Switch]]es [[Ethernet]] oferece suporte à VLAN.

![[Vlan3.png]]

Benefícios da utilização e VLAN

Com a tecnologia VLAN, uma[[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/WLAN_RedeSemFio/WLAN]] é segmentada logicamente em uma base organizacional e não em uma base de localização física. Todas as estações de trabalho e servidores em um grupo de trabalho panicular podem ser atribuídos à mesma VLAN, independentemente de sua localização física na[[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/WLAN_RedeSemFio/WLAN]].

A tecnologia VLAN oferece os seguintes benefícios:

• Isola o tráfego de broadcast em VLANs individuais. Isso reduz o desperdício de largura de banda e melhora o desempenho da rede.

• Melhora a segurança da[[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/WLAN_RedeSemFio/WLAN]]. Ao atribuir grupos de usuários a diferentes VLANs, é possível isolá-los na Camada 2. Os hosts em diferentes VLANs podem se comunicar somente por meio de um roteador ou switch de camada 3.

• Criação flexível de grupos de trabalho virtuais. Como os usuários do mesmo grupo de trabalho podem ser atribuídos à mesma VLAN, independentemente de sua localização física, a construção e a manutenção da rede são muito mais fáceis e flexíveis.
