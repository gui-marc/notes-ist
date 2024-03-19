
[Relógios de Lamport](https://pt.wikipedia.org/wiki/Rel%C3%B3gios_de_Lamport)

**Relógios lógicos de Lamport** são mecanismos usados em [algoritmos](https://pt.wikipedia.org/wiki/Algoritmos "Algoritmos") de sincronização de [relógio](https://pt.wikipedia.org/wiki/Rel%C3%B3gio "Relógio") baseados na relação **happens-before** definida por [Leslie Lamport](https://pt.wikipedia.org/wiki/Leslie_Lamport "Leslie Lamport").

## Marcas Temporais

Nesses algoritmos cada processo do [sistema distribuído](https://pt.wikipedia.org/wiki/Sistema_distribu%C3%ADdo "Sistema distribuído") mantém um contador crescente e monotônico _C_ (relógio lógico) e cada evento _a_ possui uma marca temporal _C(a)_ na qual todos os processos concordam. Dessa forma, os eventos estão sujeitos às seguintes propriedades derivadas da relação **happens-before**:

1. Se _a_ acontece antes de _b_ no mesmo processo, então _C(a) < C(b)_.
2. Se _a_ e _b_ representam, respectivamente, o envio e o recebimento de uma mensagem, então _C(a) < C(b)_.
3. Sejam _a_ e _b_ eventos quaisquer, então _C(a) ≠ C(b)_


## Relógios vetoriais

Mantem um vetor (array) com as versoes que estão no proprio e em outros sistemas.

![[Pasted image 20240220133228.png]]

Pode ser aplicado a ficheiros e outra coisas.

Caso, na hora de incrementar, os dois sejam iguais, deverá ser desenvolvida uma forma de decidir qual deve ser considerado. Ha casos que é facil fazer o merge automatico das mudanças, mas as vezes isso pode ser muito dificil.

