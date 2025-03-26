O comando `COUNT` é uma função agregada em SQL que conta o número de registros em uma coluna ou em um conjunto de resultados. É útil para obter estatísticas sobre os dados e entender a quantidade de entradas em uma tabela.

### Sintaxe

```
SELECT COUNT(coluna) AS nome_da_contagem
FROM tabela
WHERE condição;
```

### Exemplos de Uso

1. **Contar Todos os Registros**  
    Para contar o número total de usuários na tabela `usuarios`:
    
    ```
    SELECT COUNT(*) AS total_usuarios
    FROM usuarios;
    ```

2. **Contar Registros em uma Coluna Específica**  
    Para contar quantos usuários têm uma idade registrada:
    
    ```
    SELECT COUNT(idade) AS total_idades
    FROM usuarios;
    ```

3. **Contar com Condição**  
    Para contar quantos produtos estão em estoque:
    
    ```
    SELECT COUNT(*) AS total_em_estoque
    FROM produtos
    WHERE em_estoque = 'sim';
    ```

4. **Contar com `GROUP BY`**  
    Para contar o número de usuários em cada cidade:
    
    ```
    SELECT cidade, COUNT(*) AS total_usuarios
    FROM usuarios
    GROUP BY cidade;
    ```

5. **Contar Valores Distintos**  
    Para contar quantas cidades diferentes estão registradas na tabela `usuarios`:
    
    ```
    SELECT COUNT(DISTINCT cidade) AS total_cidades
    FROM usuarios;
    ```

### Considerações

- A função `COUNT` pode contar todos os registros (`COUNT(*)`) ou apenas aqueles que não são `NULL` em uma coluna específica (`COUNT(coluna)`).
- Usar `COUNT(DISTINCT coluna)` permite contar apenas valores únicos em uma coluna.

### Conclusão

A função `COUNT` é uma ferramenta essencial em SQL para realizar contagens de registros, permitindo que você obtenha insights sobre a quantidade de dados em suas tabelas, facilitando a análise e a interpretação de informações.