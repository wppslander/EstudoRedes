#MTCNA #Redes #ARP

O **ARP** (Address Resolution Protocol) é um protocolo da [[Camada de Rede]] responsável por mapear endereços IP lógicos (camada 3) para endereços MAC físicos (camada 2) dentro de uma rede local. Ele é essencial para que dispositivos na mesma rede possam se comunicar diretamente, pois o roteamento de pacotes IP depende do conhecimento do endereço MAC do próximo salto.

### Como o ARP Funciona

Quando um dispositivo (Host A) precisa enviar um pacote IP para outro dispositivo (Host B) na mesma rede local, mas não conhece o endereço MAC de Host B, ele segue este processo:

1.  **ARP Request (Requisição ARP)**: Host A envia uma mensagem de **broadcast** para todos os dispositivos na rede local perguntando: "Qual é o endereço MAC para o endereço IP X.X.X.X (endereço IP de Host B)?".
2.  **ARP Reply (Resposta ARP)**: O dispositivo que possui o endereço IP solicitado (Host B) responde com uma mensagem de **unicast** (diretamente para Host A) dizendo: "O endereço MAC para X.X.X.X é YYYY.YYYY.YYYY".
3.  **Atualização da Cache ARP**: Host A recebe a resposta e armazena o mapeamento IP-MAC em sua **cache ARP** local por um determinado período. Isso evita que ele precise fazer uma nova requisição ARP para o mesmo destino imediatamente.

### Cache ARP

A cache ARP é uma tabela mantida por cada dispositivo de rede que armazena os mapeamentos IP-MAC aprendidos. Se um dispositivo precisa se comunicar com um endereço IP cujo mapeamento já está na cache, ele pode usar essa informação diretamente, agilizando a comunicação e reduzindo o tráfego de broadcast. As entradas na cache ARP têm um tempo de vida (TTL) e são removidas se não forem usadas.

### Relação com Hostname e DNS

Muitas vezes surge a confusão: "O ARP resolve o nome do computador?"

**Não.** O ARP resolve apenas **IP $\rightarrow$ MAC**.
Existe uma cadeia de eventos que ocorre quando você tenta acessar um computador pelo nome (ex: `ping computador-dani`):

1.  **Resolução de Nome**: O seu computador usa o [[DNS]] (ou arquivo hosts) para descobrir que `computador-dani` corresponde ao IP `192.168.1.50`.
2.  **Resolução de Endereço (ARP)**: Agora que seu computador tem o IP (`192.168.1.50`), ele usa o **ARP** para descobrir qual é o [[MAC]] address daquele IP.
3.  **Envio**: O dado é enviado para o MAC descoberto.

### Protocolos Relacionados

*   **[[RARP]] (Reverse ARP)**: Realiza o processo inverso do ARP. Enquanto o ARP busca um endereço MAC a partir de um IP, o RARP é usado por dispositivos para descobrir seu próprio endereço IP a partir de seu endereço MAC (geralmente na inicialização). Foi amplamente substituído pelo [[DHCP]].
