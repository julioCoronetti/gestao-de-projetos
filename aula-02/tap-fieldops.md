# Termo de Abertura do Projeto (TAP) — Projeto FieldOps

## 1. Identificação do Projeto

| Campo | Informação |
|---|---|
| **Projeto** | FieldOps — Sistema de Gerenciamento e Execução de Inspeções em Campo |
| **Contexto** | Projeto de Referência da Disciplina de Gestão de Projetos (SENAI ADS) |
| **Patrocinador / Orientação** | Prof. Me. Deivison S. Takatu / Docência SENAI |
| **Gerente do Projeto** | Julio Coronetti Regino |
| **Equipe** | Julio Coronetti Regino, Gizela Alves, Juan, Matheus, Murilo, Pedro Vieira |
| **Data** | 15/08/2026 |
| **Versão** | 1.0 |

## 2. Breve Descrição e Justificativa

O **FieldOps** é uma plataforma integrada composta por **Aplicativo Mobile** (técnicos de campo), **Interface Administrativa Web** (supervisores) e **API REST** central com persistência em banco relacional. O sistema organiza o ciclo completo de inspeções técnicas em campo: criação de modelos de checklist, cadastro de equipamentos com QR Code, agendamento, execução offline-first no celular com captura de evidências, sincronização e revisão/aprovação pelo supervisor.

Justifica-se pela necessidade de eliminar processos baseados em papel, planilhas isoladas e mensagens informais, que causam perda de evidências, falta de rastreabilidade, impossibilidade de operação em áreas sem internet e morosidade na aprovação de laudos.

## 3. Objetivo Geral e Objetivos Específicos

**Objetivo geral:** Desenvolver uma solução integrada (Mobile, Web e API REST) para gerenciar de ponta a ponta o planejamento, a execução offline em campo e a auditoria de inspeções técnicas.

**Objetivos específicos:**
- Disponibilizar dashboard administrativo com indicadores e alertas das inspeções;
- Permitir criação e versionamento de modelos dinâmicos de checklist com snapshots imutáveis;
- Gerenciar clientes, locais e equipamentos identificados por QR Code;
- Permitir agendamento e atribuição de inspeções a técnicos;
- Garantir execução mobile offline-first (SQLite + fila Outbox) com captura de fotos e não conformidades;
- Permitir revisão, aprovação, reprovação ou devolução de inspeções com trilha de auditoria.

## 4. Principais Entregas e Requisitos Iniciais

### Entregas principais
- API REST (autenticação JWT/RBAC, cadastros, templates, snapshots, sincronização em lote, auditoria);
- Banco de dados PostgreSQL modelado e versionado com scripts de migração e dados de demonstração;
- Interface Administrativa Web (dashboard, construtor de modelos, agendamento, painel de revisão);
- Aplicativo Mobile (login, leitor de QR Code, checklist dinâmico, fotos, persistência SQLite e sync);
- Documentação técnica (OpenAPI/Swagger, arquitetura e artefatos de gestão).

### Requisitos iniciais
- Controle de acesso por perfil (Administrador, Supervisor e Técnico);
- Preservação do histórico de inspeções mesmo após alterações em versões futuras do modelo;
- Operação completa sem internet durante a vistoria em campo e sincronização idempotente ao reconectar;
- Rastreabilidade de mudanças de estado e evidências fotográficas vinculadas aos itens.

## 5. Premissas e Restrições

### Premissas
- Supervisores realizam o planejamento, configuração dos modelos e revisão pela interface Web;
- Técnicos executam as vistorias em dispositivos móveis Android/Expo em campo;
- Equipamentos e modelos publicados estarão cadastrados antes do agendamento das inspeções;
- Todos os módulos se comunicam exclusivamente via API REST autenticada.

### Restrições
- Prazo limitado ao semestre acadêmico (previsão de 16 semanas);
- Recursos financeiros e de infraestrutura limitados a ambientes gratuitos, Docker local e cota acadêmica em nuvem;
- Alterações relevantes de escopo devem ser avaliadas para não comprometer o MVP.

## 6. Partes Interessadas (Stakeholders)

| Parte Interessada | Papel / Interesse |
|---|---|
| Docente Orientador e Banca Avaliadora | Acompanhamento metodológico e avaliação das entregas |
| Supervisores de Operações | Planejamento, acompanhamento em dashboard e aprovação de laudos |
| Técnicos de Campo | Execução ágil e confiável das inspeções no aplicativo mobile |
| Administradores de TI | Gestão de acessos, segurança e estabilidade do ambiente |
| Clientes Contratantes | Recebimento de inspeções auditáveis e controle de não conformidades |
| Equipe de Desenvolvimento | Arquitetura, implementação, testes e entrega do sistema |

## 7. Marcos e Estimativa Inicial de Prazo e Custos

| Marco | Previsão |
|---|---|
| Aprovação do TAP, Escopo e EAP | Setembro / 2026 |
| Banco de Dados e API REST base operacionais | Outubro / 2026 |
| Web e Mobile integrados com fluxo offline-first | Novembro / 2026 |
| Testes integrados, homologação e entrega final | Dezembro / 2026 |

- **Prazo estimado:** 16 semanas (agosto a dezembro de 2026).
- **Estimativa inicial:** esforço da equipe técnica de 6 integrantes (~1.080 horas acadêmicas estimadas) e infraestrutura em containers Docker / nuvem acadêmica.
