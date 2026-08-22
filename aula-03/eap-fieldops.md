# EAP — Estrutura Analítica do Projeto FieldOps

## 1. Identificação

| Campo | Informação |
|---|---|
| **Projeto** | FieldOps — Sistema de Gerenciamento e Execução de Inspeções em Campo |
| **Gerente do Projeto** | Julio Coronetti Regino |
| **Data** | 22/08/2026 |
| **Versão** | 1.0 |

## 2. Estrutura Analítica do Projeto (EAP)

```text
FIELDOPS — SISTEMA INTEGRADO DE INSPEÇÕES EM CAMPO
│
├── 1. GERENCIAMENTO DO PROJETO
│   ├── 1.1 Termo de Abertura e Registro de Partes Interessadas
│   ├── 1.2 Declaração de Escopo e EAP Aprovadas
│   ├── 1.3 Cronograma, Orçamento e Matriz RACI Definidos
│   └── 1.4 Planos de Qualidade, Riscos e Comunicação Documentados
│
├── 2. BANCO DE DADOS E ARQUITETURA
│   ├── 2.1 Arquitetura da Solução e Contratos OpenAPI Definidos
│   ├── 2.2 Modelo Conceitual e Lógico Normalizado (PostgreSQL)
│   └── 2.3 Scripts de Migração DDL e Dados de Demonstração
│
├── 3. BACKEND E API REST
│   ├── 3.1 Módulo de Autenticação JWT e Controle de Acesso (RBAC)
│   ├── 3.2 Cadastros de Usuários, Clientes, Locais e Equipamentos (QR Code)
│   ├── 3.3 Motor de Modelos Versionados e Snapshots Imutáveis
│   ├── 3.4 Fluxo de Agendamento, Execução, Revisão e Auditoria
│   └── 3.5 Endpoint de Sincronização em Lote Idempotente e Upload de Mídias
│
├── 4. INTERFACE ADMINISTRATIVA WEB (SUPERVISOR)
│   ├── 4.1 Autenticação Web e Dashboard de Indicadores
│   ├── 4.2 Telas de Cadastro de Clientes, Locais e Equipamentos (QR Code)
│   ├── 4.3 Construtor Visual de Modelos de Inspeção
│   ├── 4.4 Módulo de Agendamento e Atribuição de Técnicos
│   └── 4.5 Painel de Revisão, Evidências e Histórico de Auditoria
│
├── 5. APLICATIVO MOBILE DE CAMPO (TÉCNICO)
│   ├── 5.1 Autenticação e Sessão Segura no Dispositivo
│   ├── 5.2 Listagem de Inspeções e Leitor de QR Code
│   ├── 5.3 Preenchimento de Checklist Dinâmico, Fotos e Não Conformidades
│   ├── 5.4 Persistência Local Offline-First em SQLite
│   └── 5.5 Fila Outbox e Sincronização Bidirecional
│
└── 6. TESTES, INFRAESTRUTURA E ENTREGA
    ├── 6.1 Conteinerização Docker e Pipeline CI/CD
    ├── 6.2 Testes Automatizados e Validação Ponta a Ponta Offline/Online
    └── 6.3 Pacote de Release, Manual de Execução e Apresentação Final
```

## 3. Dicionário da EAP

