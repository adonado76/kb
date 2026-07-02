---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Executando o cálculo do padrão de faturamento em Desenvolvimento/Preparação"
breadcrumb:
  - "Billing"
  - "Configurando o padrão de faturamento (implementação)"
source_path: "boit/billing/config-bs/run-bill.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Executando o cálculo do padrão de faturamento em Desenvolvimento/Preparação

Depois que os mestres de domínio, unidades, preços e mapeamentos estiverem definidos, o cálculo do Padrão de Faturamento poderá ser testado.

Passos:

1. **Executar modelos de faturamento em desenvolvimento**
   - Execute os modelos padrão de faturamento primários:
     - Serviços e consumidores.
     - Modelos específicos de domínio (nuvem, aplicativos, infraestrutura, projetos).
     - Modelos de preço e variação, se configurados.
2. **Inspecione os principais resultados**
   - Verificar:
     - Tabelas de taxas básicas (serviços × consumidores).
     - Visualizações de domínio (nuvem, servidores, armazenamento, dispositivos, aplicativos, projetos).
     - Tabelas de variação e tabelas de taxas unitárias.
3. **Publicar e testar relatórios em Desenvolvimento**
   - Abrir relatórios representativos do Padrão de Faturamento para:
     - Encargos gerais.
     - Pelo menos um domínio (por exemplo, nuvem ou aplicativos).
     - Foram utilizadas visualizações de taxa unitária e variância.
4. **Mudar para o ambiente de teste para controle de qualidade completo**
   - Após a validação inicial, verifique as alterações.
   - Valide com dados mais completos no Staging:
     - Reexecute os modelos de faturamento.
     - Execute relatórios de controle de qualidade e exceções.
     - Valide as opiniões das principais partes interessadas (líderes de nuvem, proprietários de aplicativos, equipes de infraestrutura, finanças).
