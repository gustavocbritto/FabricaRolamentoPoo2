FabricaRolamentoPoo2
====================

Descrição do Problema

Uma empresa que fabrica rolamentos possui maquinários para produzi-los, requisições
de pedidos e um técnico para consertar quando uma máquina quebra. O processo dela
funcionar é o seguinte:
1. chega um pedido de um rolamento especifico, podendo ser cilíndrico, cônico,
esférico de aço ou de titânio;
2. Cada rolamento tem: (a) uma ordem a ser seguida nas maquinas (b) um tempo
pra ficar dentro sendo processada; (c) além de uma prioridade especifica pra
cada pedido. Dessa forma, as maquinas possuem filas de prioridade aonde os
pedidos ficam a medida que são requisitados o seu uso;
3. Somente depois de sair da última máquina, é considerado que o pedido está
pronto.
Um rolamento cilíndrico possui prioridade 1, cônico possui prioridade 2, e esférico
prioridade 3. Quanto maior o numero, mais urgente é o pedido.
A ordem do maquinário para um rolamento cilíndrico é
TORNO,FRESA,TORNO,MANDRIL.
A ordem do maquinário para um rolamento cônico eh TORNO, MANDRIL, TORNO.
No caso do rolamento esférico de aço temos FRESA, MANDRIL, TORNO. A ordem
do maquinário para um rolamento esférico de titânio é FRESA, MANDRIL, TORNO,
FRESA, TORNO. O tempo de estadia no mandril é de 1.2 , 2.1 , 1.4 e 1.5 para
cilíndrico, cônico, aço e titânio, respectivamente. O tempo de estadia na fresa é de 0.5 ,
0.5 e 0.6 para cilíndrico, aço e titânio, respectivamente. O tempo de estadia no torno é
de 0.8 , 1.8 , 1.0 e 1.6 para cilíndrico, cônico, acho e titânio, respectivamente. O técnico
sempre demora 20.0 para consertar um equipamento e ele só pode consertar uma
maquina por vez. A frequência de quebra dos equipamentos é de 1.0, 0.5 e 3.0 para o
mandril, fresa e torno, respectivamente.
Por fim, A media de chegada de um pedido de rolamento cilíndrico é de 21.5 , de um
cônico 19.1 e de um esférico 8.0.

2.2Projeto

O programa recebe como entrada o tempo da simulação e deve imprimir a quantidade
de rolamentos que foram construídos de cada tipo e o tempo médio de construção
desses.
Utilize a seguinte função para definer o tempo que demora para um pedido chegar. O
parâmetro de entrada é a média de chegadas do pedido.
float Gera_Exponencial (float avg)
{ float u=0; /* Gera randomicamente um numero entre 0 e 1 */
 do u = (new random().nextFloat());
 while ((u==0) || (u==1));
 return (-avg * log (u));
}

Para saber quanto tempo o rolamento vai ficar no maquinário, use a função: 2.0 *
Estadia_Equipamento_Rolamento * new random().nextFloat()
Por fim, para saber quanto tempo vai demorar pra quebrar o equipamento, use a
função: (2.0 * 10080.0 / Frequencia_Quebra_Equipamento) * new random().nextFloat()

Trabalho de Poo2 - Fabrica de Rolamentos
