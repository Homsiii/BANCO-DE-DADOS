Os operadores matemáticos em SQL são usados para realizar cálculos aritméticos em valores numéricos. Eles são essenciais para manipular dados e realizar operações em consultas.

### Principais Operadores Matemáticos

1. **Adição (`+`)**
    
    - Soma dois valores.
    - **Exemplo:**
        ```
        SELECT preco, quantidade, (preco * quantidade) AS total
        FROM produtos;
        ```
    
2. **Subtração (`-`)**
    
    - Subtrai um valor de outro.
    - **Exemplo:**
        ```
        SELECT nome, preco, (preco - desconto) AS preco_final
        FROM produtos;
        ```
    
3. **Multiplicação (`*`)**
    
    - Multiplica dois valores.
    - **Exemplo:**
        ```
        SELECT nome, quantidade, preco * quantidade AS total_venda
        FROM vendas;
        ```
    
4. **Divisão (`/`)**
    
    - Divide um valor por outro.
    - **Exemplo:**
        ```
        SELECT nome, valor_total, quantidade, (valor_total / quantidade) 
        AS preco_unitario
        FROM vendas;
        ```
5. **Módulo (`%`)**
    
    - Retorna o resto da divisão de um número por outro.
    - **Exemplo:**
        ```
        SELECT idade, (idade % 2) AS par_impar
        FROM usuarios;
        ```
    

### Utilizando em Consultas

Os operadores matemáticos podem ser usados em expressões dentro da cláusula `SELECT`, bem como em condições na cláusula `WHERE`.

- **Exemplo em `WHERE`:**  
    Para selecionar produtos que têm um valor total acima de R$ 500:

    ```
    SELECT nome, preco, quantidade
    FROM produtos
    WHERE (preco * quantidade) > 500;
    ```

### Considerações

- Ao realizar operações matemáticas, é importante considerar o tipo de dados para evitar erros, especialmente com divisões por zero.
- Os operadores matemáticos podem ser combinados com funções de agregação, como `SUM()`, `AVG()`, etc.

### Conclusão

Os operadores matemáticos em SQL são ferramentas fundamentais para realizar cálculos e manipular dados numéricos em consultas, permitindo que você obtenha informações derivadas e insights valiosos a partir dos dados armazenados.