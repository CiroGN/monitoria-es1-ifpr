# Erro ao criar banco de dados no Azure com conta de estudante

Registro dos testes de preparação do minicurso de nível 1 do projeto DevOps Azure IFPR (Fundamentos de Cloud, DevOps e Sustentabilidade), feitos em setembro de 2026.

## O que aconteceu

Ao seguir o guia e criar o banco de dados gratuito no Azure, a criação falhou com a mensagem:

> A conta de usuário selecionada não existe no locatário 'Microsoft...'

## O que foi tentado

| Data | Onde | Tentativa | Resultado |
|---|---|---|---|
| 16/09 | Laboratório 3, IFPR Pinhais | conta de estudante | mesmo erro |
| 16/09 | Laboratório 3 | trocar o diretório da conta no portal | mesmo erro |
| 16/09 | Laboratório 3 | conta pessoal Outlook e outros dois e-mails | mesmo erro nos três |
| 17/09 | remoto | conta de estudante, depois que as portas do servidor do campus foram liberadas | mesmo erro |
| 21/09 | remoto | conta de estudante | mesmo erro |

As portas dos laboratórios foram liberadas e funcionaram. O problema ficou restrito à autenticação da Microsoft com conta de estudante, e até 24/09, data do minicurso na SciTec, a causa não tinha sido encontrada.

## Se acontecer com você

- Confira se você está logado no diretório (tenant) certo, no canto superior direito do portal do Azure.
- Tente em uma janela anônima, para não misturar sessões de contas diferentes.
- Se continuar, abra uma issue com o print do erro e o tipo de conta que você usou. Cada caso novo ajuda a entender o problema.
