O comando `AVG` é uma função agregada em SQL que calcula a média aritmética de valores em uma coluna específica. Ele é útil para resumir dados e obter insights de conjuntos numéricos.

### Sintaxe

```
SELECT AVG(coluna) AS nome_da_media
FROM tabela
WHERE condição;
```

### Exemplo de Uso

1. **Calcular a Média Simples**  
    Para calcular a média das idades de todos os usuários na tabela `usuarios`:
    
    ```
    SELECT AVG(idade) AS media_idade
    FROM usuarios;
    ```

2. **Calcular a Média com Condição**  
    Para calcular a média dos preços de produtos que estão em estoque:
    
    ```
    SELECT AVG(preco) AS media_preco
    FROM produtos
    WHERE em_estoque = 'sim';
    ```

3. **Calcular a Média de Múltiplas Colunas com `GROUP BY`**  
    Para calcular a média das idades dos usuários agrupados por cidade:
    
    ```
    SELECT cidade, AVG(idade) AS media_idade
    FROM usuarios
    GROUP BY cidade;
    ```

### Considerações

- A função `AVG` ignora valores `NULL` na coluna ao calcular a média.
- É importante usar `GROUP BY` quando você deseja calcular a média para diferentes grupos dentro de um conjunto de dados.

### Conclusão

A função `AVG` é uma ferramenta poderosa em SQL para calcular médias, permitindo que você resuma e analise dados numéricos de forma eficaz, facilitando a interpretação e a tomada de decisões baseadas em dados.