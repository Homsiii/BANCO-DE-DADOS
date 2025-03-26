O `LEFT JOIN` (ou `LEFT OUTER JOIN`) é um tipo de junção que retorna todas as linhas da tabela à esquerda e as linhas correspondentes da tabela à direita. Se não houver correspondência, os resultados da tabela à direita serão preenchidos com `NULL`.

### Sintaxe

```
SELECT coluna1, coluna2
FROM tabela_a
LEFT JOIN tabela_b ON tabela_a.chave_primaria = tabela_b.chave_estrangeira;
```

### Exemplos de Uso

1. **Exemplo Básico**  
    Para listar todos os clientes e seus pedidos, incluindo clientes que não fizeram nenhum pedido:
    
    ```
    SELECT c.nome, p.id_pedido
    FROM clientes c
    LEFT JOIN pedidos p ON c.id_cliente = p.id_cliente;
    ```

2. **Com Condição Adicional**  
    Para filtrar a lista e mostrar apenas clientes que estão ativos:
    
    ```
    SELECT c.nome, p.id_pedido
    FROM clientes c
    LEFT JOIN pedidos p ON c.id_cliente = p.id_cliente
    WHERE c.status = 'ativo';
    ```

3. **Exemplo com Múltiplas Tabelas**  
    Para obter informações sobre clientes, pedidos e produtos, incluindo clientes que não têm pedidos:
    
    ```
    SELECT c.nome, p.id_pedido, pr.nome AS produto
    FROM clientes c
    LEFT JOIN pedidos p ON c.id_cliente = p.id_cliente
    LEFT JOIN produtos pr ON p.id_produto = pr.id_produto;
    ```

### Considerações

- O `LEFT JOIN` é útil quando você deseja obter todos os registros de uma tabela, mesmo que não haja correspondência na tabela relacionada.
- Os campos da tabela à direita que não têm correspondência serão exibidos como `NULL`.
- A ordem das tabelas na junção é importante; uma `LEFT JOIN` sempre retorna todas as linhas da tabela à esquerda.

### Conclusão

O `LEFT JOIN` é uma ferramenta poderosa para consultas SQL que permite a inclusão de todos os registros de uma tabela, mesmo quando não há correspondência na tabela relacionada. Isso é especialmente útil em análises de dados onde é importante visualizar todos os registros, independentemente de suas relações.