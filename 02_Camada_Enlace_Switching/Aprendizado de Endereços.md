![[aprendizadoendereço1.png]]

Quando um [[Switch]] recebe um quadro de um [[host]]]], ele inunda o quadro em todas as portas, exceto na porta de entrada. Todos os outros [[Ativo e tecnologias de Rede/Host]]s, inclusive o [[host]]]] de destino, na [[WLAN]]]] comutada recebem o quadro de dados. Essa abordagem de encaminhamento é ineficiente e desperdiça largura de banda.

Para aumentar a eficiência do encaminhamento, todo switch Ethernet mantém uma tabela de endereços MAC, que descreve a partir de qual porta um endereço MAC (ou um [[host]]]]) pode ser acessado. Essa tabela permite que o switch encaminhe um quadro de dados somente para o seu destino.

Um switch pode preencher automaticamente sua tabela de endereços MAC aprendendo os endereços MAC de origem dos quadros de entrada em cada porta.

No primeiro passo, o PCA envia um quadro de dados.
O [[Switch]] associa o endereço MAC de origem do quadro de dados à porta de entrada.
Em seguida, o [[Switch]] encaminha o quadro de dados para todas as outras portas.


![[apdend2.png]]

Observe a figura acima. Suponha que o PCA envie um quadro de dados para o PCD. O quadro tem o [[MAC]] A (o endereço MAC do PCA) como endereço MAC de origem e o MAC D (o endereço [[MAC]] do PCD) como endereço MAC de destino.

Quando o quadro chega a porta GigabitEthernet 1/0/1, o [[Switch]] procura a tabela de endereços [[MAC]] com base no endereço MAC de origem no quadro. Se nenhuma correspondência for encontrada, o switch adiciona o [[MAC]] de origem (MAC A) juntamente com a porta G1/0/1 de entrada à tabela de endereços MAC. Em seguida, o [[Switch]] consulta a tabela de endereços MAC com base no endereço MAC de destino. Se nenhuma correspondência for encontrada, o quadro de dados será inundado em todas as portas, exceto na porta de entrada.

O processo de aprendizado é realizado sempre que um quadro é recebido de um endereço MAC de origem desconhecida até que a tabela de endereços MAC esteja totalmente preenchida.

![[apndend3.png]]

PCB PCC e PCD enviam quadros de dados.

O switch associa o endereço MAC de origem de cada quadro de dados recebido com a porta de entrada.

Ao aprender o endereço MAC, um [[Switch]] segue duas regras:

• Um endereço MAC pode ser aprendido somente em uma porta. Se o [[Switch]] descobrir que o endereço MAC aprendido em um ponto já foi aprendido em outro ponto, ele removerá a entrada aprendida anteriormente e adicionará a nova. Essa situação pode ocorrer quando um [[host]]]] é movido de um ponto para outro.
• Mais de um endereço MAC pode ser aprendido em uma porta porque vários hosts podem se conectar a uma porta por meio de um hub.

Para acomodar mudanças na topologia e evitar que entradas inativas ocupem espaço na tabela, o mecanismo de ‘envelhecimento’ é adotado para a tabela de endereços MAC. Quando uma entrada de endereço MAC é aprendida, um cronômetro de ‘envelhecimento’ é iniciado para ela. Se a entrada não for atualizada antes da expiração do cronômetro, a entrada será apagada.

![[encdqdr.png]]
O PCA envia um quadro unicast destinado ao PCD.

Conforme descrito anteriormente, um [[Switch]] encaminha quadros de dados com base na tabela de endereços MAC.

Na figura acima, o PCA envia um quadro de dados destinado ao MAC D, o endereço MAC do PCD. Ao receber o quadro de dados em G1/0/1, o switch pesquisa a tabela de endereços MAC com base no endereço MAC de destino, encontra a entrada para o MAC D e envia o quadro de dados somente pela porta de saída G1/0/4. Nem o PCB nem o PCD recebem o quadro de dados.

Encaminhamento de quadros de [[Broadcast]], [[multicast]] e [[unicast]] desconhecidos para todas as portas, exceto para a porta de entrada.

![[Fltdqdr.png]]Normalmente, nenhuma comutação é necessária ou aos hosts conectados ao mesmo ponto de comutação porque eles podem se comunicar diretamente entre si. Para evitar o encaminhamento inútil de quadros, um quadro de entrada será descartado se o seu endereço de destino tiver sido aprendido no ponto em que foi recebido.

Conforme mostrado na figura acima, o PCA e a PCB estão conectados ao hub ligado à porta G1/0/1 do switch. O switch aprende os endereços do PCA e da PCB na porta GigabitEthernet 1/0/1. Quando o PCA se comunica com a PCB, os quadros chegam à PCB e à porta GigabitEthernet 1/0/1 do [[Switch]]. O PCA descarta os quadros em vez de encaminhá-los.

