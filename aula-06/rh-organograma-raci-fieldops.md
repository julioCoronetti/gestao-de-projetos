# Recursos Humanos — Organograma e Matriz RACI do Projeto FieldOps

## 1. Identificação

| Campo | Informação |
|---|---|
| **Projeto** | FieldOps — Sistema de Gerenciamento e Execução de Inspeções em Campo |
| **Docente Orientador** | Prof. Me. Deivison S. Takatu |
| **Data** | 02/09/2026 |

---

## 2. Organograma do Projeto

```mermaid
flowchart TD
    PAT[Patrocinador / Docência SENAI] --> GP[Gerente de Projeto / Mobile Lead<br/>Julio Coronetti Regino]
    GP --> BE[Backend & API REST<br/>Pedro Vieira]
    GP --> DB[Banco de Dados<br/>Juan]
    GP --> WEB[Frontend Web<br/>Matheus]
    GP --> MOB[Frontend Mobile & QA<br/>Julio Coronetti Regino e Gizela Alves]
    GP --> DEVOPS[DevOps, Repo & Infra<br/>Murilo]
```

### Papéis e Responsabilidades

| Integrante | Papel Principal | Foco Técnico |
|---|---|---|
| Julio Coronetti Regino | Gerente de Projeto / Mobile Lead | Planejamento, integração das frentes, QR Code, SQLite e fila Outbox |
| Gizela Alves | Desenvolvedora Mobile e QA | Telas de checklist, captura de evidências, usabilidade e testes em campo |
| Pedro Vieira | Líder de Backend | API REST Spring Boot, JWT/RBAC, snapshots JSONB e sync idempotente |
| Matheus | Líder de Frontend Web | Dashboard administrativo, construtor de modelos, agendamento e revisão |
| Juan | Administrador de Banco de Dados | Modelagem relacional PostgreSQL, migrations DDL e seeds de teste |
| Murilo | DevOps e Governança | GitHub Actions (CI/CD), Docker Compose, gestão de riscos e deploy |

---

## 3. Matriz RACI

Legenda:
- **R (Responsible / Responsável):** executa a atividade.
- **A (Accountable / Aprovador):** responde pela entrega final e aprova o resultado.
- **C (Consulted / Consultado):** fornece insumos técnicos ou valida decisões antes da conclusão.
- **I (Informed / Informado):** recebe atualização sobre andamento e resultado.

| Atividade / Entrega | Julio | Gizela | Pedro | Matheus | Juan | Murilo |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| 1. Termo de Abertura, Escopo e EAP | A / R | I | C | I | C | C |
| 2. Cronograma, RACI e Comunicação | A / R | C | C | C | C | C |
| 3. Orçamento, Riscos e Governança | C | I | C | I | I | A / R |
| 4. Arquitetura e Contratos OpenAPI | C | I | A / R | C | C | C |
| 5. Modelagem Relacional e DER (PostgreSQL) | I | I | C | I | A / R | I |
| 6. Scripts DDL de Migrations e Seeds | I | I | C | I | R | A |
| 7. Autenticação JWT e Controle RBAC (API) | C | I | A / R | C | C | I |
| 8. Modelos Versionados e Snapshots JSONB | C | I | A / R | C | C | I |
| 9. Endpoint de Sincronização em Lote | C | C | A / R | I | C | I |
| 10. Dashboard e Cadastros Web | I | I | C | A / R | I | I |
| 11. Construtor de Modelos e Revisão Web | I | I | C | A / R | I | I |
| 12. Login, Listagem e Leitor QR Code Mobile | A / R | R | C | I | I | I |
| 13. Checklist Dinâmico, Fotos e Não Conformidades | C | A / R | C | I | I | I |
| 14. Banco Local SQLite e Fila Outbox | A / R | C | C | I | I | I |
| 15. Docker Compose e Pipeline CI/CD | I | I | C | C | C | A / R |
| 16. Testes Integrados Ponta a Ponta (E2E) | R | R | R | R | R | A |
| 17. Consolidação Final e Apresentação | A / R | R | R | R | R | R |
