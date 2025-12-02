#MTCNA #Fundamentos #CamadaFisica

O **Octeto** é uma unidade de informação digital que consiste em exatamente **8 [[Bit]]s**. Embora seja frequentemente usado como sinônimo de **[[Byte]]**, o termo "octeto" é preferido em padrões de engenharia de redes (RFCs e normas IEEE) para evitar ambiguidades, já que historicamente o tamanho de um "byte" variava dependendo da arquitetura do computador.

### Estrutura Matemática

Um octeto possui 8 posições binárias (zeros ou uns). Cada posição tem um "peso" decimal baseado em potências de 2.

| Posição do Bit | 8º (MSB) | 7º | 6º | 5º | 4º | 3º | 2º | 1º (LSB) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Potência de 2** | $2^7$ | $2^6$ | $2^5$ | $2^4$ | $2^3$ | $2^2$ | $2^1$ | $2^0$ |
| **Valor Decimal** | **128** | **64** | **32** | **16** | **8** | **4** | **2** | **1** |

*   **Valor Mínimo**: `00000000` = 0
*   **Valor Máximo**: `11111111` = 255 (A soma de todos os valores acima: 128+64+32+16+8+4+2+1).

### A Ligação com o IPv4

O octeto é a base fundamental do endereçamento **[[IPv4]]**.

Um endereço IPv4 tem **32 bits** de comprimento. Para tornar isso legível para humanos, dividimos esses 32 bits em **4 Octetos**.
*   $32 \text{ bits} \div 8 \text{ bits/octeto} = 4 \text{ octetos}$.

#### Notação Decimal Pontuada
Em vez de lermos uma longa sequência de 32 bits, o computador converte cada octeto isoladamente para seu valor decimal (0 a 255) e os separa por pontos.

**Exemplo Prático:**
O endereço `192.168.10.5` é formado por 4 octetos:

1.  **1º Octeto**: `11000000` $\rightarrow$ $128 + 64 = \mathbf{192}$
2.  **2º Octeto**: `10101000` $\rightarrow$ $128 + 32 + 8 = \mathbf{168}$
3.  **3º Octeto**: `00001010` $\rightarrow$ $8 + 2 = \mathbf{10}$
4.  **4º Octeto**: `00000101` $\rightarrow$ $4 + 1 = \mathbf{5}$

### Outros Usos em Redes

*   **Endereço [[MAC]]**: É composto por **6 Octetos** (48 bits). Diferente do IPv4, os octetos do MAC geralmente são representados em **[[Hexadecimal]]** e separados por dois pontos (ex: `AA:BB:CC:00:11:22`).
