---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Relatórios diários/horários na nuvem - Extensão ou alteração ( 12.5 e anteriores)"
breadcrumb: []
source_path: "cost-transparency/configuration/clouddailyhourlyreports.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Relatórios diários/horários na nuvem - Extensão ou alteração ( 12.5 e anteriores)

Os relatórios diários/horários são criados em um formato de dados que permite armazenamento e consultas rápidas e eficientes em conjuntos de dados de volume muito alto (como contas de nuvem muito granulares, como o Relatório de custo e uso do AWS ). Como resultado, a extensão do esquema dos conjuntos de dados envolvidos e a modificação dos relatórios criados com base nesses conjuntos de dados exigem alguma configuração

Aplica-se a: Cloud em Costing Standard em TBM Studio 12.3.3 e posterior; Cloud Business Management em TBM Studio 12.5.x e anterior

Os dados diários/horários são armazenados em um formato diferente, separadamente de outros dados do site Apptio. O objeto sobre o qual os relatórios são criados chama-se dbr\_daily, que pode ser encontrado na seção de tabelas do site TBM Studio, mas, devido ao volume extremamente alto de dados e ao novo formato de dados, algumas ações não podem ser executadas:

- Você não poderá ver os dados em TBM Studio.
- Não é possível adicionar itens ao pipeline de transformação (com a exceção explicada na seção "Adição de atributos novos e personalizados", abaixo).
- Não é possível adicionar transformações ao conjunto de dados.

## Ampliação do esquema diário/hora

Para usar atributos prontos para uso (a maneira mais rápida de ver os dados específicos de sua organização):

### Procedimento

1. Mapeie as colunas das faturas do provedor, como contas ou etiquetas, para os atributos do CBM prontos para uso.

   Por exemplo, se você tiver uma tag de usuário chamada Owner, mapeie essa tag para o atributo System Owner existente.
2. Para obter mais informações, consulte Mapear tags AWS para Apptio Schema ou Valores de tags em Azure para Apptio Schema.
