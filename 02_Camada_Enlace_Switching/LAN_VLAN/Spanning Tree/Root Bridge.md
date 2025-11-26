A **[[Root Bridge]]** (ou Ponte Raiz) é um conceito central do **Spanning Tree Protocol (STP)**, utilizado em redes para evitar [[loop]]s. A [[Root Bridge]] é o switch principal escolhido como ponto de referência para a estruturação da topologia da rede e determina o caminho mais eficiente entre dispositivos, evitando o looping de dados.

### Função da [[Root Bridge]]

A [[Root Bridge]] serve como o **nó central da topologia de árvore** criada pelo [[STP]]:

1. **Referência Central**: Todos os [[switch]]es na rede calculam o caminho mais curto até a [[Root Bridge]].
2. **Construção da Árvore**: Ela é o ponto de partida para construir a topologia de árvore, onde caminhos redundantes são bloqueados, garantindo que não existam loops.
3. **Definição do Caminho**: A [[Root Bridge]] influencia quais portas de outros switches serão ativas, em bloqueio ou modo standby, otimizando a comunicação.

### Processo de Eleição da [[Root Bridge]]

A [[Root Bridge]] é eleita entre os [[switch]]es da rede com base no **Bridge ID (BID)**, que é composto por:

- **Prioridade**: Valor configurável de 0 a 61440, que define a prioridade do switch na eleição (quanto menor, maior a prioridade).
- **Endereço MAC**: Se dois switches tiverem a mesma prioridade, o desempate é feito pelo menor endereço MAC.

O switch com o menor BID torna-se a [[Root Bridge]].

### Funções em uma Rede

- **Designated Ports e Blocked Ports**: Cada switch calcula o melhor caminho até a [[Root Bridge]], configurando suas portas como "designadas" (ativas) ou "bloqueadas", com base no custo do caminho, para evitar loops.
- **Convergência da Rede**: A [[Root Bridge]] orienta a convergência, garantindo que todos os switches compartilhem uma visão unificada da topologia da rede.

### Importância da [[Root Bridge]]

Ter uma [[Root Bridge]] eficiente e bem-posicionada é crucial, pois ela:

- **Minimiza o Custo dos Caminhos**: Reduzindo o número de saltos para chegar ao destino.
- **Previne Loops de Rede**: Bloqueando caminhos redundantes.
- **Otimiza o Desempenho**: Mantendo a estrutura de rede organizada e funcional.

A [[Root Bridge]] é, portanto, o switch que atua como a "raiz" de toda a topologia de árvore do STP, sendo vital para a integridade e o desempenho da rede.