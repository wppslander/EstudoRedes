O Power over Ethernet (PoE) é uma tecnologia que permite que a energia elétrica seja transmitida junto com os dados, por meio de um único cabo [[Ethernet]]. Isso simplifica a instalação de dispositivos em redes, eliminando a necessidade de fontes de energia separadas.

Padrões

Existem diferentes padrões PoE, cada um com suas próprias especificações de potência e capacidades. Veja os principais:

IEE 802.3af (PoE):

Potência máxima: 15,4W.
Aplicação: Telefones VoIP, câmeras IP de baixa potência.

IEE 802.3at (PoE+):

Potência máxima: 30W.
Aplicação: Pontos de acesso, Wi-fi, câmeras PTZ (pa-tilt-zoom)

IEE 802.3bt (PoE++):

Potência máxima: 60W (tipo 3) ou 100W (tipo 4).
Aplicação: Pontos de acesso, Wi-fi, câmeras PTZ (pa-tilt-zoom)

![[pinagenPOE.png]]Funcionamento

Quando um dispositivo é conectado à rede PoE, o equipamento que fornece energia é conhecido como PSE (Power Sourcing Equipment) detecta a presença do dispositivo alimentado, é conhecido como PD (Powered Devices) e negocia a quantidade exata de energia necessária.

O PoE opera com uma tensão de 48V, uma escolha ideal para minimizar perdas de energia ao longo do cabo Ethernet.

![[POE2.png]]

Os sistemas PoE têm mecanismos de proteção embutidos para evitar sobrecargas ou curtos-circuitos, protegendo tanto os dispositivos quanto a infraestrutura de rede.

Exemplo: Uma câmera IP pode precisar de mais energia do que um telefone VoIP, então o PSE ajusta a potência fornecida.

OBS: Não esqueça que apenas da tecnologia PoE poder funcionar com cabos UTP de diferentes categorias, deve ser dimensionado corretamente o tráfego necessário e as condições do ambiente para a escolha do cabo.

POE Passivo

Nos alguns casos em que o switch não tenha a tecnologia PoE embarcada, uma solução viável pode ser a utilização de injetores com PoE passivo.

Esses injetores não possuem nenhum tipo de inteligência para alimentar o dispositivo conectado, porém eles já são fabricados para enviar uma tensão fixa para alimentar determinado equipamento. Como podemos ver no exemplo abaixo no caso de alguns access point:
![[POE3InjetorPassivo.png]]

**Atenção!**

Para evitar riscos de queima de equipamento, recomendamos que injetores PoE passivos sejam utilizados para alimentar apenas os equipamentos aos quais eles foram fabricados. Por exemplo: Injetores que já vem nas embalagens de [[roteadores]] empresariais [[wi-fi]].

Vantagens do PoE

- Simplicidade na Instalação: Um único cabo para dados e energia.
- Flexibilidade: Instale dispositivos onde não há pontos de energia.
- Economia de Custo: Elimina a necessidade de eletricistas ou infraestruturas complexas.