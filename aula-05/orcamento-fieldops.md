# Orçamento do Projeto FieldOps

## 1. Identificação e Premissas

| Campo | Informação |
|---|---|
| **Projeto** | FieldOps — Sistema de Gerenciamento e Execução de Inspeções em Campo |
| **Responsável pelo Orçamento** | Julio Coronetti Regino / Equipe FieldOps |
| **Data** | 29/08/2026 |
| **Moeda** | Real Brasileiro (BRL — R$) |
| **Período Considerado** | 4 meses (16 semanas / semestre letivo) |

**Premissas adotadas:**
- Valor-hora técnico de referência para estimativa acadêmica de engenharia de software (nível júnior/pleno em formação): **R$ 35,00/h**.
- Serviços de nuvem orçados considerando ambiente de homologação e demonstração (com indicação de custo equivalente de mercado caso não haja isenção estudantil).
- Reserva de contingência fixada em **10%** sobre o subtotal dos custos diretos para cobrir variações de consumo e retrabalho.

## 2. Estimativa Detalhada de Custos (32 itens)

| ID | Categoria | Item | Responsável | Qtde | Unid. | Valor Unit. (R$) | Total (R$) |
|---|---|---|---|---:|---|---:|---:|
| C01 | Mão de Obra — Gestão | Gerenciamento de projeto, EAP e cronograma | Julio | 40 | h | 35,00 | 1.400,00 |
| C02 | Mão de Obra — Gestão | Gestão de riscos, custos e governança Git | Murilo | 35 | h | 35,00 | 1.225,00 |
| C03 | Mão de Obra — Arquitetura | Definição de arquitetura e contratos OpenAPI | Pedro | 30 | h | 35,00 | 1.050,00 |
| C04 | Mão de Obra — Dados | Modelagem conceitual, lógica e DER | Juan | 45 | h | 35,00 | 1.575,00 |
| C05 | Mão de Obra — Dados | Scripts de migração DDL, índices e seeds | Juan | 55 | h | 35,00 | 1.925,00 |
| C06 | Mão de Obra — Backend | Setup Spring Boot, segurança JWT e RBAC | Pedro | 40 | h | 35,00 | 1.400,00 |
| C07 | Mão de Obra — Backend | APIs de cadastros, locais e QR Code | Pedro | 35 | h | 35,00 | 1.225,00 |
| C08 | Mão de Obra — Backend | Motor de templates versionados e snapshots JSONB | Pedro | 45 | h | 35,00 | 1.575,00 |
| C09 | Mão de Obra — Backend | API de agendamento, revisão e auditoria | Pedro | 40 | h | 35,00 | 1.400,00 |
| C10 | Mão de Obra — Backend | Sincronização em lote idempotente e upload de mídias | Pedro | 40 | h | 35,00 | 1.400,00 |
| C11 | Mão de Obra — Web | Setup React/Vite, autenticação e dashboard | Matheus | 45 | h | 35,00 | 1.575,00 |
| C12 | Mão de Obra — Web | Telas de clientes, locais, equipamentos e QR Code | Matheus | 40 | h | 35,00 | 1.400,00 |
| C13 | Mão de Obra — Web | Construtor visual de modelos de checklist | Matheus | 50 | h | 35,00 | 1.750,00 |
| C14 | Mão de Obra — Web | Agendamento, painel de revisão e histórico | Matheus | 45 | h | 35,00 | 1.575,00 |
| C15 | Mão de Obra — Mobile | Setup Expo/React Native, login e listagem | Julio | 40 | h | 35,00 | 1.400,00 |
| C16 | Mão de Obra — Mobile | Leitor de QR Code, câmera e captura de GPS | Julio | 35 | h | 35,00 | 1.225,00 |
| C17 | Mão de Obra — Mobile | Checklist dinâmico, observações e não conformidades | Gizela | 60 | h | 35,00 | 2.100,00 |
| C18 | Mão de Obra — Mobile | Persistência local SQLite e fila Outbox offline | Julio | 65 | h | 35,00 | 2.275,00 |
| C19 | Mão de Obra — QA/Testes | Testes unitários, integração e testes E2E em campo | Gizela | 50 | h | 35,00 | 1.750,00 |
| C20 | Mão de Obra — DevOps | Docker Compose, CI/CD GitHub Actions e deploy | Murilo | 55 | h | 35,00 | 1.925,00 |
| C21 | Infraestrutura Cloud | Instância de aplicação backend (equivalente EC2 t3.small) | Murilo | 4 | mês | 120,00 | 480,00 |
| C22 | Infraestrutura Cloud | Banco de dados gerenciado PostgreSQL (db.t3.micro) | Juan | 4 | mês | 140,00 | 560,00 |
| C23 | Infraestrutura Cloud | Armazenamento de objetos para fotos (S3 / MinIO) | Murilo | 4 | mês | 45,00 | 180,00 |
| C24 | Infraestrutura Cloud | Hospedagem do painel Web (CDN / estático) | Matheus | 4 | mês | 50,00 | 200,00 |
| C25 | Software e Serviços | Registro de domínio e certificado SSL | Murilo | 1 | un | 60,00 | 60,00 |
| C26 | Software e Serviços | Conta/serviço de build mobile (Expo EAS — cota free/base) | Julio | 4 | mês | 0,00 | 0,00 |
| C27 | Software e Serviços | Repositório Git e esteira CI/CD (GitHub Student/Free) | Murilo | 4 | mês | 0,00 | 0,00 |
| C28 | Hardware e Testes | Smartphone Android de teste para validação em campo | Julio | 2 | un | 750,00 | 1.500,00 |
| C29 | Hardware e Testes | Plano de dados móveis 4G/5G para testes de reconexão | Gizela | 4 | mês | 80,00 | 320,00 |
| C30 | Materiais de Campo | Rolo de etiquetas sintéticas para impressão de QR Code | Matheus | 1 | un | 120,00 | 120,00 |
| C31 | Materiais de Apoio | Impressão de etiquetas, manuais e guias de teste | Gizela | 1 | cj | 90,00 | 90,00 |
| C32 | Treinamento e Homologação | Sessão piloto e capacitação de usuários de teste | Julio | 10 | h | 35,00 | 350,00 |

