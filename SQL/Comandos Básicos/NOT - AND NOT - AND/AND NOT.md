O comando `AND NOT` é uma cláusula lógica utilizada em SQL para combinar condições, onde uma condição deve ser verdadeira e outra deve ser falsa. Isso permite filtrar registros de forma mais específica, excluindo aqueles que não atendem a determinadas condições.

### Sintaxe

```
SELECT coluna1, coluna2
FROM tabela
WHERE condição1 AND NOT condição2;
```

### Exemplo

Para selecionar usuários que têm mais de 18 anos e **não** residem em "São Paulo":

```
SELECT nome, idade, cidade
FROM usuarios
WHERE idade > 18 AND NOT cidade = 'São Paulo';
```

### Funcionamento

- O `AND NOT` combina duas condições, onde a primeira deve ser verdadeira e a segunda deve ser falsa para que o registro seja incluído no resultado.
- É útil para criar filtros mais complexos em consultas.

### Exemplo com Múltiplas Condições

Para selecionar produtos que estão disponíveis e têm um preço inferior a R$ 100, mas **não** pertencem à categoria "eletrônicos":

```
SELECT nome, preco, disponibilidade, categoria
FROM produtos
WHERE disponibilidade = 'sim' AND NOT categoria = 'eletrônicos' AND preco < 100;
```

### Considerações

- O uso de `AND NOT` pode ajudar a eliminar registros indesejados de maneira eficiente.
- Você pode combinar `AND NOT` com outras cláusulas lógicas, como `OR`, para criar condições ainda mais complexas.

### Conclusão

O comando `AND NOT` é uma ferramenta poderosa em SQL para refinar consultas, permitindo a combinação de condições que incluem registros que atendem a uma condição e excluem aqueles que não atendem a outra, resultando em um controle mais preciso sobre os dados retornados.