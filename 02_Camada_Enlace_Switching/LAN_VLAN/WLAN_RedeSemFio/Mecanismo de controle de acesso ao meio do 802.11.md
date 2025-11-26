O mecanismo [[CSMACD|CSMA/CD]] usado em uma topologia de barramento [[LAN]] controla o acesso ao meio fazendo com que as estações detectem colisões. No entanto, esse mecanismo não é adequado para [[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/WLAN_RedeSemFio/WLAN]], pois os adaptadores dos produtos sem fio não conseguem detectar colisões em um canal. Para resolver o problema, o IEEE 802.11 define o mecanismo [[CSMACA|CSMA/CA]] (Carrier Sense Multiple Access with Collision Avoidance).
  
O mecanismo [[CSMACA|CSMA/CA]] minimiza a probabilidade de colisão introduzindo um atraso de transmissão aleatório e exigindo que as estações escutem o meio para detectar qualquer atividade de transmissão. Depois que uma estação detecta que o meio está ocioso, ela deve esperar um período de tempo aleatório antes de poder transmitir.

Além disso, o IEEE 802.11 oferece um mecanismo de confirmação na camada [[MAC]]. Ou seja, o [[quadro ACK]] é usado para confirmar o quadro de dados. Se o remetente não receber o [[quadro ACK]], ele retransmitirá o quadro de dados. Esse mecanismo de confirmação pode aumentar a confiabilidade da transmissão de dados e proporcionar um recurso de recuperação rápida.

![[MecanismoDeControleDeAcesso.png]]

A seguir, descrevemos como uma estação [[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/WLAN_RedeSemFio/WLAN]] funciona para transmitir quadros :

• A estação escuta o meio em busca de qualquer atividade de transmissão.

• Depois de detectar que o meio está ocioso, a estação continua a escutar o meio por um período idêntico ao **[[DIFS]]** (DCF int

• A estação inicia um cronômetro de **backoff** se nenhuma atividade de transmissão for encontrada no meio quando o intervalo **[[DIFS]]** expirar. O timer de backoff inicial assume um valor arbitrário de número no intervalo de 0 até a janela de contenção (CW). O cronômetro diminui em 1 cada vez que um intervalo de tempo fixo passa. Esse mecanismo de backoff diminui a probabilidade de contenções que podem ocorrer quando duas estações de envio detectam simultaneamente que o meio está ocioso.

• A estação começa a transmitir dados quando o cronômetro de backoff expira. Se a transmissão falhar e for necessária uma retransmissão, o procedimento de backoff se repetirá com o aumento do tamanho da janela de contenção. Se a transmissão for bem-sucedida ou o limite de retransmissão for atingido, a janela de contenção será redefinida para o padrão inicial. Isso garante a equidade entre as estações.

• Se o meio estiver ocupado antes que o cronômetro de backoff expire, o cronômetro de backoff será pausado. Se a estação ainda quiser transmitir dados após detectar que o meio está ocioso novamente, ela aguardará outro [[DIFS]] e o cronômetro de backoff será reiniciado de onde parou. Quando o cronômetro de backoff expirar, a estação poderá transmitir dados.

Com o desenvolvimento contínuo dos serviços de banda larga, a demanda das pessoas por serviços de banda larga móvel está aumentando. Como uma solução de baixo custo, a [[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/WLAN_RedeSemFio/WLAN]] (Wireless Local Area Network, rede local sem fio) tem recebido cada vez mais atenção em todas as esferas da vida. A WLAN tem as vantagens de não precisar de fios, ter instalação rápida e manutenção simples. Ela pode desempenhar um papel importante em situações em que as redes com fio não podem ser implantadas. Neste capítulo, descreveremos os fundamentos e a configuração da WLAN.