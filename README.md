# 🏦 Sistema Bancário — Exercitando POO

Sistema bancário orientado a objetos desenvolvido em Python, com suporte a clientes, contas correntes e operações financeiras básicas via terminal.

---

## 📋 Funcionalidades

- **Cadastro de clientes** com nome, CPF, data de nascimento e endereço
- **Criação de contas correntes** vinculadas a clientes
- **Depósito** em conta
- **Saque** com limite por operação
- **Extrato** com histórico de transações e saldo atual
- **Listagem de contas** cadastradas

---

## 🗂️ Estrutura do Projeto

```text
Projeto-Sistema-Bancario/
├── sistema_bancario.py
├── README.md
└── template/
    └── 2.py
```

---

## 🧱 Arquitetura

O projeto utiliza **Programação Orientada a Objetos** com os seguintes componentes:

| Classe | Descrição |
| --- | --- |
| `Cliente` | Classe base para clientes, com endereço e lista de contas |
| `PessoaFisica` | Herda de `Cliente` e adiciona nome, CPF e data de nascimento |
| `Conta` | Classe base para contas bancárias, com saldo, número, agência e histórico |
| `ContaCorrente` | Herda de `Conta` e aplica limite de saque (R$ 500,00) e limite de quantidade de saques (3) |
| `Historico` | Registra as transações realizadas com tipo, valor e data/hora |
| `Transacao` | Classe abstrata que define o contrato das operações financeiras |
| `Saque` | Implementa a operação de saque |
| `Deposito` | Implementa a operação de depósito |

---

## ▶️ Como Executar

### Pré-requisitos

- Python 3.8 ou superior

### Execução

```bash
python sistema_bancario.py
```

O menu exibido no terminal possui as opções:

```text
================ MENU ================
[d]  Depositar
[s]  Sacar
[e]  Extrato
[nc] Nova conta
[lc] Listar contas
[nu] Novo usuário
[q]  Sair
```

---

## 💡 Exemplo de Uso

1. Crie um usuário com a opção `nu`.
2. Crie uma conta com a opção `nc`.
3. Realize um depósito com a opção `d`.
4. Realize um saque com a opção `s`.
5. Consulte o extrato com a opção `e`.

---

## ⚠️ Regras de Negócio

- Não é possível sacar valor superior ao saldo disponível
- O valor máximo por saque é de **R$ 500,00**
- São permitidos no máximo **3 saques**
- Depósitos e saques com valor menor ou igual a zero são rejeitados
- Não é possível cadastrar dois clientes com o mesmo CPF

---

## 🛠️ Tecnologias Utilizadas

- **Python 3**
- `abc` — classes abstratas
- `datetime` — registro de data/hora nas transações
- `textwrap` — formatação do menu
- `os` — limpeza do terminal

---

## 📌 Observações

- O sistema mantém os dados **apenas em memória** (sem persistência em banco de dados ou arquivo)
- O arquivo `template/2.py` foi usado como referência do curso
- Atualmente a recuperação de conta usa a primeira conta do cliente