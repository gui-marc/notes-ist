>[!info] **ACID**
>Atomicidade, consistência, isolamento (pessimista e otimista) e durabilidade.

A ideia foi criada para trabalhar com bancos de dados, mas atualmente possui outras aplicações.

## Strict - Serializability

A estrita serializabilidade é um modelo de consistência usado em sistemas distribuídos para garantir que a execução de transações concorrentes produza resultados que sejam equivalentes a alguma execução sequencial dessas transações, obedecendo à ordem especificada pela sua serialização. Em outras palavras, ela garante que o sistema se comporte como se todas as transações fossem executadas uma após a outra em alguma ordem específica, mesmo que elas realmente sejam executadas concorrentemente.

Aqui está uma análise dos principais aspectos da estrita serializabilidade:

1. **Serializabilidade**: Assim como outras formas de serializabilidade, a estrita serializabilidade garante que o resultado de transações concorrentes seja equivalente ao resultado daquelas transações executadas em série, uma após a outra. Isso é crucial para manter a consistência dos dados em sistemas distribuídos.

2. **Rigor**: A estrita serializabilidade impõe restrições adicionais além da serializabilidade básica. Na estrita serializabilidade, a ordem de execução das transações deve seguir exatamente a ordem na qual elas foram serializadas. Isso significa que se a transação T1 preceder a transação T2 na ordem de serialização, então T1 deve ser concluída antes que T2 comece a ser executada.

3. **Controle de Concorrência**: Alcançar a estrita serializabilidade geralmente requer a implementação de mecanismos fortes de controle de concorrência para garantir que as transações sejam executadas em uma ordem estritamente serializável. Técnicas como bloqueio de duas fases, ordenação por timestamp ou controle de concorrência otimista podem ser empregadas para impor isso.

4. **Complexidade**: Garantir a estrita serializabilidade pode ser desafiador em sistemas distribuídos, especialmente em ambientes altamente concorrentes onde as transações podem originar-se de diferentes nós e serem executadas concorrentemente pela rede. Coordenar a execução de transações enquanto se impõe uma ordem de serialização estrita adiciona complexidade ao sistema.

5. **Impacto no Desempenho**: A imposição da estrita serializabilidade pode acarretar em sobrecarga devido à necessidade de mecanismos de coordenação e sincronização. Essa sobrecarga pode afetar o desempenho do sistema, especialmente em cenários com alta contenção ou atualizações frequentes de dados compartilhados.

Em resumo, a estrita serializabilidade fornece uma garantia de consistência forte em sistemas distribuídos, garantindo que transações concorrentes se comportem como se fossem executadas em uma ordem sequencial estrita. No entanto, alcançar a estrita serializabilidade traz desafios relacionados ao controle de concorrência e sobrecarga de desempenho, tornando essencial projetar e implementar cuidadosamente sistemas distribuídos para atender a esses requisitos.


## Snapshot Isolation

A Isolamento de Snapshot, ou "Snapshot Isolation" em inglês, é um modelo de isolamento de transações usado em sistemas distribuídos e bancos de dados. Ele visa fornecer um nível elevado de isolamento entre transações concorrentes, garantindo que cada transação veja uma visão consistente e isolada dos dados, como se estivesse observando um "instantâneo" dos dados em um determinado ponto no tempo.

Aqui estão os principais pontos sobre a Isolamento de Snapshot:

1. **Visão Consistente**: Cada transação em um sistema que utiliza o Snapshot Isolation vê um conjunto consistente de dados, conhecido como "snapshot", que reflete o estado do banco de dados em um momento específico no tempo. Isso significa que uma transação não é afetada por modificações feitas por outras transações após o momento em que o "snapshot" foi criado.

2. **Isolamento Transacional**: As transações são isoladas umas das outras, o que significa que os efeitos de uma transação não são visíveis para outras transações até que ela seja confirmada (committed). Isso ajuda a evitar problemas como "dirty reads", "non-repeatable reads" e "phantom reads", garantindo que uma transação veja uma versão consistente dos dados durante toda a sua execução.

3. **Concorrência**: O modelo de Isolamento de Snapshot permite um alto nível de concorrência entre transações, pois várias transações podem ser executadas simultaneamente sem que isso comprometa a consistência dos dados. Isso é possível porque cada transação recebe uma versão consistente dos dados no momento em que inicia sua execução.

4. **Versionamento de Dados**: Para implementar a Isolamento de Snapshot, os sistemas de banco de dados geralmente usam técnicas de versionamento de dados, onde diferentes versões dos dados são mantidas para cada transação em execução. Isso permite que cada transação veja uma versão consistente dos dados, isolada das modificações feitas por outras transações.

5. **Implementação**: A implementação da Isolamento de Snapshot pode variar dependendo do sistema de banco de dados ou da plataforma distribuída utilizada. Alguns sistemas podem usar técnicas como "multi-version concurrency control" (MVCC) para gerenciar as versões dos dados, enquanto outros podem empregar mecanismos de "locking" para garantir o isolamento entre transações.

Em resumo, a Isolamento de Snapshot é um modelo de isolamento de transações em sistemas distribuídos que fornece uma visão consistente e isolada dos dados para cada transação, ajudando a garantir a consistência e a integridade dos dados em ambientes com múltiplas transações concorrentes.


## Deadlocks

Deadlock é uma situação em sistemas de computação, especialmente em sistemas distribuídos ou em bancos de dados, onde dois ou mais processos ou transações ficam bloqueados indefinidamente, aguardando recursos que estão sendo utilizados por outros processos ou transações. Em outras palavras, ocorre quando duas ou mais entidades estão esperando por recursos que só podem ser liberados por outras entidades, criando um impasse que impede o progresso de todas elas.

#### Formas de resolver:

- __Maneira Inteligente__: quando uma transação se bloqueia, ia construindo um grafo com vertices, por exemplo T2 -> T1 (T2 esta a depender de T1), e, se houvesse um ciclo neste grafo, então haveria um deadlock.
- __Maneira bastante usada mas burra__: criar um critério de desempate para se uma transação irá ficar a espera de outra ou não. Pode ser um timestamp que vem do relógio de Lamport. Executar de forma que o acesso sempre respeite esse número. 


## Controlo de Concorrência Otimista

O sistema de fazer locks na realidade transforma qualquer operação de leitura em uma operação de leitura e escrita, já que escreve no lock, ou seja, torna as transações lentas. O controlo de concorrência otimista faz somente leitura como se não houvesse concorrências. Quando escreve, escreve numa variável local. No fim, verifica se pode dar commit às alterações na base de dados. O commit baseia-se em reler todas as variáveis usadas e verificar se os valores ainda são iguais a quando a transação começou, se forem diferentes, repete a transação com os valores atualizados.