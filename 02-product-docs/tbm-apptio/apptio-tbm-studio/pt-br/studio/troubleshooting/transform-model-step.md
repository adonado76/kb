---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Transformar colunas de etapas do modelo"
breadcrumb: []
source_path: "studio/troubleshooting/transform-model-step.html"
images:
  - "resources/images/troubleshooting_images/transform-model-step-columns-1.png"
  - "resources/images/troubleshooting_images/transform-model-step-columns-2.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Transformar colunas de etapas do modelo

Há um número máximo de colunas que você pode usar em sua tabela com uma etapa de modelo. Se você exceder esse limite, o site TBM Studio levará mais tempo para calcular os resultados e também não calculará o objeto modelo. Isso resulta em números incorretos em todos os modelos que usam esse objeto.

![](../../../../../03-media/apptio-tbm-studio/resources/images/troubleshooting_images/transform-model-step-columns-1.png)

## Recomendação de configuração para transformar colunas de etapas do modelo com erro excedido

Para resolver esse erro, adicione uma etapa de ocultar e renomear e oculte todas as colunas que não forem necessárias.

Para adicionar uma etapa de ocultar e renomear:

1. Na exibição **Project Explorer** > selecione **Tabelas**
2. Selecione o menu suspenso do projeto, selecione a tabela necessária para o projeto
3. Na guia **Home**, selecione **Check Out**
4. Adicione a etapa a partir do ícone + mostrado na configuração da etapa
5. Selecione **Hide and Rename (Ocultar e renomear** ) na configuração da etapa e, em seguida, selecione **Add Columns (Adicionar colunas)**
6. Selecione as colunas a serem ocultadas para ficar abaixo do limite.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/troubleshooting_images/transform-model-step-columns-2.png)
