---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Visibilidade no nível do componente"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
  - "Permissões de relatórios e componentes"
source_path: "studio/new-uc/concepts-architecture/security-model/component-level-visibility.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Visibilidade no nível do componente

Para um controle mais detalhado, você pode configurar componentes individuais do relatório para serem exibidos ou ocultados com base em determinadas condições.

**Opções de visibilidade**

Cada componente do relatório oferece várias opções de visibilidade:

- **O componente contém dados:** oculta o componente se ele não contiver ou não calcular dados.
- **A função atual do usuário é:** Mostra o componente apenas aos usuários com funções específicas. Isso permite que você crie um único relatório que exiba diferentes componentes para diferentes públicos.
- **O texto dinâmico resulta em “oculto”:** oculta o componente com base em uma condição calculada — por exemplo, ocultando um componente de variância quando a variância é positiva.

**Padrão de visibilidade de componentes baseado em funções**

Uma prática comum é criar grupos de relatórios que contenham componentes específicos para cada função e, em seguida, agrupar esses grupos na mesma área de relatórios. Cada grupo está configurado para ser visível apenas para uma função. Quando um usuário abre o relatório, ele vê apenas os componentes correspondentes à sua função.

Nota:

**Várias funções**

Se um usuário tiver duas funções para as quais grupos diferentes são visíveis, ele verá os componentes da função cujo grupo estiver no topo da pilha. Organize cuidadosamente as camadas do seu grupo de relatórios para atender aos usuários com várias funções.

**Tópico principal:** [Permissões de relatórios e componentes](../../../../studio/new-uc/concepts-architecture/security-model/report-component-permission.html)
