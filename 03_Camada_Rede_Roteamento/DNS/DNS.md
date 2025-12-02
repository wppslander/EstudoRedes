#MTCNA #Redes #Servicos #Aplicacao

O **DNS** (Domain Name System) é o serviço da **Camada de Aplicação** (Porta 53 UDP/TCP) responsável por traduzir **[[Hostname]]s** (nomes amigáveis como `www.google.com`) em **Endereços [[IPv4]]** ou **[[IPv6]]** (como `142.250.78.68`).

Costuma-se dizer que o DNS é a "Lista Telefônica" da Internet, mas ele é muito mais complexo que isso, funcionando como um banco de dados distribuído e hierárquico.

### A Hierarquia do DNS

O DNS não está em um único servidor gigante. Ele é dividido em níveis, lidos da direita para a esquerda (embora a gente escreva o contrário): `www.google.com.` (existe um ponto final invisível).

1.  **Root Servers (Raiz `.` )**: O topo da pirâmide. Existem 13 endereços lógicos de servidores raiz no mundo. Eles sabem quem controla os TLDs.
2.  **TLD (Top-Level Domain)**: São os finais dos domínios (`.com`, `.br`, `.org`). Eles sabem quem são os servidores autoritativos de cada domínio registrado.
3.  **Authoritative Servers (Autoritativos)**: São os servidores onde você realmente configura seu domínio (ex: Cloudflare, AWS Route53, Registro.br). Eles têm a resposta final.

### O Processo de Resolução (Recursivo vs Iterativo)

Quando você acessa um site, seu computador geralmente fala com um **DNS Recursivo** (como o 8.8.8.8 ou o DNS do seu provedor).

1.  **Cliente**: Pergunta ao Recursivo: "Qual o IP de `www.google.com`?"
2.  **Recursivo**: Se não tiver no cache, ele pergunta ao **Root**: "Quem cuida do `.com`?"
3.  **Root**: "Não sei o IP, mas fale com o servidor do TLD `.com` neste IP X".
4.  **Recursivo**: Pergunta ao TLD `.com`: "Quem cuida de `google.com`?"
5.  **TLD**: "Fale com o servidor Autoritativo do Google neste IP Y".
6.  **Recursivo**: Pergunta ao Autoritativo: "Qual o IP de `www.google.com`?"
7.  **Autoritativo**: "É `142.250.78.68`".
8.  **Recursivo**: Entrega o IP ao Cliente e guarda na memória (Cache).

### Cache e TTL

Para não repetir essa maratona toda vez, existe o **TTL** (Time To Live).
*   O TTL define por quanto tempo (em segundos) aquela informação pode ficar guardada no cache do seu roteador ou computador.
*   É por isso que mudanças de DNS demoram para se propagar (ex: de 1h a 48h).

### Tipos de Registros (Records)

| Tipo      | Significado    | Função                                                                |
| :-------- | :------------- | :-------------------------------------------------------------------- |
| **A**     | Address        | Hostname $\rightarrow$ **[[IPv4]]**.                                  |
| **AAAA**  | Quad-A         | Hostname $\rightarrow$ **[[IPv6]]**.                                  |
| **CNAME** | Canonical Name | Apelido para outro nome (`www` $\rightarrow$ `site.com`).             |
| **MX**    | Mail Exchanger | Servidor de E-mail do domínio.                                        |
| **NS**    | Name Server    | Aponta para o Servidor Autoritativo (quem manda no domínio).          |
| **PTR**   | Pointer        | O inverso do A. IP $\rightarrow$ Hostname (Usado em logs e antispam). |
| **TXT**   | Text           | Texto livre (SPF, Chaves de validação).                               |

### MikroTik como DNS Server

No RouterOS, o MikroTik pode atuar como um **DNS Caching Server**:
1.  Ele recebe as requisições dos clientes da LAN.
2.  Armazena as respostas em cache para acelerar a navegação.
3.  Permite criar **DNS Estático** (Static Entries) para nomear dispositivos locais (ex: `servidor.lan` $\rightarrow$ `192.168.88.200`), dispensando a edição do arquivo hosts em cada PC.

### Diagnóstico

Ferramentas essenciais para testar DNS:
*   `nslookup google.com`: Teste básico presente no Windows/Linux.
*   `dig google.com`: Ferramenta avançada do Linux (mostra TTL, Query time).
*   `ipconfig /flushdns`: Limpa o cache local do Windows.