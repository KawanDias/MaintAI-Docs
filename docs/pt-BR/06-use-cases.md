# 6. Casos de uso

## 6.1 Atores

| Ator | Participação |
|---|---|
| Planejador de manutenção | Consulta ordens e alertas; avalia recomendações e registra decisões |
| Almoxarifado | Consulta quantidades físicas, reservas e estoques por depósito |
| Compras e suprimentos | Avalia reposição e consulta prazos de fornecedores |
| Supervisor de manutenção | Acompanha criticidade, prioridades e riscos |
| Gestor industrial | Acompanha indicadores e pendências |
| MaintAI | Processa dados, identifica déficits, classifica riscos e apresenta recomendações |

## 6.2 UC-01 — Consultar equipamentos

**Ator principal:** planejador de manutenção ou supervisor.

**Objetivo:** consultar os equipamentos cadastrados e suas informações relevantes.

**Fluxo básico:**
1. O usuário acessa a área de equipamentos.
2. O sistema apresenta os registros disponíveis.
3. O usuário consulta código, descrição, localização, setor, criticidade e status.

**Dados relacionados:** `Equipment`.

## 6.3 UC-02 — Consultar materiais e estoques

**Ator principal:** profissional de almoxarifado.

**Objetivo:** verificar a situação de materiais e suas quantidades por depósito.

**Fluxo básico:**
1. O usuário seleciona um material.
2. O sistema apresenta os depósitos associados.
3. O sistema exibe quantidade física, reservada e disponível.
4. O usuário avalia a situação do material.

**Dados relacionados:** `Material`, `Stock` e depósito.

## 6.4 UC-03 — Consultar ordens de manutenção

**Ator principal:** planejador de manutenção.

**Objetivo:** acompanhar as ordens programadas e os materiais necessários.

**Fluxo básico:**
1. O usuário acessa a lista de ordens.
2. O sistema apresenta número, equipamento, tipo, data, prioridade e status.
3. O usuário seleciona uma ordem.
4. O sistema apresenta os materiais e quantidades associados.

**Dados relacionados:** `MaintenanceOrder`, `Equipment` e `MaintenanceOrderItem`.

## 6.5 UC-04 — Executar análise de risco

**Ator principal:** MaintAI.

**Objetivo:** identificar ordens que possam ser prejudicadas pela indisponibilidade de materiais.

**Pré-condições:** existência de ordens, itens de materiais e informações de estoque suficientes para a análise.

**Fluxo básico:**
1. O sistema identifica ordens programadas.
2. Consulta os materiais necessários.
3. Consulta a disponibilidade em estoque.
4. Considera reservas e compromissos sem duplicar descontos.
5. Verifica outros depósitos.
6. Considera prazos de reposição disponíveis.
7. Avalia criticidade do equipamento e prioridade da ordem.
8. Identifica déficits.
9. Classifica o risco com regras determinísticas.
10. Registra a situação e gera alertas quando aplicável.

**Pós-condição:** situação analisada disponível para consulta e acompanhamento.

## 6.6 UC-05 — Consultar alerta

**Ator principal:** planejador de manutenção.

**Objetivo:** compreender uma insuficiência de material identificada pelo sistema.

**Fluxo básico:**
1. O usuário acessa os alertas.
2. Seleciona um alerta.
3. O sistema apresenta ordem, equipamento, data, material, quantidades, déficit, prazo de reposição disponível, criticidade e risco.
4. O usuário analisa as informações.

## 6.7 UC-06 — Avaliar recomendação

**Ator principal:** planejador de manutenção ou responsável designado.

**Objetivo:** registrar a decisão humana sobre uma alternativa sugerida.

**Fluxo básico:**
1. O usuário consulta o alerta e suas recomendações.
2. Seleciona uma recomendação.
3. Avalia a alternativa.
4. Aprova ou rejeita a recomendação.
5. Informa justificativa, quando aplicável.
6. O sistema registra decisão, responsável e data.
7. O histórico e o acompanhamento são atualizados.

**Regra:** a aprovação não significa que o MaintAI executará automaticamente uma compra, transferência ou alteração de ordem.

## 6.8 UC-07 — Acompanhar dashboard

**Ator principal:** supervisor ou gestor industrial.

**Objetivo:** acompanhar a situação consolidada das ordens e alertas.

**Fluxo básico:**
1. O usuário acessa o dashboard.
2. O sistema apresenta indicadores.
3. O usuário consulta ordens com materiais insuficientes, alertas ativos, equipamentos críticos, materiais recorrentes e recomendações pendentes.
4. O usuário aprofunda a consulta conforme necessário.

## 6.9 UC-08 — Consultar histórico de decisões

**Ator principal:** planejador, supervisor ou gestor autorizado.

**Objetivo:** consultar decisões anteriores relacionadas a alertas e recomendações.

**Fluxo básico:**
1. O usuário acessa o histórico.
2. O sistema apresenta registros disponíveis.
3. O usuário consulta alerta relacionado, responsável, decisão, justificativa e data.

## 6.10 Fluxo ponta a ponta demonstrativo

1. Uma ordem de manutenção é recebida ou cadastrada.
2. O MaintAI identifica equipamento e data programada.
3. Identifica materiais e quantidades necessárias.
4. Consulta estoques e reservas.
5. Verifica possíveis quantidades em outros depósitos.
6. Considera prazo de reposição.
7. Identifica eventual déficit.
8. Classifica a situação como risco, conforme regras definidas.
9. Gera alerta e recomendações.
10. O planejador avalia as alternativas.
11. A decisão é encaminhada ao setor responsável ou registrada como pendência.
12. O sistema atualiza histórico e indicadores.

## 6.11 Observações

Os casos de uso representam o comportamento planejado. A disponibilidade de dados, permissões e integração com sistemas externos poderá alterar os fluxos durante a implementação.
