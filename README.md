# 💸 PicPay - Desafio Backend Finalizado

Este repositório contém a implementação finalizada do desafio backend proposto pela [PicPay](https://github.com/PicPay/picpay-desafio-backend), utilizando Java com Spring Boot. O objetivo do desafio era construir uma API RESTful para realizar transferências entre usuários, com validações, regras de negócio e integração com um serviço externo de autorização.

---

## 🚀 Tecnologias Utilizadas

- Java 17
- Spring Boot
- Maven
- JPA / Hibernate
- H2 (banco em memória para testes)
- JUnit / Mockito
- REST API
- ModelMapper
- Spring Security (mínimo para validações)

---

## ⚙️ Funcionalidades Implementadas

### ✅ Cadastro de Usuários
- Dois tipos de usuário: **Comum** e **Lojista**
- Validações básicas: CPF/CNPJ, e-mail, saldo inicial, etc.

### ✅ Transferência de valores
- Apenas usuários do tipo **Comum** podem realizar transferências
- Verificação de saldo suficiente antes da operação
- Validação via **serviço externo de autorização** (mockado)

### ✅ Notificações
- Simulação de envio de notificação via outro serviço externo (mockado)
- Apenas logado em console

### ✅ Testes unitários e de integração
- Cobertura básica com JUnit e Mockito
- Testes dos serviços principais (transferência, autorização, etc.)

### ✅ Endpoints principais
- POST /users → Cadastra novo usuário
- POST /transactions → Realiza uma transferência
- GET /users → Lista todos os usuários
- GET /transactions → Lista todas as transferências

---

## 🔄 Fluxo da Transferência

1. Usuário do tipo **Comum** inicia a transferência
2. Verifica-se:
   - Se o pagador tem saldo suficiente
   - Se o usuário é do tipo correto
   - Se a autorização externa permite a operação
3. O valor é debitado do pagador e creditado no recebedor
4. Uma notificação é enviada para o recebedor

---

## ▶️ Como rodar o projeto

```bash
git clone https://github.com/briangonc/ApiPicPayJavaSpringBoot.git
cd ApiPicPayJavaSpringBoot
./mvnw spring-boot:run
