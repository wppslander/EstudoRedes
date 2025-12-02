#MTCNA #Transporte #UDP

O **UDP** (User Datagram Protocol) é um protocolo de transporte "não confiável" e sem conexão. Ele prioriza a **velocidade** e a **baixa latência** em detrimento da garantia de entrega.

Ao contrário do [[TCP]], o UDP é um protocolo "Fire and Forget" (Dispare e Esqueça). Ele joga os dados na rede e não verifica se eles chegaram.

### Características Principais

1.  **Sem Conexão**: Não existe Handshake. O emissor simplesmente começa a enviar.
2.  **Sem Garantia**: Não há confirmação de recebimento (ACK) e nem reenvio de pacotes perdidos.
3.  **Leve (Baixo Overhead)**: O cabeçalho UDP é minúsculo (8 bytes) comparado ao do TCP (20 bytes+), consumindo menos largura de banda.

### Quando usar UDP?

O UDP é perfeito para aplicações onde **velocidade é crítica** e perder alguns dados é aceitável:

*   **Streaming de Vídeo/Áudio**: Se você perder um quadro de vídeo no YouTube ou Netflix, é melhor pular para o próximo do que pausar o vídeo para tentar recuperar o perdido.
*   **VoIP (Voz sobre IP)**: Em uma chamada, atraso é pior que falha. Recuperar um pacote de voz de 2 segundos atrás não faz sentido em uma conversa ao vivo.
*   **Jogos Online (FPS/MOBA)**: A posição do jogador precisa ser atualizada em tempo real.
*   **DNS e DHCP**: Consultas rápidas que, se falharem, o computador simplesmente tenta de novo.

### Resumo: TCP vs UDP

| Característica | TCP | UDP |
| :--- | :--- | :--- |
| Conexão | Orientado a Conexão | Sem Conexão |
| Confiabilidade | Alta (Reenvia dados) | Nenhuma (Best Effort) |
| Ordem | Garante a ordem | Chegada desordenada |
| Velocidade | Mais lento (Overhead alto) | Muito rápido |
| Exemplo | Web, E-mail, Bancos | Voz, Vídeo, DNS |
