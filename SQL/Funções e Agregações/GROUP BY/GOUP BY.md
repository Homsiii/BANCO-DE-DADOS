O comando `GROUP BY` é utilizado em SQL para agrupar registros que possuem valores idênticos em uma ou mais colunas. Ele é frequentemente utilizado em conjunto com funções agregadas, como `COUNT`, `SUM`, `AVG`, etc., permitindo a análise de dados agrupados de forma eficiente.

### Sintaxe

```
SELECT coluna1, função_agregada(coluna2) AS nome_da_agregação
FROM tabela
WHERE condição
GROUP BY coluna1;
```

### Exemplos de Uso

1. **Agrupar por uma Coluna**  
    Para contar o número de usuários em cada cidade:
    
    ```
    SELECT cidade, COUNT(*) AS total_usuarios
    FROM usuarios
    GROUP BY cidade;
    ```

2. **Agrupar por Múltiplas Colunas**  
    Para calcular a média de idade de usuários agrupados por cidade e status:
    
    ```
    SELECT cidade, status, AVG(idade) AS media_idade
    FROM usuarios
    GROUP BY cidade, status;
    ```

3. **Usar `HAVING` com `GROUP BY`**  
    Para filtrar grupos após a agregação, como contar cidades com mais de 10 usuários:
    
    ```
    SELECT cidade, COUNT(*) AS total_usuarios
    FROM usuarios
    GROUP BY cidade
    HAVING COUNT(*) > 10;
    ```

4. **Agrupar e Somar Valores**  
    Para calcular o total de vendas por produto:
    
    ```
    SELECT produto_id, SUM(preco) AS total_vendas
    FROM vendas
    GROUP BY produto_id;
    ```

### Considerações

- O comando `GROUP BY` deve incluir todas as colunas da cláusula `SELECT` que não são parte de uma função agregada.
- Ao usar `GROUP BY`, você pode combinar com `HAVING` para filtrar resultados agregados, o que não é possível com a cláusula `WHERE`.

### Conclusão

O comando `GROUP BY` é uma ferramenta poderosa em SQL para agrupar e resumir dados, permitindo que você realize análises detalhadas e obtenha insights significativos a partir de conjuntos de dados complexos.