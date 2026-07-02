---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Exportação e lançamento de diários"
breadcrumb:
  - "Billing"
  - "Executando o ciclo de faturamento"
source_path: "boit/billing/run-bill-cycle/exporting.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Exportação e lançamento de diários

Para estornos, os resultados de faturamento geralmente alimentam os sistemas financeiros como diários.

Etapas típicas:

1. **Prepare o conjunto de dados do diário**
   - Use um relatório ou exportação que contenha:
     - Identificadores de consumidores que correspondem às estruturas financeiras.
     - Mapeamentos do segmento GL ou códigos contábeis.
     - Valores por conta, consumidor e período.
     - Quaisquer campos de referência obrigatórios, como tipo de documento ou descrição.
2. **Validar totais do diário**
   - Confirme que:
     - A soma dos lançamentos contábeis corresponde ao total das cobranças.
     - Não há linhas órfãs com códigos ausentes.
     - Os débitos e créditos se equilibram se ambos estiverem presentes na exportação.
3. **Exportar no formato necessário**
   - Ajuste a ordem das colunas, os nomes dos campos e os tipos de dados para atender aos requisitos do sistema financeiro.
   - Salve no formato necessário, normalmente CSV, texto com largura fixa ou um layout compatível com integração.
4. **Encaminhe ou envie para o departamento financeiro**
   - Ou:
     - Forneça o arquivo ao departamento financeiro para upload manual.
     - Use um processo de integração para enviar diários diretamente.

1. **Confirmar postagem e rastrear**
   - Verifique se:
     - Os diários foram aceitos sem erros.
     - O sistema Financeiro mostra os totais esperados por conta e consumidor.
     - Capture referências ou IDs de documentos para auditoria e reconciliação.

Mesmo que a organização esteja usando apenas o showback atualmente, pode ser útil manter os resultados prontos para registro disponíveis, para que o chargeback possa ser habilitado posteriormente sem a necessidade de redesenhar o modelo de faturamento.
