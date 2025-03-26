O `INNER JOIN` é um tipo de junção que retorna apenas as linhas que têm correspondência em ambas as tabelas envolvidas na consulta. Isso significa que, se uma linha de uma tabela não encontrar correspondência na outra, ela será excluída do resultado.

### Sintaxe

```
SELECT coluna1, coluna2
FROM tabela_a
INNER JOIN tabela_b ON tabela_a.chave_primaria = tabela_b.chave_estrangeira;
```

### Exemplos de Uso

1. **Exemplo Básico**  
    Para obter detalhes de pedidos junto com os nomes dos clientes:
    
    ```
    SELECT p.id_pedido, c.nome
    FROM pedidos p
    INNER JOIN clientes c ON p.id_cliente = c.id_cliente;
    ```

2. **Com Mais de Duas Tabelas**  
    Para obter informações de pedidos, incluindo detalhes de produtos e clientes:
    
    ```
    SELECT p.id_pedido, c.nome AS cliente, pr.nome AS produto
    FROM pedidos p
    INNER JOIN clientes c ON p.id_cliente = c.id_cliente
    INNER JOIN produtos pr ON p.id_produto = pr.id_produto;
    ```

3. **Com Condição Adicional**  
    Para filtrar os resultados e mostrar apenas pedidos feitos após uma certa data:
    
    ```
    SELECT p.id_pedido, c.nome
    FROM pedidos p
    INNER JOIN clientes c ON p.id_cliente = c.id_cliente
    WHERE p.data_pedido > '2023-01-01';
    ```

### Considerações

- O `INNER JOIN` é o tipo de junção mais comum e é frequentemente utilizado para combinar tabelas que têm relações diretas.
- Se uma linha não tiver correspondência em ambas as tabelas, ela será omitida do resultado.
- O desempenho de um `INNER JOIN` pode ser otimizado com o uso de índices nas colunas de junção.

### Conclusão

O `INNER JOIN` é uma ferramenta essencial em SQL para combinar dados de múltiplas tabelas, permitindo consultas que extraem informações relacionais de maneira eficiente e clara. É amplamente utilizado em aplicações de banco de dados para construir relatórios e análises a partir de conjuntos de dados inter-relacionados.