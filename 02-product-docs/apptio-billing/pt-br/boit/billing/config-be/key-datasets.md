---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Principais conjuntos de dados e tabelas"
breadcrumb:
  - "Billing"
  - "Configurando os fundamentos do faturamento (implementação)"
source_path: "boit/billing/config-be/key-datasets.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Principais conjuntos de dados e tabelas

O Billing Essentials depende de um pequeno número de tabelas principais. Os nomes exatos podem variar de acordo com o modelo, mas os padrões são consistentes.

Categorias típicas:

- **Tabela de ofertas/serviços**
  - Armazena o catálogo de ofertas faturáveis.
  - Campos comuns:
    - Apresentar identificação e nome.
    - Unidade de medida.
    - Sinalizador ativo/inativo.
    - Sinalizador faturável (sim/não).
- **Mestre do consumidor**
  - Compartilhado com o Cálculo de Custos ou alinhado a ele.
  - Campos comuns:
    - Identificação e nome do consumidor.
    - Hierarquia (por exemplo, unidade de negócios, departamento, centro de custos).
    - Atributos opcionais como região, função ou gerente.
- **Tabela de consumo**
  - Mantém os volumes de uso por oferta e consumidor por período.
  - Campos comuns:
    - Ponto final.
    - Identificação do consumidor.
    - Oferecendo ID (ou uma chave mapeada para ele).
    - Unidades consumidas.

- **Tabela de taxas**
  - Mantém as taxas para cada oferta e período.
  - Campos comuns:
    - Apresentando documento de identificação.
    - Período ou início/fim efetivo.
    - Valor da taxa e moeda.
    - Tipo de tarifa opcional (padrão, ajustada, promocional).
- **Saída de faturamento / tabela de arquivo**
  - Armazena as taxas calculadas.
  - Campos comuns:
    - Ponto final.
    - Identificação do consumidor.
    - Apresentando documento de identificação.
    - Unidades, taxa, custo total.
    - Campos opcionais de mapeamento de diário.
