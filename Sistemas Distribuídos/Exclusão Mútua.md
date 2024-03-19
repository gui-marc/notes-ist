### Solução Centralizada

Imaginem que temos um conjunto de processos em que cada robô faz algo numa bancada. Escolhemos um robô mestre e sempre que alguém quiser acessar uma bancada, pede o acesso a este robô. 

O processo tem uma variável a dizer quem esta na exclusão mútua, outra para dizer quem quer entrar na exclusão mutua e não pode. Quando um processo qualquer quiser entrar na exclusão mútua faz uma _RPC_ ao processo principal e este vera se ele pode ou não entrar na exclusão mútua.

__Desvantagem__: ha uma máquina que fica sobrecarregada

### Solução Descentralizada

