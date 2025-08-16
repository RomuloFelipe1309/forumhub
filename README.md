# 📚 FórumHub

FórumHub é uma API REST desenvolvida com Spring Boot que simula o funcionamento de um fórum de discussão. O projeto permite que usuários criem tópicos, respondam, curtam respostas, recebam notificações, filtrem por categorias e muito mais — tudo com autenticação segura via JWT.

---

## 🚀 Tecnologias Utilizadas

- Java 17
- Spring Boot
- Spring Security
- Spring Data JPA
- JWT (JSON Web Token)
- H2 Database (para testes)
- PostgreSQL ou MySQL (produção)
- Maven
- JUnit & MockMvc (testes)

---

## 📦 Funcionalidades

- 🔐 Autenticação com JWT
- 🧵 CRUD completo de tópicos
- 💬 Respostas aos tópicos
- 📂 Categorias e filtro por tema
- ❤️ Likes em respostas
- 🛡️ Moderação com permissões
- 🔔 Notificações de novas respostas
- 🧾 Histórico de edição
- 📊 Estatísticas do fórum
- 🧑‍💼 Cadastro de usuários
- 🧪 Testes automatizados

---

## 🛠️ Instalação e Execução

### Pré-requisitos

- Java 17+
- Maven
- PostgreSQL ou MySQL (opcional)

### Passos

```bash
# Clone o repositório
git clone https://github.com/RomuloFelipe1309/forumhub.git
cd forumhub

# Compile o projeto
mvn clean install

# Execute a aplicação
mvn spring-boot:run

---

⚙️ Configuração do Banco de Dados
No arquivo application.properties, configure:

spring.datasource.url=jdbc:postgresql://localhost:5432/forumhub
spring.datasource.username= postgres
spring.datasource.password= 63168801 
spring.jpa.hibernate.ddl-auto=update

Para testes, o banco H2 já está configurado por padrão.

---

🔐 Autenticação

Login

POST /auth

Body:

{
  "username": "usuario",
  "password": "senha"
}

Retorno:

json

{
  "token": "jwt_token"
}

Use o token nas rotas protegidas:

Authorization: Bearer <jwt_token>

---

📚 Endpoints Principais

Usuários

Método     Rota	            Descrição
POST	   /users	        Cadastro de usuário

Tópicos

Método	        Rota	             Descrição
POST	        /topics	           Criar novo tópico
GET	         /topics	Listar     todos os tópicos
GET	         /topics/{id}	       Buscar tópico por ID
PUT	         /topics/{id}	      Atualizar tópico
DELETE	    /topics/{id}	      Deletar tópico

Respostas

Método	         Rota	                    Descrição
POST	     /topics/{id}/answers	   Criar resposta para tópico
GET	      /topics/{id}/answers	    Listar respostas do tópico

Categorias

Método	       Rota	                     Descrição
POST	      /categories	             Criar nova categoria
GET	       /categories	             Listar todas as categorias

Likes

Método	              Rota	                          Descrição
POST	    /answers/{id}/likes	                    Curtir resposta
GET	     /answers/{id}/likes/count	Contar        likes da resposta

Notificações

Método	          Rota	                 Descrição
GET	         /notifications	       Listar notificações do usuário

Estatísticas

Método	         Rota	                          Descrição
GET	            /stats	                 Retorna estatísticas gerais

---

🧪 Testes
Execute os testes com:

bash

mvn test

Inclui testes unitários e de integração com banco H2.

---

📄 Licença
Este projeto está sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.

---

👨‍💻 Autor
Desenvolvido por Rômulo Machado — apaixonado por backend, APIs e arquitetura de software.

---

💬 Contato

Email: romulomachado1309@gmail.com

LinkedIn: https://www.linkedin.com/in/rômulo-machado-analista/

GitHub: github.com/RomuloFelipe1309


