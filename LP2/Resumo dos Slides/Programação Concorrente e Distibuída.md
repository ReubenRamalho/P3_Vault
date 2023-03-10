## Programa Concorrente
- É hábil a realizar mais que uma operação em um dado momento
---

## Arquiteturas de Sistemas

### -> Sistema Multitarefa:
- Permite vários processos compartilharem o processador;
- Compartilhamento baseado na divisão do tempo;
- Concorrência de processamento e entrada/saída.

![[Sistema Multitarefa.png]]

### -> Sistemas Multiprocessador 
- Aloca processos nos vários processadores;
- Também acontece o compartilhamento de processadores.

![[Sistemas Multiprocessador.png]]

### -> Sistemas Distribuídos
- Consiste de vários computadores que operam independentemente mas que se comunicam;
- Provê maior desempenho agregado e incrementa a confiabilidade.

![[Sistemas Distribuídos.png]]

---
## Tipos de Concorrência 

### -> Concorrência Física (Paralelismo)
- Cada unidade é executada em um processador dedicado.

### -> Concorrência Lógica
- Processador é chaveado de uma unidade para outra;
- Causa a impressão que as unidades executam simultaneamente.
---

## Problemas com Concorrência

### Determinismo X Não-Determinismo

- Um programa **concorrente** é **não-determinístico**;

> [!Não-Determinístico]
> Unidades de execução prosseguem em uma ordem não predefinida.

- Não é possível predizer a seqüência de passos que é realizada ou o resultado final;
- Múltiplas execuções do programa concorrente com os mesmos dados de entrada podem gerar resultados diferentes;
- Seqüência de passos e resultado final dependem do escalonamento interno.
---

### Dependência de Velocidade

- Resultado de um programa concorrente é dependente da velocidade;
	1. Depende da velocidade relativa com que os processos seqüenciais constituintes são executados;
	2. Pequenas flutuações randômicas na velocidade do processador e dispositivos de entrada/saída podem levar ao não-determinismo.
- Quando os resultados são dependentes da velocidade diz-se que existe uma **condição de corrida (race condition)**
![[Dependencia de Velocidade 01.png]]

- Requer a adoção do conceito de **atomicidade**;

> [!Atomicidade]
> Uma variável é atômica quando é inspecionada e atualizada sem qualquer interrupção no processamento

- Atomicidade não resolve o problema geral.
![[Dependencia de Velocidade 02.png]]

---

## Deadlock

- Dois ou mais processos encontram-se impossibilitados de fazer qualquer progresso no processamento;
- Gerado em função das mútuas demandas incompatíveis por recursos;
- Pode ocorrer se e somente se as seguintes condições são satisfeitas:

	1.![[Exclusão Mútua.png]]
	
	2.![[Aquisição Incremental.png]] 
	
	3.![[Não Preempção.png]] 
	
	4.![[Espera Circular.png]]
---

## Starvation

- Processo é indefinidamente impedido de executar em função de escalonamento injusto;
- Somente pode ser evitado se o sistema é livre de deadlock e adota um escalonamento justo.

### Escalonamento Justo:
- Processo é colocado em uma fila associada ao recurso requisitado;
- Se recurso torna-se disponível, um processo na fila eventualmente ganha o acesso ao recurso.

### Escalonamento Injusto:
- Acesso preferencial a processos de alta prioridade;
- Pode retardar indefinidamente um processo de baixa prioridade.
---

## Interações entre Processos

### Processos Independentes

- Processos B e C são **independentes** se . . .
	1. Nenhum passo de B afeta o comportamento de C;
	2. Nenhum passo de C afeta o comportamento de B;
	3. Qualquer passo de B pode ser executado antes, ao mesmo tempo ou depois de qualquer passo de C;
	4. Qualquer passo de C pode ser executado antes, ao mesmo tempo ou depois de qualquer passo de B.
---
### Processos Competidores

- Processos B e C são **competidores** se . . .
	- Ambos requerem acesso exclusivo a algum recurso em um ou vários de seus passos;

- Passos de B e C que requerem acesso exclusivo são denominados regiões críticas;
- Resultados dependem da velocidade relativa dos processos competidores;
	- **Não determinismo limitado (bounded).**
---

### Processos Comunicantes

- Processos B e C são comunicantes se . . .
	1. Algum passo de B (*Bp* ) produz dados que algum passo de C (*Cp* ) consome;
		- *Bp* deve concluir antes de iniciar C.
	2. Algum passo de C (*Cp* ) produz dados que algum passo de B (*Bp* ) consome.
		- *Cp* deve concluir antes de iniciar *Bp*.

- Processos B e C são **intercomunicantes** se existe comunicação em ambas direções
--- 
