---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Carregar dados a partir de arquivos (Excel, CSV )"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Trabalhar com dados"
  - "Importação e gerenciamento de dados"
source_path: "studio/new-uc/howtoguides/work-with-data/upload-data-files.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Carregar dados a partir de arquivos (Excel, CSV )

**Objetivo:** Importar dados de arquivos do Excel ou do programa “ CSV ” para as tabelas do TBM Studio, a fim de disponibilizá-los para modelagem de custos e geração de relatórios.

**Quando usar este procedimento:** Use o envio de arquivos quando precisar:

- Importar conjuntos de dados pontuais ou específicos
- Carregar dados de custos mensais dos sistemas financeiros
- Importar dados externos que não estão disponíveis por meio de conectores automatizados
- Teste as estruturas de dados antes de configurar feeds automatizados

**Pré-requisitos:**

- Permissões para fazer check-out e editar tabelas (função AccessDev )
- Arquivo de dados em um formato compatível (Excel. xlsx/.xls, CSV, TSV ou outros formatos delimitados)
- O nome do arquivo contém apenas um ponto antes da extensão (por exemplo, cost\_data.xlsx, e não cost.data.xlsx )
- Saber em qual tabela os dados devem ser inseridos (ou permissão para criar uma nova tabela)

**Tempo estimado:** 10 a 15 minutos para o primeiro envio; 5 minutos para os envios seguintes

## Passos

**Crie uma tabela e envie seu primeiro arquivo**

1. **Crie uma nova tabela** (caso ainda não exista):
   - No **Explorador** de Projetos, clique em **Novo** → **Tabela**
   - Digite um **nome** para a tabela (por exemplo, “Contabilidade Geral”, “Custos do Servidor”)
   - Digite ou selecione uma **categoria** para organizar a tabela no Explorador de Projetos
   - Clique **em OK**
2. **Configure a fonte da tabela:**
   - O aplicativo exibe a etapa **"Fonte"** no fluxo de transformação
   - No campo “**Descrição da** tabela”, insira uma breve descrição da finalidade da tabela
   - Clique **em “Carregar arquivo”**
   - É adicionada uma etapa **de upload** ao pipeline
3. **Carregue seu arquivo de dados:**
   - Clique no painel **"Detalhes"** e navegue até o arquivo, ou arraste o arquivo do Explorador do Windows para o painel **"Detalhes"**
   - O sistema adiciona uma etapa **de importação** ao fluxo de trabalho e começa a analisar o arquivo
4. **Configurar as definições de importação:**

   Clique na etapa **“Importar”** no fluxo de trabalho para verificar as configurações:

   **Configurações básicas:**

   - **Iniciar a importação na linha:** especifique qual linha contém o primeiro registro de dados (o padrão é a linha 1, considerando que a linha 0 é o cabeçalho)
   - **Colunas a excluir:** selecione as colunas que você não deseja importar
   - **Codificação de texto:** Escolha a codificação de caracteres (selecione “Detectar codificação automaticamente” se não tiver certeza)
   - **Delimitado:** Selecione o caractere delimitador (vírgula, tabulação, barra vertical, etc.)
   - **Qualificador de texto:** especifique o caractere usado para delimitar o texto com caracteres especiais (o padrão são as aspas duplas)

   **Configuração da coluna:**

   - Consulte a seção **“Colunas”**
   - Verifique se os tipos de coluna foram detectados corretamente (Chave, Texto, Número, Data)
   - Altere os tipos das colunas conforme necessário clicando no tipo
   - Para filtrar as colunas por tipo, clique no ícone do tipo no campo de pesquisa da coluna **“Tipo”**
5. **Configurar a validação de dados** (opcional, TBM Studio v12.1+ ):
   - **A validação de dados** verifica se houve alterações no esquema ao fazer o upload para tabelas existentes: coluna adicionada, coluna excluída, tipo de coluna alterado, cardinalidade da coluna alterada
   - **A verificação de cardinalidade** verifica o conteúdo da coluna:
     - **Qualquer:** Sem validação de cardinalidade (padrão)
     - **Primeiro:** Garante que todos os valores sejam únicos (sem duplicatas)
     - **Muitos:** garante que cada entrada seja duplicada
