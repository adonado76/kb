---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Guia de configuração de relatórios de tomada de custos"
breadcrumb: []
source_path: "cost-transparency/configuration/cost-takeout-config-guide.html"
images:
  - "resources/images/ct_images/cto-reports.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Guia de configuração de relatórios de tomada de custos

## Visão geral

É importante entender a finalidade e os objetivos dos relatórios de tomada de custos antes de conhecer a configuração técnica.

Personas: Líderes de unidades de negócios, gerentes de fornecedores, gerentes de compras, líderes de soluções, proprietários de aplicativos, proprietários de serviços.

Para: Líderes de organizações que desejam identificar oportunidades para reduzir e otimizar os custos de mão de obra, fornecedores e gastos com aplicativos.

Valor: As equipes de TI e finanças lutam para identificar oportunidades de redução de custos de alto impacto devido à fragmentação dos dados e à falta de relatórios de redução de custos direcionados em IBM Apptio. Eles precisam de visibilidade clara das áreas específicas dos geradores de custos para otimizar seus gastos com mão de obra, fornecedores e aplicativos.

Solução: Relatórios de tomada de custos

Produto: Apptio Cálculo de custos padrão

## Casos de uso

Relatórios prontos para uso projetados para ajudar os usuários do IBM Apptio a

- Identificar oportunidades para reduzir e otimizar os custos de mão de obra, fornecedores e gastos com aplicativos
  - Apoiar o planejamento estratégico da força de trabalho e as decisões de contratação
  - Otimize seu portfólio de fornecedores
  - Simplifique e racionalize seu portfólio de aplicativos
- Permita que as organizações tomem decisões rápidas, baseadas em dados e defensáveis.

## Pré-requisitos

Os pré-requisitos para a solução Cost Take-Out Reports são:

- IBM Apptio Licença padrão de cálculo de custos.
- IBM Apptio Versão do servidor: R12.11.17 (ou superior).
- Versão dos componentes v120 em Configurações do projeto
  - Consulte [este guia](install-apptio-ibm-costing-old-template.html) para instalar os componentes do v120 em projetos com versões mais antigas de componentes.

## Instalação de componentes

O núcleo da solução Relatórios de tomada de custos é apresentado por meio do componente Relatórios de tomada de custos. Para novos clientes, os componentes típicos, como fonte de custos, mão de obra, fornecedor, ativos fixos, aplicativos etc., também precisariam ser instalados, de acordo com a arquitetura geral pretendida. Os clientes existentes podem reutilizar os componentes instalados anteriormente sem nenhuma alteração.

Essas alterações precisam ser feitas no TBM Studio

1. Vá para o ícone Componentes na guia Projeto e instale o componente Relatórios de retirada de custos.

   ![Relatórios do CTO](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/cto-reports.png)

   Para que os relatórios de retirada de custos sejam exibidos, alguns desses componentes podem precisar ser pré-instalados e configurados
   - CTF-Fonte de custo
   - CTF-Trabalho
   - Fornecedor de CTF
   - CT Apps - Aplicativo
   - CTF - Torres de TI
   - Aplicativos CT - Armazenamento
   - Aplicativos CT - Servidor
   - Contratos de insights do fornecedor
2. Verifique e registre as alterações. Os três relatórios estarão disponíveis em suas respectivas coleções:
   - Relatório de retirada de custos trabalhistas: disponível na coleção Labor
   - Relatório de retirada de custos do fornecedor: disponível na coleção do fornecedor
   - Relatório de retirada de custos de aplicativos: disponível na coleção de aplicativos
