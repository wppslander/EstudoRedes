A **Root Port** (ou Porta Raiz) é uma porta designada em cada [[switch]], exceto no **[[Root Bridge]]**, que tem o caminho mais curto (ou o menor custo) para a **Root Bridge** em uma rede que usa o **Spanning Tree Protocol ([[STP]])**. A Root Port é essencial para garantir que o tráfego de rede flua de forma eficiente e sem [[loop]]s, pois ela define o caminho principal pelo qual o [[switch]] se conecta à estrutura central da rede.

### Características da Root Port

- **Menor Custo para a Root Bridge**: A Root Port é determinada com base no custo cumulativo do caminho até a Root Bridge. Quanto menor o custo, mais eficiente é o caminho.
- **Exclusiva por Switch**: Cada switch tem apenas uma Root Port, que é a porta principal para alcançar a Root Bridge.
- **Porta Ativa**: A Root Port sempre está em estado ativo, permitindo a passagem de dados. Outras portas que levam a possíveis loops podem ser bloqueadas.

### Exemplo de Como é Escolhida

1. **Custo do Caminho**: O [[switch]] calcula o custo para a [[Root Bridge]] em cada porta.
2. **Critérios de Desempate**: Em caso de custos iguais, critérios como Bridge ID e número da porta são usados para escolher a Root Port.

### Função da Root Port

A Root Port atua como o principal caminho de comunicação de um switch para a rede principal, ajudando a otimizar o tráfego e a evitar loops. Em resumo, a Root Port garante que cada switch tenha um único caminho otimizado para a Root Bridge.