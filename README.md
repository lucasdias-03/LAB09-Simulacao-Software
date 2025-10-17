# Sistema Task Manager

Um pequeno sistema de **gerenciamento de tarefas** desenvolvido para fins acadêmicos.  
O projeto tem como objetivo demonstrar conceitos de modularização, testes automatizados e boas práticas de código em Python.

---

## Descrição Geral

O **Task Manager** permite criar, listar, atualizar e remover tarefas, cada uma contendo título, descrição, prioridade, prazo e status.  
O armazenamento é feito em memória (via `InMemoryStorage`), simulando um pequeno banco de dados temporário.

---

## Estrutura do Projeto

```
task_manager/
│
├── __init__.py              # Arquivo de inicialização do pacote
├── task.py                  # Define a classe Task, Prioridade e Status
├── storage.py               # Implementa armazenamento em memória
├── repository.py            # Controla persistência das tarefas
├── service.py               # (BÔNUS) Camada de serviço para orquestração
│
tests/
├── test_task.py             # Testes da classe Task
├── test_repository.py       # Testes do repositório
│
├── requirements.txt         # Dependências do projeto
└── README.md                # Este arquivo
```

---

## ⚙️ Funcionalidades

- Criar tarefas com **título**, **descrição**, **prioridade** e **prazo**
- Listar todas as tarefas
- Buscar tarefa por **ID**
- Atualizar o **status** de uma tarefa
- Deletar tarefas

---

## Principais Classes

### `Task`
Representa uma tarefa individual, com métodos de validação de dados (como título e prazo).

### `Priority`
Enum com três níveis:
- `BAIXA`
- `MEDIA`
- `ALTA`

### `Status`
Enum com três estados:
- `PENDENTE`
- `EM_PROGRESSO`
- `CONCLUIDA`

### `InMemoryStorage`
Responsável por armazenar os objetos em um dicionário interno (`Dict[int, Any]`).

### `TaskRepository`
Gerencia o ciclo de vida das tarefas, atribuindo IDs e repassando operações de CRUD ao `InMemoryStorage`.

### `TaskService` *(opcional / bônus)*
Camada de serviço que centraliza a criação, listagem e atualização de status das tarefas, aplicando regras de negócio.

---

## Testes Automatizados

Os testes foram desenvolvidos com **pytest** e **pytest-mock**, cobrindo:
- Validação de título e prazo (`test_task.py`)
- Interação entre repositório e armazenamento (`test_repository.py`)

### Executando os testes:

```bash
pytest -v
```

---

## Instalação e Execução

1. Clone este repositório:
   ```bash
   git clone https://github.com/seu-usuario/task_manager.git
   cd task_manager
   ```

2. Instale as dependências:
   ```bash
   pip install -r requirements.txt
   ```

3. Execute os testes:
   ```bash
   pytest -v
   ```

---

## Requisitos

- Python 3.10+
- pytest==7.4.0  
- pytest-mock==3.11.1  

---

## Autores

Desenvolvido para fins acadêmicos no contexto de aprendizado de **testes unitários e design modular em Python**.

---

**Licença:** Uso educacional e acadêmico livre.
