
__Razões para ter base de dados Distribuídas__
1. Tolerância a faltas. Ter replicas das bases de dados para caso alguma maquina falhar, os dados não serem perdidos
2. Expandir a capacidade de armazenamento da base de dados. As vezes a empresa dados que não cabem em uma maquina somente e por isso precisam de mais maquinas.
3. Razões politicas ou de espaço. Por exemplo, o banco Santander tem uma base de dados para cada agencia, desta forma, quando ha uma transferência, há uma transação que implica na mudança de duas bases de dados em maquinas diferentes.

A maior parte dos sistemas não usa sistemas muito complicados para detectar deadlocks, porque eles dificilmente acontecem. O sistema mais comum é o de transações otimistas.

## Two-Phase Commit

Se eu tiver várias maquinas envolvidas numa transação.

![[Pasted image 20240319131453.png]]

Na fase de PREPARE, o coordenador envia as requisições as outras máquinas para verificar se a transação pode ser _commited_ ou não.

![[Pasted image 20240319131650.png]]

Caso receba um ou mais NOT OK, o coordenador aborta a operação.

![[Pasted image 20240319131741.png]]

Este protocolo bloqueia caso uma das máquinas falhar.

## Algoritmo a base de Consenso

Uma das maquinas faz o PREPARE e depois toda gente faz um broadcast de OK ou NOK. Armazena a quantidade de OKs e, quando acho que está READY, ele faz o CONSENSO.PROPOSE(input) e alguém faz o CONSENSO.DECIDE() -> (retorna ABORT ou COMMIT).

```
quando PREPARE:
	???
	broadcast (OK ou NOK);

quando recebe OK de p_x:
	num_OKs++;

quando num_OKs == N:
	READY = true;
	INPUT = COMMIT;

quando p_x falha:
	READY = true;
	INPUT = ABORT;

quando recebo NOK de p_x:
	READY = true;
	INPUT = ABORT

quando READY:
	consenso.propose(INPUT) // INPUT PODE SER COMMIT OU ABORT
	consenso.decide() -> (COMMIT / ABORT)
```
