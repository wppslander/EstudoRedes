#MTCNA #Transporte #TCP

O **TCP** (Transmission Control Protocol) é o protocolo de transporte orientado a conexão. Ele prioriza a **confiabilidade** e a **ordem** dos dados em detrimento da velocidade bruta. É a base para serviços que não podem perder dados, como Web (HTTP), E-mail (SMTP) e Transferência de Arquivos (FTP).

### Características Principais

1.  **Orientado a Conexão**: Antes de enviar dados, o TCP estabelece um "acordo" entre as duas pontas.
2.  **Confiável**: Garante que todos os dados chegaram. Se um pacote se perder, o TCP o reenvia.
3.  **Ordenado**: Garante que os dados sejam remontados na ordem correta, mesmo que cheguem fora de ordem.
4.  **Controle de Fluxo**: Ajusta a velocidade de transmissão para não sobrecarregar o receptor (Janelamento).

---

### O Three-Way Handshake (Aperto de Mão em 3 Vias)

Para iniciar uma conexão, o TCP usa um processo de 3 etapas. Imagine uma ligação telefônica:

1.  **SYN** (Synchronize): O Cliente envia um pedido: *"Olá, quero conectar (Sincronizar)."*
2.  **SYN-ACK** (Synchronize-Acknowledge): O Servidor responde: *"Recebi seu pedido (ACK). Eu também quero conectar (SYN)."*
3.  **ACK** (Acknowledge): O Cliente finaliza: *"Entendido (ACK). Conexão estabelecida."*

Só após isso os dados reais (HTTP, etc.) começam a passar.

### Flags do Cabeçalho TCP

O cabeçalho TCP possui "bandeiras" (bits) que indicam o propósito do pacote:
*   **SYN**: Início de conexão.
*   **ACK**: Confirmação de recebimento.
*   **FIN**: Pedido de encerramento de conexão (normal).
*   **RST**: Reset. Aborta a conexão abruptamente (erro).
*   **PSH**: Push. Envia os dados imediatamente para a aplicação, sem esperar o buffer encher.

### Janelamento (Windowing)

O TCP usa "Janelas" para controlar o fluxo. O receptor diz: *"Minha janela é de 10.000 bytes"*. O emissor pode enviar até 10.000 bytes antes de precisar parar e esperar uma confirmação (ACK). Se a rede estiver boa, a janela aumenta; se houver perda, a janela diminui.
