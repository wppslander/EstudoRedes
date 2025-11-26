O IEEE 802.1Q define o formato de tag de [[VLAN]] para quadros [[Ethernet]].

![[QuadroEthernetPadrão.png]]

A adição de uma tag 802.1Q de 4 [[bit]]s a um quadro [[Ethernet]] cria um quadro com tag de [[VLAN]]. Comparativamente, um quadro [[Ethernet]] tradicional sem uma tag 802.1Q é conhecido como um quadro sem tag.
Uma tag 802.1Q contém um campo de identificador de protocolo de tag (TPID) de 2 [[byte]]s e um campo de informações de controle de tag (TCI) de 2 [[byte]]s.
O campo TPID identifica se o quadro é marcado com VLAN. Para quadros com marcação de VLAN, o campo é fixado em 0x8100.
O campo de informações de controle de tags (TCI) tem os três subcampos a seguir:
• Prioridade: Um campo de 3 [[bit]]s que indica a prioridade 802.1p do quadro. O valor da prioridade 802.1p varia de 0 a 7.

• [[CFI]]: O campo CFI de 1 [[bit]] especifica se os endereços MAC são encapsulados no formato padrão quando os pacotes são transmitidos por diferentes mídias. O valor 0 indica que os endereços [[MAC]] são encapsulados no formato padrão. O valor 1 indica que os endereços [[MAC]] são encapsulados em um formato não padrão. É usado em token rings/acesso [[MAC]] FDDI roteado pela fonte para sinalizar a ordem dos bits das informações de endereço transportadas no quadro encapsulado.

• [[VLAN]] ID (Identificador de [[VLAN]]): Um campo de 12 [[bit]]s que identifica a [[VLAN]] ID do quadro. Há 4.096 VLAN IDs no total. Todo quadro enviado por um switch habilitado para 802.1Q contém o campo para identificar a qual VLAN o quadro pertence.