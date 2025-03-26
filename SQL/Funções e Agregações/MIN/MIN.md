A função `MIN` em SQL é uma função agregada que retorna o menor valor de uma coluna específica. É útil para identificar o valor mínimo em um conjunto de dados, como a menor idade, o preço mais baixo, etc.

### Sintaxe

```
SELECT MIN(coluna) AS nome_do_minimo
FROM tabela
WHERE condição;
```

### Exemplos de Uso

1. **Encontrar o Valor Mínimo**  
    Para encontrar a idade mínima de todos os usuários na tabela `usuarios`:
    
    ```
    SELECT MIN(idade) AS idade_minima
    FROM usuarios;
    ```

2. **Encontrar o Preço Mínimo de Produtos**  
    Para encontrar o preço mais baixo entre todos os produtos:
    
    ```
    SELECT MIN(preco) AS preco_minimo
    FROM produtos;
    ```

3. **Encontrar o Mínimo com Condição**  
    Para encontrar a menor idade entre os usuários que são ativos:
    
    ```
    SELECT MIN(idade) AS idade_minima
    FROM usuarios
    WHERE status = 'ativo';
    ```

4. **Usar `MIN` com `GROUP BY`**  
    Para encontrar a idade mínima de usuários agrupados por cidade:
    
    ```
    SELECT cidade, MIN(idade) AS idade_minima
    FROM usuarios
    GROUP BY cidade;
    ```

### Considerações

- A função `MIN` ignora valores `NULL` ao calcular o mínimo.
- Pode ser combinada com outras funções agregadas e cláusulas como `GROUP BY` e `HAVING`.

### Conclusão

A função `MIN` é uma ferramenta importante em SQL para identificar o menor valor em um conjunto de dados, permitindo análises detalhadas e insights sobre as informações armazenadas nas tabelas.