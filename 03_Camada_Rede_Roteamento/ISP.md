#MTCNA #Redes #Internet

**ISP** (Internet Service Provider) é a entidade comercial ou organização que fornece acesso à Internet para usuários finais e outras redes. Eles são os "construtores" da infraestrutura da Web, conectando sua casa ou empresa ao resto do mundo.

### Hierarquia dos ISPs (Tiers)

A Internet não é uma nuvem mágica única, mas uma colcha de retalhos de redes conectadas. Os ISPs são classificados em camadas (Tiers):

#### Tier 1 (Backbone Global)
*   São os "Donos da Internet". Possuem redes de fibra óptica intercontinentais e cabos submarinos.
*   **Característica**: Eles se conectam entre si gratuitamente (Peering) e atingem qualquer lugar da Internet sem pagar trânsito a ninguém.
*   *Exemplos*: AT&T, Lumen (Level3), Tata Communications, Orange.

#### Tier 2 (Regional)
*   Compram trânsito dos Tier 1, mas possuem grandes redes regionais ou nacionais. Fazem peering com outros Tier 2 para economizar.
*   *Exemplos*: Grandes operadoras nacionais (Vivo, Claro, Oi - em algumas escalas atuam como Tier 2/1 misto dependendo da região).

#### Tier 3 (Acesso / Local)
*   É o provedor de bairro ou a operadora que entrega o cabo na sua casa.
*   Eles compram link de ISPs Tier 2 (ou Tier 1) para revender ao consumidor final.
*   **Foco**: "Last Mile" (Última Milha).

### Conceitos Chave

*   **AS (Autonomous System)**: Um ISP grande possui um número de registro único (ASN) e controla seus próprios blocos de [[IPv4]]/[[IPv6]]. Eles usam o protocolo **BGP** para rotear dados entre si.
*   **IXP / PTT (Ponto de Troca de Tráfego)**: Locais físicos onde diferentes ISPs ligam seus roteadores para trocar dados diretamente (Peering), economizando banda internacional e diminuindo a latência. O Brasil tem um dos maiores ecossistemas de IXP do mundo (IX.br).

### ISP e Privacidade

Como todo o seu tráfego passa pela infraestrutura do ISP, eles têm visibilidade técnica sobre:
1.  **Destinos**: Quais IPs você acessa.
2.  **DNS**: Quais sites você visita (se não usar [[DoH]] ou [[DoT]]).
3.  **Dados não criptografados**: Conteúdo de sites HTTP (porta 80).

Por isso, o uso de **[[VPN]]** e DNS seguro é recomendado para privacidade.
