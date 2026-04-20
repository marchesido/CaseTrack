# TechAcademy 5 - Gestão de Audiovisual

Este projeto é um sistema de gestão para produtoras de audiovisual, composto por um backend em NestJS, um frontend em React (Vite) e um banco de dados PostgreSQL.

## 🚀 Como executar o projeto com Docker Compose

Certifique-se de ter o [Docker](https://www.docker.com/) e o [Docker Compose](https://docs.docker.com/compose/) instalados em sua máquina.

### 1. Clonar o repositório
```bash
git clone <url-do-repositorio>
cd <nome-do-diretorio>
```

### 2. Configurar as variáveis de ambiente
As configurações padrão já estão definidas no arquivo `docker-compose.yml`. No entanto, para o funcionamento do JWT no backend, você pode preencher as variáveis no `docker-compose.yml` ou criar um arquivo `.env` dentro da pasta `TechAcademy-5-Api-Audiovisual`.

### 3. Subir os containers
Na raiz do projeto, execute o seguinte comando:
```bash
docker-compose up --build
```
Este comando irá baixar as imagens necessárias, construir as imagens locais para o frontend e backend, e iniciar todos os serviços.

---

## 📡 Acesso aos Serviços

Após a inicialização, os serviços estarão disponíveis nos seguintes endereços:

- **Frontend (React/Vite):** [http://localhost](http://localhost)
- **Backend (API NestJS):** [http://localhost:3000](http://localhost:3000)
- **Banco de Dados (PostgreSQL):** `localhost:5433`
  - **Usuário:** `postgres`
  - **Senha:** `postgres123`
  - **Database:** `audiovisual-gestao-db`

---

## 🛠️ Comandos Úteis

### Popular o banco de dados (Seeds)
Para inserir dados de teste no banco de dados (7 registros por entidade), execute o comando abaixo enquanto os containers estiverem rodando:
```bash
docker exec -it nest-js-app npm run seed
```

### Executar Migrations
Caso precise rodar as migrations manualmente:
```bash
docker exec -it nest-js-app npm run migration:run
```

### Parar os containers
```bash
docker-compose down
```

---

## 📖 Estrutura do Projeto

- `/TechAcademy-5-Api-Audiovisual`: Código fonte da API (Backend).
- `/gestao-audiovisual`: Código fonte da aplicação web (Frontend).
- `docker-compose.yml`: Configuração da infraestrutura Docker.
