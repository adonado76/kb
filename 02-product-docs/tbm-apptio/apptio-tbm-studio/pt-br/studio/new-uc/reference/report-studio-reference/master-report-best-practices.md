---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Melhores práticas para relatórios principais"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Relatórios principais"
source_path: "studio/new-uc/reference/report-studio-reference/master-report-best-practices.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Melhores práticas para relatórios principais

Siga estas práticas recomendadas ao criar e utilizar relatórios-padrão para garantir os melhores resultados:

**Diretrizes de design**

1. **Use relatórios principais como auxílio ao layout** : em geral, crie contêineres, como caixas de grupo, dentro dos quais você colocará componentes como gráficos e tabelas nos relatórios secundários. As diretrizes são mais eficazes quando definem a estrutura, e não o conteúdo.
2. **Planeje cuidadosamente o uso de componentes com abas** : se você adicionar um componente com abas a um relatório mestre, certifique-se de incluir todo o conteúdo necessário em cada aba dentro do próprio relatório mestre. Não é possível adicionar componentes a guias individuais no relatório secundário. Os componentes posicionados sobre um componente com abas no relatório secundário serão exibidos acima de todas as abas.
3. **Use caixas de grupo apenas para fins de estrutura visual** : as caixas de grupo adicionadas a um relatório mestre perdem a funcionalidade de agrupamento de componentes quando aplicadas a relatórios filhos. Use-os como bordas visuais e contêineres de layout, e não como mecanismos de agrupamento funcional.
4. **Configure o contexto do botão adequadamente** : se você adicionar um botão a um relatório mestre que utilize texto Wiki sem especificar um Data URL, o aplicativo utilizará o relatório atual (filho) como contexto. Planeje sua rota de acordo com isso.

**Orientações de manutenção**

- **Documente seus relatórios principais** : mantenha uma lista dos relatórios principais existentes e dos relatórios secundários que utilizam cada um deles
- **Teste as alterações cuidadosamente** : ao atualizar um relatório principal, verifique como as alterações afetam todos os relatórios secundários antes de implementá-las
- **Use convenções de nomenclatura** : coloque o prefixo “Master -” ou um identificador semelhante nos nomes dos relatórios mestre para distingui-los facilmente dos relatórios comuns
- **Limitar o aninhamento de relatórios mestre** : Embora seja possível aplicar relatórios mestre a outros relatórios mestre, isso não é recomendado devido à complexidade e ao risco de confusão

Dica: mantenha os relatórios principais o mais simples possível. Mestres complexos com muitos componentes podem dificultar o desenvolvimento de relatórios filhos e afetar o desempenho.

**Tópico principal:** [Relatórios principais](../../../../studio/new-uc/reference/report-studio-reference/master-report.html)
