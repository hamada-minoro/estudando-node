## Inicias o Projeto

```bash
npm init -y
```

```bash
npm i  typescript@latest @types/node@20.14.12 -D
```

```bash
npm i  typescript@latest @types/node@20.14.12 -D
```

```bash
npm i tsx@latest -D
```

## Criar Script para rodar o projeto

```json
"script": {
    "dev": "tsx watch src/server.ts",
     "knex": "node --import tsx ./node_modules/.bin/knex"
}
```

## Configure o TypeScript
https://github.com/microsoft/TypeScript/wiki/Node-Target-Mapping


## Instalando o dotenv
```bash
npm install dotenv
```

## Instalando o Express

```bash
npm i express@latest
```

```bash
npm i --save-dev @types/express
```

## Schema Validation (Zod)

```bash
npm i npm i zod@latest
```

## Query Builder (Prisma) + Banco de dados

```bash
npm install prisma --save-dev
npm install @prisma/client
```

```bash
npx prisma init
```

-Depois de inicializado o prisma, coloque os dados do banco no arquivo env 
DATABASE_URL="mysql://usuario:senha@localhost:3306/minha_base"
--

-Depois no aquivo schema.prisma vamos definir a estrutura do banco de dados

```json
datasource db {
  provider = "mysql"
  url      = env("DATABASE_URL")
}

generator client {
  provider = "prisma-client-js"
}

// Exemplo de modelo:
model User {
  id        Int      @id @default(autoincrement())
  name      String
  email     String   @unique
  createdAt DateTime @default(now())
  updatedAt DateTime @updatedAt
}
```
--
-Após esses pontos definidos, vamos fazer nossa primeira migrate
```bash
 npx prisma migrate dev --name init
```
-Gera o Prisma Client a partir do schema
```bash
npx prisma generate
```
---
Crie um arquivo para centralizar a instância do Prisma Client, facilitando seu uso em todo o projeto. Por exemplo, crie o arquivo src/prismaClient.ts

```typescript
import { PrismaClient } from '@prisma/client';

const prisma = new PrismaClient();

export default prisma;
```
## Migrations
-São mecanismos de gestão de mudanças do banco de dados. podendo criar, alterar, remover e versionar o banco de dados.

--migrate
```bash
npx prisma migrate dev --name nome_da_migration
```
--prisma studio
```bash
npx prisma studio
```
--formatar o arquivo schema.prisma
```bash
npx prisma format
```
--reinicia as tabelas
```bash
npx prisma migrate reset
```

