#MTCNA #Transporte

As **Portas** (ou Portas Lógicas) são identificadores numéricos usados na Camada de Transporte ([[TCP]] e [[UDP]]) para direcionar o tráfego de rede para o aplicativo ou serviço correto dentro de um computador.

Enquanto o **Endereço IP** identifica o **dispositivo** na rede (como o endereço de um prédio), a **Porta** identifica o **serviço** específico dentro desse dispositivo (como o número do apartamento).

### O Conceito de Socket

A combinação de `Endereço IP : Porta` é chamada de **Socket**.
*   Exemplo: `192.168.1.50:80` (IP 192.168.1.50 na porta 80).

### Intervalos de Portas (IANA)

Existem 65.535 portas disponíveis, divididas em três categorias:

1.  **Portas Bem Conhecidas (Well-Known Ports)**: `0` a `1023`
    *   Reservadas para serviços de sistema e protocolos padrão.
    *   Ex: HTTP (80), HTTPS (443), SSH (22), DNS (53).

2.  **Portas Registradas**: `1024` a `49151`
    *   Atribuídas a softwares específicos de fornecedores.
    *   Ex: **MikroTik Winbox** (8291), SQL Server (1433).

3.  **Portas Dinâmicas / Privadas**: `49152` a `65535`
    *   Usadas temporariamente pelos clientes. Quando você abre um site, seu computador escolhe uma porta aleatória desse intervalo para receber a resposta do servidor.

### Portas Importantes para MikroTik e Redes

| Porta | Protocolo | Serviço | Descrição |
| :--- | :--- | :--- | :--- |
| **20/21** | TCP | FTP | Transferência de Arquivos. |
| **22** | TCP | SSH | Acesso remoto seguro (CLI). |
| **23** | TCP | Telnet | Acesso remoto inseguro. |
| **53** | UDP/TCP | DNS | Resolução de Nomes. |
| **67/68** | UDP | DHCP | Atribuição de IP (Server/Client). |
| **80** | TCP | HTTP | Web (Não criptografado). |
| **443** | TCP | HTTPS | Web Segura. |
| **8291** | TCP | Winbox | Gerenciamento gráfico MikroTik. |
| **8728** | TCP | API | API do MikroTik. |
