
Focada em entregar uma funcionalidade de forma rápida, responder as mudanças de especificação do produto e minimizar os _overheads_ de desenvolvimento.

## Métodos

Desenvolvidos na decada de 1990. O manifesto do desenvolvimento agil, prioriza os individuos e interações, software que funciona, a colaboração do cliente e a resposta a mudanças ao invés de ter um plano.

Todos os métodos sao baseados no __desenvolvimento e entrega incrementais__. O desenvolvimento de um produto é focado em _features_. Começa por priorizar as _features_, de forma que as mais importantes sejam desenvolvidas primeiro.

As habilidades do time de desenvolvimento devem ser reconhecidas e exploradas. Os membros devem ser permitidos de desevolver suas proprias formas de trabalhar sem processos prescritos.

### Scrum

Método que visa agilizar o desenvolvimento e a separação das tarefas.

__Product Owner__: quem tem a decisão final sobre quais as funcionalidades que devem ser implementadas no produto e a ordem em que isso devera ser feito. acompanham o desenvolvimento do produto para que de facto a equipa esteja focada nessas funcioalidades e nao estejam a fugir para outras ideias.

__Scrum Master__: guia a equipa no uso do método Scrum. É quase um treinador da equipa, ou seja, garante que as reuniões e interações entre o time estejam otimas.

__Backlog__: lista de todas as funcionalidades que um produto deve ter. O _product owner_ define quais tem as maiores prioridades.

__Sprint__: tempos fixos (2 a 4 semanas) em que as funcionalidades do _backlog_ são implementadas. Durante essa epoca a equipa tem reuniões diarias para rever o progresso e atualizar a lista de tarefas que estão incompletas. Uma sprint deve gerar uma incrementação entregavel do produto (_shippable product increment_).

__Self-organized teams__: equipas que fazem as suas proprias decisoes e trabalham na discussão dos problemas e decisões em consenso.

É dividido em 3 partes: planeamento, execução e revisão.

## Técnicas

> [!note!] Nota
> Muitas das tecnicas vem de um livro chamado Extreme Programming (XP) - Kent Beck - 1980

#### Planeamento Incremental / User Stories

Não há um grande plano para o sistema. Portanto, o que tentamos fazer é, atraves de um processo de análise, escrever os requisitos em forma de historias (cenario de utlização que o usuário do sistema pode enfrentar). Geralmente no git utilizamos os issues para representar os __stories__. Um template de _story_ é:

```
As a <type of user>, I want <some goal> so that <some reason>.
```

A partir de uma história tambem utilizamos um __critério de aceitação__. Ou seja, para a tarefa ser considerada aceite, existem uma serie de regras que ela deve seguir ou objetivos que deve cumprir.

Geralmente são usadas tecnicas como o TDD: uso de testes para garantir a qualidade da implementação.

#### Refactoring

Melhorar a estrutura, _redability_, eficiência e segurança de um programa. No _Agile_, sempre que vemos uma oportunidade de melhorar alguma dessas caracteristicas, o recomendado é já o fazer.


## From User Stories to Tasks

Relembre-se da historia previamente discutida e dos critérios de aceitação. 