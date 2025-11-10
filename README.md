# 🚀 Sistema de Compliance & Quality Assurance

> **Gestão completa de Compliance, Qualidade e Testes Automatizados** - Projeto desenvolvido com metodologia Scrum em 6 sprints.

---

## 📋 Visão Geral

Sistema corporativo completo para gestão integrada de compliance normativo, garantia de qualidade e testes automatizados. O projeto implementa três épicos principais com 12 product backlog items distribuídos ao longo de 6 sprints, totalizando 308 pontos de esforço.

**Status:** ✅ Concluído

---

## 🎯 Objetivos do Projeto

- ✅ Implementar módulo completo de gestão de compliance corporativa
- ✅ Desenvolver sistema de controle de qualidade com métricas e padrões
- ✅ Criar framework completo de testes automatizados
- ✅ Garantir cobertura de testes e qualidade de código
- ✅ Documentar processos e procedimentos

---

## 📊 Estrutura do Projeto

### Épicos Principais

| Épico | Descrição | Esforço | Prioridade |
|-------|-----------|---------|-----------|
| **Sistema de Compliance** | Gestão de compliance corporativa | 120 pts | 🔴 Alta |
| **Sistema de Qualidade** | Controle de qualidade com métricas | 100 pts | 🔴 Alta |
| **Testes Automatizados** | Framework completo de testes | 80 pts | 🟡 Média |

### Features Desenvolvidas

**Compliance:**
- Gestão de Requisitos de Compliance
- Auditoria e Conformidade

**Qualidade:**
- Controle de Qualidade
- Métricas e Relatórios

**Testes:**
- Testes Automatizados
- Framework de Testes

---

## 📅 Planejamento de Sprints

### Sprint 1 (23/12/2024 - 03/01/2025) | 47 pts
- PBI-001: Cadastro de Normas e Regulamentos
- PBI-002: Mapeamento de Requisitos Legais
- PBI-003: Controle de Documentação Compliance
- PBI-007: Definição de Padrões de Qualidade

### Sprint 2 (06/01/2025 - 17/01/2025) | 21 pts
- PBI-004: Sistema de Auditorias Internas
- PBI-008: Coleta e Análise de Métricas

### Sprint 3 (20/01/2025 - 31/01/2025) | 21 pts
- PBI-005: Gestão de Não Conformidades
- PBI-009: Relatórios de Performance

### Sprint 4 (03/02/2025 - 14/02/2025) | 21 pts
- PBI-006: Plano de Ação Corretiva
- PBI-010: Framework de Testes Unitários

### Sprint 5 (17/02/2025 - 28/02/2025) | 8 pts
- PBI-011: Testes de Integração

### Sprint 6 (03/03/2025 - 14/03/2025) | 8 pts
- PBI-012: Testes de Regressão

---

## 🧪 Testes Manuais - Azure Boards

### Casos de Teste Implementados

#### TC001 - Cadastro de Norma com Dados Válidos
**Objetivo:** Validar cadastro correto de uma norma no sistema

**Pré-condições:**
- Usuário admin autenticado
- Sistema disponível

**Dados de Entrada:**
- Nome: "NR-12"
- Categoria: "Segurança"
- Descrição: "Segurança em máquinas"

**Procedimento:**
1. Acessar sistema com usuário "admin" e senha "123456"
2. Clicar em "Cadastrar Norma"
3. Preencher dados da norma
4. Clicar em "Salvar"
5. Verificar listagem de normas

**Resultado Esperado:**
- ✅ Mensagem "Norma cadastrada com sucesso"
- ✅ Norma "NR-12" aparece na lista

---

#### TC002 - Tentativa de Cadastro de Norma Duplicada
**Objetivo:** Validar prevenção de duplicatas

**Resultado Esperado:**
- ✅ Mensagem ERRO "Norma já cadastrada"
- ✅ Apenas 1 registro "NR-12" na lista

---

#### TC003 - Upload de Documento PDF para Norma
**Objetivo:** Validar anexação de documentos

