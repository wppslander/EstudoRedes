# Networking & MikroTik Study Vault

## Project Overview
This directory contains a **Personal Knowledge Base (Digital Garden)** dedicated to the study of **Computer Networking** and the **MikroTik RouterOS** ecosystem. The content is primarily written in **Portuguese** and is structured to support certification paths like **MTCNA**, **MTCSWE**, and others.

The vault follows an adapted [Zettelkasten](https://zettelkasten.de/) methodology, linking theoretical concepts (OSI Model) with practical implementations.

## Directory Structure
The content is organized into numbered directories, creating a logical flow from the physical layer up to application services and specific labs:

*   **`00_Fundamentos/`**: Core theory, binary/hexadecimal math, and the OSI Model.
*   **`01_Camada_Fisica/`**: Layer 1 topics: Cabling (Fiber/Copper), Modulation, RF.
*   **`02_Camada_Enlace_Switching/`**: Layer 2 topics: Ethernet, VLANs, STP/RSTP/MSTP, MAC addresses.
*   **`03_Camada_Rede_Roteamento/`**: Layer 3 topics: Routing protocols, OSPF, WAN/MAN architectures.
*   **`04_Wireless_WLAN/`**: Wireless (802.11), channels, frequencies, and roaming.
*   **`05_Seguranca_VPN/`**: Security, VPN tunnels (WireGuard, IPsec), and firewalls.
*   **`06_Infraestrutura_Virtualizacao/`**: Virtualization, servers, QoS, and data center concepts.
*   **`99_MikroTik_Labs/`**: **Practical Labs** and specific RouterOS commands (e.g., Bridge VLAN Filtering).
*   **`Imagens/`**: Central repository for all diagrams and images used in notes.

## Key Files
*   **`README.md`**: The main entry point explaining the project's purpose and structure.
*   **`Todo.md`**: A roadmap of topics to be studied or expanded, specifically focused on the **MTCSWE** certification curriculum (e.g., MSTP, QinQ, L2 Security).
*   **`.obsidian/`**: Configuration files for the Obsidian editor (plugins, themes).

## Usage & Conventions
*   **Language**: All notes are written in **Portuguese**.
*   **Linking**: Internal links use the Wiki-link syntax `[[Note Title]]`.
*   **Tags**: Used for categorization (e.g., `#MTCNA`, `#Layer2`, `#RouterOS`).
*   **Tools**:
    *   **Obsidian**: The primary editor for viewing and managing the knowledge graph.
    *   **Git**: Used for version control and backup.

## Goals
The current focus (as per `Todo.md`) is on advanced switching topics to prepare for the **MTCSWE** certification, including:
*   MTU & Jumbo Frames
*   Advanced STP (MSTP)
*   VLAN Stacking (QinQ)
*   Layer 2 Security (DHCP Snooping, Port Security)
