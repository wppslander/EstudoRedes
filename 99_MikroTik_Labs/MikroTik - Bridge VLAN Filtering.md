#MTCSWE

# MikroTik - Bridge VLAN Filtering (RouterOS v7)

## 1. Introdução à Bridge VLAN Filtering
*   **Contexto:** Abordagem moderna e flexível para gerenciamento de VLANs no MikroTik, especialmente no RouterOS v7.
*   **Objetivo:** Segmentar redes, isolar tráfego e controlar a comunicação entre VLANs usando a bridge principal.
*   **Diferença fundamental vs. Switch Chip VLANs:**
    *   **Bridge VLAN Filtering:** Processamento via CPU (ou com offload para chips compatíveis) na interface `bridge`. Mais flexível.
    *   **Switch Chip VLANs (Legado):** Processamento via hardware do chip de switch. Mais performático em certos cenários, mas menos flexível para features como o firewall na bridge.

## 2. Componentes Principais
*   **Bridge:** A interface lógica que agrupa as portas físicas.
*   **Bridge Ports:** As interfaces físicas ou virtuais adicionadas à bridge.
*   **Bridge VLANs:** Tabela de VLANs configuradas na bridge.

## 3. Configuração de VLANs na Bridge (Bridge VLAN Filtering)

### 3.1. Habilitar VLAN Filtering na Bridge
```
/interface bridge set bridge1 vlan-filtering=yes
```

### 3.2. Configurar VLANs na Tabela da Bridge
*   Define quais VLAN IDs são permitidas e em quais interfaces da bridge.
*   `vlan-id`: ID da VLAN.
*   `tagged`: Interfaces da bridge que devem **taggear** (marcar) ou receber tráfego tagueado para esta VLAN.
*   `untagged`: Interfaces da bridge que devem enviar ou receber tráfego **sem tag** para esta VLAN (geralmente uma PVID).

**Exemplo:**
```
/interface bridge vlan
add bridge=bridge1 vlan-ids=10 tagged=ether1,bridge1 untagged=ether2
add bridge=bridge1 vlan-ids=20 tagged=ether1,bridge1 untagged=ether3
```
*Neste exemplo:*
*   `ether1` (uplink) espera/envia tráfego tagueado para VLAN 10 e 20.
*   `ether2` (Access Port) pertence à VLAN 10 (untagged).
*   `ether3` (Access Port) pertence à VLAN 20 (untagged).

### 3.3. Configurar PVID (Port VLAN ID) nas Bridge Ports
*   `pvid`: Define qual VLAN ID será atribuída a frames **não tagueados** que chegam nesta porta.
*   Essencial para portas de acesso (Access Ports) e para construir "Hybrid Ports".

**Exemplo (continuando o anterior):**
```
/interface bridge port
set ether2 pvid=10
set ether3 pvid=20
```

## 4. O Conceito de "Hybrid Port" na MikroTik (Usando Bridge VLAN Filtering)
*   **Definição:** Uma porta que permite o tráfego de múltiplas VLANs, sendo que uma delas é **untagged** (definida pelo `PVID`) e as outras são **tagged**.
*   **Cenário:** Conectar um AP ou um host que precisa de acesso untagged a uma VLAN (ex: gerenciamento) e acesso tagged a outras VLANs (ex: VLANs de usuário via SSID).

**Configuração de uma Hybrid Port (`ether4`):**
1.  **Defina o PVID** para a VLAN untagged:
    ```
    /interface bridge port set ether4 pvid=99
    ```
    *(Tráfego sem tag que entra em ether4 é tratado como VLAN 99)*
2.  **Adicione a porta `ether4` como `untagged`** para a VLAN do PVID:
    ```
    /interface bridge vlan
    add bridge=bridge1 vlan-ids=99 untagged=ether4 tagged=ether1,bridge1
    ```
3.  **Adicione a porta `ether4` como `tagged`** para as outras VLANs:
    ```
    /interface bridge vlan
    add bridge=bridge1 vlan-ids=10 tagged=ether1,bridge1,ether4
    add bridge=bridge1 vlan-ids=20 tagged=ether1,bridge1,ether4
    ```
    *(Agora `ether4` envia/recebe untagged para VLAN 99 e tagged para VLAN 10 e 20)*

## 5. Parâmetros Importantes
*   **`ingress-filtering=yes` (na bridge port):** Impede que frames com tags não permitidas na porta entrem na bridge. Altamente recomendado para segurança e para evitar loops.
*   **`frame-types=admit-all | admit-only-vlan-tagged | admit-only-untagged-and-priority-tagged`:** Define quais tipos de frames (tagged/untagged) são permitidos na porta.

## 6. Considerações
*   **Performance:** A Bridge VLAN Filtering é mais flexível, mas pode ter impacto na CPU se não houver offload de hardware.
*   **Troubleshooting:** Use `/interface bridge vlan print` e `/interface bridge port print` para verificar a configuração. Use o Firewall na Bridge para depurar.
