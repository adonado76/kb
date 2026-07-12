---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Limpar e mapear dados usando as colunas do mapa"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Trabalhar com dados"
  - "Transformar e enriquecer dados"
source_path: "studio/new-uc/howtoguides/work-with-data/clean-map.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Limpar e mapear dados usando as colunas do mapa

## Objetivo

Mapeie as colunas dos dados de origem para esquemas padronizados de conjuntos de dados mestres, garantindo que os dados estejam em conformidade com a estrutura esperada para modelagem de custos e geração de relatórios.

## Quando usar isto

Use as colunas do mapa quando precisar:

- Alinhar dados externos (contabilidade geral, orçamento, previsão) às tabelas-mestre canônicas
- Padronizar dados de fontes diversas em estruturas unificadas
- Preparar dados para uso por objetos de modelo
- Certifique-se de que os campos obrigatórios sejam preenchidos para os processos subsequentes

## Pré-requisitos

- Tabela de origem carregada e importada
- Compreensão do esquema do conjunto de dados mestre de destino
- Tipos de coluna configurados corretamente na tabela de origem

## Tempo estimado

15 a 20 minutos para a configuração inicial; 5 a 10 minutos para atualizações de rotina

## Passos

1. Verifique a tabela de origem que você deseja mapear no Explorador de Projetos.
2. Clique em **“Adicionar etapa”** no pipeline de transformação e selecione “**Mapear colunas** ”.
3. Selecione o conjunto de dados mestre de destino (por exemplo, Mestre de fontes de custo, Mestre de fornecedores).
4. Mapeie as colunas de origem para as colunas de destino:
   - O sistema combina automaticamente colunas com nomes idênticos (sem distinção entre maiúsculas e minúsculas)
   - Verifique as colunas mapeadas automaticamente (indicadas por marcas de seleção verdes)
   - Para colunas obrigatórias não mapeadas (marcadas com asteriscos), selecione a coluna de origem apropriada no menu suspenso
   - Para mapear colunas com tipos diferentes, insira uma fórmula que comece com = (por exemplo, =Value( {Column} ) para converter texto em número)
5. (Opcional) Adicione colunas personalizadas ao conjunto de dados principal clicando em “**Adicionar coluna personalizada** ”. Essas adições são mantidas nas atualizações.
6. (Opcional) Para extrair dados adicionais de tabelas relacionadas, clique em **“Juntar”**, adicione ligações a outras tabelas e mapeie as colunas unidas.
7. Verifique a pré-visualização na parte inferior da caixa de diálogo para confirmar os mapeamentos.
8. Clique em **Salvar** para aplicar a etapa “Mapear colunas”.

## Resultados esperados

Seus dados de origem agora estão em conformidade com o esquema do conjunto de dados mestre e aparecem na visualização com todas as colunas mapeadas. A tabela está pronta para ser utilizada em objetos de modelo e relatórios. Uma coluna ***da tabela de origem*** é adicionada automaticamente para rastrear a linhagem dos dados.

## Armadilhas comuns

- **Coluna não aparece no menu suspenso:** verifique se o tipo da coluna de origem corresponde ao tipo de destino. As colunas numéricas não aparecem ao mapear para campos de rótulo. Corrija isso acessando a etapa de importação e alterando o tipo da coluna.
- **Colunas obrigatórias não mapeadas:** embora seja possível salvar sem mapear todas as colunas obrigatórias, os objetos do modelo a jusante podem gerar erros. Sempre mapeie os campos obrigatórios (marcados com \*) antes de usar a tabela nos modelos.
- **Erros de incompatibilidade de tipos:** Ao mapear um código numérico para um campo de rótulo, use uma fórmula como =NumberFormat({Account }*,"#,###.##”;* ) para converter o tipo.

## Tarefas relacionadas

- [Aplicar fórmulas para transformar dados](apply-formula.html)
- [Juntar dados de várias fontes](join-data.html)
- <../../reference/data-studio-ref.html>

**Tópico principal:** [Transformar e enriquecer dados](../../../../studio/new-uc/howtoguides/work-with-data/transform-enrich-data.html)
