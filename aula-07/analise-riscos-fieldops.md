# Análise de Riscos — Projeto FieldOps

## 1. Identificação

| Campo | Informação |
|---|---|
| **Projeto** | FieldOps — Sistema de Gerenciamento e Execução de Inspeções em Campo |
| **Responsável** | Julio Coronetti Regino / Equipe FieldOps |
| **Data** | 12/09/2026 |

---

## 2. Escalas de Probabilidade, Impacto e Severidade

### Escala de Probabilidade

| Nível | Classificação | Critério |
|---:|---|---|
| 1 | Muito Baixa | Improvável (< 10%) |
| 2 | Baixa | Pouco provável (10% a 30%) |
| 3 | Média | Possível ao longo do projeto (31% a 50%) |
| 4 | Alta | Provável sem ação preventiva (51% a 70%) |
| 5 | Muito Alta | Quase certa (> 70%) |

### Escala de Impacto

| Nível | Classificação | Efeito em Prazo, Custo, Escopo ou Qualidade |
|---:|---|---|
| 1 | Muito Baixo | Atraso < 1 dia; impacto imperceptível ao usuário |
| 2 | Baixo | Atraso de 2 a 3 dias; falha secundária contornável |
| 3 | Médio | Atraso de 4 a 7 dias; funcionalidade relevante afetada |
| 4 | Alto | Atraso de 8 a 14 dias; módulo principal bloqueado |
| 5 | Muito Alto | Atraso > 15 dias; perda de dados ou inviabilização da entrega |

### Níveis de Severidade (`Severidade = Probabilidade × Impacto`)

- **Baixa (1 a 6):** monitorar periodicamente.
- **Média (8 a 12):** aplicar ação preventiva planejada.
- **Alta / Crítica (15 a 25):** ação imediata de mitigação ou eliminação com acompanhamento semanal.

---

## 3. Identificação e Análise Qualitativa dos Riscos (Causa, Risco e Consequência)

| ID | Risco | Causa | Consequência | Tipo | Prob (P) | Imp (I) | Severidade | Prioridade |
|---|---|---|---|---|---:|---:|---:|---:|
| R01 | Indisponibilidade de rede durante apresentação final | Instabilidade do Wi-Fi no local ou falha de acesso externo | Impossibilidade de demonstrar o sistema ao vivo | Operacional | 4 | 5 | 20 | 1 |
| R02 | Duplicação de vistorias ou conflito na sincronização em lote | Reenvio automático do mobile após oscilação de sinal 4G | Registros duplicados no PostgreSQL e laudos inconsistentes | Técnico | 4 | 4 | 16 | 2 |
| R03 | Perda de respostas ou fotos durante execução offline | Encerramento abrupto do app pelo SO ou bateria esgotada | Retrabalho do técnico em campo e perda de evidências | Técnico | 3 | 5 | 15 | 3 |
| R04 | Sobrecarga de armazenamento e lentidão no upload de fotos | Imagens capturadas em resolução nativa (> 8 MB por foto) | Timeout de sincronização e aumento de custo de storage | Técnico / Custo | 4 | 3 | 12 | 4 |
| R05 | Desalinhamento entre contratos da API e frontends Web/Mobile | Alteração de DTOs no backend sem aviso prévio às frentes | Quebra de telas integradas e atraso nas entregas da Sprint | Técnico / Comunicação | 3 | 4 | 12 | 5 |
| R06 | Edição de modelo de checklist afetando inspeções já realizadas | Alteração direta no cadastro de perguntas em uso | Histórico de laudos antigos adulterado ou ilegível | Técnico / Qualidade | 2 | 5 | 10 | 6 |
| R07 | Acúmulo de entregas acadêmicas em semanas de avaliação | Sobreposição de prazos de outras disciplinas do semestre | Queda de ritmo e risco de atraso nos testes finais | Prazo / RH | 3 | 3 | 9 | 7 |
| R08 | Dificuldade de leitura de QR Code em ambiente industrial escuro | Baixa luminosidade ou etiquetas desgastadas nos equipamentos | Atraso no check-in presencial da inspeção | Operacional | 3 | 2 | 6 | 8 |
| R09 | Falha na execução de migrations no ambiente Docker | Divergência entre versões locais do PostgreSQL e scripts DDL | Ambiente de desenvolvimento quebrado para a equipe | Técnico | 2 | 3 | 6 | 9 |

---

## 4. Plano de Respostas e Responsáveis

| ID | Abordagem | Ação Preventiva (Mitigação / Eliminação) | Ação de Contingência | Responsável |
|---|---|---|---|---|
| R01 | Evitar | Manter ambiente espelho completo via `docker-compose.yml` rodando localmente no notebook da apresentação | Alternar para execução local (`localhost`) ou roteamento 4G dedicado | Murilo |
| R02 | Mitigar | Gerar UUID único no mobile para cada operação na fila Outbox e validar idempotência no endpoint da API | Ignorar UUIDs já processados no servidor retornando confirmação sem regravar | Pedro Vieira |
| R03 | Mitigar | Persistir cada resposta e referência de foto no SQLite local imediatamente após a interação do técnico | Restaurar automaticamente o rascunho da inspeção em aberto ao reabrir o app | Julio Coronetti Regino |
| R04 | Mitigar | Redimensionar e comprimir imagens no aplicativo mobile (máximo ~300 KB) antes de gravar na fila | Enviar fotos em requisições separadas com retomada controlada | Julio e Gizela |
| R05 | Mitigar | Documentar contratos em OpenAPI/Swagger antes da codificação dos frontends e notificar via PR | Realizar reunião técnica curta entre Pedro, Matheus e Julio para ajuste imediato | Pedro Vieira |
| R06 | Evitar | Gerar snapshot JSONB imutável dos itens do checklist no momento do agendamento da inspeção | Bloquear exclusão física e manter versionamento explícito de templates | Pedro e Juan |
| R07 | Mitigar | Priorizar funcionalidades P0 (MVP) nas primeiras sprints e acompanhar o avanço semanalmente | Redistribuir tarefas entre integrantes ou postergar itens P2 para pós-MVP | Julio Coronetti Regino |
| R08 | Mitigar | Habilitar controle de flash/lanterna na tela do leitor e validar contraste das etiquetas impressas | Permitir seleção manual do equipamento pelo código identificador em caso de dano na etiqueta | Gizela Alves |
| R09 | Mitigar | Padronizar versão da imagem PostgreSQL no Docker Compose e validar migrations na esteira de CI | Executar reset controlado do volume de desenvolvimento com script `seed.sql` | Juan |

---

## 5. Monitoramento dos Riscos

- Revisão da matriz a cada início de Sprint para atualizar probabilidade e impacto dos riscos abertos.
- Acompanhamento de gatilhos técnicos (tempo de resposta da API > 300 ms, falha de build no CI ou falhas de sincronização nos testes piloto).
- Registro de novos riscos diretamente no repositório como issues categorizadas.
