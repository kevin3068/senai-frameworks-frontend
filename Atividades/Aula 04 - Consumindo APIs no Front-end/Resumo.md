# Aula: APIs, HTTP, Express e Deploy de Aplicações Web

## Objetivos da aula

Nesta aula, foram estudados os principais conceitos relacionados ao desenvolvimento de APIs e à comunicação entre aplicações frontend e backend. Também foi desenvolvida uma API utilizando Express, realizado o deploy no Render e criada uma aplicação frontend para consumir os dados da API.

Além disso, foram analisados projetos disponíveis no GitHub que utilizam APIs em suas aplicações.

---

## Conteúdos estudados

- API — Application Programming Interface;
- Protocolo HTTP;
- Endpoints;
- JSON — JavaScript Object Notation;
- Servidor backend;
- Web Service;
- API REST;
- Framework Express;
- Consumo de APIs no frontend;
- Deploy de aplicações;
- Render;
- Vercel;
- Organização de projetos em repositórios separados;
- Integração entre GitHub, Render e Vercel.

---

## 1. API — Application Programming Interface

Uma API é uma interface que permite a comunicação entre diferentes sistemas, aplicações ou serviços.

Por meio de uma API, uma aplicação pode solicitar informações ou executar ações em outra aplicação de forma organizada e padronizada.

### Exemplos de uso de APIs

- Consultar data e hora;
- Buscar previsão do tempo;
- Consultar informações de filmes;
- Realizar pagamentos;
- Buscar dados de usuários;
- Consultar endereços;
- Consumir informações de redes sociais.

---

## 2. Protocolo HTTP

O HTTP é o protocolo utilizado para a comunicação entre clientes e servidores na internet.

Quando uma aplicação frontend faz uma solicitação para uma API, ela utiliza uma requisição HTTP. O servidor processa essa requisição e retorna uma resposta.

### Principais métodos HTTP

| Método | Utilização |
|---|---|
| `GET` | Consultar ou buscar informações |
| `POST` | Criar um novo recurso |
| `PUT` | Atualizar completamente um recurso |
| `PATCH` | Atualizar parcialmente um recurso |
| `DELETE` | Excluir um recurso |

Nesta aula, foi utilizado principalmente o método `GET`, pois a aplicação precisava consultar e exibir a data e a hora.

---

## 3. Endpoint

Endpoint é o endereço específico de uma API utilizado para realizar uma determinada operação. No caso desta API, o endpoint é /.

Exemplo:

```text
GET /api/data-hora
