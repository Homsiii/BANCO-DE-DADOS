Os operadores de comparação em SQL são usados para comparar dois valores e retornar um resultado booleano (verdadeiro ou falso). Eles são fundamentais para filtrar dados em consultas.

### Principais Operadores de Comparação

1. **Igualdade (`=`)**
    
    - Compara se dois valores são iguais.
    - **Exemplo:**
        ```
        SELECT * FROM usuarios WHERE idade = 30;
        ```
    
2. **Diferença (`<>` ou `!=`)**
    
    - Compara se dois valores são diferentes.
    - **Exemplo:**
        ```
        SELECT * FROM usuarios WHERE cidade <> 'Rio de Janeiro';
        ```
    
3. **Maior que (`>`)**
    
    - Verifica se um valor é maior que outro.
    - **Exemplo:**
        ```
        SELECT * FROM produtos WHERE preco > 100;
        ```
    
4. **Menor que (`<`)**
    
    - Verifica se um valor é menor que outro.
    - **Exemplo:**
        ```
        SELECT * FROM produtos WHERE preco < 50;
        ```
    
5. **Maior ou igual a (`>=`)**
    
    - Verifica se um valor é maior ou igual a outro.
    - **Exemplo:**
        ```
        SELECT * FROM usuarios WHERE idade >= 18;
        ```
    
6. **Menor ou igual a (`<=`)**
    
    - Verifica se um valor é menor ou igual a outro.
    - **Exemplo:**
        ```
        SELECT * FROM produtos WHERE estoque <= 10;
        ```
    

### Combinação com `NOT`

Os operadores de comparação podem ser combinados com `NOT` para inverter as condições.

- **Exemplo:**  
    Para selecionar usuários cuja idade **não** é igual a 25:
    ```
    SELECT * FROM usuarios WHERE NOT idade = 25;
    ```
    

### Considerações

- Os operadores de comparação são frequentemente usados em cláusulas `WHERE` para filtrar resultados com base em critérios específicos.
- É importante considerar o tipo de dados ao usar operadores de comparação, pois comparações entre tipos diferentes podem gerar erros.

### Conclusão

Os operadores de comparação em SQL são essenciais para realizar filtragens precisas em consultas, permitindo que você compare valores e obtenha dados relevantes de acordo com critérios definidos.