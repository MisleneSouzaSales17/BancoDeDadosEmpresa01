# Banco de Dados EmpresaDB

Este repositório contém um script SQL para criação de um banco de dados chamado **EmpresaDB**, incluindo tabelas, atributos e triggers para registrar ações realizadas na tabela de funcionários.

## 📂 Estrutura do Projeto
- **empresa.sql** → Script principal com criação do banco, tabelas e triggers.
- **README.md** → Documento explicativo do projeto.

---

## 🗄️ Banco de Dados e Tabelas

### 1. Funcionarios
Armazena informações sobre os colaboradores da empresa.
- `id_funcionario` (INT, PK, auto incremento)
- `nome` (VARCHAR)
- `cargo` (VARCHAR)
- `salario` (DECIMAL)
- `data_admissao` (DATE)

### 2. Departamentos
Armazena informações sobre os departamentos da empresa.
- `id_departamento` (INT, PK, auto incremento)
- `nome_departamento` (VARCHAR)
- `localizacao` (VARCHAR)

### 3. Log_Acoes
Registra todas as ações realizadas via triggers.
- `id_log` (INT, PK, auto incremento)
- `acao` (VARCHAR)
- `tabela_afetada` (VARCHAR)
- `data_hora` (TIMESTAMP)
- `detalhes` (TEXT)

---

## ⚡ Triggers Implementados

- **`trg_insert_funcionario`** → Registra inserções na tabela `Funcionarios`.
- **`trg_update_funcionario`** → Registra atualizações na tabela `Funcionarios`.
- **`trg_delete_funcionario`** → Registra exclusões na tabela `Funcionarios`.

---

## 🧪 Testes

O script inclui exemplos de uso:

```sql
-- Inserir funcionário
INSERT INTO Funcionarios (nome, cargo, salario, data_admissao)
VALUES ('Maria Silva', 'Analista de Dados', 4500.00, '2025-12-04');

-- Atualizar funcionário
UPDATE Funcionarios
SET salario = 5000.00
WHERE nome = 'Maria Silva';

-- Deletar funcionário
DELETE FROM Funcionarios
WHERE nome = 'Maria Silva';

-- Consultar log
SELECT * FROM Log_Acoes;
