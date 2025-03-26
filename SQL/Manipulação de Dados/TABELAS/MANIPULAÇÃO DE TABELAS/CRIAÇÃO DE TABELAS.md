A criação de tabelas é uma das operações fundamentais ao definir a estrutura de um banco de dados. Uma tabela é composta por linhas e colunas, onde cada coluna tem um tipo de dado específico.

### Sintaxe Básica

A sintaxe para criar uma tabela em SQL é a seguinte:

```
CREATE TABLE nome_da_tabela (
    coluna1 tipo_dado [opções],
    coluna2 tipo_dado [opções],
    ...
);
```

### Exemplos de Criação de Tabelas

1. **Tabela Simples de Clientes**
    ```
    CREATE TABLE clientes (
        id_cliente INT PRIMARY KEY,
        nome VARCHAR(100) NOT NULL,
        email VARCHAR(100) UNIQUE,
        data_nascimento DATE
    );
    ```

2. **Tabela de Produtos**
    ```
    CREATE TABLE produtos (
        id_produto INT PRIMARY KEY,
        nome VARCHAR(100) NOT NULL,
        preco DECIMAL(10, 2) NOT NULL,
        estoque INT DEFAULT 0
    );
    ```

3. **Tabela de Pedidos**
    ```
    CREATE TABLE pedidos (
        id_pedido INT PRIMARY KEY,
        id_cliente INT,
        data_pedido DATETIME DEFAULT CURRENT_TIMESTAMP,
        FOREIGN KEY (id_cliente) REFERENCES clientes(id_cliente)
    );
    ```

4. **Tabela de Funcionários**
    ```
    CREATE TABLE funcionarios (
        id_funcionario INT PRIMARY KEY,
        nome VARCHAR(100) NOT NULL,
        cargo VARCHAR(50),
        salario DECIMAL(10, 2) CHECK (salario > 0)
    );
    ```

### Tipos de Dados Comuns

- **INT**: Número inteiro.
- **VARCHAR(n)**: Cadeia de caracteres de até `n` caracteres.
- **DECIMAL(p, s)**: Número decimal com `p` dígitos no total e `s` dígitos após o ponto decimal.
- **DATE**: Data no formato `YYYY-MM-DD`.
- **DATETIME**: Data e hora.
- **BOOLEAN**: Valor verdadeiro/falso.

### Opções Comuns em Colunas

- **PRIMARY KEY**: Define a coluna como chave primária, que deve ser única e não nula.
- **NOT NULL**: Impede que a coluna aceite valores nulos.
- **UNIQUE**: Garante que todos os valores na coluna sejam únicos.
- **DEFAULT**: Define um valor padrão para a coluna, caso nenhum valor seja especificado.
- **CHECK**: Valida os dados com base em uma condição.

### Considerações

- **Relacionamentos**: Use chaves estrangeiras (`FOREIGN KEY`) para definir relacionamentos entre tabelas.
- **Normalização**: Considere a normalização para organizar os dados e evitar redundâncias.
- **Documentação**: Documente a estrutura das tabelas para facilitar a manutenção e compreensão do banco de dados.

### Conclusão

A criação de tabelas é um passo essencial na estruturação de um banco de dados. Compreender a sintaxe e as opções disponíveis permite que você construa uma base sólida para armazenar e gerenciar dados de forma eficaz.