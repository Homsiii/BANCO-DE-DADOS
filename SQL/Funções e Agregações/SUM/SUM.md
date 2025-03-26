A função `SUM` em SQL é uma função agregada que calcula a soma total de valores em uma coluna específica. É frequentemente usada para somar quantidades, como total de vendas, salários, ou qualquer outro valor numérico.

### Sintaxe

```
SELECT SUM(coluna) AS nome_da_soma
FROM tabela
WHERE condição;
```

### Exemplos de Uso

1. **Calcular a Soma Total**  
    Para calcular o total de idades de todos os usuários na tabela `usuarios`:
    
    ```
    SELECT SUM(idade) AS total_idades
    FROM usuarios;
    ```

2. **Calcular a Soma de Preços de Produtos**  
    Para somar todos os preços de produtos na tabela `produtos`:
    
    ```
    SELECT SUM(preco) AS total_precos
    FROM produtos;
    ```

3. **Calcular a Soma com Condição**  
    Para calcular a soma dos salários de empregados em um departamento específico:
    
    ```
    SELECT SUM(salario) AS total_salarios
    FROM empregados
    WHERE departamento_id = 1;
    ```

4. **Usar `SUM` com `GROUP BY`**  
    Para calcular o total de vendas por produto:
    
    ```
    SELECT produto_id, SUM(valor_venda) AS total_vendas
    FROM vendas
    GROUP BY produto_id;
    ```

### Considerações

- A função `SUM` ignora valores `NULL` ao calcular a soma.
- Pode ser combinada com outras funções agregadas e cláusulas como `GROUP BY` e `HAVING`.

### Conclusão

A função `SUM` é uma ferramenta poderosa em SQL para calcular totais, permitindo análises financeiras e sumarização de dados numéricos, facilitando a interpretação e a tomada de decisões baseadas em dados.

Compartilhar