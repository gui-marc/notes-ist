
Sistema que utiliza de várias máquinas para prestar um serviço ao mesmo tempo (__concorrentes__). Possiblita um escalonamento muito maior em comparação a serviços. Garante  a replicação de serviços e dados: se um dos servidores falhar, os outros ainda continuam a existir.

Hoje em dia, praticamente todas as empresas utiliazm de sistemas distribuidos para prover serviços e guardas seus dados.

Há duas maneiras de programar sistemas concorrentes:

__Troca de mensagens__:  um envia uma mensagem ao outro. É o método mais intuitivo para Sistemas Distribuídos. Geralmente por [[Remote Procedure Call]]

__Partilha de memória__: existe um ponto da memoria que é paritlhado entre serviços. Nos SD 

Geralmente o utilizador nao vê as mensagens, e sim o espaço partilhado de memória 