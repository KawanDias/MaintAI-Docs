# 1. Visão geral do projeto

## 1.1 Identificação

| Campo | Descrição |
|---|---|
| Nome | MaintAI — Industrial Maintenance Intelligence |
| Categoria | Sistema de inteligência e apoio à decisão para manutenção industrial |
| Responsabilidade do projeto | Engenheiro Analista & Lead Dev |
| Ambiente de desenvolvimento | Visual Studio Code |
| Situação | Planejado / em desenvolvimento |

## 1.2 Descrição

O MaintAI é uma aplicação complementar ao SAP que tem como finalidade identificar antecipadamente riscos de atraso ou comprometimento de manutenções programadas em razão da indisponibilidade de peças, materiais e componentes necessários à execução dos serviços.

A aplicação deverá cruzar informações de ordens de manutenção, equipamentos, materiais, estoques, reservas, depósitos e fornecedores. A partir dessa análise, deverá indicar possíveis déficits, classificar riscos e apresentar alertas e recomendações aos responsáveis.

O MaintAI não tem como objetivo substituir o SAP. Sua proposta é oferecer uma camada adicional de análise e inteligência operacional, apoiando o processo de decisão dos profissionais envolvidos.

## 1.3 Contexto de desenvolvimento

A aplicação será construída inicialmente como um sistema independente, utilizando dados simulados e banco de dados local. A arquitetura deverá permitir uma evolução futura para integração com SAP ERP / SAP S/4HANA e SAP HANA Cloud.

Essa abordagem permite desenvolver e validar o fluxo principal sem depender, desde o início, de acesso a um ambiente SAP corporativo.

## 1.4 Objetivo central

Identificar ordens de manutenção programadas que possam ser prejudicadas pela falta de materiais, com antecedência suficiente para que os responsáveis avaliem alternativas.

O fluxo de análise deverá:

1. Receber informações de equipamentos e ordens.
2. Identificar os materiais e as quantidades necessárias.
3. Consultar a disponibilidade em estoque.
4. Considerar reservas e materiais comprometidos.
5. Verificar possíveis disponibilidades em outros depósitos.
6. Considerar prazos de reposição dos fornecedores.
7. Identificar déficits.
8. Avaliar criticidade do equipamento e proximidade da manutenção.
9. Classificar o risco de execução.
10. Gerar alertas e recomendações.
11. Registrar decisões e disponibilizar indicadores.

## 1.5 Público-alvo

- Planejadores de manutenção.
- Profissionais de almoxarifado.
- Profissionais de compras e suprimentos.
- Supervisores de manutenção.
- Gestores industriais.

Cada grupo poderá utilizar as informações apresentadas pelo sistema para identificar pendências e apoiar decisões relacionadas à disponibilidade de materiais.

## 1.6 Funcionalidades previstas

### Gestão de equipamentos

Cadastro de código, nome ou descrição, setor industrial, localização, categoria, criticidade e situação operacional.

### Gestão de materiais

Cadastro de código, descrição, categoria, unidade de medida, estoque disponível, estoque reservado, estoque mínimo quando aplicável, fornecedor associado e prazo de reposição.

### Gestão de estoques e depósitos

Acompanhamento de quantidade física, reservada, disponível, comprometida e eventualmente transferível entre depósitos.

### Gestão de ordens de manutenção

Consulta de número da ordem, equipamento, tipo de manutenção, data programada, status, materiais necessários, quantidades, prioridade e responsável.

### Análise de risco

Cruzamento das informações operacionais para identificar situações em que a falta de materiais possa comprometer uma manutenção.

### Alertas e recomendações

Apresentação de déficits, nível de risco, prazo de reposição quando disponível e alternativas para avaliação humana. O sistema não deverá executar automaticamente as recomendações.

### Dashboard

Indicadores de ordens analisadas, ordens com materiais insuficientes, alertas ativos, equipamentos críticos, materiais com maior incidência de falta, recomendações pendentes e histórico.

## 1.7 Princípios

- **Complementaridade:** o MaintAI apoia processos existentes e não substitui o SAP.
- **Antecipação:** identificar riscos antes da data programada.
- **Rastreabilidade:** registrar alertas e decisões.
- **Explicabilidade:** classificar riscos por regras compreensíveis.
- **Decisão humana:** recomendações dependem da avaliação dos responsáveis.
- **Evolução gradual:** começar com dados simulados e integração local.

## 1.8 Limites da proposta

O sistema identifica riscos relacionados à disponibilidade de materiais e à execução de manutenções programadas. Não deve afirmar que prevê falhas físicas de equipamentos.

A contextualização para o setor de papel e celulose representa um cenário de aplicação possível. Não constitui confirmação de que uma empresa específica apresente a situação operacional descrita.
