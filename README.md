# Projeto de Modelagem de Dados - Biblioteca do Colégio Sol Nascente

Este projeto é dedicado à modelagem de dados da biblioteca do **Colégio Sol Nascente**. O objetivo é criar uma estrutura de banco de dados que possa gerenciar eficientemente as operações da biblioteca, incluindo o registro de livros, empréstimos, devoluções e a gestão de usuários (alunos e professores).

## Estrutura do Projeto

A estrutura do projeto é organizada da seguinte maneira:

```
modelagem-biblioteca-colegio-sol-nascente/
│
├── assets/                        # Pasta para armazenar recursos estáticos
│   └── imagens/                   # Subpasta para imagens do site
│       ├── logo.png               # Logo da Escola Nova
│       ├── modelo_logico.png      # Imagem do modelo lógico
│       └── modelo_conceitual.png  # Imagem do modelo conceitual
│
├── docs/                          # Pasta para documentação
│   ├── modelos_logico.drawio      # Arquivo do modelo lógico
│   └── modelo_conceitual.drawio   # Arquivo do modelo conceitual
│
├── js/                            # Pasta para arquivos JavaScript
│   └── scripts.js                 # Scripts do site
│
├── styles/                        # Pasta para arquivos CSS
│   ├── reset.css                  # Reset CSS
│   └── styles.css                 # Estilos do site
│
├── index.html                     # Página inicial do site
└── README.md                      # Documentação do projeto
```

## Briefing

# Briefing para Modelagem de Dados - Biblioteca do Colégio Sol Nascente

## Objetivo

Desenvolver uma modelagem de dados que permita gerenciar o empréstimo de livros na biblioteca do Colégio Sol Nascente. A estrutura deve ser flexível para suportar futuros expansões e integrações.

### Tabelas Principais

1. **Editoras**
   - **Descrição**: Contém informações sobre as editoras dos livros.
   - **Campos**:
     - `editora_id` (PK): Identificador único da editora.
     - `nome`: Nome da editora.
     - `endereco`: Endereço da editora.
     - `telefone`: Telefone da editora.

2. **Livros**
   - **Descrição**: Contém informações sobre os livros disponíveis para empréstimo.
   - **Campos**:
     - `ISBN` (PK): Identificador único do livro.
     - `titulo`: Título do livro.
     - `ano_publicacao`: Ano de publicação.
     - `editora_id` (FK): Referência à tabela Editoras.
     - `genero_id` (FK): Referência à tabela Gêneros.
     - `quantidade`: Quantidade disponível para empréstimo.

3. **Gêneros**
   - **Descrição**: Classifica os livros em diferentes gêneros.
   - **Campos**:
     - `genero_id` (PK): Identificador único do gênero.
     - `nome`: Nome do gênero.

4. **Autores**
   - **Descrição**: Contém informações sobre os autores dos livros.
   - **Campos**:
     - `autor_id` (PK): Identificador único do autor.
     - `nome`: Nome do autor.
     - `biografia`: Breve biografia do autor.

5. **Livros_Autor**
   - **Descrição**: Relaciona os livros aos seus autores.
   - **Campos**:
     - `ISBN` (FK): Referência à tabela Livros.
     - `autor_id` (FK): Referência à tabela Autores.
   - **Cardinalidade**: Um livro pode ter vários autores (N) e um autor pode ter escrito vários livros (N).

6. **Clientes**
   - **Descrição**: Contém informações sobre os clientes (alunos) que podem emprestar livros.
   - **Campos**:
     - `cliente_id` (PK): Identificador único do cliente.
     - `nome`: Nome do cliente.
     - `data_nascimento`: Data de nascimento.
     - `endereco`: Endereço do cliente.
     - `telefone`: Telefone do cliente.

7. **Cliente_Livros**
   - **Descrição**: Registra os empréstimos realizados pelos clientes.
   - **Campos**:
     - `cliente_id` (FK): Referência à tabela Clientes.
     - `ISBN` (FK): Referência à tabela Livros.
     - `data_emp_préstimo`: Data do empréstimo.
     - `data_devolucao`: Data prevista para devolução.
   - **Cardinalidade**: Um cliente pode emprestar vários livros (N) e um livro pode ser emprestado por vários clientes (N).

### Considerações Finais

- O sistema deve ser capaz de lidar com a inclusão, exclusão e atualização de registros nas tabelas mencionadas.
- É possível adicionar tabelas adicionais, como `Multimídia` para registrar outros tipos de materiais disponíveis na biblioteca, ou `Reservas` para gerenciar a reserva de livros que não estão disponíveis no momento.

### Próximos Passos

1. Validar o modelo com as partes interessadas.
2. Implementar o esquema no banco de dados.
3. Criar scripts de teste para assegurar que a modelagem atende às necessidades.
  
</br>

---

**Colégio Sol Nascente** - Despertando Potenciais e Inspirando Saberes!
