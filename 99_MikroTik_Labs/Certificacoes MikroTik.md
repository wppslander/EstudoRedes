#MTCNA #MikroTik #Certificacoes #Carreira

Este documento serve como um guia prático para orientar os laboratórios (`Labs`) de acordo com a trilha oficial de certificações da MikroTik. Use-o para decidir qual laboratório montar a seguir.

---

## 1. MTCNA - MikroTik Certified Network Associate
*O ponto de partida. Cobre o básico do RouterOS.*

**O que estudar / Labs Sugeridos:**
*   **Acesso Inicial**: Winbox, CLI, WebFig, SSH.
*   **Gestão de Usuários**: Criação de usuários, grupos e permissões.
*   **DHCP**: Configurar Server, Client e Relay. Entender o `Lease` e `Static Leases`.
*   **Bridge**: Criar uma bridge simples (sem VLAN filtering ainda) para unir portas LAN.
*   **Routing Básico**: Rota estática (`0.0.0.0/0`) e verificação de tabela de rotas.
*   **NAT (Masquerade)**: Configurar o `src-nat` para permitir acesso à internet.
*   **Wireless Básico**: Configurar um AP simples (SSID, Segurança WPA2).
*   **QoS Simples**: Filas Simples (Simple Queues) para limitar banda de um IP (Target Upload/Download).
*   **Ferramentas**: Uso do `Torch`, `Ping`, `Traceroute` e `Bandwidth Test`.

---

## 2. MTCRE - MikroTik Certified Routing Engineer
*Foco em Roteamento Estático e Dinâmico (OSPF).*

**O que estudar / Labs Sugeridos:**
*   **Roteamento Estático Avançado**: Rotas com diferentes distâncias administrativas (Failover), Check Gateway (Ping/Arp).
*   **OSPF (Single Area)**: Configurar OSPF básico, Hello timers, Adjacências.
*   **OSPF (Multi Area)**: Áreas Backbone e Stub, redistribuição de rotas.
*   **Túneis**: IPIP, EoIP, GRE.
*   **VLAN Routing**: "Router on a Stick" (VLANs chegando no roteador para serem roteadas).

---

## 3. MTCSWE - MikroTik Certified Switching Engineer
*Foco em Layer 2, VLANs e Hardware Offload.*

**O que estudar / Labs Sugeridos:**
*   **Bridge VLAN Filtering**: A maneira moderna de configurar VLANs no MikroTik (CRÍTICO).
    *   *Lab*: [[MikroTik - Bridge VLAN Filtering]]
*   **MTU e Jumbo Frames**: Configurar L2MTU e MTU para performance.
    *   *Estudo*: [[MTU e Jumbo Frames]]
*   **STP / RSTP / MSTP**: Prevenção de loops e configuração de prioridades de Bridge (Root Bridge).
*   **Bonding (Link Aggregation)**: LACP (802.3ad), Balanceamento XOR, Failover.
*   **Port Isolation**: Private VLANs (PVLAN) e Horizon.
*   **Switch Chip**: Entender quais recursos usam a CPU e quais usam o chip de switch (Switch Rules).

---

## 4. MTCSA - MikroTik Certified Security Engineer
*Foco em Firewall, Ataques e VPNs.*

**O que estudar / Labs Sugeridos:**
*   **Firewall Filter**: Input vs Forward vs Output.
*   **Packet Flow Diagram**: Entender a ordem (Raw -> Mangle -> D-NAT -> Filter).
    *   *Estudo*: [[MikroTik - Firewall Chains]]
*   **Firewall Raw**: Bloquear ataques antes de consumir CPU (DDoS mitigation simples).
*   **Ataques de Camada 2**: DHCP Snooping, ARP Inspection (combate a ARP Poisoning).
*   **VPNs Avançadas**:
    *   [[IPsec]] (Site-to-Site e Road Warrior).
    *   [[Wireguard]] (Configuração de Peers e Keys).
    *   L2TP/IPsec.
*   **Hardening**: Desativar serviços inseguros (Telnet, FTP), Port Knocking.

---

## 5. MTCWE - MikroTik Certified Wireless Engineer
*Foco em Wi-Fi Corporativo e Enlaces de Rádio.*

**O que estudar / Labs Sugeridos:**
*   **CAPsMAN**: Gerenciamento centralizado de múltiplos APs.
*   **Radiofrequência**: Escolha de Canais, Frequências, Scan List.
*   **Protocolos Proprietários**: Nstreme e NV2 (TDMA).
*   **Enlaces PTP e PTMP**: Configuração de Station e Bridge para longas distâncias.
*   **Segurança Wireless**: Access List, Connect List.

---

## 6. MTCIPv6E - MikroTik Certified IPv6 Engineer
*O futuro (e presente) do endereçamento.*

**O que estudar / Labs Sugeridos:**
*   **Endereçamento**: Configurar endereços Link-Local e Global Unicast.
*   **ND (Neighbor Discovery)**: O substituto do ARP no IPv6.
*   **SLAAC**: Autoconfiguração de endereços sem DHCP.
*   **DHCPv6-PD**: Prefix Delegation (Receber um /56 ou /48 do ISP e entregar /64 para a LAN).
*   **Firewall IPv6**: Diferenças para o IPv4 (não bloquear ICMPv6 excessivamente!).

---

## 7. MTCINE - MikroTik Certified Inter-networking Engineer
*O nível "Hardcore". Roteamento de Borda e Provedores.*

**O que estudar / Labs Sugeridos:**
*   **BGP**: iBGP vs eBGP, Filtros de rotas, Atributos (Local Pref, AS Path).
*   **MPLS**: LDP, VPLS (Estender a Camada 2 através de uma rede roteada).
*   **Traffic Engineering**: Manipular caminhos de tráfego complexos.
