# Spring Boot OAuth2 JWT Demo (password grant type)

# Spring Boot OAuth2 JWT Demo Collection

Coleção completa de implementações OAuth2 com diferentes versões do Spring Boot, incluindo Authorization Servers, Resource Servers e aplicações completas.

## 📁 Projetos Incluídos

### 🔐 Authorization Servers

- **[authorization-server-2-7-3](./authorization-server-2-7-3/)** - Authorization Server com Spring Boot 2.7.3
- **[authorization-server-3-0-4](./authorization-server-3-0-4/)** - Authorization Server com Spring Boot 3.0.4

### 🛡️ Resource Servers

- **[resource-server-2-7-3](./resource-server-2-7-3/)** - Resource Server com Spring Boot 2.7.3
- **[resource-server-3-0-4](./resource-server-3-0-4/)** - Resource Server com Spring Boot 3.0.4

### 🚀 Aplicações Completas

#### Spring Boot 2.x

- **[spring-boot-2-7-9](./spring-boot-2-7-9/)** - Aplicação completa Spring Boot 2.7.9

#### Spring Boot 3.x

- **[spring-boot-3-1-0](./spring-boot-3-1-0/)** - Aplicação Spring Boot 3.1.0 com OAuth2
- **[spring-boot-3-1-0-noauth](./spring-boot-3-1-0-noauth/)** - Aplicação Spring Boot 3.1.0 sem autenticação
- **[spring-boot-3-4-3](./spring-boot-3-4-3/)** - Aplicação Spring Boot 3.4.3 com OAuth2
- **[spring-boot-3-4-3-noauth](./spring-boot-3-4-3-noauth/)** - ⭐ **Aplicação principal** Spring Boot 3.4.3 sem autenticação

## 🛠️ Ferramentas e Configurações

### 📮 Postman Collection

- **[postman-collection.json](./postman-collection.json)** - Collection completa para testes
- **[postman-environment.json](./postman-environment.json)** - Ambiente de variáveis do Postman

## 🚀 Como usar

### 1. Escolha o projeto desejado

Navegue até a pasta do projeto que você quer executar.

### 2. Configuração do Postman

1. Importe o arquivo `postman-collection.json` no Postman
2. Importe o arquivo `postman-environment.json`
3. Configure as variáveis de ambiente conforme necessário

### 3. Executar o projeto

1. Abra o projeto no seu IDE favorito
2. Execute a classe principal (geralmente `*Application.java`)
3. Acesse `http://localhost:8080`

## 📋 Testes Recomendados

### PARTE 1: Sem autenticação

- ✅ GET `/products` (deve retornar produtos)
- ❌ GET `/products/1` (deve retornar 401)
- ❌ POST `/products` (deve retornar 401)

### PARTE 2: Logado como Alex

- 📧 Configure `alex@gmail.com` no Postman
- 🔑 Faça login (deve retornar JWT token)
- ✅ GET `/products` (deve retornar produtos)
- ✅ GET `/products/1` (deve retornar produto)
- ❌ POST `/products` (deve retornar 403)

### PARTE 3: Logado como Maria

- 📧 Configure `maria@gmail.com` no Postman
- 🔑 Faça login (deve retornar JWT token)
- ✅ GET `/products` (deve retornar produtos)
- ✅ GET `/products/1` (deve retornar produto)
- ✅ POST `/products` (deve inserir produto)

## 🔧 Versões e Compatibilidade

| Projeto                      | Spring Boot | Java    | OAuth2 | Status           |
| ---------------------------- | ----------- | ------- | ------ | ---------------- |
| authorization-server-2-7-3   | 2.7.3       | 11+     | ✅     | Estável          |
| authorization-server-3-0-4   | 3.0.4       | 17+     | ✅     | Estável          |
| resource-server-2-7-3        | 2.7.3       | 11+     | ✅     | Estável          |
| resource-server-3-0-4        | 3.0.4       | 17+     | ✅     | Estável          |
| spring-boot-2-7-9            | 2.7.9       | 11+     | ✅     | Estável          |
| spring-boot-3-1-0            | 3.1.0       | 17+     | ✅     | Estável          |
| spring-boot-3-1-0-noauth     | 3.1.0       | 17+     | ❌     | Estável          |
| spring-boot-3-4-3            | 3.4.3       | 17+     | ✅     | Estável          |
| **spring-boot-3-4-3-noauth** | **3.4.3**   | **17+** | **❌** | **🌟 Principal** |

## 📝 Notas Importantes

- 🔗 O endpoint de login pode ser `/oauth2/token` ou `/oauth/token` dependendo da versão
- 🌐 Configure `ashost=http://localhost:8080` se executar Authorization Server e Resource Server juntos
- ⚙️ Cada projeto tem seu próprio README com instruções específicas

## 📈 Changelog

- **2025-06-27**: Estrutura inicial com 9 projetos Spring Boot
- **2025-06-27**: Adicionadas collections do Postman
- **2025-06-27**: Documentação completa e organizada

## 🤝 Contribuição

Sinta-se à vontade para contribuir com melhorias, correções ou novos exemplos!

---

**⭐ Projeto em destaque:** `spring-boot-3-4-3-noauth` - A versão mais atual e estável para desenvolvimento.

Our reference minimum implementations for using OAuth2 Authorization Server and Resource Server with Spring Boot, using password grant type, and user/roles from a database.

## Postman Collection and Environment:

Download them from this folder.

## How to run:

- Import Postman collection and environment

  - Note: the Login request path may be `/oauth2/token` or `/oauth/token` depending on Spring Boot version. Change request path if needed.
  - Note: the `ashost` environment variable must be set to `http://localhost:8080` if you're running a project that contains both Authorization Server and Resource Server.

- Open Spring Boot project(s) in your favorite IDE and run

- Tests on Postman:
  - PART 1: not logged
    - Request GET /products (should return products)
    - Request GET /products/1 (should return 401)
    - Request POST /products {"name":"Tablet"} (should return 401)
  - PART 2: logged as Alex
    - Set alex@gmail.com as username in Postman environment
    - Request login request (should return 200 Ok with JWT token. That token will be saved on 'token' environment variable)
    - Request GET /products (should return products)
    - Request GET /products/1 (should return product)
    - Request POST /products {"name":"Tablet"} (should return 403)
  - PART 3: logged as Maria
    - Set maria@gmail.com as username in Postman environment
    - Request login request (should return 200 Ok with JWT token. That token will be saved on 'token' environment variable)
    - Request GET /products (should return products)
    - Request GET /products/1 (should return product)
    - Request POST /products {"name":"Tablet"} (should insert product)

# Para modificações específicas

git add password-grant/spring-boot-3-4-3-noauth/
git commit -m "fix(noauth): resolve authentication issues"

# Outros exemplos:

git add password-grant/authorization-server-2-7-3/
git commit -m "feat(auth-server-2.7.3): add new OAuth2 scopes"

git add password-grant/resource-server-3-0-4/
git commit -m "refactor(resource-server): improve token validation"
