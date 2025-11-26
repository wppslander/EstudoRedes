
![[Vlan1 1.png]]
Em uma VLAN Estática ou [[VLAN Baseada em Porta|baseada em porta]], uma porta encaminha o tráfego para uma VLAN somente depois que ele é atribuído à VLAN. A implementação da [[VLAN]] baseada em portas é a base para qualquer outro tipo de VLAN. Antes de usar qualquer outra implementação de VLAN, as configurações de VLAN baseada em portas devem ser definidas.

Na figura ao lado, GigabitEthernet 1/0/1 e GigabitEthernet 1/0/2 são atribuídos à VLAN 10, GigabitEthernet 1/0/3 e GigabitEthernet 1/0/4 são atribuídos à VLAN 20. Portanto, o PCA e o PCB estão na VLAN 10 e podem se comunicar entre si. O PCC e o PCD estão na VLAN 20 e podem se comunicar entre si. No entanto, o PCA e o PCC não podem se comunicar entre si na [[Camada Interface de Rede|Camada 2]] porque estão em VLANs diferentes.

Atribuição de VLAN baseada em porta

Na abordagem de VLAN baseada em sub-rede [[IP]], um quadro é atribuído a uma VLAN com base em seu endereço [[IP]] de origem e máscara de sub-rede.

Essa abordagem é usada para atribuir pacotes do segmento de rede ou endereço IP especificado a uma VLAN específica para fins de gerenciamento.

![[Vlan2 1.png]]

