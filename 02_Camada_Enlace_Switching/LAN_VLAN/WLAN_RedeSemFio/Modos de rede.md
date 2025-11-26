## Rede típica FAT AP

O FAT AP pode operar de forma independente e pode concluir o acesso de usuários sem fio, a criptografia de dados de serviço e o encaminhamento de pacotes de dados de serviço sem o controle centralizado de dispositivos especiais. A rede e a manutenção são simples e de baixo custo. É aplicável a clientes sem capacidade técnica. O cenário de aplicação mais comum é a rede doméstica ou a rede de pequenas empresas.

Para empresas de grande e médio porte, a [[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/WLAN_RedeSemFio/WLAN]] exige uma área de cobertura e um grande número de usuários de acesso. Portanto, é necessário implantar um grande número de [[AP]]s. No modo de rede FAT [[AP]], os FAT APs funcionam de forma independente e não têm dispositivos de controle unificados. Portanto, é difícil gerenciar e manter esses APs FAT. Por exemplo, se o software precisar ser atualizado, cada FAT AP precisará ser acessado e atualizado independentemente, o que consome muito tempo e trabalho. Portanto, para a empresa, não é recomendável usar a arquitetura FAT AP. É mais adequado usar a rede de APs AC+FIT ou a rede de APs em nuvem que será descrita a seguir.

![[Modos de rede.png]]

## Rede típica [[AC]]+FIT [[AP]]

Os [[AC]]s precisam ser implantados em "redes de grande porte": Os ABCs são responsáveis pelo controle de acesso da rede sem fio, encaminhamento, estatísticas, monitoramento da configuração do [[AP]], gerenciamento de roaming, agente de gerenciamento de rede do [[AP]] e controle de segurança. O FIT [[AP]] tem configuração zero. A configuração e o software são baixados do [[AC]], e os [[AP]]s e os clientes sem fio são gerenciados no [[AC]].

O [[AC]] facilita a manutenção de [[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/WLAN_RedeSemFio/WLAN]]s de médio e grande porte. A implantação, a atualização e a configuração do AP não exigem intervenção frequente dos usuários, liberando os mantenedores da rede de operações pesadas de configuração. Essa configuração se tornou o principal modo de implantação e manutenção de WLANs de grande escala.

Além disso, o AC tem as funções de roaming rápido, [[QoS]], proteção de segurança de rede sem fio e autorrecuperação de rede, de modo que pode oferecer suporte a mais serviços de valor agregado, como voz e vídeo Wi-Fi.

![[Rede típica AC FIT AP.png]]

Os [[AC]]s precisam ser implantados em "redes de grande porte": Os ABCs são responsáveis pelo controle de acesso da rede sem fio, encaminhamento, estatísticas, monitoramento da configuração do [[AP]], gerenciamento de [[roaming]], agente de gerenciamento de rede do [[AP]] e controle de segurança. O FIT [[AP]] tem configuração zero. A configuração e o software são baixados do [[AC]], e os [[AP]]s e os clientes sem fio são gerenciados no [[AC]].

O AC facilita a manutenção de [[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/WLAN_RedeSemFio/WLAN]]s de médio e grande porte. A implantação, a atualização e a configuração do AP não exigem intervenção frequente dos usuários, liberando os mantenedores da rede de operações pesadas de configuração. Essa configuração se tornou o principal modo de implantação e manutenção de [[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/WLAN_RedeSemFio/WLAN]]s de grande escala.

Além disso, o AC tem as funções de [[roaming]] rápido, [[QoS]], proteção de segurança de rede sem fio e autorrecuperação de rede, de modo que pode oferecer suporte a mais serviços de valor agregado, como voz e vídeo [[Wi-Fi]].

## Rede típica da plataforma de **gerenciamento de nuvem** + AP de nuvem

A rede AC+FIT AP tem muitas vantagens, mas requer a implantação dispendiosa de dispositivos AC independentes e precisa de técnicos profissionais sem fio para manter e gerenciar os dispositivos. Para as pequenas e médias empresas com várias filiais, como cadeias de lojas comerciais e cadeias de hotéis, há muitas desvantagens no uso do modo de rede AC+FIT AP, como a dificuldade de implantação devido à dispersão regional, o longo ciclo de implantação da rede, o alto custo de O&M inter-regional e a falta de pessoal de O&M qualificado.

![[Rede típica da plataforma de gerenciamento de nuvem + AP de nuvem.png]]

A plataforma de gerenciamento em nuvem + rede de [[AP]]s em nuvem pode resolver os problemas acima. Com o uso da plataforma de gerenciamento em nuvem, os APs podem ser gerenciados e mantidos de forma centralizada em qualquer lugar, reduzindo consideravelmente os custos de implantação e O&M da rede. Após a conclusão da implantação do AP em nuvem, o administrador de rede não precisa ir ao local de instalação para fazer a depuração. Depois que o AP em nuvem é ligado, ele é automaticamente conectado à plataforma de gerenciamento em nuvem e o administrador de rede pode fornecer a configuração ao AP usando a plataforma de gerenciamento em nuvem a qualquer momento e em qualquer lugar, tornando a configuração em lote mais rápida.

A plataforma INC Cloud é uma solução completa de rede de gerenciamento de nuvem especialmente projetada pela Intelbras para esse cenário, incluindo a solução de gerenciamento automático de todos os gateways, [[switch]]es, segurança, [[AC]]s e [[AP]]s, e a solução completa da plataforma de nuvem, dispositivos de software e hardware, incluindo as soluções de gerenciamento de nuvem, O&M de nuvem, autenticação de nuvem e outras tecnologias. Suas vantagens são as seguintes:

• **Implementação simples**: O dispositivo é plug-and-play e implantado sem nenhuma configuração; os conectores de acoplamento cego são usados; quando o dispositivo é conectado, não é necessário prestar atenção à porta.

• **O&M automático**: podemos ver o status de toda a rede a partir da nuvem e encontrar proativamente os problemas existentes na rede. Alguns problemas podem ser otimizados automaticamente na nuvem para realizar o ciclo fechado automático. Ao mesmo tempo, também podemos monitorar e gerenciar a rede a partir do terminal móvel a qualquer momento e em qualquer lugar.

• **Forte apreciação**: A página de autenticação do portal na nuvem é usada para enviar anúncios; as informações do usuário de autenticação são coletadas na nuvem para análise e classificação estatística, para auxiliar na tomada de decisões de negócios; além disso, um grande número de APIs é aberto na Cloudnet para que terceiros obtenham dados.