#MTCNA #Redes

O modelo OSI (Open Systems Interconnection) é um padrão que descreve como os dados devem ser transmitidos entre diferentes sistemas em uma rede de comunicação. Ele foi criado pela ISO (International Organization for Standardization) na década de 1980 e é composto por sete camadas, cada uma com responsabilidades específicas. O modelo OSI é uma referência teórica e ajuda a padronizar a forma como diferentes equipamentos e protocolos de rede se comunicam.

Aqui está um resumo das sete camadas do modelo OSI:

1. **[[Camada Física]]**: Trata da transmissão de bits através de meios físicos, como cabos e sinais. Ela especifica características como voltagens, taxas de transmissão e tipo de conector.
    
2. **[[Camada Interface de Rede]] (Enlace de Dados)**: Organiza os bits em quadros (frames) e cuida da correção de erros entre dois dispositivos conectados diretamente. Protocolos como Ethernet e Wi-Fi operam nesta camada.
    
3. **[[Camada de Rede]]**: Responsável pelo roteamento dos dados entre redes diferentes, determinando o caminho que os pacotes devem seguir. O protocolo IP (Internet Protocol) é um exemplo de protocolo dessa camada.
    
4. **[[Camada de Transporte]]**: Garante a entrega confiável dos dados, cuidando da segmentação, reordenação e controle de fluxo. Os protocolos TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são exemplos dessa camada.
    
5. **[[Camada de Sessão]]**: Estabelece, gerencia e termina sessões entre aplicações. Ela cuida da sincronização e do gerenciamento do diálogo entre dois sistemas.
    
6. **[[Camada de Apresentação]]**: Converte os dados entre o formato usado pela aplicação e o formato da rede, lidando com a criptografia, compressão e tradução de dados (como conversão de formatos de arquivos).
    
7. **[[Camada de Aplicação]]**: Interface direta com o usuário final, suportando as aplicações de rede, como navegação web, e-mails, e outros serviços. Protocolos como HTTP, FTP e SMTP operam nesta camada.
    

O modelo OSI é amplamente usado como um guia para entender e projetar sistemas de rede, mas na prática, o modelo TCP/IP, que combina algumas dessas camadas, é o mais usado na internet. O OSI é útil para fins didáticos e para ajudar a solucionar problemas de rede, pois permite identificar em que camada uma falha pode estar ocorrendo.