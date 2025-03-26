O comando `ORDER BY` é utilizado em SQL para ordenar os resultados de uma consulta com base em uma ou mais colunas. Você pode especificar a ordem de classificação como ascendente (ASC) ou descendente (DESC).

### Sintaxe

```
SELECT coluna1, coluna2
FROM tabela
ORDER BY coluna1 [ASC|DESC], coluna2 [ASC|DESC];
```

### Exemplos de Uso

1. **Ordenar em Ordem Ascendente**  
    Para selecionar todos os usuários e ordená-los pela idade em ordem crescente:
    
    ```
    SELECT nome, idade
    FROM usuarios
    ORDER BY idade ASC;
    ```

2. **Ordenar em Ordem Descendente**  
    Para selecionar produtos e ordená-los pelo preço em ordem decrescente:
    
    ```
    SELECT nome, preco
    FROM produtos
    ORDER BY preco DESC;
    ```

3. **Ordenar por Múltiplas Colunas**  
    Para selecionar usuários e ordená-los primeiro pela cidade em ordem alfabética e, em seguida, pela idade em ordem crescente:
    
    ```
    SELECT nome, idade, cidade
    FROM usuarios
    ORDER BY cidade ASC, idade ASC;
    ```

4. **Ordenar com `NULLS`**  
    Para ordenar uma coluna onde os valores `NULL` aparecem no final da lista:
    
    ```
    SELECT nome, idade
    FROM usuarios
    ORDER BY idade ASC NULLS LAST;  -- A sintaxe pode variar dependendo do SGBD
    ```

### Considerações

- O comportamento padrão do `ORDER BY` é ordenar em ordem ascendente (`ASC`), então este modificador é opcional.
- O `ORDER BY` deve ser a última cláusula em uma consulta SQL, após `WHERE` e `GROUP BY`, se usados.

### Conclusão

O comando `ORDER BY` é uma ferramenta essencial em SQL para organizar os resultados de uma consulta, facilitando a análise e a visualização dos dados de maneira estruturada e compreensível.