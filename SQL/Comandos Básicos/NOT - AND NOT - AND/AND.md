O comando `AND` é uma cláusula lógica utilizada em SQL para combinar duas ou mais condições em uma consulta. Ele permite que você refine os resultados, retornando apenas aqueles registros que atendem a todas as condições especificadas.

### Sintaxe

```
SELECT coluna1, coluna2
FROM tabela
WHERE condição1 AND condição2;
```

### Exemplo

Para selecionar usuários que têm mais de 18 anos e residem em "São Paulo":

```
SELECT nome, idade, cidade
FROM usuarios
WHERE idade > 18 AND cidade = 'São Paulo';
```

### Funcionamento

- O `AND` assegura que ambas as condições sejam verdadeiras para que um registro seja incluído no resultado.
- Você pode combinar quantas condições quiser usando `AND`.

### Exemplo com Múltiplas Condições

Para selecionar produtos que estão disponíveis e têm um preço inferior a R$ 100:

```
SELECT nome, preco, disponibilidade
FROM produtos
WHERE disponibilidade = 'sim' AND preco < 100;
```

### Considerações

- O uso de `AND` pode resultar em um número menor de registros retornados, pois todas as condições devem ser atendidas.
- Você pode combinar `AND` com outras cláusulas lógicas, como `OR`, para criar condições mais complexas.

### Conclusão

O comando `AND` é uma ferramenta essencial em SQL para combinar condições, permitindo consultas mais específicas e refinadas, resultando em um controle mais preciso sobre os dados retornados.