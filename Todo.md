# MTCSWE Study To-Do List

This list outlines topics to be covered or expanded to align with the MikroTik Certified Switching Engineer (MTCSWE) curriculum.

## 1. MTU e Jumbo Frames
- [ ] Criar nota: `00_Fundamentos/MTU_L2MTU.md` (ou em `01_Camada_Fisica/`)
  - [ ] Conceitos de MTU e L2MTU
  - [ ] Jumbo Frames
  - [ ] Impacto e configuração no RouterOS (especialmente em Bridge VLAN Filtering e interfaces VLAN)

## 2. Spanning Tree Protocol (STP) Avançado
- [ ] Revisar `02_Camada_Enlace_Switching/LAN_VLAN/Spanning Tree/`
  - [ ] Expandir sobre **RSTP (Rapid Spanning Tree Protocol)**
  - [ ] Criar nota/seção sobre **MSTP (Multiple Spanning Tree Protocol)**
    - [ ] Configuração de regiões MSTP
    - [ ] Conceitos de CIST e MSTI
    - [ ] Balanceamento de carga com MSTP

## 3. VLANs Avançadas
- [ ] Criar nota: `02_Camada_Enlace_Switching/LAN_VLAN/QinQ.md`
  - [ ] Conceitos de **VLAN Stacking (802.1ad / QinQ)**
  - [ ] Diferença entre S-Tag e C-Tag
  - [ ] Configuração de QinQ no RouterOS (Bridge VLAN Filtering e interfaces VLAN)
- [ ] Criar nota: `02_Camada_Enlace_Switching/LAN_VLAN/VLAN_Translation.md`
  - [ ] Tradução de VLANs

## 4. Segurança de Camada 2 (Layer 2 Security)
- [ ] Criar pasta: `05_Seguranca_VPN/L2_Security/`
- [ ] Criar notas dentro da pasta `L2_Security/`:
  - [ ] `DHCP_Snooping.md` (e DHCP Option 82)
  - [ ] `IGMP_Snooping.md`
  - [ ] `Loop_Protect.md` (Recurso MikroTik)
  - [ ] `Traffic_Storm_Control.md`
  - [ ] `Port_Security_802.1X.md`
  - [ ] `BPDU_Guard.md`

## 5. Isolamento de Portas (Port Isolation)
- [ ] Criar nota: `02_Camada_Enlace_Switching/Port_Isolation.md`
  - [ ] Conceitos de Bridge Horizon
  - [ ] Switch Port Isolation

## 6. SwitchOS (SwOS)
- [ ] Criar nota: `99_MikroTik_Labs/SwitchOS.md`
  - [ ] Visão geral do SwOS
  - [ ] Principais configurações (VLANs, LAG, STP) em SwOS
  - [ ] Diferenças entre SwOS e RouterOS para funções de switching

## 7. Hardware Offload e Switch Chip
- [ ] Criar nota: `02_Camada_Enlace_Switching/Hardware_Offload_Switch_Chip.md`
  - [ ] Entendimento do processamento de pacotes (CPU vs Switch Chip)
  - [ ] Configuração de VLANs via Bridge VLAN Filtering vs. menu `/interface ethernet switch`

## 8. PoE (Power over Ethernet)
- [ ] Se ainda não coberto em detalhes, expandir ou criar nota: `01_Camada_Fisica/POE.md`
  - [ ] Configuração de PoE em dispositivos MikroTik
  - [ ] Padrões PoE (802.3af, at, bt)

## 9. Automação de Infraestrutura (IaC)
- [ ] Estudar **Ansible** (Recomendação: LearnLinuxTV)
  - [ ] Instalação e conceitos básicos (Inventory, Playbooks, Tasks)
  - [ ] Gerenciamento de servidores Linux (Debian/Ubuntu)
  - [ ] **Ansible para MikroTik** (RouterOS modules)
    - [ ] Backup automático de configurações
    - [ ] Atualização em massa de usuários/senhas
    - [ ] Configuração de VLANs via Ansible

---
**Observação:** Ao criar as notas, lembre-se de seguir as convenções existentes (idioma, links internos, organização).