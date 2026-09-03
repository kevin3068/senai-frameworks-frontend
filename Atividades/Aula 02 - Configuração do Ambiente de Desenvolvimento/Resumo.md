# Resumo da Aula

## Introdução ao Versionamento

O versionamento é o processo de controlar e registrar as alterações realizadas em um projeto ao longo do tempo. Ele permite acompanhar a evolução do código, recuperar versões anteriores e facilitar o trabalho em equipe.

Por meio do versionamento, é possível identificar quem realizou cada alteração, quando ela foi feita e quais arquivos foram modificados.

## Versionamento Semântico (SemVer)

O Versionamento Semântico, também conhecido como **SemVer**, é um padrão utilizado para identificar versões de softwares.

Seu formato principal é:

```text
MAJOR.MINOR.PATCH
```

Exemplo:

```text
1.4.2
```

Cada número possui um significado:

- **MAJOR:** indica alterações incompatíveis com versões anteriores.
- **MINOR:** indica a adição de novas funcionalidades sem quebrar a compatibilidade.
- **PATCH:** indica correções de erros ou pequenas melhorias.

Exemplo de evolução de versões:

```text
1.0.0 → 1.1.0 → 1.1.1 → 2.0.0
```

## Git e Controle de Versão

O **Git** é um sistema de controle de versão distribuído utilizado para acompanhar as alterações realizadas em projetos de software.

Com o Git, é possível:

- Registrar alterações no código;
- Criar pontos de restauração;
- Trabalhar em equipe;
- Criar ramificações para novas funcionalidades;
- Integrar alterações de diferentes desenvolvedores;
- Enviar projetos para plataformas como o GitHub.

Alguns comandos básicos do Git são:

```bash
git init
git add .
git commit -m "mensagem do commit"
git status
git log
git push
git pull
```

O fluxo básico de trabalho consiste em realizar alterações nos arquivos, adicionar essas alterações à área de preparação, criar um commit e enviar o projeto para um repositório remoto.

## Tags, Branches e Boas Práticas no Git

### Tags

As tags são utilizadas para marcar versões importantes do projeto, como lançamentos ou versões estáveis.

Exemplo:

```bash
git tag v1.0.0
git push origin v1.0.0
```

### Branches

As branches, ou ramificações, permitem desenvolver funcionalidades de forma isolada, sem alterar diretamente a versão principal do projeto.

Exemplos de branches:

- `main`: versão principal e estável do projeto;
- `develop`: versão de desenvolvimento;
- `feature/nova-funcionalidade`: branch para uma funcionalidade específica;
- `fix/correcao-de-erro`: branch para correção de problemas.

Comandos relacionados:

```bash
git branch
git branch nome-da-branch
git switch nome-da-branch
git switch -c nova-branch
git merge nome-da-branch
```

### Boas Práticas

Algumas boas práticas no uso do Git são:

- Utilizar mensagens de commit claras e objetivas;
- Criar commits pequenos e relacionados a uma alteração específica;
- Utilizar nomes descritivos para branches;
- Evitar o envio de arquivos desnecessários;
- Criar um arquivo `.gitignore`;
- Manter o projeto atualizado com o repositório remoto;
- Revisar as alterações antes de realizar o commit.

## IDE e Visual Studio Code

Uma **IDE**, ou Ambiente de Desenvolvimento Integrado, é uma ferramenta que reúne recursos para facilitar a criação, edição e execução de projetos.

O **Visual Studio Code**, também conhecido como **VS Code**, é um editor de código-fonte utilizado no desenvolvimento de aplicações.

Entre seus principais recursos estão:

- Edição de arquivos;
- Integração com o Git;
- Terminal integrado;
- Extensões;
- Autocompletar código;
- Depuração de aplicações;
- Suporte a diversas linguagens e frameworks.

No desenvolvimento web, o VS Code pode ser utilizado para criar, editar, executar e versionar projetos.

## Node.js e NPM

O **Node.js** é um ambiente que permite executar JavaScript fora do navegador. Ele é utilizado em diversas etapas do desenvolvimento web, especialmente na criação e execução de projetos modernos.

O **NPM**, sigla para **Node Package Manager**, é o gerenciador de pacotes do Node.js. Ele permite instalar bibliotecas, frameworks e outras dependências para um projeto.

Comandos comuns do NPM:

```bash
npm install
npm install nome-do-pacote
npm run dev
npm run build
```

O arquivo `package.json` contém informações importantes sobre o projeto, como:

- Nome e versão;
- Scripts de execução;
- Dependências;
- Configurações do projeto.

O diretório `node_modules` armazena os pacotes instalados e normalmente não deve ser enviado para o repositório. Por isso, ele deve ser incluído no arquivo `.gitignore`.

## Criação de um Projeto React

Para criar e executar o projeto React, foram utilizados os seguintes passos:

### Passo 1: Criar o projeto React

```bash
npx create-react-app meu-projeto-react
```

### Passo 2: Navegar para a pasta do projeto

```bash
cd meu-projeto-react
```

### Passo 3: Abrir o projeto no Visual Studio Code

Caso o VS Code ainda não esteja aberto na pasta do projeto, foi utilizado o comando:

```bash
code .
```

### Passo 4: Iniciar o servidor local

Para executar o projeto e visualizá-lo no navegador, foi utilizado o comando:

```bash
npm start
```

Após executar esse comando, a aplicação React fica disponível em um endereço local indicado no terminal, geralmente:

```text
http://localhost:3000
```

## Deploy e Hospedagem com Vercel

O deploy é o processo de publicar uma aplicação para que ela possa ser acessada pela internet.

A **Vercel** é uma plataforma de hospedagem utilizada principalmente para aplicações frontend e projetos desenvolvidos com frameworks JavaScript.

O processo de publicação pode ser realizado conectando um repositório do GitHub à Vercel. Após essa conexão, a plataforma pode identificar o projeto, realizar o processo de build e disponibilizar uma URL pública.

As principais etapas são:

1. Criar um projeto React;
2. Desenvolver a aplicação utilizando o VS Code;
3. Criar um repositório no GitHub;
4. Inicializar o Git no projeto;
5. Realizar o commit das alterações;
6. Enviar o projeto para o GitHub utilizando o push;
7. Acessar a Vercel;
8. Importar o repositório do GitHub;
9. Configurar o projeto;
10. Realizar o deploy;
11. Acessar a aplicação por meio da URL gerada.

Uma das vantagens desse processo é o deploy automático. Sempre que novas alterações são enviadas para o repositório conectado, a Vercel pode gerar uma nova versão da aplicação.

## Atividade Prática

A atividade prática consistiu no desenvolvimento de uma aplicação React utilizando o Visual Studio Code como ambiente de desenvolvimento.

Após o desenvolvimento, o projeto foi versionado com o Git e enviado para um repositório no GitHub. Em seguida, o repositório foi conectado à Vercel, possibilitando a publicação da aplicação e a realização de deploys automáticos.

Ao final da atividade, a aplicação ficou disponível online por meio de uma URL pública fornecida pela Vercel.

### Tecnologias Utilizadas

- React;
- JavaScript;
- Node.js;
- NPM;
- Git;
- GitHub;
- Visual Studio Code;
- Vercel.

## Conclusão

A aula apresentou conceitos fundamentais para o desenvolvimento e a publicação de aplicações frontend. Foram abordados o controle de versões com Git, o versionamento semântico, a criação de projetos React, o uso do Visual Studio Code e o processo de deploy utilizando a Vercel.

Com esse fluxo, é possível desenvolver uma aplicação, controlar suas alterações, armazenar o código em um repositório remoto e disponibilizá-la na internet.
