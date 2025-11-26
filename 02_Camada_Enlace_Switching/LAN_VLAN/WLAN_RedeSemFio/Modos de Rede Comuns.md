1) FAT AP: O FAT AP gerencia o terminal de acesso e é aplicável à pequena rede sem fio.

2) [[AP]] em nuvem: A plataforma de gerenciamento em nuvem gerencia remotamente os terminais de acesso e os [[AP]]s em nuvem, e é aplicável a redes sem fio de médio e pequeno porte com várias filiais.

3) AC +FIT [[AP]]: O [[AC]] gerencia centralmente os terminais sem fio de acesso e os APs FIT, e é aplicável a redes sem fio grandes e médias.
![[Modos de Redes Comuns.png]]O FAT [[AP]] integra as funções de camada física, criptografia de dados de usuário, autenticação de usuário, [[QoS]], gerenciamento de rede, [[roaming]] e outras camadas de aplicativos de [[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/WLAN_RedeSemFio/WLAN]]s. Cada FAT AP é um sistema autônomo independente que funciona de forma independente um do outro.

As funções dos APs em nuvem são semelhantes às do FAT AP. Em comparação com o FAT AP, o AP em nuvem também oferece suporte à plataforma de gerenciamento em nuvem on-line. Com o uso da plataforma de gerenciamento em nuvem, o gerenciamento remoto e a O&M unificada dos APs são realizados, economizando custos de O&M e reduzindo os requisitos de capacidade técnica da equipe de O&M.

![[ModosDeRedeComun2.png]]Na solução AC+FIT AP, o AC e o FIT AP trabalham juntos para fornecer as funções dos APs convencionais, o AC lida centralmente com todas as funções de segurança, controle e gerenciamento, e o FIT AP fornece apenas funções de radiofrequência confiáveis e de alto desempenho. A solução AC+FIT AP é fácil de gerenciar e oferece suporte a [[roaming]] rápido, [[QoS]], proteção de segurança de rede sem fio, autorrecuperação de rede e outras funções avançadas.

Observação: O FAT [[AP]], o cloud AP e o FIT AP diferem apenas nos recursos de software e nos modos de rede, e o hardware que eles carregam é provavelmente o mesmo.

### Principais Diferenças entre [[AP]] e [[AC]]

- **Independência vs. Controle Centralizado**: APs geralmente operam sozinhos, enquanto ACs coordenam e centralizam a gestão de múltiplos APs.
- **Escalabilidade**: APs são suficientes em redes menores; ACs são mais indicados para redes maiores e mais complexas, onde há muitos APs.
- **Configuração e Manutenção**: Um AC simplifica a configuração e a manutenção de redes grandes, evitando que cada AP precise ser configurado individualmente.

### Exemplo de Uso Combinado

Em uma rede corporativa, por exemplo, o **AC** gerencia todos os **APs**, permitindo ajustes automáticos de potência de sinal, canais e distribuição de carga, enquanto cada AP fornece conectividade direta aos usuários.

