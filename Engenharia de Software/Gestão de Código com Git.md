[Git Book](https://git-scm.com/book/en/v2)
[Intellij - Resolve Conflicts](https://www.jetbrains.com/help/idea/resolving-conflicts.html)

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

```bash
# Muda a base do branch para o branch do argumento, ou atualiza caso for o mesmo.
git rebase <branch>
```

