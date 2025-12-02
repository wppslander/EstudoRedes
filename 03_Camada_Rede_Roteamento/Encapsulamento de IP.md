
![[EncapsulamentoIP 1.png]]

  
• Version (Versão) - Identifica a versão do IP. A versão atual do [[IPv4]]. A versão da próxima geração do [[IPv6]]

• IHL (Internet Header Length, "Comprimento do Cabeçalho da Internet") - Indica o comprimento do cabeçalho IP e tem 4 bits de comprimento

Encapsulamento de IP

• [[ToS]] (Type of Service, "Tipo de Serviço") - Identifica o tipo de serviço esperado pelo pacote e é frequentemente usado pela Qualidade de Serviço (QoS).

• Total Length (Comprimento total) - Identifica o comprimento total do pacote, incluindo a parte de dados.

• Identification (Identificação) - Identifica de forma exclusiva um datagrama IP e aumenta em 1 cada vez que um datagrama é enviado.

• TTL (Time to Live, "Tempo de Vida") - define o número máximo de roteadores pelos quais um datagrama pode passar. Ele é diminuído em 1 por cada roteador que o manipula. Quando o TTL chega a 0, o datagrama é descartado.

• Protocol (Protocolo) - Identifica o protocolo da camada superior. O número de protocolo do TCP é 6 e o do UDP é 17.

• Header Checksum (Soma de Verificação do Cabeçalho) - Usado para verificar a integridade do cabeçalho IP.

• Source Address (Endereço de origem) - Identifica o endereço IP de origem do datagrama.

• Destination Address (Endereço de Destino) - Identifica o endereço IP de destino do datagrama.