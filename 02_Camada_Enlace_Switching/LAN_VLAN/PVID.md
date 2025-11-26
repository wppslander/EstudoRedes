**PVID (Port VLAN ID)** é o identificador da [[VLAN]] que é atribuído a uma porta específica em um [[switch]]. Ele define a **[[VLAN]] padrão** para aquela porta, determinando como o [[switch]] tratará o tráfego **não marcado** (sem tags [[VLAN]]) que chega à porta.

### Como o PVID Funciona:

1. **Tráfego Não Marcado**: Quando um dispositivo envia pacotes para a porta do [[switch]] sem especificar uma [[VLAN]] (ou seja, sem marcação), esses pacotes são automaticamente associados à [[VLAN]] indicada pelo PVID da porta.
2. **Isolamento e Segurança**: O PVID ajuda a segmentar a rede, assegurando que dispositivos conectados a portas específicas sejam incluídos em determinadas VLANs para manter o isolamento entre redes diferentes.
3. **Aplicação em VLANs Nativas**: Em links de [[Trunk port|trunk]] (conexões que transportam múltiplas [[VLAN]]s entre [[switch]]es), o [[PVID]] é atribuído à VLAN nativa da porta, que recebe e envia o tráfego sem marcação para a VLAN correspondente.

### Exemplo:

Se a porta 1 de um [[switch]] tem o PVID configurado como 10, qualquer tráfego sem marcação que entrar por essa porta será tratado como parte da [[VLAN]] 10. Isso é útil, por exemplo, em redes onde dispositivos não suportam tags [[VLAN]] e precisam ser atribuídos a uma [[VLAN]] específica de forma automática.

O PVID, portanto, é uma configuração essencial para o gerenciamento de VLANs em [[switch]]es, especialmente em redes complexas que misturam dispositivos compatíveis e não compatíveis com [[VLAN]]s.