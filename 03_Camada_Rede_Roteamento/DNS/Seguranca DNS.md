#MTCNA #Seguranca #DNS

O DNS original foi projetado nos anos 80 sem foco em segurança. As requisições são enviadas em texto puro (UDP/53), o que permite que qualquer pessoa na rede intercepte (Eavesdropping) ou altere (Spoofing) as respostas.

Para combater isso, surgiram extensões e novos protocolos.

### 1. DNSSEC (DNS Security Extensions)

O **DNSSEC** garante a **Autenticidade** e **Integridade** da resposta DNS, mas **não a privacidade** (os dados ainda são legíveis).

*   **Como funciona**: Ele cria uma "Corrente de Confiança" usando criptografia assimétrica (Chaves Públicas e Privadas).
*   **O Processo**:
    1.  O servidor Raiz assina digitalmente a chave do TLD (.com).
    2.  O TLD assina a chave do domínio (google.com).
    3.  Quando você consulta o domínio, seu resolver verifica as assinaturas digitais.
*   **Proteção**: Evita ataques de **DNS Spoofing** ou **Cache Poisoning**, onde um atacante responde com um IP falso para redirecionar o usuário para um site de phishing.

### 2. DoH (DNS over HTTPS)

O **DoH** foca na **Privacidade** e **Segurança** do transporte entre o cliente e o servidor DNS Recursivo.

*   **O Problema**: O DNS normal usa a porta 53 (UDP/TCP) em texto claro. Seu provedor de internet ([[ISP]]) ou um hacker no Wi-Fi do aeroporto pode ver exatamente quais sites você visita.
*   **A Solução**: O DoH encapsula as consultas DNS dentro de um tráfego **HTTPS** criptografado (Porta 443), o mesmo usado por sites seguros.
*   **Vantagem**: O tráfego DNS se misturar com o tráfego web normal, tornando-o invisível para observadores e difícil de bloquear.
*   **MikroTik**: O RouterOS (v6.47+) suporta DoH, permitindo que o roteador envie todas as consultas da rede de forma criptografada para provedores como Cloudflare (`https://1.1.1.1/dns-query`) ou Google.

### 3. DoT (DNS over TLS)

Similar ao DoH, mas usa um túnel TLS dedicado na porta **853**. É mais fácil para administradores de rede bloquearem ou monitorarem do que o DoH, mas oferece garantias de privacidade similares.

### Resumo das Diferenças

| Protocolo      | Porta     | Criptografado?    | Foco Principal                    |
| :------------- | :-------- | :---------------- | :-------------------------------- |
| **DNS Padrão** | 53 (UDP)  | Não               | Velocidade / Legado               |
| **DNSSEC**     | 53 (UDP)  | Não (Só Assinado) | Integridade (Evitar Falsificação) |
| **DoH**        | 443 (TCP) | Sim (HTTPS)       | Privacidade (Esconder o destino)  |
| **DoT**        | 853 (TCP) | Sim (TLS)         | Privacidade (Padrão dedicado)     |