![[desvantagemstp.png]]

Apesar de todos os seus benefícios, o tempo de "convergência" da topologia com o [[STP]] não é suficientemente rápido, pois é necessário o dobro do atraso de encaminhamento para que uma porta habilitada para [[STP]] faça a transição do estado de blocking para o estado de forwarding. Isso significa dezenas de segundos intoleráveis para que uma rede recupere sua conectividade após a ocorrência de uma mudança de topologia. Se as mudanças de topologia ocorrerem com frequência, a rede perderá constantemente sua conectividade, o que resultaria em uma experiência ruim para o usuário.

Para acelerar a convergência da rede, o Rapid Spanning Tree Protocol ([[RSTP]]) foi desenvolvido com base no STP.