Identificação
===================
**Aluno(a): Taís Thomas Siqueira
**Período: 2/2016

**Disciplina:**  ELC893 - Programação de Alto Desempenho
**Profª.:** Andrea Charão


----------


Programa
-------------

O algoritmo utilizado foi o algoritmo Fibonacci. Este realiza o cálculo do Fibonacci de um determinado número.

Link: https://pm.bsc.es/projects/bots

> **Nota:**

> - A Sequência de **Fibonacci** foi proposta pelo matemático Leonardo Pisa no séc XIII. Essa sequência possui uma lei de formação simples: cada elemento, a partir do terceiro, é obtido somando-se os dois anteriores.
> (0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, ...)


----------


Desempenho
-------------------
Este algoritmo calcula o Fibonacci de um determinado número, sendo assim, para estas medições o número utilizado foi o 45.


A tabela e o gráfico a seguir apresentam os dados referentes as medições. Foram realizadas 10 execuções para cada versão do algoritmo.

| Execução 	| SERIAL    		| OMP         			|
|----------	    |-----------  		|-------------			|
| 1             	| 9,298848  		| 1,671304    		|
| 2             	| 9,159666  		| 1,392196    		|
| 3             	| 9,154627  		| 1,533812    		|
| 4        			| 9,160141  		| 1,410711    		|
| 5        			| 9,159986  		| 1,446426    		|
| 6       		 	| 9,153294  		| 1,389993    		|
| 7        			| 9,158274  		| 1,358636    		|
| 8        			| 9,156824  		| 1,526724    		|
| 9       		 	| 9,164720  		| 1,467180    		|
| 10       		| 9,157525  		| 1,349548    		|
|***Média***    		| **9,1723905** 	| **1,454653**    		|
| ***Speedup***  	| **1**         			| **6,305552252** 	|

![enter image description here](https://lh3.googleusercontent.com/-pn3S76Fb_n0/V7OZGwWvChI/AAAAAAAAFwI/_GNf5nuGGNIwl5ZG68EpxkbBz0Gs0ZhuQCLcB/s0/grafico.JPG "grafico.JPG")

Análise
-------------

Para calcular o fibonacci de um número N, o algoritmo sequencial precisa, primeiro, calcular o valor de fibonacci de N-1, para só então calcular o fibonacci de N-2 e aí sim somá-los.

Já o algoritmo paralelizado pode calcular fibonacci de N-1 e N-2 simultâneamente, de forma que a execução do programa prossegue após o cálculo dos dois termos, efetuando a soma e retornando o valor calculado.

A versão OpenMP do algoritmo cria diversas tarefas (tasks) para serem executadas, uma para cada vez que é chamada a função fibonacci. Quando executado no servidor LSC4, o programa utiliza um processador de quatro núcleos, o que faz com que o OpenMP crie 4 threads. Cada uma dessas threads pode executar uma tarefa por vez, o que faz com que quatro chamadas a função fibonacci sejam executadas em simultâneo, reduzindo o tempo necessário para concluir o cálculo, já que o algoritmo serial consegue resolver apenas uma chamada por vez.

----------


Referências
--------------------

http://www.openmp.org/mp-documents/openmp-4.5.pdf