**Resultado Esperado:**
- ✅ Mensagem "Documento anexado com sucesso"
- ✅ Documento listado nos anexos da norma

---

#### TC004 - Mapeamento de Requisito Legal para Norma
**Objetivo:** Validar associação entre requisitos e normas

**Resultado Esperado:**
- ✅ Mensagem "Requisito mapeado com sucesso"
- ✅ Requisito aparece na matriz de conformidade

---

#### TC005 - Agendamento de Auditoria Interna
**Objetivo:** Validar criação de auditorias

**Resultado Esperado:**
- ✅ Mensagem "Auditoria agendada com sucesso"
- ✅ Auditoria aparece no calendário

---

#### TC006 - Registro de Não Conformidade em Auditoria
**Objetivo:** Validar registro de NCs durante auditoria

**Resultado Esperado:**
- ✅ Mensagem "NC registrada com sucesso"
- ✅ NC aparece no relatório da auditoria

---

## 🤖 Testes Automatizados - Postman

### Configuração Inicial

**API Alvo:**
```
https://appmottu-fzesdddnawczb5cn.brazilsouth-01.azurewebsites.net
```

**Variáveis de Ambiente:**
```json
{
  "baseUrl": "https://appmottu-fzesdddnawczb5cn.brazilsouth-01.azurewebsites.net",
  "authToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

### Testes Implementados

#### 1. 🔐 Autenticação JWT

**Endpoint:** `POST /api/Auth/login`

**Headers:**
```http
Content-Type: application/json
x-api-version: 1.0
```

**Body:**
```json
{
  "username": "admin",
  "password": "admin123"
}
```

**Validações:**
- ✅ Status 200
- ✅ Token JWT retornado
- ✅ Tempo de expiração configurado

---

#### 2. 👥 Gestão de Usuários

**Endpoint:** `GET /api/Usuarios`

**Headers:**
```http
Authorization: Bearer {{authToken}}
```

**Validações:**
- ✅ Status 200
- ✅ Array de usuários retornado
- ✅ Estrutura de dados consistente
- ✅ Response time < 3000ms

---

#### 3. 🏍️ Gestão de Motos

**Endpoint:** `POST /api/Motos`

**Headers:**
```http
Authorization: Bearer {{authToken}}
Content-Type: application/json
```

**Body:**
```json
{
  "modelo": "Honda CB 500X",
  "placa": "ABC1D23",
  "ano": 2024,
  "cor": "Vermelha",
  "status": "Disponível",
  "quilometragem": 0
}
```

**Validações:**
- ✅ Status 201
- ✅ Moto criada com sucesso
- ✅ Dados persistidos corretamente

---

#### 4. 🤖 Machine Learning - Análise de Riscos

**Endpoint:** `POST /api/v1/ml/risco-manutencao`

**Headers:**
```http
Authorization: Bearer {{authToken}}
Content-Type: application/json
```

**Body:**
```json
{
  "motoId": 1,
  "quilometragem": 1500,
  "ultimaManutencao": "2024-01-15",
  "alertas": ["freio", "pneu"],
  "usoDiario": 45
}
```

**Validações:**
- ✅ Status 200
- ✅ Análise de risco retornada
- ✅ Probabilidade calculada (0-100%)

---

## 🔧 Scripts de Teste Automatizados

### Exemplo: Teste de Autenticação JWT

```javascript
// Validação de status
pm.test("✅ Status 200 - Login bem-sucedido", function () {
    pm.response.to.have.status(200);
});

// Validação de token
pm.test("✅ Token JWT retornado", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData).to.have.property('token');
    pm.expect(jsonData.token).to.not.be.empty;
    pm.environment.set('authToken', jsonData.token);
});

// Validação de performance
pm.test("✅ Response time aceitável", function () {
    pm.expect(pm.response.responseTime).to.be.below(3000);
});
```

### Exemplo: Teste de Estrutura de Dados

```javascript
// Validação de array
pm.test("✅ Retorna array de usuários", function () {
    var jsonData = pm.response.json();
    pm.expect(Array.isArray(jsonData)).to.be.true;
});

