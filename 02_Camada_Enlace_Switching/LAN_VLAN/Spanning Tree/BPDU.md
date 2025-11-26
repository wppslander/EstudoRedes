**BPDU** (Bridge Protocol Data Unit) é uma unidade de dados utilizada no protocolo Spanning Tree Protocol ([[STP]]) e em seus sucessores, como Rapid Spanning Tree Protocol ([[RSTP]]) e Multiple Spanning Tree Protocol ([[MSTP]]). O [[BPDU]] é fundamental para a operação desses protocolos, que visam evitar loops de rede em topologias com conexões redundantes.

### Tipos de BPDU

Existem dois tipos principais de [[BPDU]]:

1. **Configuration BPDU (CBPDU)**:
    
    - Usada para determinar a topologia da rede e para o processo de seleção do [[switch]] raiz.
    - Contém informações sobre o identificador da ponte (Bridge ID), o custo do caminho e outras informações necessárias para o algoritmo de [[STP]].
2. **Topology Change Notification BPDU (TCN BPDU)**:
    
    - Enviada para notificar os outros [[switch]]es sobre alterações na topologia da rede (como quando um [[switch]] é adicionado ou removido).
    - Ajuda a atualizar a tabela de topologia e a minimizar o tempo de convergência após uma mudança na rede.

### Função do BPDU

- **Detecção de Loops**: As BPDUs são transmitidas entre [[switch]]es para detectar e evitar [[loop]]s de rede. Se um [[switch]] receber BPDUs de um caminho que cria um [[loop]], ele pode desativar uma das conexões para interromper o ciclo.
- **Construção da Topologia**: Através do envio e recebimento de BPDUs, os switches podem construir uma visão coerente da topologia da rede, determinando qual [[switch]] deve ser o [[switch]] raiz e quais portas devem ser bloqueadas ou ativadas.

### Como Funciona

1. **Troca de BPDUs**: Os switches enviam BPDUs regularmente (por exemplo, a cada 2 segundos) para seus vizinhos.
2. **Eleição do Switch Raiz**: O [[switch]] com o menor Bridge ID é escolhido como o switch raiz.
3. **Cálculo do Caminho**: Os switches determinam o melhor caminho para o switch raiz com base no custo da conexão e bloqueiam as portas que poderiam criar [[loop]]s.

### Importância do BPDU

- **Estabilidade da Rede**: BPDUs são essenciais para manter a estabilidade da rede em topologias com redundância.
- **Gerenciamento de Mudanças**: O uso de BPDUs permite que os switches respondam rapidamente a mudanças na topologia da rede, garantindo que a comunicação permaneça eficiente e livre de loops.

Em resumo, as BPDUs são uma parte crucial do funcionamento do [[STP]] e de suas variantes, ajudando a manter a integridade e a eficiência das redes com múltiplas conexões.