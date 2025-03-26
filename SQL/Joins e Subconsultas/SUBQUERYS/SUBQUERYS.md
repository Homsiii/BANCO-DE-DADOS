Uma subquery, ou subconsulta, é uma consulta SQL aninhada dentro de outra consulta. Ela pode ser utilizada em várias partes de uma instrução SQL, como na cláusula `SELECT`, `FROM`, `WHERE`, ou `HAVING`. As subqueries são úteis para realizar operações complexas e podem retornar resultados que são utilizados em consultas principais.

### Tipos de Subqueries

1. **Subquery na Cláusula SELECT**  
    Retorna um valor que pode ser usado como parte da seleção dos dados.
    
    ```
    SELECT nome, (SELECT COUNT(*) FROM pedidos WHERE id_cliente = c.id_cliente) 
    AS total_pedidos
    FROM clientes c;
    ```

2. **Subquery na Cláusula WHERE**  
    Filtra os resultados da consulta principal com base em resultados de outra consulta.
    
    ```
    SELECT nome
    FROM clientes
    WHERE id_cliente IN (SELECT id_cliente FROM pedidos WHERE valor > 100);
    ```

3. **Subquery na Cláusula FROM**  
    Trata a subquery como uma tabela temporária que pode ser utilizada na consulta principal.
    
    ```
    SELECT c.nome, p.total_vendas
    FROM clientes c
    JOIN (SELECT id_cliente, SUM(valor) AS total_vendas FROM pedidos 
    GROUP BY id_cliente) p ON c.id_cliente = p.id_cliente;
    ```

4. **Subquery na Cláusula HAVING**  
    Filtra os resultados de um grupo baseado em uma subconsulta.
    
    ```
    SELECT id_cliente, COUNT(*) AS total_pedidos
    FROM pedidos
    GROUP BY id_cliente
    HAVING COUNT(*) > (SELECT AVG(total) FROM (SELECT COUNT(*) AS total 
    FROM pedidos 
    GROUP BY id_cliente) AS sub);
    ```

### Considerações

- **Performance**: Subqueries podem impactar o desempenho, especialmente se a subconsulta retornar um grande número de registros ou for executada várias vezes.
- **Correlated Subqueries**: Uma subquery que se refere a colunas da consulta externa é chamada de "correlated subquery". Ela é executada uma vez para cada linha processada pela consulta externa.
    ```
    SELECT nome
    FROM clientes c
    WHERE EXISTS (SELECT 1 FROM pedidos p WHERE p.id_cliente = c.id_cliente 
    AND p.valor > 100);
    ```


### Conclusão

As subqueries são uma ferramenta poderosa em SQL que permitem realizar consultas complexas de maneira estruturada. Elas facilitam a análise de dados ao permitir que você aninhe consultas, criando relacionamentos dinâmicos e filtrando informações de maneira eficiente.