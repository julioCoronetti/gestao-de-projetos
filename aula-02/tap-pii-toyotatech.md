# Termo de Abertura do Projeto (TAP) — ToyotaTech (PII)

## 1. Identificação do Projeto

| Campo | Informação |
|---|---|
| **Projeto** | ToyotaTech — Acompanhamento Digital de Compra e Entrega de Veículos |
| **Contexto** | Projeto Integrador (PII) — Análise e Desenvolvimento de Sistemas (SENAI) |
| **Patrocinador / Orientação** | Coordenação ADS SENAI / Docentes Orientadores |
| **Gerente do Projeto** | Julio Coronetti Regino |
| **Equipe** | Julio Coronetti Regino, Gizela Alves, Juan Abner Correa, Matheus Pulcinelli, Murilo Antunes, Victor Cavalciuk |
| **Data** | 15/08/2026 |
| **Versão** | 1.0 |

## 2. Breve Descrição e Justificativa

O **ToyotaTech** é uma plataforma composta por aplicativo mobile (React Native / Expo) e backend serverless na AWS (API Gateway, AWS Lambda em Python, DynamoDB e Amazon Cognito), complementada por protótipo web e simulador IoT para rastreamento da linha de montagem.

O projeto justifica-se pela falta de visibilidade em tempo real que clientes enfrentam entre o pedido do veículo na concessionária e a entrega final. Centralizar o acompanhamento de status, dados da garagem e documentos em um aplicativo único reduz ligações de suporte, melhora a experiência do comprador e automatiza o registro de eventos da fábrica.

## 3. Objetivo Geral e Objetivos Específicos

**Objetivo geral:** Desenvolver e implantar um MVP integrado (aplicativo mobile e backend serverless AWS) que permita ao cliente acompanhar todas as etapas da produção e entrega de seu veículo.

**Objetivos específicos:**
- Implementar autenticação segura com Amazon Cognito (e-mail/senha, OTP e login social);
- Disponibilizar consulta de veículos vinculados ao usuário (garagem e busca indexada por chassi);
- Exibir linha do tempo em tempo real dos marcos de fabricação e entrega via eventos de tracking;
- Garantir controle de tráfego (rate limiting) e contratos testados entre backend Python e tipos TypeScript do mobile;
- Integrar protótipo web e stack local de telemetria IoT (MQTT / Node-RED) para demonstração de ponta a ponta.

## 4. Principais Entregas e Requisitos Iniciais

### Entregas principais
- Aplicativo mobile em Expo / React Native (autenticação, perfil, garagem, rastreamento de etapas);
- Backend serverless AWS SAM (`AuthFunction`, `ProfileFunction`, `GarageFunction`, `TrackingFunction`);
- Modelagem NoSQL no DynamoDB (`ProfilesTable`, `GarageTable`, `PurchasesTable`, `TrackingTable`, `AuthRateLimitTable`);
- Suíte de testes unitários e testes de contrato bidirecionais;
- Documentação técnica e relatório de entrega do MVP.

### Requisitos iniciais
- Autenticação JWT via Cognito e validação padronizada de senhas entre mobile e backend;
- Indexação de consultas por chassi, CPF, e-mail e pedido sem varredura completa de tabela;
- Proteção contra abuso em endpoints de autenticação com limites configurados no API Gateway e DynamoDB;
- Execução compatível com restrições do ambiente AWS Academy.

## 5. Premissas e Restrições

### Premissas
- Os integrantes atuarão em frentes integradas (mobile, backend serverless, IoT e documentação);
- O ambiente AWS Academy estará disponível para deploy das Lambdas, DynamoDB e Cognito;
- Contratos JSON entre API e mobile serão mantidos sob versionamento no GitHub com CI automatizado.

### Restrições
- Limite de concorrência de funções Lambda e restrições de sessão/permissões da conta AWS Academy;
- Prazo limitado ao calendário semestral do Projeto Integrador;
- Escopo restrito às funcionalidades do MVP acordadas para apresentação final.

## 6. Partes Interessadas (Stakeholders)

| Parte Interessada | Papel / Interesse |
|---|---|
| Docentes e Banca Avaliadora (SENAI) | Avaliação técnica, aderência ao escopo e validação das entregas |
| Equipe de Desenvolvimento | Execução técnica, integração mobile-cloud e entrega do MVP |
| Cliente Final (Comprador do Veículo) | Acompanhamento transparente da compra, status e documentação |
| Concessionária / Operação Toyota | Redução de chamados manuais e padronização das informações |

## 7. Marcos e Estimativa Inicial de Prazo e Custos

| Marco | Previsão |
|---|---|
| Definição de escopo, arquitetura e modelagem DynamoDB | Agosto / 2026 |
| Autenticação Cognito e APIs iniciais em AWS SAM | Setembro / 2026 |
| Integração Mobile + Tracking + Testes de Contrato | Outubro / 2026 |
| Homologação, ajustes finais e apresentação do MVP | Novembro / 2026 |

- **Prazo estimado:** 16 semanas (agosto a novembro de 2026).
- **Estimativa inicial de recursos/custos:** Equipe acadêmica de 6 integrantes; infraestrutura baseada em camada gratuita / créditos AWS Academy, sem aquisição de licenças comerciais.
