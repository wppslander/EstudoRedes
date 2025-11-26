A camada de interface de rede transmite dados em um meio ou link específico. Meios de transmissão diferentes precisam de protocolos de camada de interface de rede diferentes.

![[Osi-camdaderede.png.png]]

As principais funções da camada de interface de rede são:

• Criação e [[identificação de quadros]]: Como a camada física só envia e recebe fluxos de bits sem se preocupar com suas sequências, estruturas e significados, a camada de interface de rede precisa traduzir os bits em quadros e identificar e enviar quadros para a camada de rede.

• Criação, manutenção e liberação de [[links de dados]]: A camada de interface de rede cria e mantém links de dados durante a transmissão de dados e os libera após a comunicação.

• [[Controle de recursos de transmissão]]: Em um meio compartilhado, vários terminais podem precisar enviar dados ao mesmo tempo. Nesse caso, a camada de interface de rede decide como atribuir recursos.

• [[Controle de fluxo]]: Para evitar o estouro do buffer na extremidade receptora e evitar o congestionamento da rede, a extremidade de envio precisa controlar a velocidade de envio por meio da camada de interface de rede.

• [[Controle de erros]]: Como a camada física não pode identificar erros em fluxos de bits, a camada de interface de rede realiza a detecção de erros por quadro.

• [[Endereçamento]]: A camada de interface de rede identifica todos os nós e transmite dados entre eles usando endereços de hardware.

