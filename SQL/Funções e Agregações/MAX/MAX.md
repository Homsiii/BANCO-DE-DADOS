A função `MAX` em SQL é uma função agregada que retorna o maior valor de uma coluna específica. É frequentemente utilizada para identificar o valor máximo em um conjunto de dados, como o preço mais alto, a maior idade, etc.

### Sintaxe

```
SELECT MAX(coluna) AS nome_do_maximo
FROM tabela
WHERE condição;
```

### Exemplos de Uso

1. **Encontrar o Valor Máximo**  
    Para encontrar a idade máxima de todos os usuários na tabela `usuarios`:
    
    ```
    SELECT MAX(idade) AS idade_maxima
    FROM usuarios;
    ```

2. **Encontrar o Preço Máximo de Produtos**  
    Para encontrar o preço mais alto entre todos os produtos:
    
    ```
    SELECT MAX(preco) AS preco_maximo
    FROM produtos;
    ```

3. **Encontrar o Máximo com Condição**  
    Para encontrar o maior salário entre os empregados que trabalham em um departamento específico:
    
    ```
    SELECT MAX(salario) AS salario_maximo
    FROM empregados
    WHERE departamento_id = 1;
    ```

4. **Usar `MAX` com `GROUP BY`**  
    Para encontrar a idade máxima de usuários agrupados por cidade:
    
    ```
    SELECT cidade, MAX(idade) AS idade_maxima
    FROM usuarios
    GROUP BY cidade;
    ```

### Considerações

- A função `MAX` ignora valores `NULL` ao calcular o máximo.
- Pode ser combinada com outras funções agregadas e cláusulas como `GROUP BY` e `HAVING`.

### Conclusão

A função `MAX` é uma ferramenta valiosa em SQL para identificar o maior valor em um conjunto de dados, permitindo análises mais profundas e insights sobre as informações armazenadas nas tabelas.