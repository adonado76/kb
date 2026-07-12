---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Criar relatórios-modelo"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar relatórios"
  - "Personalização de relatórios"
source_path: "studio/new-uc/howtoguides/create-reports/design-master-rep.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Criar relatórios-modelo

**Objetivo:** Criar e aplicar modelos de relatórios que garantam um layout e uma identidade visual consistentes em vários relatórios.

**Quando usar:** Use relatórios mestre quando desejar:

- Certifique-se de que os cabeçalhos, rodapés e navegação sejam consistentes em todos os relatórios
- Aplicar elementos de identidade visual padrão (cores, logotipos, caixas de grupo) a vários relatórios
- Crie layouts reutilizáveis que outros criadores de relatórios possam adotar
- Mantenha a consistência visual em todos os relatórios da sua organização

**Pré-requisitos:**

- Função de usuário avançado ou administrador
- Uma visão clara do layout desejado para o seu relatório
- Noções básicas sobre caixas de grupo e componentes com abas

**Tempo estimado:** 30 a 60 minutos para criar um modelo de relatório; 5 minutos para aplicá-lo

## Entendendo os Relatórios Principais

Os relatórios-modelo funcionam como os slides-modelo em programas de apresentação — eles fornecem uma camada de modelo que fica por trás do conteúdo do relatório. Quando você aplica um relatório mestre a um relatório personalizado, os componentes do relatório mestre aparecem como um "fundo" de tela

**Principais características:**

- Os componentes do relatório mestre não podem ser editados a partir de relatórios que utilizam o mestre
- Os componentes que você adiciona aos relatórios personalizados são sobrepostos aos elementos do modelo
- As alterações no mestre atualizam automaticamente todos os relatórios que utilizam esse mestre
- Por padrão, os relatórios principais são sempre relatórios de nível superior
- Você pode aplicar pastas principais a outras pastas principais (não recomendado)

## Passo a passo: Criar um relatório mestre

1. Crie um novo relatório ou selecione um relatório existente que deseje usar como modelo.
2. Crie o layout com os elementos que você deseja que apareçam em todos os relatórios que utilizam este modelo: caixas de grupo para definir áreas de conteúdo, botões de navegação para destinos comuns, cabeçalhos com a identidade visual da empresa e posicionamentos padrão dos filtros.
3. Na guia **Relatório**, no grupo **Avançado**, clique em **Relatório mestre** para designar este relatório como mestre.
4. Salve e verifique o relatório.

Seu relatório mestre agora aparece no menu suspenso **“Mestres”** na guia “**Relatórios** ”.

## Passo a passo: aplicar um relatório mestre

1. Selecione o relatório ao qual deseja aplicar o modelo.
2. Na guia **Relatório**, abra a lista suspensa **Modelos**.
3. Clique no relatório mestre que deseja aplicar.

Os elementos do modelo agora aparecem atrás do conteúdo do seu relatório. Posicione seus componentes de modo que fiquem alinhados com o layout principal.

**Passo a passo: Remover um relatório mestre**

1. Dê uma olhada no relatório.
2. Na guia **Relatório**, abra a lista suspensa **Modelos**.
3. Selecione **“Nenhum”** na parte inferior da lista.

## Melhores práticas para relatórios principais

1. **Use modelos como auxílios de layout:** crie contêineres (caixas de grupo) nos quais os criadores de relatórios possam inserir tabelas e gráficos. Não adicione componentes baseados em dados aos modelos.
2. **Tenha cuidado com componentes com abas:** se você adicionar um componente com abas a um modelo, inclua um conteúdo provisório em cada aba. Os usuários não podem adicionar componentes a guias individuais a partir do relatório personalizado.
3. **Entenda as limitações das caixas de grupo:** as caixas de grupo em um modelo perdem sua funcionalidade de agrupamento quando aplicadas. Use-as apenas como bordas visuais.
4. **Leve em consideração a disposição do papel de parede:** posicione os elementos do seu modelo principal sabendo que os componentes do relatório personalizado ficarão sobrepostos a eles. Deixe um espaço adequado para as áreas de conteúdo.

## Armadilhas comuns

- **Adicionar componentes de dados aos relatórios principais:** as tabelas e os gráficos nos relatórios principais não são atualizados dinamicamente nos relatórios secundários. Utilize modelos apenas para elementos de layout.
- **Componentes sobrepostos em abas:** os componentes posicionados sobre áreas com abas em um modelo aparecem em TODAS as abas quando visualizados.
- **Esquecer que as atualizações do mestre afetam todos os relatórios:** as alterações feitas no mestre afetam imediatamente todos os relatórios que o utilizam. Teste as alterações com cuidado.

**Tópico principal:** [Personalização de relatórios](../../../../studio/new-uc/howtoguides/create-reports/report-cust.html)
