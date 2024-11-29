# Email Sender Service

EmailSenderService é uma aplicação Java desenvolvida com Spring Boot para o envio de e-mails de forma simples. O projeto permite enviar e-mails utilizando um servidor SMTP, como o Gmail, e inclui uma API REST para facilitar a integração com outras aplicações.

---

## Funcionalidades

- Enviar e-mails utilizando servidores SMTP.
- API REST para envio de e-mails via endpoints HTTP.

---

## Tecnologias Utilizadas

- **Java 17** ou superior
- **Spring Boot** (versão mais recente)
- **Maven** para gerenciamento de dependências
- **Spring Boot Starter Mail** para envio de e-mails
- **Postman** ou **cURL** para testes

---

## Como Executar o Projeto

### Pré-requisitos

- Java JDK instalado e configurado.
- Maven instalado.
- Conta de e-mail com acesso SMTP (ex.: Gmail).
- Credenciais configuradas no arquivo `application.properties`.

### Passos

1. Clone o repositório:

   ```bash
   git clone https://github.com/seu-usuario/emailsenderservice.git
   cd EmailSenderService
   ```

2. Configure as credenciais no arquivo `src/main/resources/application.properties`:

   ```properties
   spring.mail.host=smtp.gmail.com
   spring.mail.port=587
   spring.mail.username=seuemail@gmail.com
   spring.mail.password=suasenhaouapptoken
   spring.mail.properties.mail.smtp.auth=true
   spring.mail.properties.mail.smtp.starttls.enable=true
   ```

3. Execute o projeto:

   ```bash
   ./mvnw spring-boot:run
   ```

4. Teste o envio de e-mails utilizando o Postman ou cURL:
   - **Endpoint**: `POST http://localhost:8080/api/emails/send`
   - **Parâmetros**:
     - `to`: E-mail do destinatário.
     - `subject`: Assunto do e-mail.
     - `text`: Mensagem do e-mail.

---

## Exemplo de Teste com cURL

```bash
curl -X POST "http://localhost:8080/api/emails/send?to=destinatario@gmail.com&subject=Teste&text=Olá! Este é um teste enviado via API."
```

---

## Considerações de Segurança

- Não armazene credenciais sensíveis diretamente no código-fonte para ambientes de produção.
- Use variáveis de ambiente ou ferramentas como **Spring Cloud Config** para gerenciar informações confidenciais.

---

## Licença

Este projeto está sob a licença MIT. Consulte o arquivo `LICENSE` para mais informações.

---
