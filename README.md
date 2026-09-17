[README.md](https://github.com/user-attachments/files/32347977/README.md)
# orm-template-main

Template de API REST em Node.js/Express usando **Prisma ORM** com PostgreSQL, criado para servir de base para novos projetos backend. Modela usuários e perguntas (`users` e `questions`) e expõe rotas CRUD básicas para ambos.

## 🚀 Tecnologias utilizadas

- Node.js + TypeScript
- Express
- Prisma ORM (`@prisma/client` + migrations em `prisma/migrations`)
- PostgreSQL
- express-async-errors (tratamento de erros assíncronos)
- tsx (execução em modo watch)

## 📦 Como rodar o projeto

```bash
# clone o repositório
git clone https://github.com/2305ray/orm-template-main.git
cd orm-template-main

# instale as dependências
npm install
```

Crie um arquivo `.env` na raiz do projeto com a string de conexão do banco (usada em `prisma/schema.prisma`):

```
DATABASE_URL="postgresql://usuario:senha@localhost:5432/nome_do_banco"
```

Depois, rode as migrations do Prisma e suba o servidor:

```bash
# aplica as migrations no banco
npx prisma migrate dev

# rode em modo desenvolvimento
npm run dev
```

O servidor sobe na porta `3334`.

## 📁 Estrutura

- `prisma/schema.prisma` — modelos `User` e `Question` e configuração do datasource
- `prisma/migrations` — histórico de migrations geradas pelo Prisma
- `src/routes` — rotas Express, separadas por recurso (`users-routes`, `questions-routes`)
- `src/controllers` — controllers com a lógica de cada rota, usando o Prisma Client (`src/prisma.ts`)
