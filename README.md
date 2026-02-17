# 🎓 Sistema de Gestão de Aulas

> Projeto Final — Algoritmos e Estruturas de Dados | Python 3

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)
![Status](https://img.shields.io/badge/Status-Concluído-brightgreen)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

---

## 📋 Índice

- [Sobre o Projeto](#sobre-o-projeto)
- [Funcionalidades](#funcionalidades)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Como Executar](#como-executar)
- [Algoritmos Implementados](#algoritmos-implementados)
- [Base de Dados](#base-de-dados)
- [Documentação](#documentação)
- [Autores](#autores)

---

## 📌 Sobre o Projeto

Sistema de gestão de presenças em ambiente académico, desenvolvido em Python como projeto final da unidade curricular de **Algoritmos e Estruturas de Dados**.

O sistema permite que **Professores** controlem sessões de aula e que **Alunos** registem a sua presença digitalmente. As presenças são ordenadas com dois algoritmos distintos — **Bubble Sort** e **Tree Sort via BST** — cujo desempenho pode ser comparado através de um módulo de testes de stress.

---

## ✅ Funcionalidades

### 👨‍🏫 Professor
- Abrir e fechar aulas com cronómetro automático
- Visualizar lista de presenças ordenada por ID
- Exportar relatório em **CSV** e **PDF**
- Executar testes de stress comparando algoritmos de ordenação

### 👨‍🎓 Aluno
- Autenticação com número e password
- Marcar presença numa aula ativa
- Proteção contra registo duplicado

### ⚙️ Sistema
- Persistência de dados em ficheiro **JSON**
- Validação de tipos e tratamento de erros em todos os inputs
- Dois algoritmos de ordenação com análise de complexidade

---

## 📁 Estrutura do Projeto

```
ProjetoFinalAED/
│
├── main.py               # Ponto de entrada — loop principal e autenticação
├── classAluno.py         # Classe Aluno com validação e menu
├── classProfessor.py     # Classe Professor com menus e exportação
├── algoritmos.py         # Bubble Sort + Árvore Binária de Busca (BST)
├── leitorDados.py        # Leitura e escrita do ficheiro JSON
├── testeStress.py        # Gerador de dados e comparação de algoritmos
├── database.json         # Base de dados local (alunos e professores)
│
└── docs/                 # Documentação do projeto
    ├── Documentacao_Diagramas_UML.docx
    ├── RegrasCriterios.docx
    └── FluxoAtividades_Aluno.docx
```

---

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Uso |
|---|---|
| Python 3 | Linguagem principal |
| `json` | Persistência de dados |
| `csv` | Exportação de relatórios |
| `time` | Cronómetro da aula |
| `random` | Geração de dados para stress test |
| `fpdf2` *(opcional)* | Exportação de relatórios PDF |

---

## 🚀 Como Executar

### Pré-requisitos

- Python 3.x instalado → [python.org](https://www.python.org/downloads/)
- *(Opcional)* `fpdf2` para exportação PDF:

```bash
pip install fpdf2
```

### Executar o programa

```bash
# Clonar o repositório
git clone https://github.com/teu-utilizador/nome-do-repo.git

# Entrar na pasta do projeto
cd nome-do-repo/ProjetoFinalAED

# Correr o programa
python main.py
```

### Credenciais de teste (database.json)

| Tipo | Identificador | Password |
|---|---|---|
| Aluno | `1001` | `123` |
| Aluno | `1002` | `456` |
| Professor | `10` | `admin` |

---

## 🧮 Algoritmos Implementados

### Bubble Sort
Algoritmo de ordenação por comparação de pares adjacentes.

| Caso | Complexidade |
|---|---|
| Melhor | O(n) — com early exit |
| Médio | O(n²) |
| Pior | O(n²) |

> Utilizado no fecho de aula para ordenar a lista de presenças por ID.

---

### Tree Sort via BST (Binary Search Tree)
Inserção em árvore binária de busca seguida de percurso in-order.

| Operação | Complexidade |
|---|---|
| Inserção (média) | O(log n) |
| Inserção (pior caso) | O(n) |
| Percurso in-order | O(n) |
| **Total** | **O(n log n)** médio |

> Utilizado no módulo de testes de stress para comparação de desempenho.

---

### Comparação de Desempenho

Para testar e comparar os dois algoritmos, acede ao **Painel do Professor → opção 3** e introduz o número de registos a gerar. O sistema mede e exibe o tempo de execução de cada algoritmo.

```
--- 🏁 CORRIDA DE ALGORITMOS: 5000 Alunos ---
🐢 Bubble Sort [O(n²)]:    2.34521 segundos
🐇 Tree Sort  [O(n log n)]: 0.01823 segundos
----------------------------------------
✅ Tree Sort foi 128.6x mais rápido que Bubble Sort.
```

---

## 🗄️ Base de Dados

O ficheiro `database.json` serve como base de dados local. É lido no arranque do programa e atualizado automaticamente ao sair.

```json
{
    "alunos": [
        {
            "nome": "Rodrigo Rodrigues",
            "idade": 20,
            "numero": 1001,
            "password": "123"
        }
    ],
    "professores": [
        {
            "nome": "Prof. Noronha",
            "senha": "admin",
            "id": 10
        }
    ]
}
```

---

## 📚 Documentação

A pasta `docs/` contém a documentação técnica completa do projeto:

| Documento | Conteúdo |
|---|---|
| `Documentacao_Diagramas_UML.docx` | Diagrama de Casos de Uso, Classes, DFD e Atividades |
| `RegrasCriterios.docx` | 29 Regras de Negócio + 30 Critérios de Aceitação |
| `FluxoAtividades_Aluno.docx` | Fluxo de atividades detalhado do ator Aluno |

---

## 👤 Autores

**[O teu nome]**
- GitHub: [@teu-utilizador](https://github.com/teu-utilizador)

---

*Projeto académico desenvolvido para a unidade curricular de Algoritmos e Estruturas de Dados.*
