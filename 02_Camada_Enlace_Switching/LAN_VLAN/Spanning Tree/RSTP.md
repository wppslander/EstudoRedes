 O RSTP foi inicialmente elaborado no padrão IEEE 802.1w e, posteriormente, foi incorporado ao padrão 802.1d-2004.

Derivado do STP IEEE 802.1D-1998, o RSTP usa [[BPDU]]s de configuração para fornecer informações para o cálculo do [[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/Spanning Tree/Spanning Tree]] e calcula o spanning tree em uma [[WLAN]]]] com base na comparação de [[BPDU]]s de configuração.

O RSTP reduz o atraso que uma porta deve sofrer para fazer a transição do estado blocking para o estado forwarding depois de ser eleito o [[root port]] ou designated. Nesse sentido, o [[RSTP]] é melhor que o [[Modelo OSI/Camada Física/Rede com Fio/STP]].

As subseções subsequentes descrevem como o RSTP alcança a convergência rápida da rede em diferentes cenários.

## Uma porta é eleita como root port

Suponha que um [[switch]] tenha duas portas que possam alcançar o [[root bridge]], sendo uma a [[root port]] e a outra a alternate port (bloqueada). A alternate port pode assumir o controle da root port sem atraso quando a topologia muda ou por qualquer outro motivo. Não é necessário enviar [[BPDU]]s para a mudança. O atraso na recuperação de falhas é, portanto, reduzido a vários milissegundos, dependendo do atraso de processamento da CPU.

## Uma porta é eleita como Designated port

Essa situação é mais complexa. Uma porta sem borda refere-se a uma porta que se conecta a outro [[switch]] e não a um dispositivo terminal. Se dois [[switch]]es usarem uma conexão ponto a ponto, um [[switch]] precisará enviar um pacote de handshake para o outro e aguardar a confirmação antes que sua porta possa passar para o estado de forwarding. O desempenho do [[RSTP]] depende, portanto, do desempenho do link ponto a ponto. A seguir estão as portas que usam links ponto a ponto:

• Interface de [[agregação de links]] (consulte o módulo sobre agregação de links para obter mais informações)
• Portas que suportam a negociação automática e operam no modo [[full duplex]] após a negociação
• Portas configuradas administrativamente para operar no modo [[full duplex]]

Se uma porta não designada como borda estiver conectada a um link não ponto a ponto, o atraso para a transição do estado de bloqueio para o estado de encaminhamento será o dobro do forward delay (atraso de encaminhamento), da mesma forma que no STP. Portanto, o atraso de transição padrão é de 30 segundos.  
Se a negociação de handshake estiver envolvida, o tempo total de convergência dependerá do diâmetro da rede, que é o número máximo de pontes entre dois pontos quaisquer de estações finais na rede comutada. O pior cenário é que o handshake se espalha por toda a rede de uma extremidade à outra. Se o diâmetro da rede for sete, pode ser necessário um máximo de seis handshakes para que a conectividade da rede possa se recuperar.

## Uma porta de borda é a designated port

Não há risco de [[loop]] em uma porta que se conecta diretamente a um dispositivo terminal em vez de um [[switch]]. Uma porta de borda não participa do cálculo da [[Modelo OSI/Camada De Interface de Rede/LAN_VLAN/Spanning Tree/Spanning Tree]] e pode fazer a transição rápida para o estado de encaminhamento sem demora.