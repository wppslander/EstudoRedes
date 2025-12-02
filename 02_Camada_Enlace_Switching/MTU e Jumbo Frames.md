#MTCNA #MTCSWE #Layer2 #Desempenho #VPN

**MTU** (Maximum Transmission Unit) define o tamanho máximo de um pacote de dados (em bytes) que pode ser transmitido através de uma interface de rede de uma só vez.

É a "altura máxima do túnel" ou o "tamanho máximo da caixa" que o meio físico aceita.

### O Padrão Ethernet (1500 Bytes)
Na grande maioria das redes mundiais e na Internet, o MTU padrão da tecnologia [[Ethernet]] é **1500 bytes**.
*   Isso significa que o payload (dados úteis) + cabeçalhos IP/TCP não podem exceder esse valor.
*   Se o protocolo [[IPv4]] tentar enviar um pacote de 4000 bytes por um cabo Ethernet padrão, ele precisará ser **Fragmentado** (quebrado em pedaços menores).

### Cenário Real: Quando o ISP não entrega 1500
Embora 1500 seja o padrão, na prática, muitas conexões entregam menos, causando dores de cabeça silenciosas.

1.  **PPPoE**: Muito comum em provedores de fibra/DSL. O protocolo PPPoE ocupa 8 bytes de cabeçalho.
    *   MTU Máximo: **1492 bytes**.
2.  **Provedores via Rádio / Redes Complexas**: Se o seu ISP usa muitos túneis internos (MPLS, VPLS, QinQ) para transportar o link até você, cada camada rouba um pouco do MTU.
    *   Não é raro receber links com MTU efetivo de **1480** ou menos.

> **Sintoma Clássico**: Você acessa o Google (pacotes pequenos), mas sites de bancos ou sistemas ERP (pacotes grandes/cheios) não abrem ou ficam "carregando" infinitamente.

---

### Jumbo Frames (> 1500 Bytes)
**Jumbo Frames** são quadros Ethernet que excedem o padrão de 1500 bytes. O valor mais comum configurado em equipamentos profissionais é **9000 bytes**.

#### Vantagens
1.  **Menor Overhead**: Imagine enviar 1GB de dados.
    *   Com MTU 1500: Você precisa de ~700.000 pacotes (e 700.000 cabeçalhos, e 700.000 interrupções na CPU).
    *   Com Jumbo 9000: Você precisa de apenas ~115.000 pacotes.
2.  **Menor Uso de CPU**: O processador do switch/servidor trabalha menos para processar cabeçalhos, sobrando mais poder para processar dados.
3.  **Alta Performance**: Ideal para transferências massivas, como Backups, iSCSI, SAN (Storage Area Network) e migração de Máquinas Virtuais.

#### O Grande Risco (Black Hole)
Para que o Jumbo Frame funcione, **TODOS** os dispositivos no caminho (Servidor A $\rightarrow$ Switch 1 $\rightarrow$ Switch 2 $\rightarrow$ Storage B) devem suportar e estar configurados com o mesmo MTU.
*   Diferente da Camada 3, a **Camada 2 (Ethernet) NÃO fragmenta**. Ou passa, ou dropa.

---

### Relação com a Camada 3 (Fragmentação) e VPNs

A [[Camada de Rede]] ([[IPv4]]) tem a capacidade de **Fragmentar**, mas isso é custoso. Em cenários de VPN (WireGuard, IPsec, GRE), o problema é crítico.

#### O Problema do "MTU Overhead"
Quando você cria um túnel VPN, o pacote original é colocado DENTRO de outro pacote (Encapsulamento). Esse "envelope" extra ocupa espaço.

*   **Cálculo de Risco**:
    *   ISP (PPPoE): 1492 bytes (ou menos!).
    *   Cabeçalho WireGuard: ~80 bytes.
    *   **Sobra Real**: 1492 - 80 = **1412 bytes**.

Se você configurar seu WireGuard com MTU 1450 (padrão de alguns tutoriais), os pacotes **não vão passar** nesse link PPPoE.

#### Bloqueio de Fragmentação e Path MTU Discovery (PMTUD)
Muitos roteadores na internet (e firewalls de ISPs) **bloqueiam** pacotes fragmentados ou pacotes [[ICMP]] "Fragmentation Needed". Isso impede que seu computador descubra automaticamente que o túnel é estreito.

#### Solução "Defensiva" (MSS Clamping)
Para evitar problemas em qualquer cliente, a melhor prática é ser conservador:

1.  **Reduzir o MTU da VPN**: Configurar interfaces WireGuard/OpenVPN para valores seguros como **1360** ou **1400**. É melhor perder uns bytes de eficiência do que perder a conexão.
2.  **MSS Clamping (MikroTik)**: Usar uma regra de Mangle para forçar o tamanho máximo do segmento TCP (MSS) a se ajustar ao MTU real, não importa qual seja.
    *   `/ip firewall mangle add chain=forward action=change-mss new-mss=clamp-to-pmtu protocol=tcp tcp-flags=syn`