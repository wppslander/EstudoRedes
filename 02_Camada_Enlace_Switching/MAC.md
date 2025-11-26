#MAC
O endereço [[MAC]] (Media Access Control) é um identificador único de 48 [[Bit]]s atribuído a cada dispositivo de rede, como:

- [[Placa de rede]]
- [[Roteador]]
- [[Switch]]

Características:

- Único para cada dispositivo
- Atribuído pelo fabricante
- Não pode ser alterado
- Utilizado para identificar dispositivos em redes locais ([[WLAN]]]])

Estrutura:

- 6 pares de dígitos [[Hexadecimal]] (00:11:22:33:44:55)
- Primeiros 3 pares: Identificador do fabricante ([[OUI]] - Organizationally Unique Identifier)
- Últimos 3 pares: Número de série do dispositivo

Diferença entre Endereço MAC e [[Subcamada MAC]]

A [[subcamada MAC]] (Media Access Control) é uma parte da [[Camada Interface de Rede|Camada de Enlace de Dados ]](Data Link Layer) do modelo OSI.

Diferenças

Endereço MAC:

- Identificador único para dispositivos
- Atribuído pelo fabricante
- Não pode ser alterado

[[Subcamada MAC]]:

- Parte da Camada de Enlace de Dados
- Gerencia acesso ao meio de transmissão
- Adiciona/remove cabeçalho MAC
- Não é um identificador

Em resumo, o [[MAC]] é um identificador único para dispositivos, enquanto a [[subcamada MAC]] é responsável por gerenciar o acesso ao meio de transmissão e controlar o fluxo de dados.

Um endereço [[MAC]] é composto por um identificador único organizacional (OUI) de 24 bits e um identificador único estendido (EUI) de 24 bits. O OUI de 24 bits é gerenciado pela Autoridade de Registro (RA) do IEEE e o EUI de 24 bits é atribuído pelos fornecedores de equipamentos.

Os endereços MAC também são chamados de endereços de hardware porque são gravados na memória somente leitura (ROM) das placas de interface de rede e são fixos. O endereço MAC de cada placa de interface de rede é globalmente exclusivo. Se um computador estiver instalado com várias placas de rede, ele terá vários endereços MAC.

![[UnicastBraodcast.png]]
Um quadro Ethernet contém dois endereços "MAC". Um identifica o remetente", chamado de endereço MAC de origem, e o outro identifica o destinatário, chamado de endereço MAC de destino. Um quadro unicast é destinado somente a uma estação. Um quadro de broadcast é destinado a todas as estações em uma[[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/WLAN_RedeSemFio/WLAN]]. Um quadro multicast é destinado a um grupo de estações.

Quando um quadro unicast é enviado, o endereço MAC de destino do quadro é o endereço MAC da estação de destino. Quando um quadro de difusão é enviado, o endereço MAC de destino do quadro é o endereço de broadcast Ethernet FFFF.FFFF.FFFF, indicando que o quadro de broadcast é enviado a todas as estações. Quando um quadro multicast é enviado, o endereço MAC de destino do quadro é um endereço MAC multicast correspondente.

A placa Ethernet tem uma função de filtragem. Uma placa de interface de rede só aceita, desencapsula e envia o quadro destinado a ela para o protocolo da camada superior para processamento. Os quadros não destinados a ela serão descartados. Para realizar essa função, a placa de interface de rede mantém uma tabela de endereços de recebimento, que armazena seu próprio endereço MAC, endereço de broadcast e o endereço MAC do grupo multicast ao qual pertence. Quando um quadro chega, a placa de interface de rede compara o endereço de destino com o endereço da tabela de endereços de recebimento. Se for encontrada uma correspondência, isso indica que o quadro é destinado a ela. Portanto, embora o sinal físico de cada quadro chegue a todas as estações, somente a estação correta pode recebê-lo.

Algumas placas de interface de rede podem funcionar no modo promíscuo. Nesse modo, uma placa pode receber qualquer quadro, independentemente de o quadro ser destinado a ela. As placas no modo promíscuo geralmente são usadas em ferramentas de monitoramento de rede, como o Sniffer.