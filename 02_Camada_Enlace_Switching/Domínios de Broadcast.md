Os quadros de broadcast são quadros com o endereço [[MAC]] de destino FFFF.FFFF.FFFF. Um quadro de broadcast deve ser recebido por todos os dispositivos da [[WLAN]]]], exceto o remetente. Os hosts que um quadro de broadcast pode alcançar formam um domínio de broadcast. Embora um [[Switch]] de camada 2 divida os domínios de colisão, ele não divide os domínios de broadcast. Um quadro de broadcast será encaminhado para fora de todas as portas, exceto a porta de entrada.

Para isolar os domínios de broadcast, você pode implementar roteadores ou [[Switch]]es de camada 3. Cada porta da Camada 3 em um roteador ou [[Switch]] da Camada 3 forma o limite de um domínio de broadcast. Como alternativa, você pode criar LANs virtuais em switches da Camada 2.

![[DominioBroadcast.png]]

Conforme mostrado na figura acima, o PCA e a PCB estão conectados a um hub. Os quadros de broadcast que o PCA envia podem alcançar a PCB porque um hub não encerra um domínio de broadcast. No entanto, os quadros não podem alcançar o PCC ou o PCD porque o PCA e o PCB estão isolados do domínio de broadcast do PCC e do PCD por um switch de camada 3.