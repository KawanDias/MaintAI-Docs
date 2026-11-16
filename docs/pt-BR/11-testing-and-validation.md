# 11. Testes e validação

## 11.1 Objetivo

Validar se o MaintAI identifica corretamente insuficiências de materiais, considera reservas e depósitos, classifica riscos conforme as regras definidas e apresenta alertas e recomendações coerentes.

Os testes deverão utilizar dados simulados na primeira versão. Todos os resultados derivados desses dados deverão ser identificados como demonstrativos.

## 11.2 Tipos de teste previstos

### Testes unitários

Validar funções isoladas, especialmente cálculos de disponibilidade, déficit e regras de classificação.

### Testes de integração

Validar a comunicação entre serviços, banco de dados e componentes da aplicação.

### Testes do motor de risco

Verificar o processamento de ordens, materiais, estoques, reservas, depósitos, prazos e criticidade.

### Testes de interface

Verificar a apresentação de ordens, materiais, alertas, recomendações, dashboard e histórico.

### Testes de cenário

Executar simulações que representem situações operacionais previstas no contexto do projeto.

## 11.3 Cenários essenciais

| ID | Cenário | Resultado esperado |
|---|---|---|
| CT-001 | Estoque disponível atende à quantidade necessária | Não identificar déficit para o material analisado |
| CT-002 | Estoque disponível é inferior à quantidade necessária | Identificar déficit positivo |
| CT-003 | Parte do estoque está reservada | Não contabilizar a parcela reservada como livre |
| CT-004 | Existem compromissos ainda não descontados | Considerar os compromissos sem duplicar descontos |
| CT-005 | Existe saldo em outro depósito | Identificar a alternativa para avaliação |
| CT-006 | Prazo de reposição ultrapassa a data da manutenção | Considerar a condição na análise de risco |
| CT-007 | Equipamento possui criticidade elevada | Considerar a criticidade na classificação |
| CT-008 | Ordem possui prioridade definida | Considerar a prioridade na análise |
| CT-009 | Há insuficiência e risco identificado | Gerar alerta com os dados disponíveis |
| CT-010 | Há alternativas possíveis | Apresentar recomendações para avaliação |
| CT-011 | Recomendação é aprovada | Registrar decisão, responsável e data |
| CT-012 | Recomendação é rejeitada | Registrar decisão, justificativa quando informada e data |
| CT-013 | Usuário consulta dashboard | Exibir os indicadores calculados a partir dos registros |
| CT-014 | Usuário consulta histórico | Apresentar decisões registradas |

## 11.4 Exemplo de validação manual

Cenário fictício:

- Equipamento: bomba industrial BP-04.
- Manutenção: daqui a cinco dias.
- Material: rolamento industrial.
- Quantidade necessária: três unidades.
- Quantidade disponível: uma unidade.

Cálculo esperado:

```text
Déficit = 3 - 1
Déficit = 2 unidades
```

O sistema deverá identificar a insuficiência de duas unidades e, em seguida, considerar reservas, outros depósitos e prazo de reposição antes de apresentar a classificação e as recomendações.

## 11.5 Validação dos alertas

Um alerta deverá apresentar, conforme disponibilidade:

- Ordem e equipamento.
- Data programada.
- Material.
- Quantidade necessária.
- Quantidade disponível.
- Quantidade faltante.
- Prazo estimado de reposição.
- Criticidade.
- Nível de risco.
- Recomendações.

A informação apresentada deverá permitir que o usuário compreenda a origem do alerta.

## 11.6 Validação das recomendações

Os testes deverão confirmar que:

- Recomendações são apresentadas como alternativas.
- O usuário pode aprovar ou rejeitar.
- A decisão é registrada.
- O sistema não executa automaticamente compras, transferências ou alterações no SAP.

## 11.7 Métricas e resultados

O projeto deverá permitir calcular:

- Ordens analisadas.
- Ordens com materiais insuficientes.
- Alertas antecipados.
- Tempo médio de antecedência dos alertas.
- Recomendações aprovadas.
- Pendências resolvidas.
- Materiais com maior incidência de falta.
- Equipamentos com maior exposição a riscos.

Não inventar percentuais de economia, redução de paradas ou aumento de produtividade. Resultados de simulações devem ser identificados como simulados.

## 11.8 Registro dos testes

A documentação de validação deverá registrar:

- Identificador do teste.
- Cenário e dados utilizados.
- Resultado esperado.
- Resultado obtido.
- Situação (aprovado ou reprovado).
- Observações e eventuais defeitos.

## 11.9 Critério geral de validação

O fluxo principal deverá ser reproduzível: receber ordem, identificar materiais, calcular disponibilidade, detectar déficit, classificar risco, gerar alerta, apresentar recomendação, registrar decisão e atualizar acompanhamento.
