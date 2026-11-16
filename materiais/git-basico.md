# Git no dia a dia de uma equipe

Resumo dos comandos que mais aparecem nos atendimentos da monitoria. Não cobre tudo, só o que a equipe usa toda semana.

## Começando

```bash
git clone https://github.com/equipe/projeto.git   # baixa o repositório
cd projeto
git status                                          # mostra o que mudou
```

## Trabalhando numa branch

Cada tarefa do quadro vira uma branch. Assim ninguém mexe direto na `main`.

```bash
git switch main
git pull                          # atualiza a main antes de começar
git switch -c tarefa/login        # cria a branch da tarefa
# ... edita os arquivos ...
git add .
git commit -m "Adiciona tela de login"
git push -u origin tarefa/login   # envia a branch para o GitHub
```

Depois do push, abra um pull request no GitHub e peça para alguém da equipe revisar. Ligue o PR à issue da tarefa escrevendo `Closes #12` na descrição. Quando o PR for aceito, a issue fecha sozinha e o card anda no GitHub Projects.

## Mensagens de commit

Escreva o que o commit faz, no presente: "Corrige validação do e-mail", não "mudanças" ou "ajustes". Quem ler o histórico daqui a um mês precisa entender sem abrir o código.

## Conflitos

Conflito acontece quando duas pessoas mudam a mesma linha. O Git marca o trecho assim:

```text
<<<<<<< HEAD
texto da sua branch
=======
texto que veio da main
>>>>>>> main
```

Para resolver:

1. Atualize sua branch com a main: `git pull origin main`.
2. Abra o arquivo e deixe só a versão certa, apagando as marcações `<<<<<<<`, `=======` e `>>>>>>>`.
3. `git add arquivo` e `git commit`.
4. `git push`.

Se o conflito for grande, converse com quem fez a outra mudança antes de escolher.

## Desfazendo coisas

| Situação | Comando |
|---|---|
| Descartar mudanças de um arquivo que ainda não foi commitado | `git restore arquivo` |
| Tirar um arquivo do `git add` | `git restore --staged arquivo` |
| Corrigir a mensagem do último commit (antes do push) | `git commit --amend` |
| Desfazer um commit que já foi enviado | `git revert <hash>` |

Evite `git push --force` em branch compartilhada. Ele apaga o trabalho de quem já tinha enviado.
