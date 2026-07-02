---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Comparando dados entre a interface do usuário do relatório e as exportações do CSV"
breadcrumb:
  - "Cloudability Premium"
  - "Referência de dados"
source_path: "product/comparing-data-between-report.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Comparando dados entre a interface do usuário do relatório e as exportações do CSV

Ao exportar seus relatórios em Cloudability, você poderá observar:

- As unidades de medida de algumas métricas não coincidem entre a interface do usuário do relatório e os dados exportados do CSV.
- Alguns nomes de colunas não coincidem entre a interface do usuário do relatório e os dados exportados do CSV.

**Diferença nas unidades de medida ( UoM ) entre a interface do usuário do relatório e os dados exportados do CSV**

Os dados exportados no CSV podem apresentar uma unidade de medida diferente para algumas métricas. Para algumas medidas, como GB e porcentagem, queremos fornecer valores como decimais com precisão total disponível e sem formatação, para que você possa formatar como desejar para usos programáticos e não precise tentar "analisar" a formatação. No entanto, fornecer esses "números brutos" com precisão decimal total na interface do usuário do relatório tornaria a interface do usuário menos utilizável.

**Diferença nos títulos das colunas entre a interface do usuário do relatório e os dados exportados do CSV**

Consulte esta tabela para entender o mapeamento dos títulos das colunas que diferem entre os dados exportados do CSV e a interface do usuário do relatório:

| Cabeçalho no arquivo “ CSV ” exportado | Cabeçalho na interface do usuário do relatório | Comentários |
| --- | --- | --- |
| custo faturado | Custo (total combinado) | � |
| taxa mista | Taxa (combinada) | � |
| custo\_antes\_dos\_impostos | Custo (total não misturado antes dos impostos) | � |
| Iops | IOPS Meses | � |
| meses | Meses de GiB | � |
| byte\_horas | Horas de GiB | � |
| Mês | Mês (categoria) | � |
| chave\_de\_serviço | Código do produto | � |
| service\_name | Produto Nome | � |
| região\_zona | Zona de disponibilidade | � |
| identificador\_da\_conta | ID da conta do pagador | � |
| account\_name | Nome da conta do pagador | � |
| identificador de conta de fornecedor | ID da conta | � |
| nome\_do\_grupo [x] | Grupo de contas [x] | 'x' representa a cardinalidade dos grupos de contas (por exemplo: Grupo de contas 1, Grupo de contas 2, Grupo de contas 3) em seu ambiente Cloudability. |
| é\_capex | Tarifas únicas | � |
| Semana | Semana (categoria) | � |
| bytes\_transferidos | Transferência de dados ( GiB ) | � |
| custo não combinado | Custo (total) | � |
| taxa não combinada | Taxa (não combinada) | � |
| taxa\_de\_utilização\_reservada | Taxa de cobertura reservada | � |
| identificador\_de\_recursos | ID do recurso | � |
| contagem de identificadores de recursos | Contagem de recursos | � |
| custo\_amortizado\_total | Custo (amortizado) | � |
| identificador\_de\_reserva | ID de Reserva | � |
| nome\_do\_serviço\_ampliado | Nome do serviço | � |
| ano\_mês | Mês (ano) | � |
| ano\_semana | Semana (ano) | � |
| ajustado ao custo | Ajuste de custos | � |
| custo\_ajustado | Custo (ajustado) | � |
| Categoria[x] | Dimensão do negócio [x] | 'x' representa a cardinalidade das Business Dimensions (por exemplo: Business Dimension 1, Business Dimension 2, Business Dimension 3) em seu ambiente Cloudability. |
| chave de categoria[x] | Chave de dimensão do negócio [x] | 'x' representa a cardinalidade das Business Dimension Keys (por exemplo: Business Dimension Key 1, Business Dimension Key 2, Business Dimension Key 3) em seu ambiente Cloudability. |
| custo\_amortizado\_ajustado\_total | Custo (amortizado ajustado) | � |
| custo\_público\_sob\_demanda | Custo (lista) | � |
| classe\_de\_oferta | Classe de reserva | � |
| nome\_do\_cluster\_do\_contêiner | Nome do cluster | � |
| espaço\_nome do contêiner | Namespace: | � |
| números\_ancestrais | GCP Números de ascendência | � |
| custo\_de\_fairshare amortizado | Custo do Fairshare (amortizado) | � |
| custo amortizado\_utilizado | Custo utilizado (amortizado) | � |
| amortized\_idle\_cost Ocioso | Custo (amortizado) | � |
| custo\_de\_fairshare\_ajustado | Custo do Fairshare (ajustado) | � |
| custo\_utilizado\_ajustado | Custo utilizado (ajustado) | � |
| custo\_ajustado\_idle | Custo ocioso (ajustado) | � |
| custo\_de\_fairshare\_ajustado\_amortizado | Custo do Fairshare (amortizado ajustado) | � |
| custo\_utilizado\_amortizado\_ajustado | Custo Utilizado (Amortizado Ajustado) | � |
| adjusted\_amortized\_idle\_cost Ocioso | Custo (amortizado ajustado) | � |
