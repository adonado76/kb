---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Componente Botão"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "ApptioIBM Report Studio (Novo)"
  - "Componentes"
source_path: "studio/report-studio/components/button-comp.html"
images:
  - "resources/images/studio_images/but-for.png"
  - "resources/images/studio_images/button.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Componente Botão

O componente Botão permite que os usuários acionem ações diretamente a partir de um relatório, possibilitando fluxos de trabalho interativos e dinâmicos. Os botões podem ser configurados para realizar tarefas como navegar para outro relatório, executar scripts ou atualizar o contexto do relatório (por exemplo, alterar a data).

## Quando usar botões

Use os botões quando quiser:

- Permitir que os usuários naveguem entre relatórios
- Acionar ações ou scripts predefinidos
- Ofereça interações rápidas sem depender de filtros ou menus
- Simplifique os fluxos de trabalho oferecendo elementos claros de chamada à ação

## Adicionar botão a um relatório

Para adicionar um botão ao seu relatório:

1. Abra o relatório no editor.
2. No painel “Componentes” da barra de ferramentas, arraste e solte o botão na tela.
3. Selecione o botão para definir suas propriedades usando o painel Dados e o painel Formato.

**Exemplo**

**Painel de dados dos botões**

![imagem para o componente de botão](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/button.png)

Use o painel Dados para definir o comportamento do botão:

- **Texto do botão** - Defina o texto exibido no botão.
- **Ativado** - Por padrão, o botão está ativado. Você pode definir uma regra de ativação para desativar o botão condicionalmente.
- **Ação do servidor** - Anexe um script do lado do servidor que seja executado quando o botão for clicado.
- **Ação** "Alterar data" - Defina uma data específica para que, ao clicar no botão, o relatório seja atualizado para essa data.
- **Ação de navegação** - Selecione um relatório de destino para o qual navegar quando o botão for clicado.

**Painel de Formatação**

![imagem para o componente do botão de formatação](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/but-for.png)

**Guia Propriedades**

Personalize a aparência e o layout do botão:

- **Alternar ícone**
- Ative esta opção para incluir um ícone.
  - Ícone padrão: Ícone de informações
  - Escolha a partir de uma lista suspensa de ícones disponíveis
  - Definir a posição do ícone: à esquerda ou à direita
- **Estilo padrão do botão**
- Personalize a aparência do botão em seu estado padrão:
  - Fonte
  - Cor do texto
  - Cor do plano de fundo
  - Tamanho e cor da borda
  - Cor e tamanho do ícone
- **Estilo do botão ao passar o mouse**
- Defina como o botão aparece quando o cursor passa por cima dele, incluindo as mesmas opções de estilo do estado padrão.

**Guia Geral**

- **Alt text**
- Adicione um texto descritivo para fins de acessibilidade.
- **Posição e tamanho**
- Ajuste o posicionamento e as dimensões na tela.
- **Estilo**
  - Margem (incluindo ajustes por lado)
  - Raio do canto para bordas arredondadas

O componente Botão aumenta a interatividade do relatório, permitindo que os usuários realizem ações diretamente. Com uma configuração flexível em termos de comportamento e estilo, ele pode ser adaptado para atender a uma ampla variedade de casos de uso — desde navegação até automação —, mantendo uma experiência do usuário consistente.