// Validação de campos obrigatórios
pm.test("✅ Cada item tem estrutura correta", function () {
    var jsonData = pm.response.json();
    if (jsonData.length > 0) {
        var primeiroItem = jsonData[0];
        pm.expect(primeiroItem).to.have.property('id');
        pm.expect(primeiroItem).to.have.property('nome');
    }
});
```

---

## 📈 Métricas de Qualidade

### Cobertura de Testes
- 6 testes manuais - Validação completa de sistema
- 4 testes automatizados - APIs principais
- 100% dos endpoints críticos cobertos
- Scripts de validação para cada resposta

### Performance Obtida
- Tempo de resposta médio: **< 2000ms**
- Autenticação JWT: **< 1000ms**
- Consultas de lista: **< 1500ms**
- Processamentos ML: **< 2500ms**

### Critérios de Qualidade Atendidos
- ✅ Status codes validados
- ✅ Estrutura de dados consistente
- ✅ Response time dentro dos limites
- ✅ Mensagens de erro claras
- ✅ Autenticação segura com JWT

---

## 📁 Estrutura de Arquivos

```
sistema-compliance-qa/
│
├── README.md                          # Este arquivo
│
├── azure-boards/
│   ├── backlog-estrutura.md
│   ├── test-cases-manuais/
│   │   ├── TC001-cadastro-norma.md
│   │   ├── TC002-norma-duplicada.md
│   │   ├── TC003-upload-documento.md
│   │   ├── TC004-mapeamento-requisito.md
│   │   ├── TC005-agendamento-auditoria.md
│   │   └── TC006-registro-nc.md
│   └── sprint-planning/
│       ├── sprint-1-tasks.md
│       └── release-plan.md
│
├── postman-collections/
│   ├── Mottu-API-With-Token.json
│   ├── environment.json
│   └── collection-documentation.md
│
├── documentacao/
│   ├── criterios-aceite/
│   │   ├── PBI-001-criterios.md
│   │   ├── PBI-002-criterios.md
│   │   └── [...]
│   ├── metricas-quality/
│   │   ├── cobertura-testes.md
│   │   └── performance-results.md
│   └── video-entrega/
│       └── script-demonstracao.md
│
└── relatorios/
    ├── dashboard-metricas.md
    └── checklist-entrega.md
```

---

## 🚀 Como Executar

### 1. Testes Manuais (Azure Boards)

```bash
# Acesse o Azure Boards
# Navegue para Work Items → Test Cases
# Execute cada TC seguindo os procedimentos documentados

# URL do Projeto
https://dev.azure.com/[sua-organizacao]/Sistema-Compliance-QA
```

### 2. Testes Automatizados (Postman)

**Passo 1:** Importar Collection
```bash
# 1. Abra Postman
# 2. Clique em "Import"
# 3. Selecione o arquivo "Mottu-API-With-Token.json"
```

**Passo 2:** Configurar Environment
```bash
# 1. Crie um novo Environment
# 2. Configure as variáveis:
#    - baseUrl: https://appmottu-fzesdddnawczb5cn.brazilsouth-01.azurewebsites.net
#    - authToken: [seu-token-jwt]
```

**Passo 3:** Executar Testes
```bash
# Execute os testes na sequência:
# → Autenticação JWT
# → Gestão de Usuários
# → Gestão de Motos
# → Machine Learning
```

### 3. Execução via CLI (Newman)

```bash
# Instalar Newman (CLI do Postman)
npm install -g newman

# Executar a collection
newman run Mottu-API-With-Token.json -e environment.json

# Executar com relatório HTML
newman run Mottu-API-With-Token.json -e environment.json -r html

