# Instalação

Para rodar a aplicação basta executar:

python main.py

mas antes é necessário rodar o postgres e criar a tabela user

### Configuração do postgres

Primeiro executar o Postgres no Docker
```
docker run -d --name postgres-users -e POSTGRES_USER=appuser -e POSTGRES_PASSWORD=apppass -e POSTGRES_DB=postgres -p 5432:5432 postgres:16
```

Entrar no postgres
```
docker exec -it postgres-users psql -U appuser -d postgres
```


```
CREATE DATABASE users;
```

```
\c users
```


```
CREATE TABLE users (
  id UUID PRIMARY KEY,
  name TEXT NOT NULL,
  email TEXT NOT NULL UNIQUE
);
```