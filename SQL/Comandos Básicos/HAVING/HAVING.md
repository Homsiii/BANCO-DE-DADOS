O `HAVING` é uma cláusula utilizada em SQL para filtrar resultados de grupos criados com a cláusula `GROUP BY`. Ele permite aplicar condições a agregações, sendo especialmente útil para restringir os resultados após a agregação de dados.

### Sintaxe

```
SELECT coluna1, AGG_FUNC(coluna2)
FROM tabela
GROUP BY coluna1
HAVING condição;
```

### Exemplo

Para encontrar categorias de produtos que têm uma média de preço superior a R$ 150:

```
SELECT categoria, AVG(preco) AS media_preco
FROM produtos
GROUP BY categoria
HAVING AVG(preco) > 150;
```

### Funcionamento

- O `HAVING` é aplicado após a agregação dos dados, permitindo filtrar os resultados com base nos valores agregados.
- Ele pode usar funções de agregação, como `SUM()`, `AVG()`, `COUNT()`, entre outras.

### Considerações

- Ao contrário da cláusula `WHERE`, que filtra linhas antes da agregação, o `HAVING` filtra grupos após a agregação.
- Você pode usar `HAVING` em conjunto com `GROUP BY` para realizar análises mais específicas.

### Conclusão

O comando `HAVING` é crucial para aplicar condições em resultados agregados em SQL, permitindo uma análise mais refinada e filtrada de dados agrupados.