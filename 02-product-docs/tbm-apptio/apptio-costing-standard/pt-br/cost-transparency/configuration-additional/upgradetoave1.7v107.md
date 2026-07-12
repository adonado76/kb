---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Faça upgrade para Apptio Value Explorer 12.7 ( v107 )"
breadcrumb: []
source_path: "cost-transparency/configuration-additional/upgradetoave1.7v107.html"
images:
  - "resources/images/ct_images/ave-before-v107.png"
  - "resources/images/ct_images/ave-updated-to-v107.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Faça upgrade para Apptio Value Explorer 12.7 ( v107 )

Aplica-se a: Apptio Value Explorer (AVE) em TBM Studio 12.7 e posterior, com Template v107 e posterior

O processo de configuração geral para atualizar todos os aplicativos para TBM Studio 12.7 está descrito em [Upgrade Costing Standard to the Latest Template Version](../user-guide/upgradecttolatest-9740.html). Este artigo contém uma etapa de configuração específica para atualizar o Apptio Value Explorer (AVE) de qualquer versão anterior do modelo para o modelo v107.

## Instruções de atualização

1. Siga as instruções de atualização do modelo em [Upgrade Costing Standard para a versão mais recente do modelo](../user-guide/upgradecttolatest-9740.html)

   Quando chegar à Etapa 5, mude para este artigo, certificando-se de que você está no ramo correto antes de continuar.
2. Atualize o componente Apptio Value Explorer.
3. Verifique a atualização do componente AVE.
4. Acesse o conjunto de dados mestre do Apptio Value Explorer no Project Explorer.
5. Confira o documento.
6. Clique em **Append**.
7. Exclua a tabela Apptio Value Explorer Raw.
8. Reaproveite a tabela Apptio Value Explorer Raw.

   Todas as colunas serão mapeadas automaticamente.
9. Salve e verifique suas alterações.
10. Retorne às instruções de atualização de modelo em [Upgrade Costing Standard to the Latest Template Version](../user-guide/upgradecttolatest-9740.html) para concluir as atualizações de componentes restantes.

## Segundo plano

O AVE foi desenvolvido na plataforma TBM Studio e é fornecido como parte de um projeto Costing Standard . O AVE inclui uma lista abrangente de casos de uso de produtos. A atualização do AVE 12.7 oferece os seguintes aprimoramentos:

1. Atualize o conteúdo do AVE para incluir casos de uso de novos produtos e recursos.
2. Simplifique a quantidade de documentação em favor de descrições e resultados mais robustos que se concentrem no "porquê".
3. Remova a complexidade dos fatiadores, das mensagens de vendas e das linhas duplicadas.

## Persona

O AVE foi projetado para ser usado pelas seguintes funções:

- Escritório da TBM
  - Revisar e priorizar os recursos
  - Determinar quais componentes do produto devem ser configurados
  - Comunicar o valor que os produtos Apptio oferecem à organização
- Gerentes de sucesso do cliente, consultores de sucesso do cliente, gerentes de engajamento
  - Comunicar o valor que os produtos Apptio oferecem

## Comparar versões

AVE antes v107

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ave-before-v107.png)

AVE atualizado para o modelo v107

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ave-updated-to-v107.png)

## Resumo das mudanças

Conteúdo
:   - - Foram adicionados casos de uso de produtos em todos os produtos Apptio.
      - Criou casos de uso mais granulares com uma descrição abrangente e resultados para identificar o motivo por trás do caso de uso
      - Incluiu casos de uso não fornecidos nos relatórios prontos para uso do Apptio, mas disponíveis usando a extensibilidade do TBM Studio.

        Esses casos de uso estão vinculados ao [Insights Toolkit](https://community.apptio.com/community/apptio/tbm-cookbook "(Abre em uma nova guia ou janela)") no TBM Connect.

Fatiadores
:   - - Alterado para compactar as segmentações no modelo de relatório mestre do AVE.
      - A hierarquia do slicer **TBM Categoria > Subcategoria** substitui a **Área**.
      - Removido o fatiador de **resultados**.

Tabela AVE
:   - Simplificou a tabela de três abas em uma tabela sem abas. Removida a guia **Value and Apptio Approach** e consolidada a guia **Required Data Sources** em uma única tabela.
    - Colunas na nova tabela AVE:
      - **Categoria TBM** - Categoria de alto nível para organizar os casos de uso. Substitui **Area** (por exemplo, Financials, Applications & Services).
      - **Caso de uso** - O "quê" Uma expressão curta que define a capacidade do produto, expressa em uma frase verbo-substantivo consistente.
      - **Descrição** - Uma descrição mais longa do caso de uso que pode incluir os vários atributos e o escopo do caso de uso.
      - **Resultado** - O "porquê" O valor esperado do caso de uso.
      - **Capacidade** - A capacidade ou ação de alto nível do caso de uso (por exemplo, Planejar, Otimizar, Influenciar)
      - **Relatório** - Se o componente associado estiver instalado, essa coluna conterá links para o relatório específico do Apptio que pode ser usado para analisar as métricas do caso de uso. Se o componente não estiver configurado, essa coluna será vinculada ao projeto de referência. Se o relatório for personalizado em vez de pronto para uso, essa coluna terá um link para o [Insights Toolkit](https://community.apptio.com/community/apptio/tbm-cookbook "(Abre em uma nova guia ou janela)") no TBM Connect.
      - **Requisitos de dados** - Essa coluna é vinculada ao Data Advisor para que você possa visualizar os conjuntos de dados e colunas necessários (e opcionais) para configurar o componente e os casos de uso associados.
    - Seletores adicionais:
      - **Produto** - O produto Apptio que habilita o caso de uso (por exemplo, Apptio for Cloud).
      - **Module** - O módulo subjacente do Apptio que habilita o caso de uso (por exemplo, HBM).
      - **No produto** - O indicador de que o caso de uso é compatível pronto para uso, em vez de ser uma configuração personalizada com TBM Studio.
      - **Is Configured (Está configurado** ) - Classifica com base no fato de o componente relacionado estar ou não instalado.
