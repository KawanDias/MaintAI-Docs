# 10. Estratégia de integração SAP

## 10.1 Objetivo

Preparar o MaintAI para uma futura integração com SAP ERP / SAP S/4HANA e SAP HANA Cloud, sem tornar essa integração uma dependência para o desenvolvimento e validação do MVP.

## 10.2 Estratégia gradual

A integração deverá ser tratada em etapas:

1. Construir a aplicação independente.
2. Utilizar dados simulados e banco local.
3. Validar cadastros, serviços e motor de análise.
4. Identificar as fontes de dados necessárias no ambiente SAP.
5. Estudar APIs e mecanismos de integração disponíveis.
6. Definir autenticação e autorização.
7. Implementar leitura de informações, caso exista acesso autorizado.
8. Validar sincronização e consistência.
9. Documentar limitações e resultados.
10. Avaliar a utilização de SAP HANA Cloud e implantação.

## 10.3 Sistemas e tecnologias considerados

- SAP ERP / SAP S/4HANA: possível origem de informações corporativas.
- SAP CAP: camada de serviços da aplicação.
- SAP HANA Cloud: banco de dados previsto para uma etapa posterior.

O uso de cada componente dependerá dos ambientes e recursos efetivamente disponíveis.

## 10.4 Informações potencialmente necessárias

O MaintAI poderá precisar obter informações relacionadas a:

- Equipamentos.
- Ordens de manutenção.
- Materiais e componentes.
- Estoques e depósitos.
- Reservas e compromissos.
- Fornecedores e prazos de reposição.

A origem exata, os objetos de negócio, os serviços e os campos deverão ser identificados durante o estudo do ambiente SAP. Este documento não presume APIs específicas já selecionadas.

## 10.5 Diretrizes

### Acesso autorizado

A integração com um SAP corporativo real dependerá de acesso autorizado, ambiente disponível e APIs habilitadas.

### Leitura como ponto inicial

O planejamento prevê começar pela obtenção e leitura de informações necessárias à análise. Alterações transacionais automáticas não fazem parte do escopo inicial.

### Separação de responsabilidades

A lógica de análise do MaintAI deverá permanecer organizada na aplicação, sem depender de uma integração corporativa para funcionar no ambiente de demonstração.

### Sincronização

Frequência, direção, tratamento de falhas e estratégia de atualização deverão ser definidos após o conhecimento das APIs e das necessidades operacionais.

### Segurança

Autenticação, autorização, proteção de credenciais e permissões deverão seguir os mecanismos disponibilizados pelo ambiente corporativo. Credenciais reais não devem ser armazenadas no repositório de código ou documentação.

## 10.6 SAP HANA Cloud

O desenvolvimento inicial deverá utilizar SQLite local. SAP HANA Cloud está previsto para uma etapa posterior, após a validação do sistema.

A migração ou adaptação deverá considerar compatibilidade do modelo, persistência, configuração e execução da aplicação.

## 10.7 Limitações e dependências

A integração real depende de:

- Acesso autorizado ao ambiente.
- Disponibilidade do sistema SAP.
- APIs habilitadas e documentadas.
- Definição de autenticação e autorização.
- Conhecimento das estruturas e dados de origem.
- Condições técnicas para sincronização.

Se esses recursos não estiverem disponíveis, a entrega poderá consistir em protótipo de integração ou demonstração local documentada.

## 10.8 Fora do escopo de integração inicial

- Integração automática com todos os módulos SAP.
- Execução automática de compras.
- Transferências automáticas de estoque.
- Alterações automáticas em ordens SAP.

Essas ações não deverão ser presumidas como parte do MVP.

## 10.9 Entrega esperada

A fase de integração deverá resultar em integração demonstrável ou protótipo de integração, conforme os recursos disponíveis, com suas limitações documentadas.
