# Gerenciamento das Aquisições — Projeto FieldOps

## 1. Identificação

| Campo | Informação |
|---|---|
| **Projeto** | FieldOps — Sistema de Gerenciamento e Execução de Inspeções em Campo |
| **Gerente do Projeto** | Murilo Antunes da Silva |
| **Data** | 26/09/2026 |

---

## 2. Tabela de Gerenciamento das Aquisições

| ID | Cód. EAP | Item a ser Adquirido | Urgência | Motivo da Decisão de Compra | Fornecedores Potenciais | Qtde | Custo Unitário (R$) | Custo Total (R$) | Previsão de Entrega | Observações |
|---:|---|---|---|---|---|---:|---:|---:|---|---|
| 1 | 6.1 | Instância de aplicação em nuvem (EC2 t3.small / VPS equivalente) | 4 — Alta | Hospedar a API REST Spring Boot e containers de homologação | AWS / DigitalOcean / Azure | 4 meses | 120,00 | 480,00 | 07/09/2026 | Pode usar cota AWS Academy durante o semestre |
| 2 | 2.2 | Banco de dados gerenciado PostgreSQL | 5 — Muito Alta | Persistência central das inspeções, usuários e snapshots JSONB | AWS RDS / Supabase / Neon | 4 meses | 140,00 | 560,00 | 07/09/2026 | Em dev local roda via Docker sem custo |
| 3 | 3.5 | Serviço de Object Storage (armazenamento S3) | 4 — Alta | Armazenar fotografias e evidências enviadas pelos técnicos | AWS S3 / Cloudflare R2 / MinIO | 4 meses | 45,00 | 180,00 | 14/09/2026 | MinIO local utilizado em ambiente de testes |
| 4 | 4.1 | Hospedagem do painel administrativo Web | 3 — Média | Disponibilizar interface React para acesso dos supervisores | Vercel / Netlify / AWS Amplify | 4 meses | 50,00 | 200,00 | 14/09/2026 | Plano gratuito aplicável em ambiente acadêmico |
| 5 | 6.1 | Registro de domínio e DNS | 2 — Baixa | Endereço amigável e certificado HTTPS para acesso à plataforma | Registro.br / Cloudflare / Namecheap | 1 un (anual) | 60,00 | 60,00 | 21/09/2026 | Certificado SSL emitido via Let's Encrypt |
| 6 | 5.2 | Smartphones Android para testes de campo | 5 — Muito Alta | Validar leitor de QR Code, câmera, GPS e operação offline real | Samsung / Motorola (varejo local) | 2 un | 750,00 | 1.500,00 | 14/09/2026 | Uso prioritário dos aparelhos da própria equipe quando disponível |
| 7 | 5.5 | Chips 4G/5G com plano de dados móveis | 3 — Média | Simular queda e retorno de conectividade durante testes externos | Vivo / Claro / TIM | 4 meses (2 linhas) | 80,00 | 320,00 | 21/09/2026 | Valor referente ao pacote conjunto das 2 linhas por mês |
| 8 | 4.2 | Rolo de etiquetas térmicas sintéticas para QR Code | 4 — Alta | Identificação física de equipamentos nos testes práticos de bancada | Mercado Livre / Kalunga / Distribuidora local | 1 rolo (1.000 un) | 120,00 | 120,00 | 18/09/2026 | Resistentes a umidade e poeira |
| 9 | 6.3 | Impressão de etiquetas, guias rápidos e checklists de teste | 2 — Baixa | Apoio aos testes piloto presenciais com usuários | Gráfica local / SENAI | 1 cj | 90,00 | 90,00 | 10/11/2026 | Material complementar para validação final |
| 10 | 5.1 | Serviço de build de aplicativo mobile (Expo EAS) | 4 — Alta | Gerar pacotes APK instaláveis para testes em Android | Expo Application Services | 4 meses | 0,00 | 0,00 | 14/09/2026 | Plano gratuito atende o volume de builds do MVP |
| 11 | 6.1 | Plataforma de repositório Git e CI/CD | 5 — Muito Alta | Versionamento do código e execução automatizada de pipelines | GitHub (Student Pack / Free) | 4 meses | 0,00 | 0,00 | 17/08/2026 | Já provisionado no início do projeto |
| | | **Total Estimado de Aquisições** | | | | | | **3.510,00** | | |

---

## 3. Critérios de Aceitação e Encerramento das Aquisições

- **Serviços de nuvem e software:** verificação de disponibilidade dos endpoints, limites de cota e validação de faturas/créditos acadêmicos antes do encerramento mensal.
- **Materiais físicos e equipamentos de teste:** conferência de recebimento, teste de leitura das etiquetas QR Code e validação de funcionamento da câmera/armazenamento nos dispositivos.
- **Encerramento:** confirmação formal de entrega de todos os itens contratados e revisão de eventuais renovações após o período piloto de 4 meses.
