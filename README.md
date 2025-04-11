## Inicias o Projeto

```bash
npm init -y
```
--
```bash
npm i  typescript@latest @types/node@20.14.12 -D
```
--
```bash
npm i  typescript@latest @types/node@20.14.12 -D
```
--
```bash
npm i tsx@latest -D
```
--
## Criar Script para rodar o projeto

```json
"script": {
    "dev": "tsx watch src/server.ts",
    "knex": "node --import tsx ./node_modules/knex"
}
```
--
## Configure o TypeScript
https://github.com/microsoft/TypeScript/wiki/Node-Target-Mapping
--

## Instalando o dotenv
```bash
npm install dotenv
```
--
## Instalando o Express

```bash
npm i express@latest
```

```bash
npm i --save-dev @types/express
```
--
## Schema Validation (Zod)

```bash
npm i npm i zod@latest
```
--
## Query Builder (Knex) + Banco de dados

```bash
npm i knex@latest mysql2@latest
```
--
Como alternativa para estudos mais simples, podemos estar usando o SQLite
```bash
npm i knex@latest sqlite3@latest
```
--
```bash
npm install --save-dev @types/knex
```
--
## Comandos Knex
```bash
npm run knex -- make 
```
```bash
npm run knex -- latest
```
npm run knex migrate:latest
npm run knex seed:run
npm run knex migrate:rollback
--
## Migrations
-São mecanismos de gestão de mudanças do banco de dados. podendo criar, alterar, remover e versionar o banco de dados.