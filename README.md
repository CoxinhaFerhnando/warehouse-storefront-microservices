# Warehouse Service

Este documento apresenta o Warehouse Service, um dos microsserviços do projeto Warehouse-Storefront Microservices. O Warehouse é responsável por gerenciar o estoque de produtos, processar atualizações de inventário e se comunicar com o serviço de vitrine (Storefront Service).

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

O Warehouse Service se comunica com o Storefront Service de duas formas:
- **Síncrona (HTTP):** Para fornecer informações de estoque em tempo real.
- **Assíncrona (RabbitMQ):** Para receber e processar eventos de pedidos e atualizações de estoque.

Essa arquitetura permite maior escalabilidade, desacoplamento e resiliência.

## Como Executar

1. **Clone o repositório:**
   ```
   git clone https://github.com/seuusuario/warehouse-storefront-microservices.git
   ```

2. **Acesse a pasta do serviço:**
   ```
   cd warehouse-storefront-microservices/warehouse-service
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
   docker build -t warehouse-service .
   docker run -p 8081:8081 warehouse-service
   ```

## Configuração

- Certifique-se de que o RabbitMQ esteja rodando (padrão: `localhost:5672`).
- Ajuste as configurações de conexão com o banco de dados e o RabbitMQ no arquivo `application.yml`.

## Principais Endpoints

- `GET /inventory` — Lista o estoque de todos os produtos.
- `PUT /inventory/{productId}` — Atualiza a quantidade em estoque de um produto.

> **Observação:** Consulte a documentação Swagger (caso disponível) para detalhes completos dos endpoints.

## Testes

Os testes unitários estão localizados em `src/test/java/com/example/warehouse`.  
Para executá-los:
```
mvn test
```

## Contribuição

Contribuições são bem-vindas!  
Abra uma issue ou envie um pull request com sugestões de melhorias ou correções.

---

*Este projeto faz parte do desafio de arquitetura de microsserviços da DIO.*