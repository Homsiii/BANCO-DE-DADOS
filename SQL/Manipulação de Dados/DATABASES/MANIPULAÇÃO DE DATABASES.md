A manipulação de databases e usuários é essencial para gerenciar a segurança e o acesso aos dados em um sistema de banco de dados. Aqui estão as operações comuns relacionadas à criação de databases, usuários, concessão de permissões e verificação de usuários e permissões.

### 1. Criar um Database

Para criar um novo database, você utiliza a instrução `CREATE DATABASE`.

#### Sintaxe

```
CREATE DATABASE nome_do_database;
```

#### Exemplo

```
CREATE DATABASE loja;
```

### 2. Criar um Usuário

Para criar um novo usuário, você utiliza a instrução `CREATE USER`.

#### Sintaxe

```
CREATE USER 'nome_usuario'@'host' IDENTIFIED BY 'senha';
```

#### Exemplo

```
CREATE USER 'novo_usuario'@'localhost' IDENTIFIED BY 'senha123';
```

### 3. Conceder Permissões

Após criar um usuário, você pode conceder permissões específicas a ele usando a instrução `GRANT`.

#### Sintaxe

```
GRANT tipo_permissao ON nome_do_database.* TO 'nome_usuario'@'host';
```

#### Exemplo

```
GRANT ALL PRIVILEGES ON loja.* TO 'novo_usuario'@'localhost';
```

### 4. Revogar Permissões

Se precisar revogar permissões de um usuário, você pode usar a instrução `REVOKE`.

#### Sintaxe

```
REVOKE tipo_permissao ON nome_do_database.* FROM 'nome_usuario'@'host';
```

#### Exemplo

```
REVOKE ALL PRIVILEGES ON loja.* FROM 'novo_usuario'@'localhost';
```

### 5. Verificar Usuários e Permissões

Para verificar os usuários existentes e suas permissões, você pode usar algumas consultas.

#### Listar Usuários

```
SELECT User, Host FROM mysql.user;
```

#### Verificar Permissões de um Usuário

```
SHOW GRANTS FOR 'nome_usuario'@'host';
```

#### Exemplo

```
SHOW GRANTS FOR 'novo_usuario'@'localhost';
```

### 6. Excluir um Usuário

Se precisar remover um usuário, você pode usar a instrução `DROP USER`.

#### Sintaxe

```
DROP USER 'nome_usuario'@'host';
```

#### Exemplo

```
DROP USER 'novo_usuario'@'localhost';
```

### Conclusão

A manipulação de databases e usuários é fundamental para a administração de um sistema de banco de dados. Compreender como criar databases, usuários, conceder e revogar permissões, e verificar informações de usuários ajuda a manter a segurança e integridade dos dados. É importante seguir boas práticas de segurança e gerenciar as permissões de forma adequada para proteger as informações sensíveis.



with usuarios (nome) as (

select
    trim(u.sec$user_name)
from sec$users u
where u.sec$user_name <> 'SYSDBA')

select
    cast('grant select on ' || trim(r.rdb$relation_name) ||  ' to '   || list('"'||u.nome||'"')  || ';' as varchar(1000))
from rdb$relations r
cross join usuarios u
where r.rdb$system_flag = 0
group by r.rdb$relation_name

REVOKE ALL ON ALL FROM "JOAO.COSTA";