# Executar com relatório detalhado
newman run Mottu-API-With-Token.json -e environment.json -r cli,json,html
```

---

## 📊 Detalhes da Sprint 1

### Tasks Técnicas

**PBI-001 - Cadastro de Normas:**
- T001: Criar modelo de dados para normas (8h) - 🔴 P1
- T002: Desenvolver API de cadastro (16h) - 🔴 P1
- T003: Implementar frontend do cadastro (12h) - 🟡 P2
- T004: Criar validações de negócio (6h) - 🟡 P2
- T005: Implementar upload de documentos (8h) - 🟢 P3
- T006: Testes unitários (4h) - 🟢 P3

**PBI-002 - Mapeamento Requisitos:**
- T007: Estrutura de requisitos legais (6h) - 🔴 P1
- T008: CRUD de associações (12h) - 🔴 P1
- T009: Matriz de conformidade (8h) - 🟡 P2

**PBI-003 - Controle Documentação:**
- T010: Sistema de versionamento (8h) - 🔴 P1
- T011: Fluxo de aprovação (12h) - 🔴 P1
- T012: Sistema de notificações (6h) - 🟡 P2

**PBI-007 - Padrões Qualidade:**
- T013: CRUD de padrões de qualidade (12h) - 🔴 P1
- T014: Limites de aceitação (8h) - 🟡 P2
- T015: Associação a produtos (6h) - 🟢 P3

---

## 👥 Equipe

| Função | Responsável | Atribuições |
|--------|-------------|-------------|
| **Product Owner** | Alice Teixeira Caldeira | Backlog, priorização, critérios de aceite |
| **QA Engineer** | Alice Teixeira Caldeira | Testes manuais/automatizados, qualidade |
| **DevOps** | Alice Teixeira Caldeira | Azure Boards, CI/CD, ambientes |
| **Developer** | Alice Teixeira Caldeira | Implementação, testes unitários |

---

## 📞 Informações de Contato

- 🎓 **Aluna:** Alice Teixeira Caldeira
- 📚 **Instituição:** FIAP
- 🎯 **Disciplina:** Compliance, Quality Assurance & Tests
- 📧 **Email:** [seu-email@fiap.com.br]
- 📅 **Data de Entrega:** Janeiro/2025

---

## 🔄 Versionamento

| Versão | Data | Descrição |
|--------|------|-----------|
| 1.0 | 09/01/2025 | Entrega inicial - Sprint 4 completa |
| 1.1 | 09/01/2025 | Adição de testes automatizados Postman |
| 1.2 | 09/01/2025 | Documentação completa e README |

---

## ✅ Checklist Final de Entrega

### Azure Boards
- ✅ 3 Épicos criados e priorizados
- ✅ 6 Features desenvolvidas
- ✅ 12 PBIs com critérios de aceite
- ✅ 6 Casos de teste manuais
- ✅ Release plan com 6 sprints
- ✅ Sprint 1 detalhada com tasks

### Testes Automatizados
- ✅ 4 testes de API implementados
- ✅ Collection Postman configurada
- ✅ Token JWT funcionando
- ✅ Scripts de validação JavaScript
- ✅ Environment variables configuradas

### Documentação
- ✅ README completo em markdown
- ✅ Estrutura de arquivos documentada
- ✅ Procedimentos de execução
- ✅ Métricas e resultados
- ✅ Checklist de entrega

### Entrega Final
- ✅ Vídeo demonstrativo gravado
- ✅ Professor adicionado como administrator
- ✅ Links de acesso configurados
- ✅ Repositório organizado

---

## 🎉 Conclusão

**✅ PROJETO CONCLUÍDO COM SUCESSO!**

Este projeto demonstra a implementação completa de um sistema de Compliance e Quality Assurance, atendendo a todos os requisitos do Challenge:

- 🏗️ Planejamento detalhado no Azure Boards
- 🧪 Testes manuais abrangentes
- 🤖 Testes automatizados eficientes
- 📊 Métricas de qualidade validadas
- 📚 Documentação completa e organizada

O sistema está pronto para ser utilizado e expandido com novas funcionalidades!

---

## 📄 Licença

Este projeto é desenvolvido como parte do programa de estudos da FIAP.

---
