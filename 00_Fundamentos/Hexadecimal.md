#MTCNA #Fundamentos #Matematica

O **Hexadecimal** (ou Base 16) é um sistema numérico fundamental em redes de computadores, utilizado para representar valores binários de forma compacta e legível para humanos.

Enquanto o sistema **Decimal** usa 10 símbolos (0-9) e o **Binário** usa 2 (0-1), o Hexadecimal utiliza **16 símbolos**.

### Os 16 Símbolos

| Decimal | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Hex** | **0** | **1** | **2** | **3** | **4** | **5** | **6** | **7** | **8** | **9** | **A** | **B** | **C** | **D** | **E** | **F** |

### A Relação com Bits e Bytes

A mágica do Hexadecimal é que ele se alinha perfeitamente com a contagem binária.
*   **1 Dígito Hexadecimal** representa exatamente **4 bits** (um "Nibble").
*   **2 Dígitos Hexadecimais** representam exatamente **8 bits** (um [[Octeto]] ou [[Byte]]).

Essa é a razão pela qual ele é tão usado: é muito mais fácil escrever `FF` do que `11111111`.

#### Tabela de Conversão Rápida

| Binário (4 bits) | Hex | Decimal |
| :--- | :--- | :--- |
| `0000` | **0** | 0 |
| `0001` | **1** | 1 |
| `0010` | **2** | 2 |
| `0011` | **3** | 3 |
| `0100` | **4** | 4 |
| `0101` | **5** | 5 |
| `0110` | **6** | 6 |
| `0111` | **7** | 7 |
| `1000` | **8** | 8 |
| `1001` | **9** | 9 |
| `1010` | **A** | 10 |
| `1011` | **B** | 11 |
| `1100` | **C** | 12 |
| `1101` | **D** | 13 |
| `1110` | **E** | 14 |
| `1111` | **F** | 15 |

### Aplicações em Redes

#### 1. Endereço MAC
Um endereço [[MAC]] tem 48 bits (6 octetos). Em vez de escrever 48 zeros e uns, usamos 12 dígitos hexadecimais divididos em pares.
*   Ex: `00:1A:2B:3C:4D:5E`
*   Cada par (ex: `1A`) é um [[Octeto]] (8 bits).

#### 2. Endereço IPv6
O [[IPv6]] tem 128 bits. Para representá-lo, usamos 8 grupos de 4 dígitos hexadecimais.
*   Ex: `2001:0db8:85a3:0000:0000:8a2e:0370:7334`
*   Cada grupo (ex: `2001`) representa 16 bits.

#### 3. EtherType
No cabeçalho Ethernet, o campo que identifica o protocolo (IPv4, ARP, IPv6) é escrito em Hex.
*   `0x0800` = IPv4
*   `0x0806` = ARP
*   `0x86DD` = IPv6
