---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Relatórios - Configuração do AHQ e mensagens de erro comuns"
breadcrumb: []
source_path: "cost-transparency/reports-v103/reportingahqconfig.html"
images:
  - "resources/images/ct_images/reportingahqconfig_1.png"
  - "resources/images/ct_images/reportingahqconfig_2.png"
  - "resources/images/ct_images/reportingahqconfig_3.png"
  - "resources/images/ct_images/reportingahqconfig_4.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Relatórios - Configuração do AHQ e mensagens de erro comuns

## Guia Relatórios (AHQ)

**Aplicativo**

A configuração da consulta ah-hoc aparece ao inserir uma tabela, um gráfico, uma cascata, etc. A configuração do uso do AHQ determinará a aparência dos relatórios/relatórios na superfície de relatórios.

**Objetos AHQ**

A imagem a seguir mostra o objeto no qual o relatório se baseará. Os objetos atuais escolhidos são "Aplicativos" e "Projetos" Isso preencherá todas as perspectivas dentro do AHQ com base nos valores do(s) objeto(s) de apoio. Apptio suporta apenas a geração de relatórios a partir de dois objetos e a filtragem a partir de um terceiro objeto.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/reportingahqconfig_1.png)

**OBSERVAÇÃO** : quando o AHQ estiver bloqueado em um objeto, a opção ficará acinzentada e bloqueada no objeto de apoio. Isso não significa necessariamente que sejam os dados desse objeto.

**Erro comum nº 1**

O erro abaixo aparecerá quando você tiver valores de slicer/picker que estejam fazendo uma pesquisa em três objetos diferentes.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/reportingahqconfig_2.png)

**Erro comum nº 2**

- Esse erro ocorrerá quando um valor de slicer/picker tiver uma métrica calculada associada aos resultados do relatório.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/reportingahqconfig_3.png)

- A métrica do tipo de modelo calculado pode ser visualizada na guia **Métricas**. O exemplo a seguir usa a métrica **Fixed**.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/reportingahqconfig_4.png)
