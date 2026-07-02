---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Integração de dados de consumo"
breadcrumb:
  - "Billing"
  - "Configurando os fundamentos do faturamento (implementação)"
source_path: "boit/billing/config-be/integrate.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Integração de dados de consumo

Os dados de consumo são o que impulsionam as unidades no cálculo do PxQ.

Etapas típicas de integração:

1. **Identificar fontes**
   - Sistemas de emissão de bilhetes ou ITSM (por exemplo, número de bilhetes).
   - Sistemas de identidade (usuários ativos).
   - Ferramentas de monitoramento ou medição (capacidade ou uso).
   - Planilhas nas quais não existe nenhum sistema de registro.
2. **Defina o layout de destino**
   - Cada registro deve incluir:
     - Ponto final.
     - ID do consumidor ou uma chave mapeável.
     - Oferecendo ID ou uma chave mapeável.
     - Unidades consumidas.
     - Opcionalmente, inclua atributos como ambiente, região ou centro de custos.
3. **Crie processos ETL ou de upload**
   - Use o TBM Studio ETL, Datalink ou uma integração equivalente para carregar dados na tabela de consumo de faturamento.
   - Para feeds pequenos ou ad hoc, use o Table Upload e um modelo controlado CSV.
4. **Executar carga inicial em Desenvolvimento**
   - Carregue um período de amostra e confirme:
     - Os volumes parecem razoáveis.
     - As chaves correspondem às ofertas e aos consumidores.
5. **Promova uma lógica de consumo comprovada**
   - Depois que os padrões forem validados em Desenvolvimento e Preparação, promova-os para Produção.
