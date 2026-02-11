# instalar o postgres

docker run -d --name postgres-users -e POSTGRES_USER=appuser -e POSTGRES_PASSWORD=apppass -e POSTGRES_DB=postgres -p 5432:5432 postgres:16


docker exec -it postgres-users psql -U appuser -d postgres

CREATE DATABASE users;

\c users

CREATE TABLE users (
  id UUID PRIMARY KEY,
  name TEXT NOT NULL,
  email TEXT NOT NULL UNIQUE
);