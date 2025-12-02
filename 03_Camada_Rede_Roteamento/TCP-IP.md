#MTCNA #Redes #Modelos

O **Modelo TCP/IP** (Transmission Control Protocol/Internet Protocol) é a arquitetura de protocolos usada na Internet e na maioria das redes modernas. Diferente do [[Modelo OSI]] que é conceitual e possui 7 camadas, o TCP/IP é prático e geralmente é descrito com **4 camadas**.

Ele é chamado de "Pilha de Protocolos" (Protocol Stack) porque cada camada resolve uma parte do problema de comunicação e serve a camada superior.

### Comparação: TCP/IP vs. OSI

| Camada TCP/IP | Camada OSI Correspondente | Protocolos Principais | Unidade de Dados (PDU) |
| :--- | :--- | :--- | :--- |
| **4. Aplicação** | Aplicação, Apresentação, Sessão | HTTP, DNS, DHCP, SSH | Dados |
| **3. Transporte** | Transporte | [[TCP]], [[UDP]] | Segmento / Datagrama |
| **2. Internet** | Rede | [[IPv4]], [[IPv6]], [[ICMP]], [[ARP]], OSPF | Pacote |
| **1. Acesso à Rede** | Enlace, Física | Ethernet, Wi-Fi, PPP | Quadro (Frame) / Bits |

---

### As 4 Camadas do TCP/IP

#### 1. Camada de Acesso à Rede (Network Access)
Combina as camadas Física e de Enlace do OSI. Define como os dados são enviados fisicamente através da rede (cabos, ondas de rádio) e como os quadros são formatados.
*   **Foco**: Endereçamento MAC, Placas de Rede, Cabos.

#### 2. Camada de Internet
Equivalente à Camada de Rede do OSI. Responsável pelo endereçamento lógico e roteamento de pacotes entre redes diferentes.
*   **Foco**: Endereçamento IP, Roteamento.
*   **Protagonistas**: [[IPv4]], [[IPv6]], [[ICMP]].

#### 3. Camada de Transporte
Responsável pela comunicação ponta-a-ponta entre dois dispositivos. Define *como* os dados devem ser entregues: com confiabilidade total ([[TCP]]) ou com máxima velocidade ([[UDP]]).
*   **Foco**: Portas lógicas, Confiabilidade, Controle de Fluxo.
*   **Conceito Chave**: [[Portas e Sockets]].

#### 4. Camada de Aplicação
Onde os aplicativos de rede operam. Interage diretamente com o software (Navegador, Cliente de E-mail).
*   **Foco**: HTTP (Web), SMTP (Email), DNS (Nomes).

---

### Encapsulamento

O segredo do TCP/IP é o **Encapsulamento**. Quando você envia um dado:
1.  **Aplicação**: Cria o dado (ex: uma página HTML).
2.  **Transporte**: Adiciona um cabeçalho (TCP ou UDP) indicando a porta de origem/destino -> vira um **Segmento**.
3.  **Internet**: Adiciona um cabeçalho IP (Endereço Origem/Destino) -> vira um **Pacote**.
4.  **Acesso à Rede**: Adiciona um cabeçalho MAC e um trailer (FCS) -> vira um **Quadro**.

Ao chegar no destino, ocorre o processo inverso (**Desencapsulamento**).