# 🌧️ AlertaChuva API

Este projeto é uma API REST desenvolvida em **Java com Spring Boot**, que monitora dados de sensores IoT e emite alertas de chuva intensa para usuários cadastrados. A aplicação segue boas práticas de arquitetura, validação, autenticação via JWT e documentação Swagger.

---

## 🚀 Tecnologias Utilizadas

- Java 17
- Spring Boot 3.2.5
- Spring Data JPA
- Spring Security + JWT
- H2 Database (para testes locais)
- Bean Validation (Jakarta)
- Swagger/OpenAPI
- Maven

---

## 🧠 Funcionalidades

- ✅ Cadastro e autenticação de usuários
- ✅ Registro de sensores e leitura de dados (ex: intensidade da chuva)
- ✅ Emissão automática de alertas quando os níveis superam o limite
- ✅ Endpoints com paginação, ordenação e filtros
- ✅ Documentação automática da API com Swagger
- ✅ Segurança com autenticação via JWT

---


## 🛠️ Como Executar Localmente

### 🔧 Pré-requisitos

- [Java 17+](https://www.oracle.com/br/java/technologies/javase/jdk17-archive-downloads.html)
- [Maven](https://maven.apache.org/install.html)
- [Git](https://git-scm.com/)

### ⏬ Clone o repositório

```bash
git clone https://github.com/DuGiovannini/GsJava.git
cd GsJava
```

### ▶️ Execute a aplicação


```bash
mvn clean install
mvn spring-boot:run

```

---

## 🔐 Acesso e Autenticação

1. **Acesse o Swagger** (após rodar a aplicação):  
   [http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html)

2. **Registre um novo usuário**
   - `POST /usuarios/cadastrar`  
   Exemplo:
   ```json
   {
     "nome": "João",
     "email": "joao@email.com",
     "senha": "123456"
   }
   ```

3. **Realize o login**
   - `POST /auth/login`  
   Exemplo:
   ```json
   {
     "email": "joao@email.com",
     "senha": "123456"
   }
   ```

   Isso retornará um **token JWT**.

4. **Use o token** para autenticar nos endpoints protegidos:
   - No Swagger, clique em "Authorize" e insira:
     ```
     Bearer SEU_TOKEN_JWT
     ```

---

## ✅ Como Testar a API

Você pode testar usando o **Swagger UI** ou o **Postman**.

### Exemplos de endpoints para testar:

- `GET /sensores` → lista de sensores (com paginação)
- `POST /leituras` → cadastrar nova leitura (autenticado)
- `GET /alertas` → visualizar alertas ativos
- `GET /usuarios` → visualizar usuários cadastrados

---


## 🔐 Segurança com JWT

- Todos os endpoints protegidos exigem token JWT no header `Authorization`.
- Use `Bearer SEU_TOKEN_AQUI` para autenticar nas requisições.

---

## 👨‍💻 Contribuidores

RM 555962 Gabriel Teodoro Gonçalves Rosa

RM 558123 Luka Yuiti Ura Shibuya

RM 555030 Eduardo Ribeiro Giovannini

---

## 📄 Licença

Este projeto é acadêmico e foi desenvolvido como parte da disciplina de Java Advanced na FIAP.
