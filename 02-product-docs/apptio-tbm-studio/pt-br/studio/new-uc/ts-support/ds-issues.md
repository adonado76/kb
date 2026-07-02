---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Data Studio Questões"
breadcrumb:
  - "TBM Studio"
  - "Solução de problemas e suporte"
  - "Problemas comuns e soluções"
source_path: "studio/new-uc/ts-support/ds-issues.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Data Studio Questões

## Os dados não carregam ou o envio falha

**Sintomas:**

- O envio do arquivo falha devido a um erro de validação
- A tabela de dados mostra zero linhas após o upload
- O upload parece travar ou atingir o tempo limite

**Possíveis causas:**

- O formato do arquivo não corresponde ao esquema esperado
- Faltam colunas obrigatórias
- Incompatibilidades de tipos de dados
- Problemas de codificação de arquivos
- O arquivo excede os limites de tamanho

**Soluções:**

1. **Verifique o formato e o conteúdo do arquivo** - Confirme se o arquivo contém conteúdo e se está corretamente delimitado. Verifique se os cabeçalhos das colunas correspondem ao esquema esperado. Certifique-se de que as colunas numéricas contenham apenas valores numéricos.
2. **Verifique a validação das colunas** - Abra a tabela de dados e verifique se há algum indicador de validação (números vermelhos ao lado do nome da tabela). Clique no ícone para ver os erros de validação específicos. Corrija as incompatibilidades de tipo de dados no seu arquivo de origem.
3. **Verifique as divisões por data** - Certifique-se de que os dados referentes ao período correto estão sendo carregados. Verifique se as colunas de data estão no formato esperado.

**Dicas de prevenção**

- Sempre visualize os dados antes de enviá-los
- Use a etapa de validação de dados para detectar erros logo no início
- Mantenha convenções consistentes de nomenclatura e formato de arquivos

*Relacionado: Arquitetura de dados (Seção 4.2 ), Carregar dados (Seção 3.1.1 )*

## A tabela de transformação não está sendo calculada

**Sintomas:**

- O Transform exibe dados desatualizados
- Os objetos do modelo a jusante apresentam valores incorretos
- Aparece um ícone de erro na tabela de transformação

**Soluções:**

1. **Salvar e verificar se há erros** - Clique em “Salvar” em todas as tabelas de transformação modificadas. Procure os ícones de erro (números vermelhos) ao lado do nome da tabela.
2. **Verificar o status do documento** - Verifique se o documento está em uso. Se o arquivo estiver em uso por outro usuário, entre em contato com ele.
3. **Revisar a lógica das etapas de transformação** - Abrir cada etapa de transformação e verificar as fórmulas. Verifique se há referências circulares.
