Há duas abordagens de agregação de links:
## Agregação estática

Na abordagem de agregação estática, os dispositivos em ambas as extremidades não executam nenhum protocolo de agregação de links para negociar o status de agregação das portas membros em um grupo de agregação de links.  
  

Use essa abordagem se o dispositivo em uma das extremidades não for compatível com nenhum protocolo de agregação de link ou se os protocolos suportados nas duas extremidades não forem compatíveis.

## Agregação dinâmica
  
Na abordagem de agregação dinâmica, o protocolo de controle de agregação de links ([[Link Aggregation|LACP]]) IEEE 802.3ad é ativado nos dispositivos em ambas as extremidades para negociar o status de agregação dos membros em um grupo de agregação de links.

O IEEE 802.3ad LACP usa unidades de dados do protocolo de controle de agregação de links ([[LACPDUs]]) para a troca de informações entre dois dispositivos habilitados para [[LACP]].