# 🍀 Cadastro de Apostas da Mega-Sena

> Aplicação web para cadastrar e listar jogos da Mega-Sena, com frontend estático em HTML/CSS/JavaScript e backend em Node.js com Express conectado ao PostgreSQL.

---

## 📌 Sobre o Projeto

Esta aplicação permite ao usuário cadastrar jogos da Mega-Sena digitando 6 dezenas separadas por espaços, e visualizar todos os jogos cadastrados exibidos como bolinhas numeradas. Os dados são persistidos em um banco de dados PostgreSQL por meio de uma API REST desenvolvida com Express.

A atividade foi desenvolvida como parte das práticas acadêmicas da **FATEC Jacareí – Faculdade de Tecnologia de Jacareí**, no curso de **Desenvolvimento de Software Multiplataforma (DSM)**.

---

## 🚀 Tecnologias Utilizadas

- [Node.js](https://nodejs.org/) — Ambiente de execução JavaScript no servidor
- [Express v5](https://expressjs.com/) — Framework web para Node.js
- [PostgreSQL](https://www.postgresql.org/) — Banco de dados relacional
- [node-postgres (pg)](https://node-postgres.com/) — Cliente PostgreSQL para Node.js
- [dotenv](https://github.com/motdotla/dotenv) — Gerenciamento de variáveis de ambiente
- HTML5 + CSS3 + JavaScript (Fetch API) — Interface e comunicação com o backend

---

## 📁 Estrutura do Projeto

```
app/
├── public/
│   ├── assets/
│   │   ├── css/
│   │   │   └── main.css              # Estilos da aplicação
│   │   └── js/
│   │       └── main.js               # Lógica do frontend (Fetch API)
│   └── pages/
│       └── index.html                # Página principal
├── src/
│   ├── database/
│   │   └── connection.js             # Configuração do Pool de conexão com o PostgreSQL
│   ├── routes/
│   │   └── sena.routes.js            # Rotas da API de jogos
│   └── server.js                     # Arquivo principal do servidor Express
├── .env                              # Variáveis de ambiente
├── .gitignore
├── package.json
└── package-lock.json
```

---

## 🔀 Rotas da API

| Método | Rota       | Descrição                     |
|--------|------------|-------------------------------|
| GET    | `/`        | Página principal              |
| GET    | `/assets/*`| Arquivos estáticos            |
| GET    | `/senas`   | Lista todos os jogos          |
| POST   | `/senas`   | Cadastra um novo jogo         |

---

## ✨ Funcionalidades

- Cadastro de jogos com 6 dezenas separadas por espaços
- Validação do número de dezenas antes de salvar
- Listagem dos jogos cadastrados exibidos como bolinhas numeradas
- Disparo do cadastro ao pressionar **Enter**
- Feedback visual de estados: cadastrando, sucesso e erro

---

## 🗃️ Banco de Dados

A aplicação utiliza PostgreSQL com a seguinte estrutura de tabela:

```sql
CREATE TABLE senas (
  id_sena SERIAL PRIMARY KEY,
  nros    VARCHAR(20) NOT NULL
);
```

> Execute esse comando no seu banco antes de iniciar a aplicação.

---

## 🔧 Variáveis de Ambiente

Crie um arquivo `.env` na raiz do projeto com as seguintes variáveis:

```env
PORT=3004  # ou qualquer outra porta de sua preferência

POSTGRES_HOST=localhost
POSTGRES_USER=postgres
POSTGRES_PASSWORD=sua_senha
POSTGRES_DB=nome_do_banco
POSTGRES_PORT=5432
```

> ⚠️ O arquivo `.env` já está no `.gitignore` e **não deve ser versionado**.

---

## ⚙️ Como Executar

### Pré-requisitos

- [Node.js](https://nodejs.org/) instalado (versão 14 ou superior)
- [PostgreSQL](https://www.postgresql.org/) instalado e rodando
- npm (incluído com o Node.js)

### Passo a passo

```bash
# 1. Clone o repositório
git clone https://github.com/gm-paiva/Cadastro-de-Apostas-da-Mega-Sena.git

# 2. Acesse a pasta do projeto
cd app

# 3. Instale as dependências
npm install

# 4. Configure as variáveis de ambiente
# Crie o arquivo .env conforme a seção acima

# 5. Crie a tabela no banco de dados
# Execute o SQL da seção "Banco de Dados" no seu PostgreSQL

# 6a. Inicie o servidor (produção)
npm start

# 6b. Inicie o servidor (desenvolvimento com hot reload)
npm run dev
```

Acesse no navegador: [http://localhost:3004](http://localhost:3004)

---

## 📚 Contexto Acadêmico

| Campo          | Informação                                        |
|----------------|---------------------------------------------------|
| 🏫 Instituição | FATEC Jacareí                                     |
| 🎓 Curso       | Desenvolvimento de Software Multiplataforma – DSM |
| 📖 Disciplina  | Desenvolvimento Web I                            |
| 👨‍🏫 Professor(a) | [Arley Ferreira de Souza](https://github.com/arleysouza)     |
| 📅 Semestre    | 1º Semestre - 2026 

---

## 👤 Autor

Desenvolvido por **[Guilherme Matos Paiva](https://github.com/gm-paiva)**.

---

## 📄 Licença

Este projeto está sob a licença MIT.
