
![[Introdução - Modo de Compatibilidade - Ex 02.png]]

## O sistema é livre de deadlock?

Não, pois devido ao jeito que foi estruturado o sistema ele não está livre de casos de espera circular.

## Existe alguma situação específica em que ocorre deadlock?

Caso cada processo acesse o arquivo de de mesmo número(n), nenhum processo podera acessar dois arquivos simuntaneamente, e se essa for uma condição para a conclusão de um ou mais processos os arquivo acessados por ele nunca serem liberados, enfim causando um deadlock.

## Caso afirmativo, proponha um padrão de acesso que evite deadlock

1. Um jeito de evitar deadlocks seria definir um tempo máximo que cara processo pode reter um arquivo, porém essa soloção ainda geraria problemas com **Starvation**.

2. Uma melhor solução seria definir que cada processo deve sempre acessar os dois arquivos simuntaneamente, se ele não conseguir o acesso duplo, ou seja, se ele acessar apenas um arquivo ele deve libera-lo para que outro processo possa conseguir o acesso duplo.                                                 Assim seria possivél eliminar Deadlocks porém o desempenho ainda está longe de ser otimizado.

	Ilustração:
	![[Jantar dos filósofos.png]]
