A **[[Subcamada MAC]] (Media Access Control)** é responsável por controlar como os dispositivos na mesma [[rede]] compartilham e acessam o [[Camada Física|meio físico]] (cabo, fibra, ou ondas de rádio) para transmitir dados. A [[MAC]] gerencia o acesso ao meio de transmissão e garante que os dados sejam entregues no lugar certo, utilizando endereços [[MAC]] exclusivos.

### Funções Principais da Subcamada [[MAC]]:

1. **[[Endereçamento]] [[MAC]]**:
    
    - Cada dispositivo de rede possui um [[MAC]] único atribuído a sua interface de rede. A subcamada [[MAC]] usa esses endereços para identificar de forma única cada dispositivo dentro de uma rede local ([[WLAN]]]]).
    - Isso permite que os quadros sejam entregues ao dispositivo correto na rede local, atuando como uma forma de "identificação de hardware".
2. **Controle de Acesso ao Meio**:
    
    - A subcamada [[MAC]] define como os dispositivos podem acessar o meio físico de rede para evitar colisões de dados. Em redes Ethernet, por exemplo, a [[MAC]] pode usar protocolos como o **CSMA/CD (Carrier Sense Multiple Access with Collision Detection)** para regular o acesso ao meio.
    - Em redes sem fio ([[Wi-Fi]]), a subcamada [[MAC]] usa **CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance)** para minimizar colisões.
3. **Encapsulamento de Dados**:
    
    - A subcamada [[MAC]] encapsula os dados recebidos da camada [[LLC]] em quadros (frames) e os prepara para transmissão. Esses quadros contêm, entre outros, os endereços MAC de origem e destino, além dos dados que estão sendo transmitidos.

### Relação entre [[Subcamada MAC|MAC]] e [[LLC]]:

- A **subcamada LLC** é responsável por fornecer uma interface mais abstrata para as camadas superiores (como a [[camada de rede]]), lidando com a multiplexação e identificação dos protocolos de rede (como IPv4 ou IPv6).
- Já a **subcamada MAC** cuida das especificidades do acesso ao meio físico e da entrega dos quadros para o dispositivo correto. Enquanto o LLC foca na comunicação lógica, o MAC lida diretamente com a comunicação física e o controle do acesso ao meio.

Em resumo, a subcamada MAC na camada 2 do OSI é responsável por garantir que os dados sejam transmitidos de maneira ordenada e controlada através do meio físico, usando endereços MAC para identificar dispositivos e protocolos de acesso ao meio para evitar conflitos.