# 🛒 Sistema de Gerenciamento de Vendas, Estoque e Cadastro

Este projeto em Python simula um sistema de gerenciamento de produtos, estoque, vendas, fornecedores, clientes e funcionários. Os dados são armazenados em arquivos `.txt` para fins de persistência, utilizando o padrão DAO (Data Access Object).

---

## 📁 Estrutura do Projeto

```
📂 projeto-gerenciamento
│
├── Models.py         # Classes principais do sistema (modelo)
├── Dao.py            # Classes responsáveis por salvar e ler dados (persistência)
├── categoria.txt     # Armazena categorias
├── venda.txt         # Armazena registros de vendas
├── estoque.txt       # Armazena produtos em estoque
├── fornecedores.txt  # Armazena fornecedores
├── clientes.txt      # Armazena clientes
├── funcionarios.txt  # Armazena funcionários
└── README.md         # Documentação do projeto
```

---

## 🧠 Tecnologias Utilizadas

- Python 3.x
- Programação Orientada a Objetos (POO)
- Manipulação de arquivos `.txt`
- Padrão DAO para persistência de dados

---

## 📌 Classes Modeladas

### 📦 Categoria
```python
Categoria(nome: str)
```

### 📦 Produtos
```python
Produtos(nome: str, preco: float, categoria: str)
```

### 📦 Estoque
```python
Estoque(produto: Produtos, quantidade: int)
```

### 📦 Venda
```python
Venda(itensVendido: Produtos, vendedor: str, comprador: str, quantidadeVendida: int, data: str)
```

### 📦 Fornecedor
```python
Fornecedor(nome: str, cnpj: str, telefone: str, categoria: str)
```

### 📦 Pessoa (classe base)

### 📦 Funcionario (herda de Pessoa)
```python
Funcionario(clt: str, nome: str, telefone: str, cpf: str, email: str, endereco: str)
```

---

## 💾 Classes DAO

Cada classe DAO é responsável por salvar e ler informações em arquivos `.txt`.

- `DaoCategoria`
- `DaoVenda`
- `DaoEstoque`
- `DaoFornecedor`
- `DaoPessoa`
- `DaoFuncionario`

---

## 🛠️ Exemplos de Uso

### ✅ Salvar um produto no estoque:

```python
from Models import *
from Dao import DaoEstoque

cat = Categoria("Eletrônicos")
prod = Produtos("Fone de Ouvido", 99.90, cat.categoria)
DaoEstoque.salvar(prod, 10)
```

### ✅ Ler produtos em estoque:

```python
estoque = DaoEstoque.ler()
for item in estoque:
    print(item.produto.nome, item.quantidade)
```

---

## ⚙️ Melhorias Futuras

- [ ] Utilizar banco de dados relacional (ex: SQLite, MySQL)
- [ ] Criar interface gráfica com Tkinter ou web com Flask
- [ ] Implementar autenticação de funcionários
- [ ] Validar dados de entrada
- [ ] Adicionar testes automatizados

---

## 🚀 Como Executar o Projeto

1. Clone o repositório:
```bash
git clone https://github.com/seu-usuario/nome-do-repositorio.git
cd nome-do-repositorio
```

2. Execute o projeto:
```bash
python nome_do_arquivo_principal.py
```
