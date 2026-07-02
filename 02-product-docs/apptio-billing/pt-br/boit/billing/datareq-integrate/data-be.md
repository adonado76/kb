---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Requisitos de dados para o Billing Essentials"
breadcrumb:
  - "Billing"
  - "Requisitos e integração de dados"
source_path: "boit/billing/datareq-integrate/data-be.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Requisitos de dados para o Billing Essentials

Observação: aplica-se apenas ao Billing Essentials.

O Billing Essentials utiliza um conjunto específico de tabelas e conjuntos de dados para executar um processo de faturamento e cobrança ( PxQ ). Os nomes e as estruturas exatas das tabelas podem variar de acordo com a versão do modelo, mas o padrão é consistente.

Famílias típicas de tabelas:

- **Solução / Biblioteca de ofertas**
  - Uma lista de ofertas faturáveis (serviços, produtos ou pacotes).
  - Campos comuns:
    - Apresentar identificação e nome.
    - Unidade de medida.
    - Sinalizador ou status ativo.
    - Sinalizadores para indicar se a oferta é faturável, apenas exibida ou interna.
- **Alimentação para consumo**
  - Unidades consumidas pela oferta e pelo consumidor durante um determinado período.
  - Campos comuns:
    - Identificação do consumidor.
    - Oferecendo ID (ou uma chave que corresponda a ele).
    - Período (mês, trimestre, etc.).
    - Unidades consumidas.
    - Atributos opcionais, como ambiente, região ou segmento do centro de custos.
- **Tabelas de tarifas e preços**
  - Taxas por oferta e período.
  - Campos comuns:
    - Apresentando documento de identificação.
    - Período ou data de vigência.
    - Valor da taxa.
    - Tipo de tarifa (por exemplo, padrão, com desconto, promocional).
- **Tabelas mestre de faturamento/saída**
  - Resultados da cobrança e quaisquer resultados prontos para publicação.
  - Campos comuns:
    - Identificação do consumidor.
    - Apresentando documento de identificação.
    - Ponto final.
    - Unidades, taxa e custo total.
    - Campos opcionais do segmento GL para exportações do diário.

Padrões de integração para o Billing Essentials:

- As fontes de alimentação de consumo geralmente vêm de:
  - Sistemas de emissão de bilhetes ou ITSM.
  - Sistemas de identidade/acesso (para contagem de usuários).
  - Ferramentas de monitoramento ou medição.
  - Planilhas ou arquivos de e-mail ( CSV ) quando não existe um sistema de registro.
- Os dados são normalmente carregados por:
  - Processos ETL do TBM Studio.
  - Datalink ou outras ferramentas de integração.
  - Upload de tabelas para entradas estruturadas CSV quando o acesso ao Studio não está disponível para a organização de TI.

Se um consumidor ou oferta no feed de consumo não corresponder às tabelas principais, as cobranças relacionadas podem cair ou aparecer em visualizações de exceção. Planeje o controle de qualidade básico dos dados em torno dessas junções.
