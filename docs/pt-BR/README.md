# MaintAI — Industrial Maintenance Intelligence

Documentação oficial do **MaintAI**, uma aplicação complementar ao SAP voltada à identificação antecipada de riscos de atraso ou comprometimento de manutenções programadas por indisponibilidade de peças, materiais e componentes.

O projeto propõe uma camada de análise e apoio à decisão para equipes industriais. A primeira versão será desenvolvida de forma independente, com dados simulados e banco local, mantendo a arquitetura preparada para uma futura integração com SAP ERP / SAP S/4HANA e SAP HANA Cloud.

> **Status:** projeto em desenvolvimento. As funcionalidades, arquitetura e integrações descritas representam o planejamento atual e não devem ser interpretadas como funcionalidades já implementadas.

## Objetivo

Identificar, antes da data planejada, ordens de manutenção que podem ser prejudicadas pela falta de materiais. Para isso, o MaintAI relaciona ordens, equipamentos, materiais, estoques, reservas, depósitos e prazos de reposição, apresentando riscos, alertas e recomendações para avaliação humana.

O MaintAI **não substitui o SAP** e não pretende prever falhas físicas de equipamentos. Seu foco é analisar a disponibilidade de materiais necessária à execução das manutenções programadas.

## Documentação

A documentação detalhada está organizada em [`docs/`](.):

| Documento | Conteúdo |
|---|---|
| [Visão geral](01-project-overview.md) | Contexto, proposta, público-alvo e conceitos do projeto |
| [Problema](02-problem-statement.md) | Situação operacional, exemplo e limites das afirmações |
| [Objetivos e escopo](03-objectives-and-scope.md) | Objetivos, MVP, exclusões e critérios de sucesso |
| [Requisitos](04-requirements.md) | Requisitos funcionais e não funcionais iniciais |
| [Regras de negócio](05-business-rules.md) | Disponibilidade, déficit, risco e decisões |
| [Casos de uso](06-use-cases.md) | Atores e fluxos operacionais |
| [Arquitetura](07-system-architecture.md) | Componentes, responsabilidades e tecnologias |
| [Modelo de dados](08-data-model.md) | Entidades e relacionamentos previstos |
| [Motor de análise de risco](09-risk-analysis-engine.md) | Fluxo, entradas, regras e saídas da análise |
| [Estratégia de integração SAP](10-sap-integration-strategy.md) | Abordagem gradual para integração futura |
| [Testes e validação](11-testing-and-validation.md) | Estratégia de testes e cenários |
| [Roadmap](12-roadmap.md) | Fases e cronograma estimado |
| [Glossário](13-glossary.md) | Termos utilizados |
| [Diagramas](../diagrams/README.md) | Diagramas previstos para a documentação |

O histórico de alterações está em [`../CHANGELOG.md`](../CHANGELOG.md).

## Tecnologias previstas

- **JavaScript e Node.js:** desenvolvimento do backend.
- **SAP CAP:** estruturação dos serviços e APIs.
- **CDS:** modelagem de dados e definição dos serviços.
- **SQLite:** banco inicial para desenvolvimento local e testes.
- **SAP Fiori / SAPUI5:** interface web.
- **SAP HANA Cloud:** banco previsto para uma etapa posterior.
- **SQL:** consultas e manipulação de dados.
- **Git e GitHub:** versionamento e publicação.
- **Python:** possibilidade futura para análises avançadas, caso exista necessidade real.

O ambiente principal de desenvolvimento previsto é o Visual Studio Code.

## Princípios do projeto

1. Começar com uma aplicação independente e dados simulados.
2. Priorizar regras determinísticas, transparentes e explicáveis no MVP.
3. Não contabilizar materiais reservados como disponíveis.
4. Considerar estoques de diferentes depósitos e prazos de reposição.
5. Manter as recomendações sujeitas à aprovação humana.
6. Não executar compras, transferências ou alterações no SAP automaticamente.
7. Identificar claramente dados fictícios e resultados de simulação.
8. Não divulgar métricas de economia ou produtividade sem resultados medidos.

## Cenário demonstrativo

Uma bomba industrial BP-04 possui manutenção programada para daqui a cinco dias. A ordem exige três rolamentos, mas há somente uma unidade disponível. O déficit inicial é de duas unidades. O MaintAI deverá verificar reservas, outros depósitos e prazo de reposição, classificar o risco e apresentar um alerta com alternativas para o planejador.

Esse cenário é **fictício** e serve para demonstrar o fluxo esperado.

## Escopo e limitações

A primeira versão contempla cadastros, ordens, associação de materiais, cálculo de disponibilidade, reservas, identificação de déficits, classificação de risco por regras, alertas, recomendações, decisão humana, dashboard e histórico.

Não fazem parte do escopo inicial: IA generativa, machine learning complexo, previsão de falhas físicas, integração automática com todos os módulos SAP, execução automática de compras ou transferências, alteração automática de ordens SAP, aplicativo mobile nativo e integração com sensores em tempo real.

## Integração SAP

A integração com SAP ERP / SAP S/4HANA e a utilização de SAP HANA Cloud são etapas posteriores. Dependem de ambiente disponível, acesso autorizado, APIs habilitadas e definição dos mecanismos de autenticação e sincronização. A ausência desses recursos não deve bloquear a construção do protótipo local.

## Organização do repositório

Este repositório contém exclusivamente a documentação do MaintAI. O código-fonte da aplicação deverá permanecer em seu próprio repositório.

```text
MaintAI-Documentation/
├── README.md
└── docs/
    ├── 01-project-overview.md
    ├── 02-problem-statement.md
    ├── 03-objectives-and-scope.md
    ├── 04-requirements.md
    ├── 05-business-rules.md
    ├── 06-use-cases.md
    ├── 07-system-architecture.md
    ├── 08-data-model.md
    ├── 09-risk-analysis-engine.md
    ├── 10-sap-integration-strategy.md
    ├── 11-testing-and-validation.md
    ├── 12-roadmap.md
    ├── 13-glossary.md
    ├── CHANGELOG.md
    └── diagrams/
        └── README.md
```

## Aviso sobre o contexto industrial

O projeto foi contextualizado para empresas industriais, especialmente o setor de papel e celulose, considerando a possibilidade de aplicação em empresas desse segmento. Isso não representa confirmação de que uma empresa específica possua o problema descrito. O MaintAI deve ser apresentado como uma solução proposta para uma necessidade operacional plausível, e não como resposta a uma falha interna comprovada de qualquer organização.

## Contribuições e evolução

A documentação representa uma especificação inicial. Entidades, regras, arquitetura e requisitos poderão ser refinados durante as fases de descoberta, implementação e validação. Alterações relevantes devem ser registradas no changelog.

**Idioma / Language:** Português (Brasil) · [English](../en/README.md)
