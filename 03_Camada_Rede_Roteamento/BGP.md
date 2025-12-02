#MTCINE #Redes #Roteamento #BGP

O **BGP** (Border Gateway Protocol) é o protocolo de roteamento dinâmico que faz a Internet funcionar. Enquanto protocolos como **OSPF** e **RIP** são usados para mover dados *dentro* de uma empresa (IGP - Interior Gateway Protocol), o BGP é o único protocolo projetado para mover dados *entre* empresas e provedores diferentes (EGP - Exterior Gateway Protocol).

### O "GPS" da Internet

Se a Internet é uma coleção de milhares de redes independentes chamadas de **AS (Autonomous Systems)**, o BGP é o sistema que diz: "Para chegar na rede do Google (AS15169), passe pelo ISP A, depois pelo ISP B...".

### Por que o BGP é "Melhor"?

Dizer que o BGP é melhor que o OSPF é como comparar um caminhão de carga com um carro de Fórmula 1. Eles têm propósitos diferentes, mas o BGP brilha onde os outros falham:

1.  **Escalabilidade Massiva**:
    *   O OSPF começa a engasgar com alguns milhares de rotas.
    *   O BGP carrega a **Tabela de Roteamento Global da Internet**, que hoje possui mais de **900.000 rotas** [[IPv4]] e centenas de milhares de rotas [[IPv6]], sem travar.

2.  **Decisões baseadas em Políticas (Policy-Based)**:
    *   Protocolos internos (IGP) escolhem sempre o caminho *mais rápido* (menor custo).
    *   O BGP permite escolher o caminho *comercialmente mais interessante*.
    *   *Exemplo*: "Tenho dois links de internet. O Link A é mais rápido, mas é caro. O Link B é mais lento, mas tenho tráfego ilimitado. Vou configurar o BGP para enviar YouTube pelo Link B e VoIP pelo Link A".

3.  **Estabilidade (Path Vector)**:
    *   O BGP não precisa desenhar o mapa inteiro da rede (como o OSPF). Ele só precisa saber "quem é o próximo vizinho" e "por quais ASs o pacote já passou" (AS-Path) para evitar loops.

### Tipos de BGP

*   **eBGP (External)**: Troca de rotas entre dois AS diferentes (Ex: Sua empresa conectada ao [[ISP]]).
*   **iBGP (Internal)**: Troca de rotas BGP dentro do mesmo AS (usado em grandes provedores para levar as rotas da borda até o núcleo).

### Relação com o Ecossistema

*   **[[ISP]]**: Todo Provedor de Internet (Tier 1, 2 ou 3) usa BGP para "anunciar" seus IPs para o mundo.
*   **[[Roteador]]**: Apenas roteadores robustos (como MikroTik CCR, Cisco ASR, Juniper MX) conseguem processar a tabela completa do BGP ("Full Routing").
*   **[[TCP-IP]]**: Curiosamente, o BGP roda sobre a porta **TCP 179**, garantindo que as atualizações de rota sejam entregues com confiabilidade.
