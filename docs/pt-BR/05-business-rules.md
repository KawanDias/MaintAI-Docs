# 5. Regras de negócio

## 5.1 Objetivo

As regras de negócio definem como o MaintAI deverá interpretar a disponibilidade de materiais e identificar situações que possam comprometer ordens de manutenção programadas.

A primeira versão deverá utilizar regras determinísticas e explicáveis. Não há dependência de inteligência artificial ou machine learning no MVP.

## 5.2 Disponibilidade de materiais

A regra inicial prevista é:

```text
Quantidade disponível =
    Quantidade física
    - Quantidade reservada
    - Quantidade comprometida que ainda não tenha sido descontada
```

A implementação deverá definir claramente quais reservas e compromissos já estão refletidos na quantidade reservada ou disponível. Um mesmo compromisso não poderá ser descontado duas vezes.

### Conceitos

- **Quantidade física:** quantidade registrada fisicamente no estoque.
- **Quantidade reservada:** parcela destinada a uma ou mais necessidades identificadas.
- **Quantidade comprometida:** parcela associada a outras necessidades e que ainda não tenha sido descontada no cálculo.
- **Quantidade disponível:** parcela que pode ser considerada para utilização, após os descontos aplicáveis.

A regra exata de contabilização deverá ser validada durante a implementação do modelo de dados.

## 5.3 Cálculo do déficit

A regra inicial é:

```text
Déficit = Quantidade necessária - Quantidade disponível para a ordem
```

Interpretação:

- Se o resultado for maior que zero, existe insuficiência de materiais.
- Se o resultado for igual a zero, a quantidade disponível atende exatamente à necessidade.
- Se o resultado for menor que zero, a disponibilidade supera a quantidade necessária.

Para apresentação operacional, um déficit negativo pode ser tratado como ausência de déficit, preservando-se a quantidade excedente quando ela for relevante.

## 5.4 Reservas e compromissos

Materiais já reservados ou comprometidos com outras ordens não devem ser tratados como livres para uma nova manutenção.

A análise deverá evitar dupla contagem ou dupla dedução de reservas. A origem e o estado dos compromissos precisam ser compreendidos antes de aplicar o cálculo.

## 5.5 Múltiplos depósitos

A disponibilidade deverá ser analisada considerando diferentes depósitos.

Quando houver material em outro depósito, o sistema poderá indicar a existência de uma alternativa de transferência. Essa possibilidade deverá ser apresentada para avaliação do responsável.

O MaintAI não deverá efetuar transferências automaticamente no MVP.

## 5.6 Prazo de reposição

O motor deverá considerar o prazo estimado de reposição do fornecedor, quando disponível.

A análise deverá relacionar o prazo de reposição à data programada da manutenção. Se a reposição estimada não ocorrer a tempo, essa condição deverá contribuir para a avaliação do risco.

A documentação inicial não define uma fórmula universal para datas, atrasos ou incerteza do fornecedor; esses critérios deverão ser especificados durante a implementação.

## 5.7 Criticidade e prioridade

A análise deverá considerar:

- Criticidade do equipamento.
- Prioridade da ordem.
- Data programada da manutenção.
- Déficit de materiais.
- Disponibilidade em outros depósitos.
- Prazo de reposição.
- Existência de alternativas.

A forma de ponderar esses fatores e os limites entre níveis de risco ainda deverá ser definida e documentada. Não se deve presumir uma matriz ou pontuação que ainda não foi aprovada.

## 5.8 Classificação de risco

A classificação deverá ser:

- Determinística na primeira versão.
- Baseada em regras de negócio explícitas.
- Explicável ao usuário.
- Reproduzível em testes.
- Fundamentada nos dados disponíveis.

Os níveis e critérios exatos de classificação permanecem como decisão de projeto a ser detalhada.

## 5.9 Alertas

Quando for identificada insuficiência ou condição de risco, o alerta deverá apresentar, conforme disponibilidade dos dados:

- Equipamento.
- Ordem de manutenção.
- Data programada.
- Material em falta.
- Quantidade necessária.
- Quantidade disponível.
- Quantidade faltante.
- Prazo estimado de reposição.
- Criticidade do equipamento.
- Nível de risco.
- Recomendações.

## 5.10 Recomendações e aprovação humana

O sistema poderá sugerir:

- Verificar disponibilidade em outros depósitos.
- Avaliar transferência de materiais.
- Solicitar ou antecipar uma compra.
- Consultar o fornecedor.
- Reavaliar o planejamento da manutenção.

As recomendações não deverão executar ações automaticamente. O usuário responsável deverá avaliar e decidir se aprova ou rejeita cada recomendação.

A decisão deverá ser registrada no histórico, incluindo responsável, decisão, justificativa e data, conforme os dados disponíveis.

## 5.11 Limite funcional

O MaintAI identifica riscos relacionados à disponibilidade de materiais e à execução de manutenções programadas. Não deverá afirmar que prevê falhas físicas de equipamentos.
