# Projeto React — React Shop

## Descrição

O **React Shop** é uma aplicação web de e-commerce desenvolvida em **React** com **Vite** e **React Router**, criada para consolidar na prática todos os conceitos abordados nas **Aulas 08 e 09** da disciplina de **Frameworks Front-end**.

A aplicação consome dados reais de produtos da **Fake Store API** (`https://fakestoreapi.com/products`), permitindo navegar pelo catálogo, filtrar itens, visualizar detalhes individuais, gerenciar um carrinho de compras persistido no navegador (`localStorage`) e simular a finalização de pedidos com validação de formulário.

- **Repositório no GitHub:** [kevin3068/react-shop](https://github.com/kevin3068/react-shop)

---

## Funcionalidades

- **Catálogo de Produtos:** Listagem dinâmica de produtos carregados da Fake Store API com estados de carregamento (`loading`) e tratamento de erro.
- **Filtro e Busca:** Filtragem de produtos na página inicial por meio do componente `Filter`.
- **Detalhes do Produto:** Rota dedicada (`/produto/:id`) exibindo informações completas do item selecionado e opção de adicionar ao carrinho.
- **Carrinho de Compras:** Adição, incremento de quantidade, remoção de itens e limpeza total do carrinho, com contador em tempo real no cabeçalho (`Header`) e persistência automática no `localStorage`.
- **Checkout com Validação:** Página `/checkout` com formulário controlado (dados pessoais, endereço e pagamento), validação de campos obrigatórios e formato de e-mail, resumo do pedido e feedback visual de envio.
- **Tratamento de Rotas Inexistentes:** Página `NotFound` (`*`) para URLs não mapeadas.

---

## Conceitos Utilizados

### Aula 08 — Fundamentos do React

| Conceito | Aplicação no Projeto |
|---|---|
| **JSX** | Uso de sintaxe declarativa combinando marcação HTML e expressões JavaScript em todos os componentes e páginas (`App.jsx`, `ProductCard.jsx`, `Checkout.jsx`, etc.). |
| **Componentes** | Interface modularizada em componentes reutilizáveis (`Header`, `ProductList`, `ProductCard`, `ProductDetail`, `Filter`, `Cart`, `CartNotification`, `Checkout`) e páginas (`Home`, `CheckoutPage`, `NotFound`). |
| **Props** | Passagem de dados e funções de callback do componente pai `App` para filhos e páginas, como `totalItens`, `itensCarrinho`, `onAdicionarAoCarrinho`, `onRemoverDoCarrinho` e `onLimparCarrinho`. |
| **Virtual DOM** | Atualização eficiente da interface gerenciada pelo React ao alterar o estado do carrinho, filtros ou carregamento, sem manipulação manual do DOM real. |
| **Listas e Keys** | Renderização de listas de produtos e itens do carrinho utilizando `.map()` com a propriedade `key={item.id}` para identificação estável dos elementos. |
| **Renderização Condicional** | Exibição condicional para estados de carregamento, erro na API, carrinho vazio, produto já adicionado ao carrinho e mensagem de sucesso no checkout. |

### Aula 09 — Estado, Formulários, Efeitos, APIs e Rotas

| Conceito | Aplicação no Projeto |
|---|---|
| **State e `useState`** | Gerenciamento do estado global do carrinho (`itensCarrinho`) em `App.jsx`, estado de produtos/carregamento/erro em `useProducts.js` e dados do formulário em `Checkout.jsx`. |
| **Formulários** | Campos controlados (`value` + `onChange`) no formulário de `Checkout.jsx`, com prevenção de recarregamento (`e.preventDefault()`) e validação no `handleSubmit`. |
| **`useEffect`** | Sincronização do carrinho com o `localStorage` ao montar e atualizar (`[itensCarrinho]`), além do disparo de requisições à API na montagem dos hooks `useProducts` e `useProdutoDetalhes`. |
| **Consumo de APIs** | Requisições HTTP assíncronas com `fetch()` no módulo `src/services/api.js` (`buscarProdutos`, `buscarProdutoPorId`, `finalizarCompra`) consumindo a Fake Store API com tratamento `try/catch` e `response.ok`. |
| **React Router** | Navegação SPA configurada com `BrowserRouter`, `Routes` e `Route` em `App.jsx` (`/`, `/produto/:id`, `/checkout`, `*`), além de `useNavigate` e `useParams` para rotas dinâmicas e redirecionamentos. |

---

## Estrutura do Projeto

```text
react-shop/
├── index.html
├── package.json
├── vite.config.js
└── src/
    ├── App.jsx                   # Rotas, estado global do carrinho e persistência
    ├── main.jsx                  # Ponto de entrada React
    ├── components/               # Componentes reutilizáveis (Header, Cart, Checkout, ProductCard, etc.)
    ├── hooks/
    │   └── useProducts.js        # Hooks customizados para listagem e detalhes via API
    ├── pages/                    # Páginas (Home, CheckoutPage, NotFound)
    ├── services/
    │   └── api.js                # Integração HTTP com Fake Store API
    └── styles/                   # Arquivos CSS (global.css, home.css, checkout.css)
```

---

## Como Executar Localmente

```bash
git clone https://github.com/kevin3068/react-shop.git
cd react-shop
npm install
npm run dev
```
