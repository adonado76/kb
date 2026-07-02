---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configurar dimensionamento e posicionamento dinâmicos"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar relatórios"
  - "Relatórios avançados"
source_path: "studio/new-uc/howtoguides/create-reports/dynamic-sizing.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar dimensionamento e posicionamento dinâmicos

**Objetivo:** Criar layouts de relatórios responsivos que se adaptem a diferentes tamanhos de tela e permitam a visibilidade de componentes com base na função, sem deixar espaços em branco.

**Quando usar:** Quando os relatórios são visualizados em telas de tamanhos diferentes, quando os componentes são exibidos de forma condicional com base na função do usuário ou quando é necessário um controle preciso sobre a disposição dos componentes.

**Tempo estimado:** 15 a 20 minutos

## Entendendo as opções de layout

O TBM Studio oferece ferramentas de layout flexíveis na guia Formato para organizar os componentes do relatório. Você pode posicionar os componentes manualmente ou usar caixas de grupo com opções de layout automático que se ajustam quando os componentes são ocultados ou exibidos.

## Método 1: Posicionamento manual dos componentes

**Mover componentes:**

1. Clique e mantenha pressionado o cabeçalho do componente (a barra de título na parte superior do componente).
2. Arraste o componente até o local desejado.
3. Solte para encaixar o componente no lugar.

**Redimensionar componentes:**

1. Passe o mouse sobre a borda ou o canto de um componente até que o cursor de redimensionamento apareça.
2. Clique e arraste para redimensionar o componente.

**Posicionamento preciso:**

1. Clique com o botão direito do mouse no componente e selecione “Posição e tamanho”.
2. Insira os valores exatos em pixels para a posição X, a posição Y, a largura e a altura.
3. Clique em “Aplicar” para visualizar e, em seguida, em “OK” para salvar.

Dica: Use valores negativos para a posição X (até -24 pixels) para ocultar o cabeçalho de um componente e posicioná-lo alinhado à borda de uma caixa de grupo.

## Método 2: Ferramentas de alinhamento e distribuição

Use as ferramentas da guia Formatar para alinhar e distribuir vários componentes:

1. Selecione vários componentes (Ctrl+clique no Windows, Alt+clique no Mac).
2. Na guia Formatar, use o grupo Alinhar:
   - **Esquerda/Centro/Direita:** Alinhar componentes horizontalmente
   - **Superior/Central/Inferior:** Alinhar componentes verticalmente
3. Use o grupo Distribuir:
   - **Horizontal:** Distribuir os componentes uniformemente da esquerda para a direita
   - **Vertical:** Distribui os componentes uniformemente de cima para baixo
4. Use a opção “Ajustar tamanho” para deixar os componentes com a mesma largura, altura ou ambas (usa o primeiro componente selecionado como padrão).

## Método 3: Caixas de grupo com layout automático

As caixas de grupo oferecem um layout automático que se ajusta quando os componentes são ocultados:

1. Na guia Relatório, clique em Agrupar. É adicionada uma caixa de grupo ao relatório.
2. Arraste os componentes para dentro da caixa de grupo.
3. Selecione a caixa de grupo e clique na guia "Grupo" para acessar as opções de layout:
   - **Manual:** Os componentes permanecem onde você os coloca
   - **Vertical:** os componentes são dispostos em uma única coluna, preenchendo automaticamente os espaços vazios quando estão ocultos
   - **Horizontal:** os componentes são dispostos em fileiras, preenchendo automaticamente os espaços vazios quando estão ocultos
4. Clique em “Espaçamento” para definir a distância entre os componentes em pixels.

## Método 4: Ajuste automático do tamanho das caixas de grupo

Configure as caixas de grupo para que se redimensionem dinamicamente de acordo com seu conteúdo:

1. Selecione a caixa de grupo.
2. Na guia "Grupo", use as opções de dimensionamento automático:
   - **Corrigido:** A caixa de grupo mantém seu tamanho independentemente do conteúdo (pode exibir barras de rolagem)
   - **Largura automática:** a largura da caixa de grupo se ajusta para acomodar o conteúdo
   - **Altura automática:** a altura da caixa de grupo se ajusta para acomodar o conteúdo
   - **Automático (Ambas):** Ambas as dimensões são ajustadas dinamicamente

## Método 5: Configurações de visibilidade dos componentes

Configure os componentes para serem exibidos ou ocultados com base em condições:

1. Selecione o componente.
2. Na guia Relatório, no grupo Avançado, clique em Visibilidade.
3. Configurar condições de visibilidade:
   - **O componente contém dados:** ocultar quando o componente não tiver dados para exibir
   - **A função atual do usuário é:** Mostrar apenas para funções específicas de usuário
   - **O texto dinâmico não resulta em "oculto":** use uma fórmula para controlar a visibilidade

**Exemplo:** Para mostrar um componente de explicação da variância apenas quando a variância for negativa, use texto dinâmico:

`<%=IF(Variance<0,"visible","hidden")%>`

## Método 6: Grupos de componentes com abas

Use grupos com abas para organizar vários componentes em um espaço compacto:

1. Na guia Relatório, clique em Grupo com guias.
2. Arraste os componentes para o grupo com abas. Cada componente aparece em sua própria guia.
3. Use os botões de seta abaixo da área das guias para reorganizar as guias.
4. Para remover um componente, arraste-o para fora do grupo com abas.

## Método 7: Opções de layout dinâmico

Para layouts responsivos avançados, use as opções do menu Dinâmico:

- **Alinhar horizontalmente:** alinha o componente no centro do seu contêiner à medida que o contêiner é redimensionado
- **Manter distância da parte superior/inferior:** mantém a posição do componente em relação às bordas do contêiner
- **Ajustar ao tamanho do contêiner:** o componente redimensiona-se proporcionalmente à medida que o contêiner muda de tamanho
- **Atracagem à direita/parte inferior:** o componente mantém sua posição em relação à borda direita ou inferior

## Considerações sobre o tamanho da tela

Ao criar um relatório, você seleciona o tamanho da tela de destino:

- **Padrão:** 1024 pixels de largura
- **Tela panorâmica:** 1440 pixels de largura

Escolha com base nas resoluções de tela mais comuns dos seus usuários. Use opções de layout dinâmico para garantir que os relatórios sejam exibidos corretamente em telas diferentes daquelas para as quais foram projetados.

## Alinhar à grade

Na guia Formato, marque a opção Alinhar à grade para que os componentes se alinhem a uma grade invisível ao serem posicionados. Isso ajuda a criar layouts organizados e alinhados rapidamente.

## Ordem Z (Frente/Verso)

Quando os componentes se sobrepõem, controle qual deles aparece na frente:

1. Selecione o componente.
2. Na guia Formato, no grupo Posição e tamanho, clique em Trazer para a frente ou Enviar para trás.

## Resultados esperados

- Os componentes são alinhados com precisão por meio de ferramentas de alinhamento
- As caixas de grupo com layout vertical/horizontal se reorganizam automaticamente quando os componentes são ocultados
- As condições de visibilidade mostram ou ocultam componentes com base na função do usuário ou em critérios de dados
- Os grupos com abas permitem uma navegação compacta entre vários componentes

## Tarefas relacionadas

- Criar modelos de relatório (Seção 3.3.1 )
- Configurar layouts de impressão (esta seção)
- Definir permissões de componentes por função (Seção 3.4 )

**Tópico principal:** [Relatórios avançados](../../../../studio/new-uc/howtoguides/create-reports/adv-rep.html)
