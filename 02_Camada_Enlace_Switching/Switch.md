#MTCNA #MTCSWE #Layer2 #Hardware

Um **switch** é um dispositivo de rede que conecta diferentes dispositivos dentro de uma mesma rede local ([[WLAN]]]]), permitindo a comunicação entre eles. Seu principal papel é o de gerenciar e otimizar o tráfego de dados, fazendo com que pacotes de dados sejam enviados apenas aos dispositivos de destino correto, o que melhora o desempenho e reduz a possibilidade de colisões de dados na rede.

### [[Modelo OSI|Camada OSI]] e o Papel do Switch

O switch opera majoritariamente nas camadas **Layer 2** ([[Camada Interface de Rede|Camada de Enlace]]) e **Layer 3** ([[Camada de Rede]]) do modelo OSI:

- **Layer 2 [[Camada Interface de Rede|Camada de Enlace]]**: Nessa camada, o switch se baseia nos[[MAC| endereços MAC ]](Media Access Control) para direcionar o tráfego de rede. Ele constrói uma **[[MAC|tabela MAC]]** que mapeia endereços MAC aos seus respectivos dispositivos conectados em cada porta do switch, permitindo a comunicação direta entre dispositivos específicos sem que o tráfego passe por toda a rede. Um switch de camada 2 é eficiente para redes locais e é comumente usado para segmentação de rede e redução de colisões em redes Ethernet.
    
- **Layer 3 ([[Camada de Rede]])**: Aqui, o switch é chamado de **switch Layer 3** ou **switch de camada 3**. Ele funciona de forma semelhante a um roteador em certos aspectos, pois é capaz de **encaminhar pacotes entre diferentes redes** baseando-se em endereços IP, não apenas em endereços MAC. Esse tipo de switch é especialmente útil para redes que necessitam de segmentação IP, permitindo que diferentes sub-redes se comuniquem. Isso é comum em redes empresariais, onde a segurança e o isolamento de tráfego entre departamentos ou setores são necessários.
    

### Tipos de Switch: Layer 2 vs Layer 3

1. **Switch Layer 2**:
    
    - Opera na camada de [[Camada Interface de Rede|Camada de Enlace]] (Camada 2).
    - Trabalha com [[MAC|endereços MAC]].
    - É mais simples e mais econômico em termos de processamento e custo.
    - É ideal para redes locais pequenas, onde não é necessário encaminhar pacotes entre redes diferentes.
    - **Exemplo**: Empresas pequenas e médias, com redes Ethernet que não precisam de comunicação entre diferentes sub-redes.
2. **Switch Layer 3**:
    
    - Opera na camada de rede (Camada 3) além da camada de enlace.
    - Trabalha com endereços [[IP]], além dos [[MAC|endereços MAC]], permitindo o encaminhamento entre redes.
    - Possui funcionalidades semelhantes a um roteador, com roteamento estático e, em alguns casos, até roteamento dinâmico.
    - Mais complexo e com maior custo, geralmente usado em redes maiores.
    - **Exemplo**: Redes empresariais maiores que exigem separação de rede entre departamentos e precisam de controle de tráfego entre sub-redes.

### Vantagens e Aplicações dos Switches Layer 2 e Layer 3

- **Layer 2**:
    
    - Reduz a carga de tráfego ao enviar pacotes diretamente ao destino.
    - Aumenta a segurança, pois limita o tráfego desnecessário na rede.
    - Simplifica o gerenciamento de redes locais.
- **Layer 3**:
    
    - Facilita o roteamento entre sub-redes.
    - É mais seguro, pois permite isolar diferentes segmentos de rede.
    - Suporta funcionalidades avançadas, como Quality of Service (QoS) e VLANs, que são ideais para redes complexas.

### Resumo: Relação com o [[Modelo OSI]]

- **Layer 2**: Focado no tráfego dentro de uma mesma rede local (MAC address).
- **Layer 3**: Expande a capacidade do switch para rotear tráfego entre redes (IP address).

Assim, a escolha entre um switch Layer 2 e um switch Layer 3 depende das necessidades da rede, da complexidade da comunicação entre dispositivos e das políticas de segurança e segmentação de rede da organização.