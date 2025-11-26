Para bloquear links redundantes, o [[STP]] introduz três regras de porta: [[Root port]], [[Designated Port]] e [[Alternate port]]. Ele permite que as portas raiz e designadas encaminhem dados, mas bloqueia as portas alternativas. As funções das portas são atribuídas da seguinte forma:

1) Todas as portas do [[Root Bridge]] são designated port.

2) Entender que **todas as portas do [[Root Bridge]] serão Designated port**, com status **Forwarding**.

3) Os [[switch]]es que não forem o root da rede irão avaliar o caminho com menor custo para chegar ao [[Root Bridge]]. Ao identificar o caminho de menor custo, essa porta será então uma “Root port”.

4) Todo enlace deve possuir uma Designated port, com status Forwarding.

5) As portas que não são designated nem root port são portas que chamamos de Alternate port. Os quadros de dados Ethernet comuns são bloqueados nas portas alternativas.