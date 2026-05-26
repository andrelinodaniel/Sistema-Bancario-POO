# Sistema Bancario em Python

Sistema bancario orientado a objetos desenvolvido em Python, com suporte a clientes, contas correntes e operacoes financeiras basicas via terminal.

## Funcionalidades

- Cadastro de clientes com nome, CPF, data de nascimento e endereco
- Criacao de contas correntes vinculadas a clientes
- Deposito em conta
- Saque com limite por operacao
- Extrato com historico de transacoes e saldo atual
- Listagem de contas cadastradas

## Estrutura do Projeto

```text
Projeto-Sistema-Bancario/
|- sistema_bancario.py
|- README.md
`- template/
   `- 2.py
```

## Arquitetura

O projeto utiliza Programacao Orientada a Objetos com os seguintes componentes:

| Classe | Descricao |
| --- | --- |
| `Cliente` | Classe base para clientes, com endereco e lista de contas |
| `PessoaFisica` | Herda de `Cliente` e adiciona nome, CPF e data de nascimento |
| `Conta` | Classe base para contas bancarias, com saldo, numero, agencia e historico |
| `ContaCorrente` | Herda de `Conta` e aplica limite de saque e limite de quantidade de saques |
| `Historico` | Registra as transacoes realizadas |
| `Transacao` | Classe abstrata que define o contrato das operacoes financeiras |
| `Saque` | Implementa a operacao de saque |
| `Deposito` | Implementa a operacao de deposito |

## Como Executar

### Pre-requisitos

- Python 3.8 ou superior

### Execucao

```bash
python sistema_bancario.py
```

O menu exibido no terminal possui as opcoes:

```text
================ MENU ================
[d]  Depositar
[s]  Sacar
[e]  Extrato
[nc] Nova conta
[lc] Listar contas
[nu] Novo usuario
[q]  Sair
```

## Exemplo de Uso

1. Crie um usuario com a opcao `nu`.
2. Crie uma conta com a opcao `nc`.
3. Realize um deposito com a opcao `d`.
4. Realize um saque com a opcao `s`.
5. Consulte o extrato com a opcao `e`.

## Regras de Negocio

- Nao e possivel sacar valor superior ao saldo disponivel
- O valor maximo por saque e de R$ 500,00
- Sao permitidos no maximo 3 saques
- Depositos e saques com valor menor ou igual a zero sao rejeitados
- Nao e possivel cadastrar dois clientes com o mesmo CPF

## Tecnologias Utilizadas

- Python 3
- `abc`
- `datetime`
- `textwrap`
- `os`

## Observacoes

- O sistema mantem os dados apenas em memoria
- O arquivo `template/2.py` foi usado como referencia do curso
- Atualmente a recuperacao de conta usa a primeira conta do cliente
