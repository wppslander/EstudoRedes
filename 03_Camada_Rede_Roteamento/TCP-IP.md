#MTCNA #Redes #Modelos

O **Modelo TCP/IP** (Transmission Control Protocol/Internet Protocol) é a arquitetura de protocolos usada na Internet e na maioria das redes modernas. Diferente do [[Modelo OSI]] que é conceitual e possui 7 camadas, o TCP/IP é prático e geralmente é descrito com **4 camadas**.

Ele é chamado de "Pilha de Protocolos" (Protocol Stack) porque cada camada resolve uma parte do problema de comunicação e serve a camada superior.

### Comparação: TCP/IP vs. OSI

| Camada TCP/IP | Camada OSI Correspondente | Protocolos Principais (Clique para ver) | Unidade de Dados (PDU) |
| :--- | :--- | :--- | :--- |
| **4. Aplicação** | Aplicação, Apresentação, Sessão | [[DNS]], [[DHCP]], HTTP, SSH, FTP | Dados |
| **3. Transporte** | Transporte | [[TCP]], [[UDP]] | Segmento / Datagrama |
| **2. Internet** | Rede | [[IPv4]], [[IPv6]], [[ICMP]], [[ARP]]*, OSPF | Pacote |
| **1. Acesso à Rede** | Enlace, Física | Ethernet, Wi-Fi, PPP | Quadro (Frame) / Bits |

> *Nota: O [[ARP]] opera entre a camada 2 e 3, mas no TCP/IP geralmente é agrupado funcionalmente na camada Internet.

---

### Os Protocolos da Pilha (Detalhado)

#### 1. Camada de Aplicação
Onde os aplicativos de rede operam.
*   **[[DNS]]**: Traduz nomes (google.com) em IPs.
*   **[[DHCP]]**: Configura IPs automaticamente.
*   **HTTP/HTTPS**: Web.

#### 2. Camada de Transporte
Responsável pela comunicação ponta-a-ponta.
*   **[[TCP]]**: Confiável, orientado a conexão (3-Way Handshake).
*   **[[UDP]]**: Rápido, sem conexão (Streaming, Voz).
*   **[[Portas e Sockets]]**: Endereçamento lógico dos serviços.

#### 3. Camada de Internet
Responsável pelo endereçamento e roteamento.
*   **[[IPv4]] / [[IPv6]]**: O sistema de endereçamento global.
*   **[[ICMP]]**: Diagnóstico (Ping) e controle de erros.
*   **[[IGMP]]**: Gerenciamento de grupos Multicast.
*   **[[ARP]]**: Conecta o IP (Lógico) ao MAC (Físico).

#### 4. Camada de Acesso à Rede
Combina as camadas Física e de Enlace do OSI.
*   **Foco**: Endereçamento [[MAC]], Placas de Rede, Cabos.

---

### Encapsulamento

O segredo do TCP/IP é o **Encapsulamento**. Quando você envia um dado:
1.  **Aplicação**: Cria o dado (ex: uma página HTML).
2.  **Transporte**: Adiciona um cabeçalho ([[TCP]] ou [[UDP]]) indicando a porta de origem/destino -> vira um **Segmento**.
3.  **Internet**: Adiciona um cabeçalho [[IPv4]] (Endereço Origem/Destino) -> vira um **Pacote**.
4.  **Acesso à Rede**: Adiciona um cabeçalho [[MAC]] e um trailer (FCS) -> vira um **Quadro**.

Ao chegar no destino, ocorre o processo inverso (**Desencapsulamento**).
