# Storefront Service

Este documento apresenta o Storefront Service, um dos microsserviços do projeto Warehouse-Storefront Microservices. O Storefront é responsável por gerenciar a vitrine de produtos, processar pedidos e se comunicar com o serviço de armazém (Warehouse Service).

## Índice

- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Arquitetura do Serviço](#arquitetura-do-serviço)
- [Como Executar](#como-executar)
- [Configuração](#configuração)
- [Principais Endpoints](#principais-endpoints)
- [Testes](#testes)
- [Contribuição](#contribuição)

## Tecnologias Utilizadas

- Java 11
- Spring Boot
- Spring Data JPA
- RabbitMQ (comunicação assíncrona)
- Maven
- Docker

## Arquitetura do Serviço

O Storefront Service se comunica com o Warehouse Service de duas formas:
- **Síncrona (HTTP):** Para consultar informações em tempo real.
- **Assíncrona (RabbitMQ):** Para processar eventos e pedidos de forma desacoplada.

Essa abordagem garante escalabilidade, flexibilidade e resiliência ao sistema.

## Como Executar

1. **Clone o repositório:**
   ```
   git clone https://github.com/seuusuario/warehouse-storefront-microservices.git
   ```

2. **Acesse a pasta do serviço:**
   ```
   cd warehouse-storefront-microservices/storefront-service
   ```

3. **Configure as propriedades em `src/main/resources/application.yml` conforme necessário.**

4. **Compile o projeto:**
   ```
   mvn clean install
   ```

5. **Execute a aplicação:**
   ```
   mvn spring-boot:run
   ```

6. **(Opcional) Docker:**
   ```
   docker build -t storefront-service .
   docker run -p 8080:8080 storefront-service
   ```

## Configuração

- Certifique-se de que o RabbitMQ esteja rodando (padrão: `localhost:5672`).
- Ajuste as configurações de conexão com o banco de dados e o RabbitMQ no arquivo `application.yml`.

## Principais Endpoints

- `GET /products` — Lista todos os produtos disponíveis na vitrine.
- `POST /orders` — Cria um novo pedido.

> **Observação:** Consulte a documentação Swagger (caso disponível) para detalhes completos dos endpoints.

## Testes

Os testes unitários estão localizados em `src/test/java/com/example/storefront`.  
Para executá-los:
```
mvn test
```

## Contribuição

Contribuições são bem-vindas!  
Abra uma issue ou envie um pull request com sugestões de melhorias ou correções.

---

*Este projeto faz parte do desafio de arquitetura de microsserviços da DIO.*