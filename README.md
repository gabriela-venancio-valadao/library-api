# 📚 Library API

API REST para gerenciamento de autores e livros, desenvolvida com **Java + Spring Boot**.
Este projeto foi criado com foco em boas praticas de arquitetura backend, validacoes de negocio e organizacao em camadas.

---

##  Visao Geral

A **Library API** permite operacoes de cadastro, consulta, atualizacao e remocao de autores (com estrutura preparada para livros), utilizando:

- Camada de **Controller** para exposicao dos endpoints REST
- Camada de **Service** para regras de negocio
- Camada de **Repository** com Spring Data JPA
- Camada de **Validator** para validacoes customizadas
- Tratamento de excecoes para respostas mais consistentes

---

## 🛠️ Tecnologias

- **Java**
- **Spring Boot**
- **Spring Web**
- **Spring Data JPA**
- **Maven**
- **YAML** (configuracao)
- **Banco relacional** (via JPA)

---

##  Estrutura do Projeto

```bash
src/main/java/io/github/gabriela_wossiman/libraryapi
├── config/         # Configuracoes da aplicacao e banco
├── controller/     # Endpoints REST + DTOs de resposta
├── exceptions/     # Excecoes de dominio
├── model/          # Entidades (Autor, Livro, GeneroLivro)
├── repository/     # Interfaces JPA
├── service/        # Regras de negocio
└── validator/      # Validacoes customizadas
```

---

##  Como Executar

### Pre-requisitos

- **JDK 17+** (ou versao compativel com seu `pom.xml`)
- **Maven Wrapper** (ja incluido no projeto)

### Executando no Windows (PowerShell)

```powershell
.\mvnw.cmd spring-boot:run
```

Aplicacao (padrao Spring Boot):

```text
http://localhost:8080
```

## ✅ Regras de Negocio em Destaque

- Validacao de autor antes de salvar/atualizar (`AutorValidator`)
- Bloqueio de atualizacao sem `id` valido
- Pesquisa de autores por `nome`, `nacionalidade` ou combinacao de ambos
- Tratamento de duplicidade com excecao de dominio (`RegistroDuplicadoException`)

---

## 📌 Proximas Melhorias

- [ ] Documentacao de API com **Swagger/OpenAPI**
- [ ] Testes unitarios e de integracao para services/controllers
- [ ] Paginacao e ordenacao nas consultas
- [ ] Autenticacao e autorizacao (Spring Security + JWT)
- [ ] Docker para ambiente padronizado

## 📄 Licenca

Este projeto esta sob a licenca definida no repositorio (`LICENSE`).
