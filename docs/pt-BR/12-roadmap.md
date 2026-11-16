# 12. Roadmap

## 12.1 Visão geral

O desenvolvimento do MaintAI será dividido em fases para permitir a validação progressiva da solução. A estimativa inicial é de **8 a 10 semanas**, sujeita à disponibilidade de tempo e à complexidade técnica.

A sequência poderá ser ajustada conforme a evolução do projeto.

## 12.2 Fases de desenvolvimento

### Fase 1 — Descoberta e requisitos

Atividades:
- Documentar o problema.
- Definir usuários.
- Identificar casos de uso.
- Definir regras de negócio.
- Estabelecer critérios de aceitação.
- Delimitar o escopo da primeira versão.

**Entrega:** documento de requisitos.

### Fase 2 — Arquitetura e modelagem

Atividades:
- Definir arquitetura.
- Definir entidades.
- Criar relacionamentos.
- Planejar APIs.
- Planejar estrutura do projeto.

**Entrega:** diagramas de arquitetura e modelo de dados.

### Fase 3 — Preparação do ambiente

Atividades:
- Instalar Visual Studio Code.
- Instalar Node.js LTS.
- Instalar Git.
- Instalar SAP CAP CLI.
- Configurar SQLite.
- Instalar extensões necessárias.
- Criar o repositório Git.

Comando previsto para instalar o SAP CAP CLI:

```bash
npm install -g @sap/cds-dk
```

Comandos para verificar o ambiente:

```bash
node -v
npm -v
git --version
cds -v
```

Criação inicial do projeto:

```bash
cds init maintai --nodejs
cd maintai
cds watch
```

**Entrega:** ambiente funcional e aplicação CAP inicial executando localmente.

### Fase 4 — Banco de dados

Atividades:
- Criar schema CDS.
- Implementar entidades.
- Criar relacionamentos.
- Criar dados simulados.
- Testar consultas.
- Validar integridade dos dados.

**Entrega:** banco local estruturado e populado.

### Fase 5 — Backend e serviços

Atividades:
- Criar serviços CAP.
- Criar APIs.
- Implementar operações de consulta.
- Implementar validações.
- Organizar regras de negócio.

**Entrega:** backend funcional.

### Fase 6 — Motor de análise de risco

Atividades:
- Identificar ordens programadas.
- Consultar materiais.
- Calcular disponibilidade.
- Identificar déficits.
- Considerar reservas.
- Considerar depósitos.
- Considerar prazos.
- Classificar riscos.
- Gerar alertas.
- Gerar recomendações.

**Entrega:** motor de análise funcional e testável.

### Fase 7 — Interface

Atividades:
- Desenvolver interface com SAP Fiori / UI5.
- Criar dashboard.
- Criar tela de ordens.
- Criar tela de materiais.
- Criar visualização de estoque.
- Criar alertas.
- Criar recomendações.
- Criar histórico de decisões.

**Entrega:** interface utilizável.

### Fase 8 — Integração entre componentes

Atividades:
- Conectar frontend e backend.
- Conectar backend e banco.
- Validar fluxo de dados.
- Testar comunicação.
- Tratar erros.

**Entrega:** aplicação integrada.

### Fase 9 — Integração SAP

Atividades:
- Estudar APIs e mecanismos de integração disponíveis.
- Identificar fontes de dados necessárias.
- Preparar autenticação e autorização.
- Implementar leitura de informações.
- Validar sincronização.
- Documentar limitações.

A integração com um SAP corporativo real dependerá de acesso autorizado, ambiente disponível e APIs habilitadas.

**Entrega:** integração demonstrável ou protótipo de integração, conforme os recursos disponíveis.

### Fase 10 — Testes e validação

Atividades:
- Testes unitários.
- Testes de integração.
- Testes do motor de risco.
- Testes de disponibilidade.
- Testes de reservas.
- Testes de múltiplos depósitos.
- Testes de atrasos de fornecedores.
- Testes de recomendações.
- Testes de interface.
- Simulações de cenários industriais.

**Entrega:** documentação de testes e resultados.

### Fase 11 — Implantação

Atividades:
- Preparar ambiente de implantação.
- Configurar SAP HANA Cloud.
- Ajustar configurações.
- Preparar persistência.
- Publicar aplicação, quando houver infraestrutura disponível.
- Validar execução.

**Entrega:** aplicação implantada ou demonstração local documentada, dependendo dos recursos disponíveis.

### Fase 12 — Documentação e portfólio

Atividades:
- Criar README em português.
- Criar README em inglês.
- Documentar arquitetura.
- Documentar modelo de dados.
- Documentar APIs.
- Documentar regras de negócio.
- Adicionar diagramas.
- Adicionar capturas de tela.
- Criar demonstração.
- Registrar resultados dos testes.
- Explicar decisões técnicas.

**Entrega:** projeto organizado e apresentável profissionalmente no GitHub.

## 12.3 Cronograma estimado

| Período | Atividade principal |
|---|---|
| Semana 1 | Requisitos e descoberta |
| Semana 2 | Arquitetura, modelagem e ambiente |
| Semana 3 | Banco de dados e backend |
| Semana 4 | Serviços e regras de negócio |
| Semana 5 | Motor de análise de risco |
| Semana 6 | Interface e dashboard |
| Semana 7 | Integração entre componentes |
| Semana 8 | Testes e ajustes |
| Semana 9 | Integração SAP e implantação |
| Semana 10 | Documentação e apresentação |

O cronograma é uma estimativa inicial, não um compromisso de prazo. A ordem poderá ser ajustada conforme a evolução e a disponibilidade dos recursos.

## 12.4 Entregáveis finais

Ao final do projeto, estão previstos:

1. Código-fonte completo.
2. Banco de dados estruturado.
3. Dados de demonstração.
4. Backend SAP CAP.
5. APIs funcionais.
6. Motor de análise de risco.
7. Interface SAP Fiori / UI5.
8. Dashboard.
9. Sistema de alertas.
10. Sistema de recomendações.
11. Histórico de decisões.
12. Testes.
13. Documentação técnica.
14. Diagramas de arquitetura e fluxos.
15. README em português.
16. README em inglês.
17. Capturas de tela.
18. Demonstração funcional.
19. Repositório GitHub organizado.
