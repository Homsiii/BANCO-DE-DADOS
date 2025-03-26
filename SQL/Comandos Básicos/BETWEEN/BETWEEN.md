O `BETWEEN` é uma cláusula utilizada para filtrar resultados dentro de um intervalo específico de valores. É frequentemente usado em consultas para definir um limite inferior e um limite superior.

### Sintaxe

```
SELECT coluna1, coluna2
FROM tabela
WHERE coluna BETWEEN valor_inferior AND valor_superior;
```

### Exemplo

Para encontrar produtos com preços entre R$ 100 e R$ 200:

```
SELECT nome
FROM produtos
WHERE preco BETWEEN 100 AND 200;
```

### Funcionamento

- O comando retorna todos os registros em que o valor da coluna `preco` está dentro do intervalo especificado, incluindo os limites.

### Considerações

- O `BETWEEN` é inclusivo, ou seja, inclui os valores do limite inferior e superior.
- Pode ser usado com números, datas e strings.

### Conclusão

O `BETWEEN` é uma maneira eficaz de filtrar registros em SQL dentro de um intervalo específico, facilitando a consulta de dados que atendem a critérios de faixa.