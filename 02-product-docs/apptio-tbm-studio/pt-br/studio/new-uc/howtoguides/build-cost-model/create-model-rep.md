---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Criar relatórios de modelo (diagramas de Sankey)"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar modelos de custos"
  - "Modelagem avançada"
source_path: "studio/new-uc/howtoguides/build-cost-model/create-model-rep.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Criar relatórios de modelo (diagramas de Sankey)

## Objetivo

Crie um relatório modelo que visualize os fluxos de custos ao longo do seu modelo no formato de um diagrama de Sankey, facilitando a comunicação com as partes interessadas e a auditabilidade.

## Quando utilizar este procedimento

Crie relatórios modelo quando:

- Você precisa comunicar os fluxos de custos às partes interessadas sem formação técnica
- Você deseja apresentar uma visualização intuitiva de como os custos se propagam pelo modelo
- Você precisa apoiar auditorias financeiras ou iniciativas de transparência
- Você deseja que os usuários finais explorem os fluxos de custos de forma interativa sem acessar o Model Studio
- Você está apresentando dados financeiros de TI aos líderes das unidades de negócios

**Pré-requisitos**

- O modelo foi construído com alocações fluindo entre objetos
- As tabelas que você deseja incluir no relatório possuem etapas do modelo
- Você definiu os níveis (camadas) que deseja exibir

## Tempo estimado

20 a 30 minutos para a configuração inicial; 5 a 10 minutos para alterações

## Entendendo os diagramas de Sankey

Em um diagrama de Sankey, o valor flui da esquerda para a direita. A largura de cada linha de alocação é proporcional ao valor que representa. Essa metáfora visual ajuda a entender:

- Quais fontes representam o maior custo (linhas mais largas)
- Como os custos são distribuídos à medida que passam pelo modelo
- A proporção relativa dos custos que incidem sobre cada destino

## Passos para criar um relatório modelo

1. No Project Explorer, clique com o botão direito do mouse na pasta Modelos, localizada em Relatórios, e selecione Novo relatório de modelo.
2. Digite um nome para o seu relatório de modelo (por exemplo, “Fluxo de Custos de TI” ou “Modelo de Custos de Mão de Obra”).
3. O relatório é aberto no editor de modelos de relatório. Confira o relatório para edição.
4. Clique no menu Exibir na guia Início e selecione Mostrar Editor de Níveis.
5. No Editor de Níveis, clique no ícone “Adicionar Nível” para criar seu primeiro nível.
6. Clique no campo "Nome" na parte superior do nível e insira um nome descritivo (por exemplo, "Finanças", "Grupos de custos", "Infraestrutura", "Serviços").
7. No Project Explorer, arraste uma tabela modelada para a camada. Repita o procedimento para adicionar várias tabelas ao mesmo nível, se necessário.
8. Como alternativa, expanda uma tabela no Project Explorer e arraste uma coluna específica para criar um nível focado nessa dimensão (por exemplo, arraste a coluna “Cost Pool” em vez da tabela completa).
9. Repita os passos 5 a 8 para criar camadas adicionais que representem cada camada do seu modelo.
10. Use o ícone “Reorganizar” para arrastar as camadas na ordem correta, da esquerda para a direita.
11. Clique em Exibir > Mostrar documento para visualizar o relatório do seu modelo.
12. Salve e verifique o relatório.

## Configuração de camadas

Os níveis controlam o layout e a granularidade do seu relatório de modelo. Considere estas opções:

- Nível da tabela: Mostra a tabela inteira. Os usuários podem clicar no menu e selecionar “Detalhar” para visualizar as colunas individualmente.
- Nível da coluna: mostra uma dimensão específica (por exemplo, Grupo de custos, Nome do fornecedor). Oferece uma análise detalhada.
- Nível com várias tabelas: Contém várias tabelas no mesmo nível. Útil para mostrar fluxos de custos paralelos.

Observação: um nível pode conter uma única coluna OU uma ou mais tabelas, mas não ambos.

## Interagindo com relatórios de modelos

Depois de criados, os usuários podem interagir com os relatórios de modelo das seguintes maneiras:

- Clique em um elemento da tabela para ver seus controladores e alocações
- Continue clicando nos elementos da tabela para acompanhar o fluxo de valores pelo modelo
- Abra o menu em uma tabela e clique em “Detalhar” para ver os valores de uma coluna específica
- Clique nas linhas de alocação para visualizar os detalhes subjacentes no nível da transação

## Adicionando relatórios de modelo às coleções de relatórios

No TBM Studio 12.2.2 e versões posteriores, é possível adicionar relatórios de modelo a coleções de relatórios para facilitar o acesso:

1. Abra o modelo de relatório e dê uma olhada nele.
2. Clique na guia “Modelagem” na faixa de opções.
3. Clique em “Atribuir à coleção”.
4. Selecione a coleção de relatórios de destino no menu suspenso.
5. Salve e verifique o relatório.

## Boas Práticas

- Use nomes de níveis claros e fáceis de entender para o público empresarial (“Infraestrutura de TI”, em vez de “Nível 3”)
- Limite os níveis a 4-6 para facilitar a leitura — muitos níveis podem sobrecarregar os leitores
- Crie vários relatórios de modelo específicos em vez de um único relatório abrangente
- Use níveis de coluna quando quiser destacar uma dimensão específica (por exemplo, fluxo do grupo de custos)
- Adicione relatórios modelo às coleções de relatórios para que os usuários finais possam encontrá-los facilmente

## Tarefas relacionadas

- [Acompanhar os fluxos de custos ao longo do modelo](trace-cost-flow.html)
- [Criar coleções de relatórios de compilação](../create-reports/build-rc.html)
- [Veja o diagrama do modelo](view-model-diagram.html)

**Tópico principal:** [Modelagem avançada](../../../../studio/new-uc/howtoguides/build-cost-model/adv-model.html)
