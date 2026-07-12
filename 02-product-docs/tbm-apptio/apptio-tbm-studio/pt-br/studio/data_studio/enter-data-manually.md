---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Inserir dados manualmente usando tabelas editáveis"
breadcrumb: []
source_path: "studio/data_studio/enter-data-manually.html"
images:
  - "resources/images/studio_images/enter-data-1.png"
  - "resources/images/studio_images/enter-data-2.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Inserir dados manualmente usando tabelas editáveis

**Aplica-se a** : TBM Studio R12.0 e posterior

Você pode usar tabelas editáveis para inserir dados manualmente. Esses dados são então mantidos diretamente no banco de dados do projeto Apptio. Por exemplo, você pode usar tabelas editáveis para mapear outros pools de custos para os IT Resource Towers.

Você pode criar dois tipos diferentes de tabelas editáveis:

- Tabela editável em branco: Essa é uma tabela simples em que os valores de linha e coluna são digitados diretamente na interface do usuário Apptio por um ou mais indivíduos.
- Tabela editável enriquecida: Essa é uma tabela combinada ou gerada em que alguns dos valores são digitados e outros vêm de outra tabela.

Você deve usar uma tabela editável enriquecida se tiver dados gerados por máquina que precisam de um ser humano para enriquecê-los. Por exemplo, você pode querer que um ser humano forneça um "projeto responsável" para cada tag de instância detectada em uma fatura Amazon Web Services.

Dica: se os usuários finais quiserem adicionar e remover linhas na superfície do relatório, crie uma tabela editável em branco independente. Nesse caso, você deve considerar a tabela editável como a fonte da verdade, não a superfície do relatório.

## Tabelas editáveis em branco

É possível criar uma tabela simples em que os valores de linha e coluna são digitados diretamente na interface de usuário do Apptio por um ou mais indivíduos.

## Criar uma tabela editável em branco

1. Na guia Página **inicial**, no grupo **Documento**, selecione Novo > Tabela editável.
2. Na caixa de diálogo New Manually Entered Table (Nova tabela inserida manualmente), selecione Blank Table (Tabela em branco).
3. Quando solicitado, digite um nome para a tabela editável e selecione OK.
4. Vá para Steps > Configure Columns (Etapas > Configurar colunas) e atualize as propriedades da coluna.

   [Saiba mais sobre as propriedades da coluna](editabletables.html "Aplica-se a: TBM Studio 12.6 e posterior")
5. Verifique a tabela editável.

## Tabelas editáveis enriquecidas

Você pode criar uma tabela editável com base em uma tabela Transform existente. Os usuários não podem excluir linhas de uma tabela editável enriquecida porque as linhas incluídas são baseadas na tabela Transform de origem.

Observação: Às vezes, os usuários usam tabelas editáveis enriquecidas quando uma [função TableMatch](../formulas-and-functions/functions/tablematch.html "Retorna um valor com base em uma tabela de regras que funciona como um conjunto de instruções IF. Cada linha da tabela de regras define uma regra. As condições na mesma linha são combinadas com AND, e os valores na mesma célula são tratados como condições OR.") ou similar seria uma opção melhor. Embora existam casos de uso válidos para tabelas editáveis enriquecidas, considere se elas são a solução correta.

## Criar uma tabela editável enriquecida

1. Na guia Página **inicial**, no grupo **Documento**, selecione Novo > Tabela editável.
2. Na caixa de diálogo New Manually Entered Table (Nova tabela inserida manualmente), selecione Enriched Table (Tabela enriquecida).
3. Quando solicitado, digite um nome para a tabela editável e selecione OK.
4. Vá para Etapas > Gerado e configure a tabela de origem.
5. Para adicionar colunas editáveis à tabela enriquecida, vá para Steps > Configure Columns (Etapas > Configurar colunas), selecione Add a new column (Adicionar uma nova coluna) e atualize as propriedades da coluna.

   [Saiba mais sobre as propriedades da coluna](editabletables.html "Aplica-se a: TBM Studio 12.6 e posterior")
6. Verifique a tabela editável.

## Como os dados vão para a tabela editável

**Componente de relatório de tabela editável**

O componente de relatório Editable Table (Tabela Editável) permite que você insira, atualize e faça upload de dados diretamente, sem acesso ao site TBM Studio .

**Como inserir dados diretamente on-line**

1. Na visualização Project Explorer, selecione **Relatórios**.
2. Selecione um relatório.
3. Selecione **Check Out** > os recursos do componente de relatório estão disponíveis.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/enter-data-1.png)
4. Selecione **Editable Table (Tabela editável** ) na lista de recursos. Agora, você pode inserir seus dados diretamente na tabela > Selecione **Save (Salvar)**.

**Como fazer upload de dados para a tabela editável**

1. Na visualização Project Explorer, selecione **Relatórios**.
2. Selecione um relatório.
3. Se você rolar a tabela para baixo, terá opções de download e upload.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/enter-data-2.png)
4. Faça o download da tabela com a opção **Abrir no Excel** > Faça suas alterações > Faça o upload da tabela com a opção **Clicar ou arrastar arquivo**.
5. Selecione **Check Out**.

Observação: talvez você também queira ver o [componente Table Upload](../reports/table-report-upload-component.html "Aplica-se a: TBM Studio 12.9.3 e posterior") para se familiarizar com esse recurso, pois ele tem uma finalidade semelhante.

O fluxo de dados de uma tabela bruta para a tabela Transform não ocorrerá, a menos que a tabela bruta seja registrada.
