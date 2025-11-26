Um **loop de rede** ocorre quando há um ciclo de conexão redundante entre [[switch]]es ou dispositivos de rede, fazendo com que os pacotes fiquem presos em uma transmissão contínua entre os dispositivos. Esse ciclo contínuo causa a replicação infinita de pacotes de dados, resultando em uma sobrecarga de tráfego que pode paralisar a rede.

### Como um Loop de Rede Acontece

Um loop de rede geralmente ocorre devido a uma configuração incorreta ou à ausência de protocolos que controlem redundância. Imagine o seguinte cenário:

1. **Conexões Redundantes**: Para fornecer redundância e evitar falhas, muitas redes criam caminhos alternativos, conectando [[switch]]es entre si de forma redundante.
2. **Ciclo Infinito**: Sem um mecanismo para controlar esses caminhos redundantes, como o **Spanning Tree Protocol ([[STP]])**, os pacotes podem começar a circular repetidamente entre os switches, criando um loop.
3. **Multiplicação de Pacotes**: Cada pacote que entra no loop pode ser replicado indefinidamente, pois cada [[switch]] continua retransmitindo os pacotes para as outras portas, acreditando que eles ainda precisam chegar ao destino.

### Efeitos de um Loop de Rede

- **Sobrecarga de Tráfego**: Os dispositivos de rede ficam sobrecarregados com o tráfego de pacotes duplicados, resultando em uma queda de desempenho.
- **[[Tempestade de Broadcast]]**: Loops de rede geralmente resultam em uma tempestade de broadcast, onde pacotes de broadcast se replicam continuamente, consumindo toda a largura de banda.
- **Queda de Comunicação**: O tráfego útil é interrompido, afetando a comunicação entre dispositivos e serviços.

### Prevenção de Loops de Rede

Para evitar loops, o **Spanning Tree Protocol ([[STP]])** é amplamente utilizado. Ele detecta e desativa automaticamente caminhos redundantes, permitindo apenas um caminho ativo entre dois pontos na rede. Em caso de falha em um caminho, o [[STP]] reativa um caminho alternativo, mantendo a rede funcional e evitando loops.

Loops de rede são, portanto, um problema crítico em redes com alta redundância, e protocolos de controle como o [[STP]] são essenciais para manter a estabilidade da rede.