Apesar do risco de ciclagem e proliferação de quadros em uma rede comutada em [[loop]], as pontes transparentes são populares por seu bom desempenho em uma rede sem [[loop]]. A questão é como eliminar os loops e, ao mesmo tempo, manter a redundância do caminho.

Para resolver o problema, o IEEE elaborou o 802.1D Spanning Tree Protocol ([[STP]]). O STP 802.1D poda uma rede em ponte com [[loop]] em uma [[Topologia de Árvore Sem Loop]], bloqueando links redundantes. Quando um link ativo é desconectado, o STP recupera a conectividade da rede ao desbloquear seu link redundante.

![[STP.png]]

A figura acima mostra o diagrama de uma rede em ponte podada em uma árvore que se estende a partir de um [[switch]] raiz. No diagrama, as linhas sólidas representam links ativos, ou seja, ramos da árvore, e as linhas tracejadas representam links redundantes bloqueados, que serão desbloqueados somente quando os links ativos forem desconectados.

Divisão de domínios de [[Broadcast]] com [[switch]]

A figura acima mostra o diagrama de uma rede em ponte podada em uma árvore que se estende a partir de um [[switch]] raiz. No diagrama, as linhas sólidas representam links ativos, ou seja, ramos da árvore, e as linhas tracejadas representam links redundantes bloqueados, que serão desbloqueados somente quando os links ativos forem desconectados.

![[STP2.png]]



O STP IEEE 802.1d elimina [[loop]]s na [[Camada Interface de Rede]] em uma [[WLAN]]]]. Os dispositivos que executam esse protocolo detectam [[loop]]s na rede por meio da troca de informações entre eles e eliminam os [[loop]]s bloqueando seletivamente as portas para transformar a topologia em [[loop]] em uma [[Topologia de Árvore Sem Loop]].

Unidade de dados de protocolo do STP

O STP usa **Bridge Protocol Data Units** ([[BPDU]]s) para trocar informações para o cálculo do spanning tree. Há dois tipos de BPDUs:

• BPDUs de configuração, usados para calcular um spanning tree e manter a topologia do spanning tree.

• BPDUs de notificação de alteração de topologia (TCN), usados para notificar os dispositivos em questão sobre alterações na topologia da rede, se houver.

**Hello**: As BPDUs são enviadas/recebidas a cada 2 segundos

**Max Age**: Caso o [[switch]] não receba uma [[BPDU]] em até 20 segundos, ele vai entender que aquele caminho não está mais ativo e vai então iniciar uma notificação para renegociação dos status das portas.

Cada BPDU de configuração contém essas informações para o cálculo do spanning tree:
  
• **Root ID**
O identificador exclusivo da ponte que o [[switch]] transmissor acredita ser a raiz. A ponte com o ID raiz mais baixo é eleita como a ponte raiz.

• **Custo do caminho da raiz**
O caminho de menor custo de uma ponte ou porta até a ponte raiz. Na eleição da porta raiz em uma ponte, a ponte com o menor custo do caminho raiz é eleita a porta raiz da ponte. Na eleição da ponte designada em cada segmento físico em uma [[WLAN]]]] em ponte, a ponte com o menor custo do caminho raiz é eleita a ponte designada para o segmento físico. O custo do caminho da raiz da ponte raiz é zero.

• **Designated bridge ID**
A ID de cada ponte em uma[[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/WLAN_RedeSemFio/WLAN]] para a eleição da ponte designada. Ele consiste na prioridade e no endereço [[MAC]] da ponte. Caso haja duas ou mais pontes na [[WLAN]]]] com o menor custo de caminho raiz, aquela com o menor ID de ponte designada é eleita como a ponte designada para a [[WLAN]]]].

• **Designated port ID**
A ID de cada porta que conecta uma porta designada à [[WLAN]]]]. Ele consiste na prioridade da porta designada e no índice da porta. O ponto com o menor ID de ponto designado é eleito a porta designada para a [[WLAN]]]].
Inicialmente, cada [[switch]] habilitado para [[STP]] na rede envia um [[BPDU]] de configuração de cada porta, indicando a si mesmo como a raiz. No BPDU de configuração, o custo do caminho da raiz é 0, o Designated bridge ID é o ID do dispositivo e o Designated port ID é o ID do ponto de transmissão. As bridges da rede calculam o spanning tree comparando os BPDUs de configuração recebidos de outros dispositivos. Como resultado:

• Um **Root bridge** exclusivo é eleita para a topologia spanning tree.

• Uma **Designated bridge** é escolhida para cada segmento de rede.

• Um **Root port** e um **Designated port** são eleitos em cada Designated bridge para o encaminhamento do tráfego.

As seções seguintes descrevem detalhadamente como uma topologia spanning tree é criada.

## Status das portas

O IEEE 802.1d STP define cinco status de portas:

• **Disabled**: Uma porta nesse estado não recebe nem envia nenhum pacote. Esse estado pode ser causado porque a camada física da porta não está ativa ou porque a porta está administrativamente desligada.

• **Blocking**: Uma porta nesse estado só pode receber BPDUs de configuração e enviá-los à CPU. Ela não pode enviar BPDUs de configuração, encaminhar dados de usuário ou aprender endereços MAC.  

• **Listening**: Uma porta nesse estado não encaminha dados de usuário nem aprende endereços MAC, mas pode receber e enviar BPDUs de configuração.

• **Learning**: Uma porta nesse estado não encaminha dados de usuário, mas pode aprender endereços MAC e receber, processar e enviar BPDUs de configuração.

• **Forwarding**: Uma porta nesse estado pode encaminhar dados de usuário, aprender endereços MAC e receber, processar e enviar BPDUs de configuração.

Desses cinco estados de porta, listening e learning são estados status intermediários.

### Transição dos status das portas

![[Transição das portas.png]]

O status de uma porta muda "junto com as mudanças de topologia".

Quando uma porta deixa de ser o root ou designated devido a uma alteração na topologia, ela passa imediatamente para o estado de blocking.

Quando uma porta é eleita a [[root port]] ou designated port, ela passa do estado de blocking para o estado de listening primeiro e, em seguida, para o estado de learning após sofrer um atraso no encaminhamento e, finalmente, para o estado de forwarding após sofrer outro atraso no encaminhamento, conforme mostrado na figura acima.

O atraso no encaminhamento é introduzido para garantir que, quando a topologia mudar, as novas [[BPDU]]s de configuração possam se propagar por toda a rede antes que uma [[root port]] ou designated port mude para o estado de forwarding, a fim de evitar [[loop]]s temporários que possam ocorrer devido à convergência incompleta da rede.

O atraso de encaminhamento padrão é de 15 segundos, conforme definido no IEEE 802.1d STP.