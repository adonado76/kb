---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Navegação condicional"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Navegação"
source_path: "studio/new-uc/reference/report-studio-reference/conditional-navigation.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Navegação condicional

Controle a visibilidade e o comportamento dos componentes de navegação com base em valores de dados, funções do usuário ou outras condições. A navegação condicional garante que os usuários vejam apenas as opções de navegação relevantes.

**Condições de estado dos botões**

Use fórmulas no campo "Ativado" das propriedades do botão para controlar a disponibilidade do botão:

**Botão "Ativar" quando o custo exceder o limite:**

`<%=IF(Cost>5000,"enabled","disabled")%>`

**Ocultar o botão quando não houver dados:**

`<%=IF(RowCount()=0,"hidden","enabled")%>`

**Visibilidade dos componentes por função**

Controle quais componentes de navegação são exibidos com base na função atribuída ao usuário:

1. Selecione o componente de navegação (botão, caixa de grupo contendo navegação, etc.)
2. No grupo “Avançado” da guia “Relatório”, clique em “Visibilidade”
3. Selecione a função atual do usuário e escolha as funções que devem ter acesso a este componente
4. Os usuários que não pertencerem às funções selecionadas não verão o componente

**Visibilidade dinâmica do texto**

Use a opção de visibilidade “O texto dinâmico não resulta em ‘oculto’” para mostrar ou ocultar a navegação de forma condicional com base em valores calculados. Se a sua fórmula retornar "oculto", o componente desaparecerá.

**Tópico principal:** [Componentes do relatório: Navegação](../../../../studio/new-uc/reference/report-studio-reference/report-component-navigation.html)
