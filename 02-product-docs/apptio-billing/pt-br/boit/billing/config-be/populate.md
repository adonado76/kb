---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Preenchendo o catálogo de ofertas"
breadcrumb:
  - "Billing"
  - "Configurando os fundamentos do faturamento (implementação)"
source_path: "boit/billing/config-be/populate.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Preenchendo o catálogo de ofertas

O catálogo de ofertas determina o que aparece nas contas. Deve ser preenchido e validado antes da primeira execução de faturamento.

Passos:

1. **Defina o catálogo inicial**
   - Liste os serviços/produtos a serem faturados.
   - Atribuir:
     - Nomes curtos e fáceis de reconhecer.
     - Unidades de medida (por exemplo, usuário por mês, GB por mês).
     - Oferecendo IDs estáveis e exclusivas.
2. **Carregar ofertas na tabela**
   - Usar:
     - TBM Studio ETL se a configuração for totalmente gerenciada no Studio, ou
     - Carregamento da tabela se o catálogo for mantido em um arquivo do Excel ( CSV ) ou planilha eletrônica.
3. **Definir sinalizadores**
   - Marca:
     - Faturável = Sim para ofertas que devem aparecer nas faturas.
     - Ativo para ofertas atualmente em uso.
     - Sinalizadores internos ou similares, se algumas ofertas forem utilizadas apenas para alocações internas.
4. **Validar catálogo**
   - Execute um relatório ou consulta simples para:
     - Verifique se há duplicatas.
     - Confirme se as unidades estão preenchidas.
     - Confirme se os indicadores de status estão corretos.

Mantenha o catálogo inicial conciso. É mais fácil adicionar ofertas posteriormente do que reverter um catálogo desorganizado.
