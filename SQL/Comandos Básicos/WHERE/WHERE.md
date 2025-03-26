O comando `WHERE` é utilizado em SQL para filtrar registros com base em condições específicas. Ele é essencial para restringir os resultados de uma consulta, permitindo que você recupere apenas os dados que atendem a critérios determinados.

### Sintaxe

```
SELECT coluna1, coluna2
FROM tabela
WHERE condição;
```

### Exemplos de Uso

1. **Filtrar Registros Simples**  
    Para selecionar usuários com idade maior que 18:
    
    ```
    SELECT nome, idade
    FROM usuarios
    WHERE idade > 18;
    ```

2. **Filtrar com Igualdade**  
    Para selecionar produtos que têm um preço específico:
    
    ```
    SELECT nome, preco
    FROM produtos
    WHERE preco = 100;
    ```

3. **Filtrar com Múltiplas Condições usando `AND`**  
    Para selecionar usuários que têm mais de 18 anos e residem em "São Paulo":
    
    ```
    SELECT nome, idade, cidade
    FROM usuarios
    WHERE idade > 18 AND cidade = 'São Paulo';
    ```

4. **Filtrar com Múltiplas Condições usando `OR`**  
    Para selecionar produtos que são eletrônicos ou móveis:
    
    ```
    SELECT nome, categoria
    FROM produtos
    WHERE categoria = 'eletrônicos' OR categoria = 'móveis';
    ```

5. **Negar Condições com `NOT`**  
    Para selecionar usuários que não têm o status de "ativo":
    
    ```
    SELECT nome, status
    FROM usuarios
    WHERE NOT status = 'ativo';
    ```

6. **Utilizar Operadores de Comparação**  
    Para selecionar produtos que têm um preço inferior a R$ 50:
    
    ```
    SELECT nome, preco
    FROM produtos
    WHERE preco < 50;
    ```

7. **Usar `LIKE` para Busca de Padrões**  
    Para selecionar usuários cujo nome começa com "A":
    
    ```
    SELECT nome
    FROM usuarios
    WHERE nome LIKE 'A%';
    ```
### Considerações

- O comando `WHERE` é frequentemente usado em combinação com outros comandos SQL, como `SELECT`, `UPDATE`, e `DELETE`.
- O uso adequado de `WHERE` pode melhorar a performance da consulta, reduzindo a quantidade de dados processados.

### Conclusão

O comando `WHERE` é uma ferramenta crucial em SQL para filtrar resultados e refinar consultas, permitindo que você recupere apenas os registros que atendem a critérios específicos, otimizando assim a análise e a manipulação de dados.