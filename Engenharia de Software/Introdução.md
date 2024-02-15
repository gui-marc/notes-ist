
> é recomendado ver os videos antes das aulas

Laboratorios = horarios de duvidas

__Objetivo__: expor metodos e abordagens para garantir a qualidade de projetos de software


_Projetos de Software x Projetos de Engenharia Civil_

quando fazemos a entrega de um produto, há sempre uma evolução: sao feitas adições ou melhorias. (depois de construir uma ponte, ela ja esta feita, não se muda mais nada)


_Aspectos Sociais_: colaborar com pessoas desconhecidas.


__Avaliação__: 
- _Exame_ (minimo: 8, 10 questoes teoricas + 10 questoes do projeto, multipla escolha)
- _Projeto_ (minimo: 8, 2 entregas, discussão na semana 8)


__Discussão Individual__: mudança para fazer em 1 hora. Identificar discrepancias entre a nota do projeto e o coiso.

### Bibliografia

- Software Egnineering at Google - Lessons Learned from Programming Over Time - Curated By Titus Winters, Tom Manshrec & Hyrum Wright
- Software Engineering - Ian Summerville
- Patterns of Enterprise Application Architecture - Martin Fowler

---

## Projeto - Primeira Entrega

Cada subgrupo tera uma tarefa especifica a implementar. Os critérios de avaliação dividem-se entre critérios individuais, do grupo e do subgrupo. Todas as peças de código estão descritas nos critérios de avaliação.

Cada subgrupo devera implementar uma funcionalidade diferente. A carga de trabalho deve ser dividida de forma semelhante entre os 2 compoenntes do subgrupo. O trabalho de cada individuo sera avaliado a partir dos commits dos autores.


---

## Engenharia de Software

> The purpose of software engineering is to develop software-based systems that let customers achieve business goals.

__Sustentabilidade__ -> para o tempo de vide de um codigo, temos de ser capazes de responder a mundanças (dependencias, tecnologias, etc)

---

## Git

```bash
# copia o repositorio para o ambiente local
git clone <repo-url.git>
```

```bash
# Mostra o historico dos nós
git log [--graph] [--oneline]
```

```bash
# Criar ramo
git checkout -b <nome-do-branch>
```

```bash
# Verificar o que mudou
git status
```

```bash
# Adiciona as modificações a area 'staged' -> sera colocada no commit
git add <ficheiro> <ficheiro> ... <ou . para tudo>
```

```bash
# Guarda as mudanças na base de dados do git
git commit -m "<mensagem>"
```

```bash
# Envia as mudanças locais a base de dados remota
git push
```

```bash
# Recebe as mudanças da base de dados remota
git pull
```

