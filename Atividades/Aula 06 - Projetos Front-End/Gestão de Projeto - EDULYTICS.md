# Gestão de Projeto Front-End — Projeto Integrador (EDULYTICS)

## 1. Visão Geral do Projeto

Esta documentação descreve o planejamento e a gestão ágil aplicados ao **Projeto Integrador Interdisciplinar — EDULYTICS** ([repositório P.I.-2sem-2026](https://github.com/CauaFelipe1738/P.I.-2sem-2026)), desenvolvido em resposta à demanda SENAI **Desafios relacionados ao Monitoramento do Desempenho Acadêmico de Estudantes**.

### Proposta e Público-Alvo

O **EDULYTICS** é uma plataforma educacional voltada ao acompanhamento do desempenho acadêmico de estudantes. Além de registrar notas e frequência, o sistema propõe integrar informações de comportamento e evolução pedagógica para apoiar decisões personalizadas dos docentes, otimizando processos antes manuais.

- **Público-alvo principal:** Docentes (professores) e Coordenação Pedagógica.
- **Público-alvo secundário:** Alunos (consulta às próprias informações acadêmicas).

### Stack Tecnológica

- **Front-end:** React 19, Vite 8, Tailwind CSS 4, CSS3, Web Storage API (`localStorage`) e `useSyncExternalStore`.
- **Back-end:** Java com Spring Boot, Gradle e integração com Swagger (em `backend_spring/`).
- **Qualidade e Build:** ESLint, testes de normalização em Node.js (`academicoStore.test.js`) e build via Vite.

---

## 2. Gestão de Requisitos (Requisito → História → Tarefa)

Seguindo os conceitos de **Gestão de Requisitos** da Aula 06, as necessidades do sistema foram convertidas em requisitos claros, detalhados em *User Stories* e quebrados em tarefas técnicas executáveis.

### Exemplo de Decomposição

- **Requisito:** O sistema deve permitir o registro e acompanhamento da frequência dos alunos por turma e disciplina.
  - **User Story:** *Como professor, quero registrar a chamada de uma aula selecionando curso, turma e disciplina, para acompanhar a taxa de presença dos estudantes.*
  - **Tarefas:**
    - Criar formulário de seleção de curso, turma, disciplina, data e aula (`frequencia.jsx`).
    - Implementar listagem de alunos com opções de status (`Presente`, `Atraso`, `Falta`, `Justificada`).
    - Persistir registros no estado compartilhado (`academicoStore.js` + `localStorage`).
    - Calcular indicadores de taxa de presença em tempo real.
    - Permitir edição e histórico de correções de chamadas anteriores.

- **Requisito:** O sistema deve calcular indicadores de desempenho e permitir exportação de relatórios.
  - **User Story:** *Como professor ou coordenador, quero visualizar alertas de alunos abaixo de 75% de presença ou com registros de dificuldade e exportar relatórios em CSV, para tomar decisões pedagógicas rápidas.*
  - **Tarefas:**
    - Implementar cálculo de indicadores e alertas no módulo `desempenho.jsx`.
    - Criar filtros combinados de frequência e aprendizagem em `relatorio.jsx`.
    - Implementar geração de prévia, impressão e exportação em CSV.
    - Criar testes unitários de normalização em `academicoStore.test.js`.

---

## 3. Product Backlog, Prioridades e Estimativas

O **Product Backlog** reúne todas as funcionalidades, melhorias e tarefas de infraestrutura necessárias para construir e evoluir a plataforma.

- **Critério de Priorização:** MoSCoW / Criticidade para os critérios de aceite (**Alta**, **Média**, **Baixa**).
- **Critério de Estimativa:** *Story Points* (escala Fibonacci: 1, 2, 3, 5, 8) considerando complexidade relativa, esforço e risco técnico.

| ID | Item do Backlog (User Story / Entrega) | Prioridade | Estimativa (pts) | Módulo / Área |
|---|---|---|---|---|
| **PB-01** | Estrutura base React + Vite + Tailwind e layout do painel | Alta | 5 | `App.jsx`, `index.css` |
| **PB-02** | Tela de login demonstrativa e seleção de perfil (Professor, Aluno, Coordenação) | Alta | 3 | `Login.jsx`, `App.jsx` |
| **PB-03** | Catálogo acadêmico de cursos e alunos com busca, filtro e paginação | Alta | 5 | `CatalogoAcademico.jsx`, `professor.jsx`, `dadosAcademicos.js` |
| **PB-04** | Store compartilhada com persistência local e normalização de dados | Alta | 5 | `academicoStore.js` |
| **PB-05** | Módulo de registro, consulta e correção de frequência | Alta | 8 | `frequencia.jsx` |
| **PB-06** | Módulo de registro e edição de observações e planos de aprendizagem | Alta | 5 | `aprendizagem.jsx` |
| **PB-07** | Painel de desempenho com cálculo de indicadores e alertas (limite 75%) | Alta | 5 | `desempenho.jsx` |
| **PB-08** | Módulo de relatórios com filtros, prévia, impressão e exportação CSV | Média | 5 | `relatorio.jsx` |
| **PB-09** | Telas demonstrativas de Aluno e Coordenação | Baixa | 3 | `alunos.jsx`, `coodernador.jsx` |
| **PB-10** | Estrutura inicial da API Back-end em Spring Boot + Swagger (entidade Aluno) | Média | 8 | `backend_spring/` |
| **PB-11** | Testes automatizados de normalização de dados e validação de build/lint | Alta | 3 | `academicoStore.test.js` |
| **PB-12** | Infraestrutura de banco de dados AWS e deploy do Front-end (S3) | Média | 5 | Infra / DevOps |
| **PB-13** | Documentação técnica e diagramas de arquitetura (ER e Classes) | Média | 3 | `README.md`, `DOCUMENTACAO_TECNICA.md` |

---

## 4. Planejamento de Sprints (Scrum)

O desenvolvimento foi organizado em **Sprints** incrementais de 2 semanas, permitindo inspeção frequente, adaptação e entregas contínuas de valor.

### Sprint 1 — Base da Aplicação e Catálogo (18 pts)
- **Objetivo:** Estruturar o projeto React com Vite e Tailwind, implementar o shell do painel, acesso demonstrativo por perfis e catálogo de cursos/alunos.
- **Itens:** `PB-01`, `PB-02`, `PB-03`, `PB-04`.
- **Incremento entregue:** Aplicação navegável com seleção de perfil e catálogo filtrável de cursos e alunos.

### Sprint 2 — Núcleo Pedagógico, Indicadores e Relatórios (21 pts)
- **Objetivo:** Implementar os fluxos de chamada e acompanhamento pedagógico, além do cálculo de indicadores de desempenho e exportação de relatórios.
- **Itens:** `PB-05`, `PB-06`, `PB-07`, `PB-08`, `PB-11`.
- **Incremento entregue:** Plataforma funcional com registro local de frequência/aprendizagem, alertas de desempenho e exportação CSV.

### Sprint 3 — Back-end, Telas Complementares e Infraestrutura (19 pts)
- **Objetivo:** Iniciar a API REST em Spring Boot com Swagger, finalizar telas demonstrativas, documentar arquitetura e preparar deploy em nuvem.
- **Itens:** `PB-09`, `PB-10`, `PB-12`, `PB-13`.
- **Incremento entregue:** Back-end Spring Boot inicializado, documentação técnica completa com diagramas Mermaid e pipeline de deploy estruturado.

---

## 5. Quadro Kanban

Para acompanhar o fluxo diário de trabalho e evitar tarefas esquecidas ou gargalos de integração, o projeto utiliza um quadro **Kanban** (GitHub Projects) dividido em cinco colunas:

| Backlog | A Fazer (To Do) | Em Andamento (In Progress) | Em Revisão (Code Review) | Concluído (Done) |
|---|---|---|---|---|
| Itens priorizados para Sprints futuras (`PB-12`, melhorias de API) | Tarefas selecionadas para a Sprint atual aguardando início | Tarefas em desenvolvimento ativo em uma branch dedicada | Pull Requests abertos aguardando revisão de pares e checagem de lint/testes | Tarefas que atenderam ao *Definition of Done* e foram integradas à `develop`/`main` |

### Regras do Quadro
- Cada card no Kanban deve estar vinculado a uma **User Story** ou **Tarefa**, possuir responsável definido e estimativa em pontos.
- Limite de WIP (*Work in Progress*): máximo de **2 tarefas em andamento por integrante** para evitar retrabalho e conflitos no Git.

---

## 6. Estratégia de Branches e Versionamento (Git)

Para evitar conflitos no Git e garantir rastreabilidade, o repositório adota um fluxo baseado em **Git Flow** adaptado à estrutura real do projeto:

- **`main`**: Branch de produção, contendo apenas versões estáveis e validadas.
- **`develop`**: Branch de integração contínua das funcionalidades concluídas na Sprint.
- **`feature/<nome>`**: Branches criadas a partir de `develop` para desenvolvimento de novas funcionalidades (ex.: `feature/alunos`, `feature/miniTCC`, `feature/backend_inicio`, `feature/README`).
- **`infra/<nome>`**: Branches dedicadas a infraestrutura e deploy (ex.: `infra/database-aws`, `infra/deploy-frontend-s3`).

### Fluxo de Trabalho
1. Criar branch a partir de `develop` (`git checkout -b feature/nome-da-tarefa`).
2. Realizar commits semânticos e atômicos (`feat:`, `fix:`, `docs:`, `refactor:`, `style:`).
3. Abrir **Pull Request (PR)** para `develop` ao concluir a tarefa.
4. Após revisão e aprovação dos critérios de conclusão, realizar o *merge*.

---

## 7. Definition of Done (DoD) — Critérios de Conclusão

Uma tarefa só é movida para **Concluído (Done)** quando atende a todos os critérios abaixo:

- [x] **Código implementado:** Funcionalidade completa conforme requisitos da User Story.
- [x] **Qualidade de código:** Execução sem erros de `npm run lint` e `npm run build`.
- [x] **Testes realizados:** Testes automatizados (`npm test`) executados e aprovados, além de validação manual dos fluxos principais no navegador.
- [x] **Responsividade verificada:** Interface testada em resoluções desktop e mobile com Tailwind CSS.
- [x] **Revisão concluída:** Pull Request revisado por pelo menos um integrante da equipe, sem conflitos de merge.
- [x] **Integração e documentação:** Alterações integradas na branch `develop` e documentadas no `README.md` ou `DOCUMENTACAO_TECNICA.md` quando aplicável.
