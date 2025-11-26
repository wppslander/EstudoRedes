#MTCNA #MTCSA

# MikroTik - Firewall Chains (MTCNA, MTCSA)

## 1. Introdução ao Firewall no RouterOS
*   **Função:** Proteger o roteador e a rede por trás dele, controlando o fluxo de pacotes.
*   **Tipos de Firewall:**
    *   **Filter (Chain Input/Output/Forward):** Permitir/Bloquear tráfego.
    *   **NAT (Chain srcnat/dstnat):** Tradução de endereços.
    *   **Mangle (Chain prerouting/postrouting):** Marcar pacotes para QoS ou roteamento.
*   **Processamento:** O RouterOS processa as regras de firewall de cima para baixo. A primeira regra que casa (match) é aplicada e geralmente o processamento para (`action=accept`, `drop`, etc.).

## 2. Cadeias Principais (Filter Rules)

### 2.1. `input` Chain
*   **Propósito:** Regras para pacotes **destinados ao próprio roteador**.
*   **Exemplos de tráfego:**
    *   Tentativas de acesso ao roteador (Winbox, SSH, HTTP, Ping).
    *   DHCP requests recebidos pelo roteador.
    *   DNS requests recebidos pelo roteador.
*   **Uso:** Proteger o acesso administrativo ao MikroTik, bloquear serviços indesejados no próprio roteador.

**Exemplo:** Permitir acesso Winbox apenas da rede local:
```
/ip firewall filter
add chain=input action=accept protocol=tcp dst-port=8291 src-address=192.168.88.0/24 comment="Allow Winbox from LAN"
add chain=input action=drop comment="Drop all other input traffic"
```

### 2.2. `output` Chain
*   **Propósito:** Regras para pacotes **gerados pelo próprio roteador**.
*   **Exemplos de tráfego:**
    *   O roteador pingando um host.
    *   O roteador fazendo um NTP query.
    *   Respostas do roteador a requisições (ex: resposta a um ping de fora).
*   **Uso:** Controlar o que o roteador pode iniciar ou responder.

**Exemplo:** Permitir que o roteador faça ping para qualquer lugar:
```
/ip firewall filter
add chain=output action=accept protocol=icmp comment="Allow router to ping"
```

### 2.3. `forward` Chain
*   **Propósito:** Regras para pacotes que **atravessam o roteador** (não são destinados a ele, nem gerados por ele).
*   **Exemplos de tráfego:**
    *   Um computador da LAN acessando a internet.
    *   Tráfego entre VLANs roteadas pelo MikroTik.
*   **Uso:** Controlar o tráfego de usuários, implementar regras de segurança entre diferentes segmentos de rede (LAN para WAN, VLAN para VLAN).

**Exemplo:** Permitir tráfego da LAN para a WAN:
```
/ip firewall filter
add chain=forward action=accept connection-state=established,related comment="Allow established/related connections"
add chain=forward action=accept connection-state=new in-interface=ether2 (LAN) out-interface=ether1 (WAN) comment="Allow new connections from LAN to WAN"
add chain=forward action=drop comment="Drop all other forward traffic"
```

## 3. Cadeias de NAT (Network Address Translation)
*   **`srcnat` (Source NAT):** Modifica o endereço IP de origem do pacote. Usado principalmente para dar acesso à Internet a múltiplos clientes usando um único IP público (Masquerade).
    *   **Chain:** `srcnat`
    *   **Exemplo:**
    ```
    /ip firewall nat
    add chain=srcnat action=masquerade out-interface=ether1 (WAN) comment="Masquerade LAN to WAN"
    ```
*   **`dstnat` (Destination NAT):** Modifica o endereço IP de destino do pacote. Usado para "abrir portas" (Port Forwarding), redirecionando requisições externas para um servidor interno.
    *   **Chain:** `dstnat`
    *   **Exemplo:**
    ```
    /ip firewall nat
    add chain=dstnat action=dst-nat protocol=tcp dst-port=80 to-addresses=192.168.88.100 to-ports=80 in-interface=ether1 (WAN) comment="Web Server Port Forward"
    ```

## 4. Cadeias de Mangle (Packet Marking)
*   Usado para marcar pacotes para processamento posterior (ex: QoS, roteamento).
*   **`prerouting`:** Marca pacotes antes que o roteador decida para onde enviá-los.
*   **`postrouting`:** Marca pacotes depois que o roteador decidiu o caminho.
*   **Exemplo:** Marcar tráfego de um tipo específico para priorização:
    ```
    /ip firewall mangle
    add chain=prerouting action=mark-packet new-packet-mark=voip_traffic protocol=udp dst-port=5060 comment="Mark VoIP traffic"
    ```

## 5. Ordem de Processamento do Firewall
1.  **Mangle (Prerouting)**
2.  **NAT (Dst-NAT)**
3.  **Filter (Input/Forward)**
4.  **Routing Decision**
5.  **Filter (Output)**
6.  **NAT (Src-NAT)**
7.  **Mangle (Postrouting)**
