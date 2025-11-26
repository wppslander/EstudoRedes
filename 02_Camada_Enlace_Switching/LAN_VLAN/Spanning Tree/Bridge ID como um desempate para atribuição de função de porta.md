Se um [[switch]] não [[root bridge]] tiver pelo menos dois caminhos que atravessam diferentes pontes upstream imediatas até o [[root bridge]], a porta conectada ao enlace upstream que tiver o bridge ID mais baixo será eleito o root port desse [[switch]].

Se vários [[switch]]es estiverem conectados a um segmento físico com o menor custo de caminho raiz, aquela com o menor bridge ID será eleita o enlace designado para o segmento físico. A porta que conecta a ponte designada ao segmento físico recebe a função de [[Designated Port]].

Na figura abaixo, SWD tem duas portas que podem alcançar a ponte raiz SWA com o mesmo custo de caminho raiz. Como o ID da ponte de SWB é menor que o de SWC, a porta conectada a SWB é eleita a porta raiz para SWD. Pelo mesmo motivo, SWB é eleita a ponte designada para o segmento físico entre SWB e SWC, e a porta que conecta SWB ao segmento físico é eleita a porta designada.


![[desempate para atribuição de função de porta.png]]

### ID da porta como fator de desempate para atribuição de função de porta
Se uma [[switch]] que não for o [[root bridge]] tiver pelo menos dois caminhos de custo mínimo que atravessam a mesma ponte upstream imediatamente do [[root bridge]], o ponto conectado à porta de upstream que tiver o bridge ID mais baixo será eleito o root bridge da ponte.

Cada bridge ID inclui o índice e a prioridade da porta. Ao comparar dois IDs de porta, o STP primeiro compara suas prioridades de porta. A porta com prioridade mais alta (um valor numérico mais baixo) vence. Se as prioridades das portas forem as mesmas, a porta com índice mais baixo vencerá.


| ![[criteriodedesempatebridge.png]] | Na figura ao lado, duas portas do SWB se conectam ao SWA. Como elas têm o mesmo custo de caminho raiz e ponte upstream, a porta conectada à ponte upstream com ID de porta inferior é eleita a root port do SWB.<br><br>  <br><br>Como o número de índice de uma porta é normalmente fixo, você pode influenciar o cálculo da topologia STP alterando as prioridades das portas. |
| ---------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

### Status das portas
O IEEE 802.1d STP define cinco status de portas:

• **Disabled**: Uma porta nesse estado não recebe nem envia nenhum pacote. Esse estado pode ser causado porque a camada física da porta não está ativa ou porque a porta está administrativamente desligada.

• **Blocking**: Uma porta nesse estado só pode receber BPDUs de configuração e enviá-los à CPU. Ela não pode enviar BPDUs de configuração, encaminhar dados de usuário ou aprender endereços MAC.  

• **Listening**: Uma porta nesse estado não encaminha dados de usuário nem aprende endereços MAC, mas pode receber e enviar BPDUs de configuração.

• **Learning**: Uma porta nesse estado não encaminha dados de usuário, mas pode aprender endereços MAC e receber, processar e enviar BPDUs de configuração.

• **Forwarding**: Uma porta nesse estado pode encaminhar dados de usuário, aprender endereços MAC e receber, processar e enviar BPDUs de configuração.

Desses cinco estados de porta, listening e learning são estados status intermediários.