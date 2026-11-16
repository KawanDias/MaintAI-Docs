# 4. Requisitos

## 4.1 Considerações

Este documento consolida os requisitos iniciais derivados da proposta do MaintAI. Eles representam o comportamento esperado do MVP e deverão ser refinados durante a descoberta e a implementação.

Os requisitos não significam que as funcionalidades já estejam implementadas.

## 4.2 Atores

| Ator | Responsabilidade no contexto do sistema |
|---|---|
| Planejador de manutenção | Acompanhar ordens, avaliar alertas e decidir sobre recomendações |
| Almoxarifado | Consultar estoques, reservas e disponibilidade por depósito |
| Compras e suprimentos | Avaliar reposições e prazos de fornecedores |
| Supervisor de manutenção | Acompanhar riscos e prioridades das manutenções |
| Gestor industrial | Consultar indicadores e situação operacional |
| Sistema / motor de análise | Cruzar dados, identificar déficits, classificar riscos e gerar alertas |

## 4.3 Requisitos funcionais

| ID | Requisito | Descrição |
|---|---|---|
| RF-001 | Gestão de equipamentos | O sistema deverá permitir armazenar e consultar código, nome, descrição, localização, setor, criticidade e status do equipamento. |
| RF-002 | Gestão de materiais | O sistema deverá permitir armazenar e consultar código, descrição, unidade de medida, estoque mínimo e fornecedor principal. |
| RF-003 | Gestão de depósitos | O sistema deverá representar depósitos e permitir associar estoques a eles. |
| RF-004 | Gestão de estoque | O sistema deverá registrar quantidade física, reservada e disponível por material e depósito. |
| RF-005 | Gestão de ordens | O sistema deverá armazenar número, equipamento, tipo, data programada, prioridade, status e responsável da ordem. |
| RF-006 | Itens da ordem | O sistema deverá relacionar materiais e quantidades necessárias a cada ordem. |
| RF-007 | Consulta de disponibilidade | O sistema deverá calcular a disponibilidade considerando reservas e compromissos sem duplicar descontos. |
| RF-008 | Análise de depósitos | O sistema deverá verificar possíveis quantidades disponíveis em outros depósitos. |
| RF-009 | Análise de reposição | O sistema deverá considerar prazo estimado de reposição quando essa informação estiver disponível. |
| RF-010 | Identificação de déficit | O sistema deverá comparar a quantidade necessária com a quantidade disponível para a ordem. |
| RF-011 | Classificação de risco | O sistema deverá classificar a situação por regras determinísticas e explicáveis. |
| RF-012 | Alertas | O sistema deverá gerar alertas com ordem, equipamento, data, material, quantidades, déficit, criticidade e nível de risco. |
| RF-013 | Recomendações | O sistema deverá apresentar alternativas para avaliação dos responsáveis. |
| RF-014 | Decisão humana | O sistema deverá permitir registrar aprovação ou rejeição de recomendações. |
| RF-015 | Histórico | O sistema deverá registrar decisões, justificativas, responsáveis e datas. |
| RF-016 | Dashboard | O sistema deverá apresentar indicadores operacionais previstos no projeto. |
| RF-017 | Dados demonstrativos | O sistema deverá permitir execução do MVP com dados simulados claramente identificados. |
| RF-018 | Acompanhamento | O sistema deverá atualizar a situação de alertas e pendências conforme os dados e decisões registrados. |

## 4.4 Requisitos não funcionais iniciais

Os pontos abaixo são diretrizes de qualidade e arquitetura. Metas quantitativas de desempenho, disponibilidade e segurança ainda não foram definidas.

| ID | Requisito | Descrição |
|---|---|---|
| RNF-001 | Explicabilidade | A classificação de risco deverá ser baseada em regras compreensíveis e rastreáveis. |
| RNF-002 | Integridade | O modelo deverá manter relacionamentos consistentes entre ordens, equipamentos, materiais, estoques e alertas. |
| RNF-003 | Rastreabilidade | Decisões e alterações relevantes deverão possuir registro histórico. |
| RNF-004 | Separação de responsabilidades | Interface, serviços, regras de análise e persistência deverão possuir responsabilidades organizadas. |
| RNF-005 | Evolução tecnológica | A arquitetura deverá permitir evolução do banco local para SAP HANA Cloud, conforme viabilidade. |
| RNF-006 | Integração gradual | A integração com SAP deverá ser planejada sem bloquear o desenvolvimento independente do MVP. |
| RNF-007 | Segurança de integração | Uma futura integração deverá utilizar mecanismos autorizados de autenticação e acesso. |
| RNF-008 | Clareza de dados | Dados fictícios e resultados de simulação deverão ser identificados como demonstrativos. |
| RNF-009 | Testabilidade | Regras de negócio e fluxos críticos deverão permitir testes automatizados ou reproduzíveis. |

## 4.5 Regras de aceitação iniciais

- Materiais reservados não podem ser contabilizados como livres.
- O déficit deve refletir a quantidade necessária menos a disponibilidade considerada para a ordem.
- A análise deve identificar quando a reposição estimada ocorre depois da data necessária, se as datas estiverem disponíveis.
- Uma alternativa em outro depósito deve ser apresentada como possibilidade, não como transferência executada.
- Recomendações não podem executar ações automaticamente.
- Aprovações e rejeições devem ser registradas.
- Alertas devem apresentar informações suficientes para que o responsável compreenda a origem do risco.

## 4.6 Dependências e pontos ainda a definir

- Definição final dos níveis e limites de classificação de risco.
- Política de contabilização de compromissos e reservas para evitar dupla dedução.
- Regras de disponibilidade e transferência entre depósitos.
- Formato e frequência de atualização dos dados.
- Perfis de acesso e permissões da aplicação.
- Metas quantitativas de desempenho e disponibilidade.
- APIs e mecanismos concretos para eventual integração SAP.

Esses pontos não devem ser tratados como decisões já tomadas.