| Código | Elemento | Descrição da Entrega e Critério Principal |
|---|---|---|
| 1.0 | Gerenciamento do Projeto | Artefatos de iniciação, planejamento, monitoramento e encerramento do projeto. |
| 1.1 | Termo de Abertura e Partes Interessadas | Formalização de objetivos, premissas, restrições e identificação inicial de stakeholders. |
| 1.2 | Declaração de Escopo e EAP | Definição dos limites do produto, exclusões e decomposição das entregas. |
| 1.3 | Cronograma, Orçamento e RACI | Sequenciamento de atividades, estimativa de custos e matriz de responsabilidades. |
| 1.4 | Planos de Qualidade, Riscos e Comunicação | Critérios de aceitação, matriz de riscos com respostas e plano de comunicação. |
| 2.0 | Banco de Dados e Arquitetura | Estrutura de persistência e especificação técnica de integração entre os componentes. |
| 2.1 | Arquitetura e Contratos OpenAPI | Definição dos componentes (Mobile, Web, API, DB, Storage) e contratos JSON iniciais. |
| 2.2 | Modelo Conceitual e Lógico | Modelagem relacional contemplando usuários, clientes, locais, equipamentos, modelos, inspeções e auditoria. |
| 2.3 | Scripts de Migração e Seeds | Migrations versionadas e carga inicial para testes reproduzíveis. |
| 3.0 | Backend e API REST | Serviços centrais em Java / Spring Boot responsáveis pelas regras de negócio e segurança. |
| 3.1 | Autenticação JWT e RBAC | Emissão/renovação de tokens e bloqueio de rotas por perfil (Admin, Supervisor, Técnico). |
| 3.2 | Cadastros e QR Code | Endpoints de gestão de entidades mestres e identificação única por QR Code. |
| 3.3 | Modelos Versionados e Snapshots | Versionamento de templates de checklist e congelamento imutável no agendamento. |
| 3.4 | Fluxo de Inspeção e Auditoria | Transições de estado (agendada, em andamento, enviada, aprovada, reprovada) e trilha de auditoria. |
| 3.5 | Sincronização Idempotente e Mídias | Recebimento em lote de operações offline sem duplicidade e armazenamento de fotografias. |
| 4.0 | Interface Administrativa Web | Aplicação web para operação de supervisores e administradores. |
| 4.1 | Autenticação e Dashboard Web | Controle de sessão no navegador e painel com métricas e alertas de inspeções. |
| 4.2 | Cadastros Administrativos Web | Telas de manutenção de clientes, locais e equipamentos com etiqueta QR Code. |
| 4.3 | Construtor Visual de Modelos | Editor de seções, perguntas, tipos de resposta, obrigatoriedade e pré-visualização. |
| 4.4 | Agendamento e Atribuição | Seleção de modelo publicado, equipamento, técnico, prioridade e data prevista. |
| 4.5 | Painel de Revisão e Auditoria | Visualização de respostas, fotos, não conformidades, histórico e decisão formal. |
| 5.0 | Aplicativo Mobile de Campo | Aplicação React Native / Expo voltada à execução em campo pelo técnico. |
| 5.1 | Autenticação e Sessão Mobile | Login e manutenção segura de credenciais/sessão para uso em campo. |
| 5.2 | Lista de Inspeções e Leitor QR | Filtros de inspeções atribuídas e validação presencial do equipamento via câmera. |
| 5.3 | Checklist Dinâmico e Evidências | Resposta a itens, observações, captura de fotos, localização e registro de não conformidades. |
| 5.4 | Persistência Local SQLite | Banco local garantindo continuidade do preenchimento sem internet ou após reinício do app. |
| 5.5 | Fila Outbox e Sincronização | Enfileiramento ordenado com UUID idempotente e envio automático ao restabelecer conexão. |
| 6.0 | Testes, Infraestrutura e Entrega | Empacotamento, validação integrada e entrega final do sistema. |
| 6.1 | Docker e Pipeline CI/CD | Arquivos Docker Compose para subida unificada e automação de build/testes no GitHub. |
| 6.2 | Testes e Validação Offline/Online | Testes automatizados e validação de ponta a ponta do ciclo completo em modo avião e online. |
| 6.3 | Release e Apresentação Final | Congelamento da versão de entrega, guia de execução e apresentação executiva. |

## 4. Requisitos Principais Mapeados na EAP

| ID | Requisito | Elemento EAP |
|---|---|---|
| REQ-01 | Controle de acesso por perfil (Admin, Supervisor, Técnico) com JWT | 3.1, 4.1, 5.1 |
| REQ-02 | Gestão de clientes, locais e equipamentos com código QR único | 3.2, 4.2, 5.2 |
| REQ-03 | Construtor de checklists versionados sem impactar inspeções antigas | 3.3, 4.3 |
| REQ-04 | Agendamento e atribuição de inspeções com snapshot imutável | 3.3, 3.4, 4.4 |
| REQ-05 | Execução offline completa no mobile com SQLite e fila Outbox | 5.3, 5.4, 5.5 |
| REQ-06 | Sincronização idempotente em lote evitando duplicação de registros | 3.5, 5.5 |
| REQ-07 | Revisão pelo supervisor com aprovação, reprovação e trilha de auditoria | 3.4, 4.5 |
| REQ-08 | Ambiente reproduzível via Docker e testes automatizados | 6.1, 6.2 |
