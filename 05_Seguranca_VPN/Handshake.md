O **handshake** é um processo de negociação inicial que ocorre entre dois dispositivos em uma rede antes do início da transmissão de dados. O objetivo do handshake é estabelecer uma conexão, sincronizar parâmetros e garantir que ambos os dispositivos estão prontos para se comunicar. O processo de handshake pode variar de acordo com o protocolo utilizado, mas em geral envolve várias etapas, incluindo:

1. **Solicitação de Conexão**: Um dispositivo (como um cliente) envia um pedido de conexão para outro dispositivo (como um [[servidor]]).
2. **Confirmação**: O segundo dispositivo responde, confirmando que está pronto para estabelecer a conexão.
3. **Estabelecimento da Conexão**: Ambos os dispositivos concordam sobre parâmetros como velocidade de transmissão, métodos de codificação, e outras configurações.

#### Exemplos de Handshake

- **[[TCP]] 3-Way Handshake**: No protocolo [[TCP]] (Transmission Control Protocol), o handshake é realizado em três etapas:
    1. O cliente envia um segmento SYN (synchronize) para o servidor.
    2. O servidor responde com um segmento SYN-ACK (synchronize acknowledgment).
    3. O cliente finaliza o processo enviando um segmento [[ACK]] (acknowledgment).