---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Atualizar o padrão de cálculo de custos do modelo v103 para a versão mais recente"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/upgrade-guide-v103-to-latest/upgradect.html"
images:
  - "resources/images/ct_images/template_v103_home_page.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Atualizar o padrão de cálculo de custos do modelo v103 para a versão mais recente

Aplica-se a: Costing Standard em TBM Studio 12.3 e posterior, com modelo v104 e posterior

## Visão geral

Este documento descreve os motivos por trás da atualização da interface do usuário (UI) do Costing Standard e as etapas recomendadas para atualizar o conteúdo do aplicativo Apptio conteúdo do aplicativo do modelo v103 para a versão mais recente do modelo do aplicativo.

## VEJA TAMBÉM

Para entender a diferença entre os modelos v103 e v104, vá para [Comparar os relatórios de transparência de custos v104 e v103](../../reports-v104/comparev103v104reports.html).

Para entender como os relatórios são mapeados para o modelo v104, vá para [Mapeamento dos relatórios de transparência de custos do modelo v103 para v104](../../reports-v104/mappingctreports103to104.html).

Para obter uma planilha que lista todos os conjuntos de dados que precisam ser atualizados para v104, vá para [Template v103 para v104 Data Updates](../../user-guide/template103to104dataupdates-9027.html).

## Objetivos

A interface de usuário do Costing Standard foi redesenhada para fazer o seguinte:

- Simplificar a navegação do relatório em Costing Standard
- Simplificar e separar relatórios complexos
- Melhor suporte à configuração incremental
- Segmentar produtos em seleções de nível superior, como separar relatórios Vendor Insights de Costing Standard
- Suporte à taxonomia da TBM v2 como padrão (a taxonomia da TBM v1 ainda é suportada)
- Suporte à conformidade com a Seção 508
- Melhorar o desempenho de relatórios conhecidos como "caros"

## Coleções de relatórios no modelo v104

Os relatórios do site Costing Standard foram organizados nas seguintes coleções de relatórios no Modelo v104:

- Aplicativos
- Linha de base para testes
- Unidades de negócios
- Dimensões dos dados
- Qualidade de dados
- Infraestrutura e nuvem
- Finanças de TI
- Projetos
- Recursos
- Serviços
- Visão geral da TBM
- Fornecedores

## Tipos de relatório

As coleções de relatórios do site v104 são organizadas de acordo com os seguintes tipos de relatórios:

- os relatórios de "revisão" fornecem uma visão geral gráfica das principais áreas, como os 10 aplicativos ou categorias com o maior gasto.
  - Exemplo: Revisão financeira
  - Exemplo: Revisão do projeto
- os relatórios de "portfólio" fornecem métricas de todos os itens em uma área.
  - Exemplo: Portfólio de projetos
- os relatórios "Analysis" (Análise) ou "List" (Lista) oferecem uma visualização tabular de cada área para localizar rapidamente valores específicos.
  - Exemplo: Análise financeira
  - Exemplo: Lista de projetos
- Outros relatórios são adicionados a uma coleção para lidar com casos de uso de "insight" exclusivos de uma área.
  - Exemplo: Projetos em risco
  - Exemplo: Impacto da desativação de aplicativos

## Expectativas de atualização para o modelo v104

Devido à amplitude das alterações na interface do usuário e na navegação subjacente, é importante que todos os componentes existentes **DEVEM** ser atualizados; caso contrário, a navegação da página de destino para os relatórios de nível superior poderá ser interrompida. Além disso, os links de um relatório para um relatório em outra área podem ser interrompidos (por exemplo, um link do relatório do portfólio de serviços para um relatório de projeto relacionado a um serviço específico)

## Identificação do modelo v103

Você pode determinar se o seu aplicativo está usando o Template v103 consultando a página inicial Costing Standard ou a lista de coleções de relatórios Costing Standard .

Se a página inicial for semelhante à página abaixo, você tem o Template v103. Procure seções como "IT Finance" e "IT Management", cada uma com três links abaixo.

![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/template_v103_home_page.png)

Como alternativa, consulte o menu Relatórios. Navegue até as coleções de relatórios.

Para entender a diferença entre os modelos, acesse [os relatórios Compare v104 e v103 Cost Transparency](../../reports-v104/comparev103v104reports.html).

## Atualize para os componentes mais recentes

As etapas a seguir são necessárias para atualizar o aplicativo do Template v103 para v104 e posteriores. Conclua estas etapas depois de fazer o upgrade da plataforma de TBM Studio 12.3 ou 12.4 ou posterior.

## Informações relacionadas

- ![](../../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
