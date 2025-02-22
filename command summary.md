# Comentários aula

---

## Necessário ter instalando
- Node.js
- Docker

### GET → Recupera informações do servidor.
- Exemplo: Buscar um usuário: GET /users/1

### POST → Envia dados para o servidor (criação de recursos).
- Exemplo: Criar um novo usuário: POST /users (com dados no corpo da requisição).

### PUT → Atualiza um recurso inteiro.
- Exemplo: Atualizar um usuário completo: PUT /users/1 (substitui todos os dados).

### PATCH → Atualiza parcialmente um recurso.
- Exemplo: Alterar só o e-mail do usuário: PATCH /users/1 (envia só o campo necessário).

### DELETE → Remove um recurso.
- Exemplo: Apagar um usuário: DELETE /users/1

### HEAD → Igual ao GET, mas sem corpo na resposta (só retorna os cabeçalhos).
- Exemplo: HEAD /users/1 (verifica se o usuário existe sem baixar os dados).

### OPTIONS → Retorna os métodos HTTP permitidos para um recurso.
- Exemplo: OPTIONS /users pode retornar GET, POST, PUT, DELETE.

---

### Body: Dados enviados no corpo da requisição (POST, PUT, PATCH).
- Ex: Criar usuário
json
{ "nome": "William", "email": "william@email.com" }

### Search Params: Filtros e paginação na URL, após ?.
- Ex: GET /products?categoria=eletronicos&preco_max=1000

### Route Params: Identificam recursos na URL, sem ?.
- Ex: GET /users/123 (Busca usuário com ID 123).

---

### Códigos de status HTTP que indicam o resultado de uma solicitação feita a um servidor:
- 200 OK: A solicitação foi bem-sucedida e o servidor retornou a resposta esperada.
- 201 Created: A solicitação foi bem-sucedida e resultou na criação de um novo recurso no servidor.
- 204 No Content: A solicitação foi bem-sucedida, mas o servidor não retorna nenhum conteúdo na resposta, como em casos de exclusão de dados.

---

# Instalações no terminal

--- 

## aula01

npm init -y
npm i fastify
npm i tsx typescript @types/node -D
npx tsc --init (obs.: usar o tsc config para cada versão do node)
npx tsx src/server.ts 
npm run dev
npm i @fastifycors
npm i zod
npm i fastify-type-provider-zod
npm i @fastify/swagger @fastify/swagger-ui
npm i @biomejs/biome -D

### npm init -y
Inicializa um novo projeto Node.js, criando um arquivo package.json com as configurações padrão. O -y aceita automaticamente as configurações padrão sem perguntar ao usuário.

### npm i fastify
Instala o Fastify, um framework web para Node.js, focado em alta performance e baixo uso de recursos.

### npm i tsx typescript @types/node -D:
- tsx: Instala o pacote tsx para executar arquivos TypeScript diretamente no Node.js.
- typescript: Instala o TypeScript, uma linguagem que adiciona tipagem estática ao JavaScript.
- @types/node: Instala as definições de tipo para o Node.js, permitindo usar recursos do Node com TypeScript.
- O -D instala essas dependências como dependências de desenvolvimento (não são necessárias em produção).
npx tsc --init: Cria um arquivo de configuração tsconfig.json para um projeto TypeScript. Esse arquivo configura como o TypeScript compilará o código. O npx executa o comando sem precisar instalar o TypeScript globalmente.

### npx tsx src/server.ts
Executa o arquivo TypeScript server.ts diretamente com tsx, sem precisar compilar o código antes.

### npm run dev
Executa o script dev definido no package.json (geralmente usado para iniciar um servidor de desenvolvimento ou uma aplicação local).

### npm i @fastify/cors
Instala o plugin CORS para Fastify, permitindo configurar permissões de compartilhamento de recursos entre origens diferentes (Cross-Origin Resource Sharing).

### npm i zod
Instala a biblioteca Zod, usada para validação de dados e criação de esquemas de validação fortemente tipados em TypeScript.

### npm i fastify-type-provider-zod
Instala o Fastify Type Provider Zod, que integra o Zod com o Fastify, permitindo validar dados com Zod e usar a tipagem do TypeScript.

### npm i @fastify/swagger @fastify/swagger-ui
Instala os plugins Swagger e Swagger UI para Fastify, permitindo gerar documentação interativa da API.

### npm i @biomejs/biome -D
Instala Biome (uma ferramenta de linting e formatação de código) como dependência de desenvolvimento. Ele ajuda a manter o código limpo e formatado conforme padrões definidos.

Esses comandos são para configurar um projeto utilizando Fastify com TypeScript, Zod para validação de dados, Swagger para documentação de API, CORS para compartilhar recursos entre diferentes origens, e Biome para formatação e linting de código.

## configuração do arquivo biome
{
  "$schema": "./node_modules/@biomejs/biome/configuration_schema.json",
  "organizeImports": {
    "enabled": true
  },
  "formatter": {
    "indentStyle": "space",
    "indentWidth": 2,
    "lineWidth": 80
  },
  "javascript": {
    "formatter": {
      "arrowParentheses": "asNeeded",
      "jsxQuoteStyle": "double",
      "quoteStyle": "single",
      "semicolons": "asNeeded",
      "trailingCommas": "es5"
    }
  },
  "linter": {
    "enabled": true,
    "rules": {
      "recommended": true
    }
  },
  "files": {
    "ignore": [
      "node_modules"
    ]
  }
}

---

## aula02

npm i ioredis
npm i postgres drizzle-orm
npm i drizzle-kit -D

---

## aula03

npm i tsup -D
npm run build
node dist/server.mjs
node --env-file .env dist/server.njs
