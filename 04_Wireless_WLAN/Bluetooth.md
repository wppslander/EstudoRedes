O **Bluetooth** é uma tecnologia de comunicação sem fio que permite a troca de dados entre dispositivos em distâncias curtas, geralmente em uma faixa de até 10 metros. É amplamente utilizado para conectar dispositivos como fones de ouvido, teclados, mouses, impressoras e dispositivos móveis.

### Como o Bluetooth se Encaixa nas Camadas OSI

O Bluetooth pode ser relacionado principalmente às camadas 1, 2 e 3 do modelo OSI:

1. **Camada 1 - [[Camada Física]]**:
    
    - O Bluetooth opera na camada física, utilizando ondas de rádio na faixa de frequência de 2,4 GHz. Essa camada é responsável pela transmissão e recepção de sinais de rádio entre dispositivos.
2. **Camada 2 - [[Camada Interface de Rede|Camada de Enlace de Dados]]**:
    
    - O Bluetooth também opera na camada de enlace de dados, onde protocolos de controle de acesso ao meio ([[MAC]]) e protocolos de controle de enlace lógico (L2CAP) são usados. A camada de enlace de dados cuida da detecção de erros e da sincronização de dados entre dispositivos conectados.
3. **Camada 3 - [[Camada de Rede]]**:
    
    - Embora o Bluetooth não seja um protocolo de rede tradicional, ele pode ser considerado em algumas situações na camada de rede. O Bluetooth pode criar uma rede chamada **piconet**, onde um dispositivo central (master) se conecta a até sete dispositivos periféricos (slaves). A comunicação entre esses dispositivos pode envolver o roteamento de dados, semelhante ao que ocorre na camada de rede.

### Resumo

- **Bluetooth** é uma tecnologia de comunicação sem fio que permite a troca de dados entre dispositivos a curtas distâncias.
- Nas camadas OSI, o Bluetooth se encaixa nas camadas 1 (física), 2 (enlace de dados) e, em algumas situações, na camada 3 (rede).
- Ele utiliza ondas de rádio para a transmissão de dados e protocolos específicos para garantir uma comunicação confiável e eficiente entre dispositivos conectados.