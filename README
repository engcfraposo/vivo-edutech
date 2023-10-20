
# Projeto de API TODO com Nest.js

Este é um exemplo de um projeto de API TODO simples usando o framework Nest.js. Neste README, mostraremos como criar rotas para gerenciar tarefas TODO. Vamos começar!

## Pré-requisitos

Certifique-se de que você tenha o Node.js e o Nest.js instalados na sua máquina antes de prosseguir.

- [Node.js](https://nodejs.org/)
- [Nest.js](https://nestjs.com/)

## Passo 0: Instalar o NestJS CLI

```bash

npm i -g @nestjs/cli
```

## Passo 1: Criar um novo projeto Nest.js

Execute o seguinte comando para criar um novo projeto Nest.js chamado 'todo-api':

```bash
nest new todo-api
```

Siga as instruções para configurar seu projeto.

## Passo 2: Gerar um recurso 'todo'

Para criar um recurso chamado 'list' que representará as listas de tarefas TODO, use o seguinte comando:

```bash
nest generate resource todo
```

Isso criará um controlador, um serviço e as rotas necessárias para gerenciar listas de tarefas TODO.

Agora você tem um projeto Nest.js básico configurado com rotas para gerenciar tarefas TODO e listas de tarefas. Personalize seu projeto e adicione a lógica de negócios necessária conforme suas necessidades.

## Executando o projeto

Para executar o projeto, use o seguinte comando:

```bash
npm run start
```

### 3. Configurando o Prisma

Certifique-se de que o Prisma CLI esteja instalado no seu sistema. Em seguida, siga as etapas abaixo para configurar o Prisma com um banco de dados SQLITE.

#### 3.1. Inicialize o Prisma

Execute o seguinte comando para criar um novo projeto Prisma:

```bash
npx prisma init
```

Siga as instruções no terminal para configurar o projeto Prisma. Certifique-se de selecionar "Database Type" como "PostgreSQL".

#### 3.2. Defina o modelo de dados

No diretório `prisma`, edite o arquivo `schema.prisma` e defina o modelo de dados para as tarefas. Por exemplo:

```prisma
generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "sqlite"
  url      = env("DATABASE_URL")
}

model Todo {
  id      Int      @id @default(autoincrement())
  title   String
  description String?
  completed Boolean  @default(false)
}

```

criar o env:

```env
DATABASE_URL="file:./dev.db"
```

#### 3.3. Aplicar migrações

Execute o seguinte comando para aplicar as migrações ao banco de dados:

```bash
npx prisma migrate dev
```

### 3.4. Criar o adaptador do Prisma.io

Crie o modulo e o serviço

```ts
import { Injectable, OnModuleInit } from '@nestjs/common';
import { PrismaClient } from '@prisma/client';

@Injectable()
export class PrismaService extends PrismaClient implements OnModuleInit {
  async onModuleInit() {
    await this.$connect();
  }
}

```

### 4. Executando o projeto

Agora você pode executar o projeto Nest.js com o seguinte comando:

```bash
npm run start
```

Se tudo estiver configurado corretamente, sua API estará disponível em `http://localhost:3000`.

## Endpoints da API

Aqui estão alguns dos endpoints da API que você pode começar a usar:

- `GET /todo` - Recupere todas as tarefas.
- `GET /todo/:id` - Recupere uma tarefa específica por ID.
- `POST /todo` - Crie uma nova tarefa.
- `PUT /todo/:id` - Atualize uma tarefa existente.
- `DELETE /todo/:id` - Exclua uma tarefa por ID.

## Conclusão

Você configurou com sucesso um projeto Nest.js que gerencia tarefas usando o Prisma para persistência de dados. Agora você pode personalizar e expandir sua API de acordo com suas necessidades.

Lembre-se de que este é um guia básico e que existem muitas maneiras de melhorar e expandir este projeto. Explore a documentação do Nest.js e do Prisma para obter mais informações.
