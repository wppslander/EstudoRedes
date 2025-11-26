# 🧠 Network Engineering & MikroTik Study Vault

Este repositório contém meu **Digital Garden** (ou *Second Brain*) dedicado ao estudo aprofundado de Redes de Computadores, Protocolos e o ecossistema **MikroTik RouterOS**.

O conteúdo é organizado utilizando a metodologia [Zettelkasten](https://zettelkasten.de/) adaptada, focando na conexão entre conceitos teóricos (Modelo OSI) e implementação prática.

---

## 🎯 Foco e Certificações

Este material serve como base de conhecimento para as seguintes certificações e áreas de estudo:

*   **MTCNA** (MikroTik Certified Network Associate)
*   **MTCSWE** (MikroTik Certified Switching Engineer)
*   **MTCSA** (MikroTik Certified Security Engineer)
*   **MTCRE** (MikroTik Certified Routing Engineer)
*   **MTCWE** (MikroTik Certified Wireless Engineer)
*   **Fundamentos de Redes** (CCNA/Network+ concepts)

---

## 📂 Estrutura do Conhecimento

A estrutura de pastas segue um fluxo lógico de aprendizado, partindo da camada física até a aplicação e serviços:

| Diretório | Conteúdo Principal | Tags Relacionadas |
| :--- | :--- | :--- |
| `00_Fundamentos` | Base teórica, binário, hexadecimal e introdução ao Modelo OSI. | `#Redes` `#Teoria` |
| `01_Camada_Fisica` | Cabeamento estruturado, Fibra Óptica, Modulação e RF. | `#Layer1` |
| `02_Camada_Enlace_Switching` | Switching, VLANs, STP/RSTP/MSTP, MAC Address. | `#MTCSWE` `#Layer2` |
| `03_Camada_Rede_Roteamento` | Roteamento estático/dinâmico, OSPF, Estrutura da Internet (WAN/MAN). | `#MTCRE` `#Layer3` |
| `04_Wireless_WLAN` | Wi-Fi (802.11), Canais, Frequências e Roaming. | `#MTCWE` `#Wireless` |
| `05_Seguranca_VPN` | Túneis (WireGuard, IPsec), Firewalls e Criptografia. | `#MTCSA` `#Security` |
| `06_Infraestrutura_Virtualizacao` | Servidores, Virtualização, QoS e Datacenter. | `#Infra` |
| `99_MikroTik_Labs` | **Laboratórios Práticos** e comandos específicos do RouterOS (Bridge VLAN, Chains). | `#RouterOS` `#Labs` |

---

## 🛠️ Ferramentas Utilizadas

*   **[Obsidian](https://obsidian.md/):** Para escrita e conexão dos conhecimentos (Linkagem bidirecional).
*   **Git:** Para versionamento e histórico de evolução dos estudos.
*   **Plugins Obsidian:**
    *   `obsidian-git`: Para backup automático.
    *   `obsidian-kanban`: Para gerenciamento de tarefas de estudo.

## 🚀 Como utilizar este Vault

1.  Clone este repositório:
    ```bash
    git clone https://github.com/SEU_USUARIO/NOME_DO_REPO.git
    ```
2.  Abra a pasta como um "Cofre" (Vault) no **Obsidian**.
3.  Navegue pelos links ou utilize a busca (`Ctrl+K`) para encontrar tópicos como `[[VLAN]]` ou `[[Wireguard]]`.

---

## ⚠️ Disclaimer

Estas são anotações pessoais de estudo. Embora eu me esforce pela precisão técnica, o conteúdo reflete meu entendimento no momento da escrita e pode conter simplificações para fins didáticos. Sempre consulte a [Documentação Oficial da MikroTik](https://help.mikrotik.com/docs/) para implementações em produção.

---
*Criado e mantido por Dani.*
