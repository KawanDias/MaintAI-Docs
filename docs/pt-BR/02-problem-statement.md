# 2. Problema que o projeto pretende resolver

## 2.1 Contexto operacional

Em ambientes industriais, equipamentos passam por manutenções preventivas e corretivas. Para que uma manutenção programada seja executada adequadamente, os materiais, peças e componentes necessários precisam estar disponíveis na quantidade correta e no momento previsto.

Uma ordem pode estar programada e possuir planejamento definido, mas ainda assim enfrentar um impedimento operacional caso o estoque não tenha quantidade suficiente dos materiais necessários.

A situação pode se tornar mais difícil de resolver quando existem reservas para outras ordens, materiais comprometidos, estoques distribuídos em diferentes depósitos ou prazos de reposição incompatíveis com a data da manutenção.

## 2.2 Problema central

A proposta do MaintAI parte da seguinte situação:

> Uma manutenção programada pode ser prejudicada porque os materiais necessários não estarão disponíveis na quantidade necessária até a data prevista para sua execução.

O sistema pretende identificar essa condição antecipadamente, consolidando informações que permitam aos responsáveis avaliar alternativas antes que a insuficiência se torne um impedimento imediato.

## 2.3 Exemplo ilustrativo

Considere o cenário fictício:

- Equipamento: bomba industrial BP-04.
- Manutenção programada: daqui a cinco dias.
- Material necessário: rolamento industrial.
- Quantidade exigida: três unidades.
- Estoque disponível: uma unidade.
- Déficit inicial: duas unidades.

O fornecedor possui determinado prazo de reposição. Se esse prazo ultrapassar a data da manutenção, a ordem poderá ser prejudicada caso não exista outra alternativa.

O MaintAI deverá identificar o déficit, verificar reservas e outros depósitos, considerar o prazo de reposição e apresentar um alerta ao planejador.

> Os dados deste exemplo são fictícios e devem ser identificados como dados de demonstração.

## 2.4 Consequências possíveis

A indisponibilidade de materiais pode exigir que os responsáveis avaliem alternativas, como:

- Verificar a existência de materiais em outros depósitos.
- Avaliar uma transferência entre depósitos.
- Solicitar ou antecipar uma compra.
- Consultar o fornecedor sobre o prazo de entrega.
- Reavaliar o planejamento da manutenção.

O projeto não presume que uma dessas alternativas estará sempre disponível. O objetivo é tornar a situação visível e apoiar a avaliação.

## 2.5 Necessidade de análise antecipada

Uma verificação isolada da quantidade física em estoque pode não representar a disponibilidade real. Materiais reservados ou comprometidos com outras ordens não devem ser tratados como livres para utilização.

A análise também precisa considerar a data em que o material será necessário, os prazos de reposição e a possibilidade de disponibilidade em outros depósitos.

Por isso, a proposta é reunir essas informações em um fluxo único de análise.
