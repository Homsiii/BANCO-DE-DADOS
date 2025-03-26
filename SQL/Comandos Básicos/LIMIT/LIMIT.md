O comando `LIMIT` é utilizado em SQL para restringir o número de registros retornados por uma consulta. É especialmente útil quando você deseja controlar a quantidade de dados exibidos ou paginar resultados.

### Sintaxe

```
SELECT coluna1, coluna2
FROM tabela
LIMIT número;
```

### Exemplo

Para selecionar os 5 primeiros usuários da tabela `usuarios`:

```
SELECT nome, idade
FROM usuarios
LIMIT 5;
```

### Funcionamento

- O `LIMIT` especifica quantos registros você deseja que a consulta retorne.
- Ele é frequentemente utilizado em conjunto com a cláusula `ORDER BY` para retornar os registros mais relevantes ou os primeiros em uma ordem específica.

### Exemplo com `ORDER BY`

Para selecionar os 3 produtos mais caros da tabela `produtos`:

```
SELECT nome, preco
FROM produtos
ORDER BY preco DESC
LIMIT 3;
```

### Considerações

- O `LIMIT` é suportado em muitos sistemas de gerenciamento de banco de dados, como MySQL e PostgreSQL, mas pode ter uma sintaxe diferente em outros, como SQL Server, onde é usado `TOP`.
- É uma prática comum usar `LIMIT` em conjunto com mecanismos de paginação para exibir resultados em partes.

### Conclusão

O comando `LIMIT` é uma ferramenta útil em SQL para controlar o número de registros retornados em consultas, facilitando a visualização de dados e a implementação de paginação em aplicações.