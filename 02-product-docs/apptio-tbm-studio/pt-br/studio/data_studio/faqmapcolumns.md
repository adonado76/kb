---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Perguntas frequentes sobre Map Columns"
breadcrumb: []
source_path: "studio/data_studio/faqmapcolumns.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Perguntas frequentes sobre Map Columns

**Aplica-se a** : TBM Studio 12.7 e posterior

Dica: se você não encontrar o que está procurando aqui, consulte as postagens no [Fórum de Perguntas e Respostas do TBM Studio 12](https://community.apptio.com/community/apptio/product-central/apptio-qa-forum "(Abre em uma nova guia ou janela)") ou [faça uma pergunta no Fórum](https://community.apptio.com/community/apptio/product-central/apptio-qa-forum "(Abre em uma nova guia ou janela)").

## Transformar pipeline e mapear colunas

**Por que não vejo todas as minhas colunas durante o mapeamento?**

Somente colunas com o mesmo tipo podem ser mapeadas. Portanto, quando você selecionar uma coluna para uma coluna de destino com um tipo de rótulo, somente as colunas com um tipo de rótulo serão exibidas. Se o upload inicial não contiver dados (somente cabeçalhos), nenhum tipo será selecionado por padrão. Os códigos geralmente são importados como numéricos. Em ambos os casos, vá para a etapa **Importar** para substituir o tipo de coluna padrão.

Quando você selecionar o tipo Data em Importar, preencha o formato da data à direita dos seletores de tipo.

**Exemplo:** Formato de data

```
yyyy-mm-dd:
      2018-09-26
```

.

**Quero unir outra tabela a essa, mas preciso fazer alguma lógica nos resultados. O que devo fazer?**

Use a etapa do pipeline Join imediatamente antes de Map Columns para retornar colunas vinculadas à tabela primária por uma coluna de informações correspondentes. Quando possível, complete qualquer lógica na outra tabela. Você pode selecionar "Add Custom Column" (Adicionar coluna personalizada) para adicionar a coluna à saída ou mapear para uma coluna de destino existente disponível.

Para "Is Labor" e "Is Depr": O Plano de Contas Master Data calculará esses campos em v107. Como alternativa, deixe as colunas em branco e altere a alocação para usar o pool de custos ou o sub pool para filtrar a origem das alocações.

No entanto, se você precisar completar a lógica com base nas colunas da tabela primária e da tabela unida, use uma fórmula Lookup() na etapa Formulas do pipeline. Você ainda pode usar a etapa Join para retornar o restante das colunas, se necessário.

**Posso mudar a ordem da etapa Join e Map Columns?**

Nesse momento, a etapa Join aparecerá ao lado da etapa Model ou da etapa Map Columns (selecione uma ou outra).

O Map Columns sempre será a etapa anterior à Table, a menos que haja uma etapa Assign Cost Pools. Essencialmente, tudo o que vem depois de Map Columns faz parte da oferta de conteúdo. No entanto, você pode ter quantas etapas ou transformações quiser antes da etapa Map Columns.

## Tabelas mapeadas e o conjunto de dados mestre

**Vejo uma coluna Source Table no conjunto de dados mestre, mas não mapeei nada para ela. De onde ele veio?**

Apptio adiciona automaticamente uma coluna com o nome da tabela que enviou dados para um conjunto de dados mestre por meio do Map Columns. Isso permite que você rastreie seus dados do modelo até os dados de origem com mais rapidez. Somente os dados adicionados por meio de Map Columns têm essas informações. Você deve adicionar manualmente quaisquer dados anexados às informações ou elas ficarão em branco.

**VEJA TAMBÉM** :

- [Colunas do mapa](mapcolumns.htm "(Abre em uma nova guia ou janela)")
- [Atribuir pools de custos com aprendizado de máquina](assigncostpools.htm "(Abre em uma nova guia ou janela)")
- [Configurar o aprendizado de máquina para pools de custos](configuremachinelearning.htm "(Abre em uma nova guia ou janela)")
