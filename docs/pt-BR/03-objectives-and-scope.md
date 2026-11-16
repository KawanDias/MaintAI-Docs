# 3. Objetivos e escopo

## 3.1 Objetivo geral

Construir uma plataforma complementar ao SAP capaz de identificar antecipadamente riscos relacionados à indisponibilidade de materiais para manutenções programadas, apresentando alertas, recomendações e indicadores que apoiem a tomada de decisão.

## 3.2 Objetivos específicos

1. Receber informações de equipamentos e ordens de manutenção.
2. Identificar materiais necessários para cada ordem.
3. Consultar a disponibilidade dos materiais em estoque.
4. Considerar reservas e materiais comprometidos.
5. Verificar possíveis alternativas em outros depósitos.
6. Considerar prazos de reposição de fornecedores.
7. Identificar déficits de materiais.
8. Avaliar criticidade dos equipamentos e proximidade da manutenção.
9. Classificar riscos por regras determinísticas e explicáveis.
10. Gerar alertas antecipados.
11. Apresentar recomendações para avaliação dos responsáveis.
12. Disponibilizar dashboards e indicadores.
13. Registrar decisões e histórico de acompanhamento.

## 3.3 Escopo do MVP

A primeira versão deverá priorizar a implementação completa do fluxo principal, utilizando dados simulados e banco local.

### Funcionalidades obrigatórias

- Cadastro de equipamentos.
- Cadastro de materiais.
- Cadastro de depósitos e estoques.
- Cadastro e consulta de ordens de manutenção.
- Associação de materiais às ordens.
- Controle de quantidades necessárias e disponíveis.
- Consideração de reservas.
- Identificação de déficits.
- Classificação de risco baseada em regras.
- Geração de alertas.
- Geração de recomendações.
- Aprovação ou rejeição humana das recomendações.
- Dashboard operacional.
- Histórico de decisões.
- Testes automatizados ou reproduzíveis.

## 3.4 Fora do escopo inicial

Os seguintes itens não devem ser iniciados como parte do MVP:

- Inteligência artificial generativa.
- Machine learning complexo.
- Previsão de falhas físicas de equipamentos.
- Integração automática com todos os módulos SAP.
- Execução automática de compras.
- Transferências automáticas de estoque.
- Alterações automáticas em ordens do SAP.
- Aplicativo mobile nativo.
- Integração com sensores industriais em tempo real.

Esses recursos poderão ser estudados futuramente, desde que exista justificativa, disponibilidade de dados e condições técnicas.

## 3.5 Evolução posterior

Após a validação do protótipo, poderão ser consideradas:

- Integração autorizada com SAP ERP / SAP S/4HANA.
- Utilização de SAP HANA Cloud.
- Sincronização de dados corporativos.
- Análises mais avançadas, caso exista necessidade real.
- Ampliação dos indicadores e recursos operacionais.

A evolução depende de acesso aos ambientes, APIs e recursos necessários.

## 3.6 Critérios iniciais de conclusão do MVP

O MVP poderá ser considerado funcional quando demonstrar, com dados de teste:

1. Cadastro e consulta dos registros essenciais.
2. Associação entre ordens, equipamentos e materiais.
3. Cálculo consistente de disponibilidade, respeitando reservas.
4. Identificação correta de déficits.
5. Consideração de depósitos alternativos e prazos quando esses dados estiverem disponíveis.
6. Classificação de risco explicável.
7. Geração de alertas com informações suficientes para análise.
8. Apresentação de recomendações sem execução automática.
9. Registro de aprovação ou rejeição e histórico correspondente.
10. Visualização dos principais indicadores no dashboard.
11. Execução dos testes definidos para os cenários principais.

Esses critérios são uma referência inicial e poderão ser detalhados durante a implementação.

## 3.7 Indicadores de resultado

O sistema deverá permitir medir:

- Quantidade de ordens analisadas.
- Quantidade de ordens com materiais insuficientes.
- Quantidade de alertas antecipados.
- Tempo médio de antecedência dos alertas.
- Quantidade de recomendações aprovadas.
- Quantidade de pendências resolvidas.
- Materiais com maior incidência de falta.
- Equipamentos com maior exposição a riscos.

Os indicadores devem ser calculados a partir dos dados efetivamente utilizados nos testes. Resultados simulados devem ser identificados como tais. Não devem ser inventados percentuais de economia, redução de paradas ou aumento de produtividade.
