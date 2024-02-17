(from wikipedia)
**Chamada remota de procedimento** (**RPC**, acrônimo de _Remote Procedure Call_) é uma tecnologia de [comunicação entre processos](https://pt.wikipedia.org/wiki/Comunica%C3%A7%C3%A3o_entre_processos "Comunicação entre processos") que permite a um [programa de computador](https://pt.wikipedia.org/wiki/Programa_de_computador "Programa de computador") chamar um procedimento em outro [espaço de endereçamento](https://pt.wikipedia.org/wiki/Espa%C3%A7o_de_endere%C3%A7amento "Espaço de endereçamento") (geralmente em outro computador, conectado por uma [rede](https://pt.wikipedia.org/wiki/Rede_de_computadores "Rede de computadores")). O programador não se preocupa com detalhes de implementação dessa interação remota: do ponto de vista do código, a chamada se assemelha a chamadas de procedimentos locais.

> [!note] Nota
> No fundo é basicamente chamar uma função que vai ser executada em outro servidor

## Interface Definition Language - IDL

Linguagem para definir comunicação entre o cliente e o servidor. Existem várias dessas linguagens. Cada sistema de RPCs tem um tipo especifico de linguagem, no caso do gRPC a linguagem é o `ProtoBuf`.

```protobuf
program counter {
	version c_version {
		void limpa(void) = 0,
		void mc(int) = 1,
		int consulta(void) = 2, // o numero define o indice do metodo
	} = 1
} = 45484
```

> [!info] Nota
> Se assemelha a definição de um header file (.h) em c. Todos os clientes e todos os servidores tem de usar o mesmo formato.

## Diferenças entre SD e Concorrência Centralizada

Nos Sistemas Distribuídos, as coisas falham-se aos bocados. Por exemplo, pode acontecer de chamar um procedimento, como são máquinas diferentes em sítios diferentes, ao enviar um pedido nunca receber a resposta: e agora? Nunca sabemos. Não há como saber se a máquina falhou a receber a instrução, a processar a instrução, ou se ele processou e falou a enviar. Imagine este erro ao fazer uma transferencia bancária, por exemplo.

Uma das soluções é a implementação de um protocolo de _melhor esforço_: envia o pedido e nao se importa caso a resposta chegar ou não (funciona quando o serviço não é assim tão importante). Outra solução é enviar o pedido _pelo menos uma vez_ e usar _timeouts_ para reenviar o pedido caso não seja respondido. A última solução é enviar _exatamente uma vez_, isto é possível, por exemplo, a partir da atribuição de um _UID_ (Identificador unico) ao pedido, e o servidor guarda a resposta aquele pedido (log). Se houver uma falha na comunicação, o resultado do pedido já está processado e é somente enviado novamente.

> [!info] Nota
> No caso de enviar _exatamente uma vez_, teoricamente precisariamos guardar o log de um pedido para todo sempre, o que não é possível na pratica. Ou seja, esse sistema, na prática, não é 100% possível. (mesmo assim é utilizado)

## Serviço de Nomes (nameserver)

Serviço no qual se envia uma string `www.exemplo.com` e se recebe um `IP`. O DNS é um exemplo de serviço de nomes.


### Load Balancing

Escolher entre todos os servidores, qual vai ser selecionado para responder um pedido. Existem varias estratégias para `Load Balancing`, por exemplo escolher um servidor ao calhas ou escolher o servidor mais próximo ao usuário de modo a reduzir a latência.