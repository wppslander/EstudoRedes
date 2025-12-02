#MTCNA #Redes #IPv4

O **IPv4** (Internet Protocol version 4) é a quarta versão do protocolo de internet, operando na [[Camada de Rede]] do modelo OSI.

### Estrutura do Endereço: Binário vs Decimal

Um endereço IPv4 é, na verdade, uma sequência de **32 bits** (zeros e uns). Como é difícil para humanos memorizarem 32 números binários, dividimos esse endereço em 4 partes e convertemos para decimal.

#### A Regra dos Octetos
1.  **32 Bits**: O endereço total.
2.  **4 [[Octetos]]**: Dividimos os 32 bits em 4 grupos de 8 bits.
3.  **Decimal Pontuado**: Convertemos cada grupo de 8 bits (Octeto) para um número decimal (0 a 255) e separamos por pontos.

**Exemplo Visual:**

| Formato | 1º Octeto | 2º Octeto | 3º Octeto | 4º Octeto |
| :--- | :---: | :---: | :---: | :---: |
| **Binário** | `11000000` | `10101000` | `00000001` | `00000001` |
| **Decimal** | **192** | **168** | **1** | **1** |

> **Nota**: Cada octeto tem 8 bits. O valor mínimo é `00000000` (0) e o máximo é `11111111` (255).

---

### Classificação dos Endereços (Classes)

O IPv4 é dividido em "Classes" para determinar o tamanho da rede. A maneira mais rápida de identificar a classe é olhando apenas o **Primeiro Octeto** (os primeiros 8 bits).

| Classe | Intervalo do 1º Octeto | Máscara Padrão        | Uso Típico                             | Bits Iniciais (Binário) |
| :----- | :--------------------- | :-------------------- | :------------------------------------- | :---------------------- |
| **A**  | **1 - 126**            | `255.0.0.0` (/8)      | Grandes Redes (Governos, Grandes ISPs) | `0...`                  |
| **B**  | **128 - 191**          | `255.255.0.0` (/16)   | Médias Empresas, Universidades         | `10...`                 |
| **C**  | **192 - 223**          | `255.255.255.0` (/24) | Pequenas Redes (Domésticas, LANs)      | `110...`                |
| **D**  | **224 - 239**          | (N/A)                 | **Multicast** (IPTV, OSPF, etc.)       | `1110...`               |
| **E**  | **240 - 255**          | (N/A)                 | **Experimental** (P&D)                 | `1111...`               |

> **Curiosidade**: O 127 (`127.0.0.0/8`) é reservado para **Loopback** (localhost) e não pertence à Classe A.

---

### Endereços Privados (RFC 1918)

Estes endereços **não roteiam na Internet**. São usados dentro da sua casa ou empresa. Para acessar a internet, eles precisam ser traduzidos para um IP Público via [[NAT]].

*   **Classe A**: `10.0.0.0` a `10.255.255.255` (1 Rede gigante)
*   **Classe B**: `172.16.0.0` a `172.31.255.255` (16 Redes médias)
*   **Classe C**: `192.168.0.0` a `192.168.255.255` (256 Redes pequenas - O padrão da maioria dos roteadores Wi-Fi)

---

### Máscara de Sub-rede

A máscara define "quem é quem" no endereço IP. Onde tiver `1` na máscara (ou 255), aquela parte do IP pertence à **Rede**. Onde tiver `0`, pertence ao **Host**.

*   IP: `192.168.1.10`
*   Máscara: `255.255.255.0`
*   **Rede**: `192.168.1`
*   **Host**: `.10`