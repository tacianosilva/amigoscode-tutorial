# Tutorial

Java Tutorial - Complete User Login and Registration Backend + Email Verification

Link: https://www.youtube.com/watch?v=QwQuro7ekvc

## Banco de Dados

Crie um usuário para o banco de dados.
```sql
CREATE ROLE tutorial_user WITH
  LOGIN
  NOSUPERUSER
  NOINHERIT
  NOCREATEDB
  NOCREATEROLE
  NOREPLICATION
  ENCRYPTED PASSWORD 'md5b2cf5cff91e9208549fee9915d12ceed';
```
Crie o banco de dados.
```sql
CREATE DATABASE tutorial_db
    WITH 
    OWNER = tutorial_user
    ENCODING = 'UTF8'
    LC_COLLATE = 'en_US.utf8'
    LC_CTYPE = 'en_US.utf8'
    TABLESPACE = pg_default
    CONNECTION LIMIT = -1;
```
Atribua permissões de acesso ao banco de dados.
```sql
GRANT ALL PRIVILEGES ON DATABASE tutorial_db TO tutorial_user;
GRANT ALL PRIVILEGES ON SCHEMA public TO tutorial_user;
```

## Serviço de e-mail para testes

[MailDev](https://github.com/maildev/maildev) is a simple way to test your project's generated email during development, with an easy to use web interface that runs on your machine built on top of Node.js. Link: https://github.com/maildev/maildev

### Docker Run

If you want to use MailDev with [Docker](https://www.docker.com/), you can use the
[**maildev/maildev** image on Docker Hub](https://hub.docker.com/r/maildev/maildev).
For a guide for usage with Docker,
[checkout the docs](https://github.com/maildev/maildev/blob/master/docs/docker.md).

```console
docker run -p 1080:1080 -p 1025:1025 maildev/maildev
```
