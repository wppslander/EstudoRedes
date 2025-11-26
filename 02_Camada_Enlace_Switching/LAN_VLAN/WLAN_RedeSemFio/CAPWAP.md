![[capwap.png]]

Em redes sem fio de médio e grande porte, vários [[AP]]s na rede precisam ser gerenciados uniformemente usando [[AC]]s, e a especificação do protocolo [[CAPWAP]] (Control and Provisioning of Wireless Access Points) foi desenvolvida pela [[IETF]]. Esse protocolo define como os [[AC]]s gerenciar e configurar os APs. Ou seja, os túneis CAPWAP são estabelecidos primeiro entre os [[AC]]s e os [[AP]]s e, em seguida, os ACs gerenciam e controlam centralmente os APs usando os túneis CAPWAP.

O túnel CAPWAP pode transmitir pacotes de controle entre ACs e APs e pacotes de dados de terminais de clientes. Os modos de encaminhamento de WLAN incluem encaminhamento centralizado e encaminhamento local de acordo com o caminho de encaminhamento de dados do serviço.

## • **Modo de encaminhamento centralizado**: 
Depois que os dados do serviço de terminal chegam ao AP, eles são encapsulados usando CAPWAP e enviados ao AC; em seguida, são desencapsulados pelo AC e encaminhados à rede da camada superior.

• **Vantagens**: Os pacotes de dados são encaminhados pelos ACs de forma centralizada, garantindo a segurança e facilitando o gerenciamento e o controle centralizados.

• **Desvantagens**: Os dados do serviço devem ser encaminhados pelos ACs, o que faz com que a eficiência do encaminhamento de pacotes seja menor do que a do modo de encaminhamento direto, e os ACs ficam sob grande pressão.

## • **Modo de encaminhamento local**: 
Depois que o pacote do terminal chega ao AP, ele é encaminhado diretamente pelo AP para a rede da camada superior.

• **Vantagens**: Os pacotes de dados não precisam ser encaminhados pelos ACs; a eficiência do encaminhamento de pacotes é alta, e os ACs estão sob baixa pressão.

• **Desvantagens**: Os dados do serviço não podem ser gerenciados e controlados de forma centralizada.

## • **Modo de encaminhamento local**: 
Depois que o pacote do terminal chega ao AP, ele é encaminhado diretamente pelo AP para a rede da camada superior.  

• Vantagens: Os pacotes de dados não precisam ser encaminhados pelos ACs; a eficiência do encaminhamento de pacotes é alta, e os ACs estão sob baixa pressão.

• Desvantagens: Os dados do serviço não podem ser gerenciados e controlados de forma centralizada.