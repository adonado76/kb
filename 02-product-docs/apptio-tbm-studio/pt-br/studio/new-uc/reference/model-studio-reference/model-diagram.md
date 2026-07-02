---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Diagramas de modelos"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Model Studio"
source_path: "studio/new-uc/reference/model-studio-reference/model-diagram.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Diagramas de modelos

Os diagramas de modelo fornecem representações visuais da estrutura do modelo de custos, mostrando como o valor flui entre os objetos do modelo.

## Tipos e vistas de diagramas

O TBM Studio oferece três formas de visualizar o modelo, cada uma com uma finalidade diferente.

**Visualização de tabela única (Área de trabalho de edição do modelo)**

**Descrição:** Mostra um objeto modelo com seus controladores e alocações em um diagrama de Sankey. Utilizado para configurar objetos individuais.

**Layout**

- Coluna da esquerda: Motoristas (motoristas da unidade e alocações recebidas)
- Centro: O objeto modelo que está sendo editado
- Coluna da direita: Alocações de saída (objetos de destino)

**Como acessar**

1. Clique em uma tabela no Explorador de Projetos
2. Clique na etapa “Modelo” no fluxo de transformação

**Visualização métrica modelada (Visualização do diagrama)**

**Descrição:** Visualização de alto nível que mostra todos os objetos do modelo e suas conexões. Semelhante a um diagrama do Visio. Utilizado para compreender a estrutura geral do modelo.

**Recursos**

- Exibe todos os objetos do modelo e suas conexões
- Suporta zoom e panorâmica
- Ao clicar em um nó, a visualização de tabela única desse objeto é aberta
- Rastreabilidade de custos para linhas de alocação específicas
- Reflete o modelo atualmente implantado

**Observação:** a visualização do diagrama não pode ser usada para modificar alocações diretamente. As alterações devem ser feitas na visualização de tabela única.

**Visualização do relatório do modelo (visualização em camadas/Sankey)**

**Descrição:** Visualização do usuário final mostrando tabelas selecionadas organizadas em camadas com visualização de fluxo no estilo Sankey. Utilizado para relatórios e análises.

**Recursos**

- Estrutura de níveis personalizável
- Mostra as larguras proporcionais do fluxo
- Aprofundar a análise até os detalhes da coluna
- Acesso aos dados em nível de transação
- Pode ser adicionado às coleções de relatórios ( v12.2.2+ )

*Consulte [os relatórios de modelo para obter informações detalhadas sobre a configuração](model-reports.html)*

- **[Conceitos do diagrama de Sankey](../../../../studio/new-uc/reference/model-studio-reference/sankey-diagram.html)**
- **[Navegação pelo diagrama](../../../../studio/new-uc/reference/model-studio-reference/diagram-navigation.html)**
- **[Opções de personalização do diagrama](../../../../studio/new-uc/reference/model-studio-reference/diagram-customization.html)**
- **[Exportação e compartilhamento](../../../../studio/new-uc/reference/model-studio-reference/export-sharing.html)**
