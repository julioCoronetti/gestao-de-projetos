# Plano de Comunicação — Projeto FieldOps

## 1. Identificação

| Campo | Informação |
|---|---|
| **Projeto** | FieldOps — Sistema de Gerenciamento e Execução de Inspeções em Campo |
| **Gerente do Projeto** | Julio Coronetti Regino |
| **Data** | 04/09/2026 |

---

## 2. Matriz do Plano de Comunicação

| Informação / Comunicação | Destinatários (Público) | Responsável (Proprietário) | Canal / Ferramenta | Frequência | Formato / Tipo | Momento de Realização |
|---|---|---|---|---|---|---|
| Alinhamento diário (avanços e bloqueios) | Equipe do projeto (Julio, Gizela, Pedro, Matheus, Juan, Murilo) | Julio Coronetti Regino | Discord (canal de voz/texto) | Diária (15 min) | Síncrono / Verbal e texto curto | Início do turno noturno de trabalho |
| Planejamento de Sprint e divisão de tarefas | Equipe do projeto | Julio e Murilo | Google Meet + GitHub Projects | Quinzenal | Síncrono / Quadro Kanban | Primeiro dia útil de cada Sprint |
| Revisão e demonstração de entregas | Docente orientador, banca e equipe | Equipe (apresentador definido por Sprint) | Presencial em sala / Google Meet | Quinzenal / Por marco | Síncrono / Demonstração ao vivo | Ao encerramento de cada Sprint |
| Atualização de contratos de API e payloads | Matheus (Web), Julio e Gizela (Mobile), Juan (DB) | Pedro Vieira | Swagger UI (`/swagger-ui`) e GitHub PR | Contínua (por alteração) | Assíncrono / Documentação OpenAPI | Antes de mergear alterações de endpoints |
| Alterações de schema e migrations SQL | Pedro (Backend) e Murilo (DevOps) | Juan | GitHub (pasta `database/`) e Discord | Sob demanda (por migration) | Assíncrono / Script SQL + aviso | Antes da atualização dos containers |
| Status de builds, pipelines CI/CD e deploys | Toda a equipe | Murilo | GitHub Actions + webhook Discord | Automática por push/PR | Assíncrono / Log automatizado | A cada commit ou Pull Request |
| Relatório de acompanhamento e riscos | Docente orientador (Prof. Deivison Takatu) | Julio e Murilo | Repositório GitHub (`docs/`) | Mensal e nas avaliações | Assíncrono / Markdown | Ao final de cada mês e entregas formais |
| Escalonamento de defeitos críticos (S1) | Líder da frente afetada e gerente do projeto | Identificador do defeito | GitHub Issue (`bug`) + Discord | Imediata (sob demanda) | Síncrono / Alerta direto | No momento da detecção do erro |
| Validação de usabilidade e feedback de campo | Julio, Gizela e Matheus | Gizela Alves | Formulário / lista de ajustes no GitHub | Por ciclo de testes | Assíncrono / Checklist de validação | Após testes piloto em smartphone |

---

## 3. Diretrizes de Comunicação e Escalonamento

1. **Fonte oficial de decisões:** decisões técnicas relevantes (mudança de contrato JSON, regra de negócio ou escopo) devem ser registradas em Issue ou Pull Request no GitHub.
2. **Prazo de resposta para bloqueios:** dúvidas de integração entre frentes devem ser tratadas em até 24 horas; sem consenso, a equipe realiza chamada rápida de alinhamento para decidir com base nos requisitos do MVP.
3. **Critério de eficácia:** redução de retrabalho por divergência de API e manutenção das entregas sincronizadas ao final de cada Sprint.