## 3. Estimativa de Três Pontos nos Blocos Críticos

Para os pacotes de maior incerteza técnica, aplicou-se a fórmula PERT `E = (O + 4M + P) / 6`:

| Bloco | Otimista (cO) | Mais Provável (cM) | Pessimista (cP) | Estimativa PERT (R$) |
|---|---:|---:|---:|---:|
| Offline-First SQLite e Fila Outbox (C18) | 1.750,00 | 2.275,00 | 3.150,00 | 2.333,33 |
| Motor de Snapshots e Sync API (C08 + C10) | 2.450,00 | 2.975,00 | 3.850,00 | 3.033,33 |
| Infraestrutura Cloud 4 meses (C21–C24) | 960,00 | 1.420,00 | 2.100,00 | 1.456,67 |

## 4. Consolidação do Orçamento

| Grupo de Custo | Subtotal (R$) | % do Total |
|---|---:|---:|
| Mão de Obra Direta (C01–C20, C32 — 910 h) | 31.850,00 | 81,88% |
| Infraestrutura Cloud e Serviços (C21–C27) | 1.480,00 | 3,81% |
| Hardware e Materiais de Teste (C28–C31) | 2.030,00 | 5,22% |
| **Subtotal de Custos Diretos** | **35.360,00** | **90,91%** |
| Reserva de Contingência (10% sobre custos diretos) | 3.536,00 | 9,09% |
| **Orçamento Total Previsto (Linha de Base + Contingência)** | **38.896,00** | **100,00%** |

## 5. Acompanhamento e Controle de Custos

- **Acompanhamento quinzenal por Sprint:** comparação entre horas planejadas vs. realizadas e consumo real de recursos cloud.
- **Indicadores principais:** Variação de Custo (`VC = VA - CR`) e Índice de Desempenho de Custo (`IDC = VA / CR`).
- **Tratamento de desvios:** caso `IDC < 0,90` ou haja aumento nos custos de armazenamento de mídias, acionar compressão mais restritiva de fotos no mobile, revisar consultas no banco e reequilibrar tarefas entre os integrantes antes de consumir a reserva de contingência.
