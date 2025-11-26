O **ACK** é um sinal enviado de um dispositivo para outro, confirmando que um pacote de dados foi recebido corretamente. A função principal do ACK é assegurar que os dados enviados foram entregues, permitindo que o remetente saiba que pode prosseguir com a transmissão de mais dados. Se um dispositivo não receber um ACK dentro de um determinado período, ele geralmente assume que o pacote foi perdido e tentará retransmiti-lo.

#### Funcionamento do ACK

- Em uma comunicação confiável (como no [[TCP]]), cada segmento de dados enviado é aguardado por um ACK correspondente. Se um dispositivo (o receptor) recebe um pacote, ele envia um ACK de volta ao remetente.
- Caso um pacote não seja recebido ou um erro ocorra, o receptor pode enviar um NACK (negative acknowledgment) ou simplesmente não enviar um ACK, indicando que o remetente deve retransmitir os dados.

### Importância do Handshake e ACK

- **Confiabilidade**: Ambos os processos garantem que a comunicação entre dispositivos é confiável, minimizando a perda de dados e erros de transmissão.
- **Sincronização**: O handshake inicial permite que os dispositivos se sincronizem e estabeleçam um contexto para a comunicação, enquanto o ACK assegura que os dados estão sendo transferidos corretamente.
- **Controle de Fluxo**: Esses mecanismos ajudam a gerenciar o fluxo de dados entre dispositivos, garantindo que não haja sobrecarga na rede.

Em resumo, o handshake e o ACK são fundamentais para estabelecer e manter comunicações confiáveis em redes de dados, assegurando que os dados sejam transmitidos corretamente entre dispositivos.