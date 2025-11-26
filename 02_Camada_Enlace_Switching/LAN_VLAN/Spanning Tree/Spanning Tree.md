É desejável fornecer redundância de caminho em uma [[WLAN]]]] para garantir a confiabilidade. Isso traz riscos de loop e, portanto, [[Tempestades Broadcast]] na [[WLAN]]]] se houver caminhos ativos alternativos disponíveis entre duas estações. Para eliminar os [[loop]]s em uma [[WLAN]]]], o IEEE elaborou o Spanning Tree Protocol ([[Modelo OSI/Camada Física/Rede com Fio/STP]]). Este capítulo descreve como o [[Modelo OSI/Camada Física/Rede com Fio/STP]] funciona para gerar uma árvore de abrangência dinâmica, apresenta o Rapid Spanning Tree Protocol ([[RSTP]]) e o Multiple Spanning Tree Protocol ([[MSTP]]), dois protocolos derivados do [[Modelo OSI/Camada Física/Rede com Fio/STP]], e descreve como configurar o protocolo de árvore de abrangência em um [[switch]].

![[Spanning Tree.png]]

Em uma [[WLAN]]]], um quadro [[Ethernet]] não registra quantas pontes atravessou. Se houver um loop na rede, os quadros se proliferam e circulam até sobrecarregar a rede.

A figura ao lado mostra como um loop causa proliferação de quadros e ciclos em uma rede.

Antes de o PCA enviar qualquer quadro, as pontes SWA, SWB e SWC não têm nenhuma entrada de endereço para o PCA em suas tabelas de endereços [[MAC]].

Quando o PCA envia seu primeiro quadro, todas as três pontes recebem o quadro, registram o endereço do PCA como sendo no segmento físico A e encaminham o quadro para o segmento físico B.

Depois que SWA encaminha o quadro para o segmento B, SWB e SWC recebem o quadro novamente. Como SWB e SWC não estão cientes de SWA, parece a SWB e SWC que o quadro é enviado de PCA no segmento B. Como resultado, SWB e SWC registram o endereço de PCA como no segmento B e encaminham o novo quadro para o segmento A.

Da mesma forma, depois que SWB encaminha o quadro inicial para o segmento B, SWA e SWC recebem esse quadro. SWC acha que PCA ainda está no segmento B e SWA acha que PCA foi transferido para o segmento B. Em seguida, SWA e SWC encaminham o novo quadro para o segmento A. Dessa forma, o quadro continua circulando na rede de loop. Para piorar a situação, toda vez que um quadro é enviado com êxito, duas cópias do quadro são geradas na rede.