6. **Selecione um ciclo de atualização:**

   Na parte superior da tela, selecione a frequência com que os dados serão atualizados:

   - **Atualizações pontuais:** sem cronograma; envie conforme necessário
   - **1 versão; Sem atualizações programadas:** Versão única, substituir ao fazer o upload
   - **1 versão; Atualização mensal:** atualização mensal, substitui os dados existentes
   - **1 versão; Atualização anual:** Atualização anual
   - **Versões mensais; Atualização mensal:** Nova versão a cada mês (consulte “Tabelas de versões para dados mensais”)
   - **Versões anuais** (várias opções): conjuntos de dados anuais com diferentes padrões de atualização
7. **Revise e salve:**
   - Clique na etapa **“Tabela”** no fluxo de trabalho para visualizar os dados importados
   - Verifique se os dados aparecem corretamente
   - Clique em **“Salvar”** na guia “Página inicial”
   - Clique em **“Check-in”** para disponibilizar a tabela para o projeto

**Carregar dados adicionais em uma tabela existente**

Quando você precisar adicionar mais dados a uma tabela existente (por exemplo, ao inserir os custos do próximo mês):

1. **Fazer check-out da tabela:** Navegue até a tabela no **Explorador** de Projetos, clique com o botão direito do mouse e selecione **“Fazer check-out”**
2. **Selecione o período desejado** (para tabelas com versões mensais/anuais): use o seletor de datas na parte superior da tela para selecionar o período ao qual os dados devem ser adicionados. Aparece um espaço reservado na etapa de upload.
3. **Carregue o novo arquivo:** clique no espaço reservado e selecione o arquivo ou arraste-o para dentro do espaço reservado.
4. **Salvar e fazer check-in:** clique em **“Salvar”** na guia “Página inicial” e, em seguida, clique em “**Fazer check-in** ”.

## Resultados esperados

- Seu arquivo de dados foi importado com sucesso para o TBM Studio
- Os tipos de coluna são identificados corretamente (ou corrigidos manualmente)
- Os dados aparecem na visualização da tabela com a formatação correta
- A tabela está disponível para uso em transformações, modelos e relatórios
- No caso de tabelas com versões, cada período contém seu próprio conjunto de dados

## Problemas comuns e solução de problemas

**Problema:** Erro “Extensão de arquivo não suportada”

- **Motivo:** O nome do arquivo contém vários pontos (por exemplo, cost.data.xlsx )
- **Solução:** Renomeie o arquivo para que tenha apenas um ponto antes da extensão (por exemplo, cost\_data.xlsx )

**Problema:** os dados aparecem nas colunas erradas ou com formatação incorreta

- **Causa:** As configurações do delimitador ou do qualificador de texto estão incorretas
- **Solução:** Verifique as configurações da etapa de importação e ajuste o delimitador e o qualificador de texto para que correspondam ao formato do seu arquivo

**Problema:** os dados numéricos aparecem como texto

- **Causa:** O tipo da coluna foi detectado incorretamente ou os dados contêm caracteres não numéricos
- **Solução:** Na etapa de importação, altere o tipo da coluna para Número. Se o problema persistir, verifique se há caracteres especiais nos seus dados de origem.

**Problema:** O envio do arquivo falha ou os dados parecem estar corrompidos

- **Motivo:** o arquivo do Excel contém macros, formatação especial ou fórmulas
- **Solução:** Com o analisador de Excel aprimorado ( v12.11.16+ ), o sistema lê os valores brutos diretamente. Salve o arquivo do Excel como um arquivo do TBM Studio ( CSV ), remova formatações especiais ou macros, ou aplique formatação n utilizando etapas de transformação.

## O que vem a seguir

Após enviar os dados com sucesso, você pode:

- [Transforme os dados](transform-enrich-data.html) : adicione etapas de transformação para limpar, mapear, filtrar ou unir dados.
- [Adicionar a um modelo](../build-cost-model/model-basics.html) : Incorporar a tabela a um modelo de custos (consulte a Seção 3.2 )
- Configurar o monitoramento da atualidade dos dados: Configure alertas para dados ausentes ou desatualizados (consulte a seção 6.4 )
- [Automatizar uploads](connect-external-dl.html) : Mude para uploads via DataLink ou por API para feeds de dados regulares

**Tópico principal:** [Importação e gerenciamento de dados](../../../../studio/new-uc/howtoguides/work-with-data/data-import-mgmt.html)
