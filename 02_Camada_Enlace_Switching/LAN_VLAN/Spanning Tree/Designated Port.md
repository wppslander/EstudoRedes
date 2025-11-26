A **Designated Port** é a porta de um [[switch]], em uma rede com **Spanning Tree Protocol ([[STP]])**, que é responsável por encaminhar o tráfego em um segmento de rede específico. Ela é a porta "designada" para enviar e receber dados em um determinado segmento, garantindo que não ocorram [[loop]]s nesse segmento.

### Características Principais

- **Ativa e Enviando Tráfego**: A Designated Port está sempre em estado ativo, permitindo o tráfego.
- **Única por Segmento**: Apenas uma porta por segmento de rede é eleita como Designated Port, para evitar redundâncias.
- **Menor Custo para o Segmento**: A Designated Port é escolhida com base no menor custo do caminho até a **Root Bridge**.

Essencialmente, a Designated Port é a principal porta de comunicação para cada segmento da rede, direcionando o tráfego de forma organizada.