---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Aquisição e transformação de dados"
breadcrumb: []
source_path: "studio/data_studio/about-data-transforms.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Aquisição e transformação de dados

**Aplica-se a** : TBM Studio 12.0 e posterior

## Sobre o pipeline de transformação de tabelas

Para modificar dados em uma tabela, você pode adicionar ou modificar etapas no pipeline de transformação. No pipeline, você pode:

- Veja todas as etapas de transformação na ordem em que são executadas.
- Adicione, edite e exclua etapas de transformação para modificar o resultado.
- Arraste para reordenar etapas individuais.
- Procure vídeos na [comunidade Apptio](https://community.apptio.com/communities/community-home/librarydocuments/viewdocument?DocumentKey=c7ec37da-b3ef-41af-9671-3039095fa2a9 "(Abre em uma nova guia ou janela)") (o link requer credenciais TBM Connect).

Observação: As tabelas editáveis não são transformações de tabela e não são abordadas neste artigo. Para obter mais informações, consulte [Tabelas editáveis: Acomodando a entrada do usuário](editabletables.htm "(Abre em uma nova guia ou janela)").

## Etapas do pipeline de transformação de tabelas

Ao criar uma nova tabela, as seguintes etapas do pipeline serão preenchidas automaticamente, independentemente da origem dos dados:

- **Fonte** : Determina o tipo de dados em que se baseia uma tabela.
- **Tabela** : Visualiza a tabela de dados criada pela transformação.

Dependendo da opção Source selecionada, outras etapas do pipeline serão adicionadas automaticamente:

Opções de origem do upload de arquivos:

- **Upload** : Permite que o usuário selecione o arquivo a ser carregado.
- **Importar** : Exibe as configurações usadas para definir como o sistema deve importar um arquivo.

Opção de fonte de tabela existente:

- **Tabela existente** : Define a transformação da tabela na qual a tabela deve se basear.

Você pode adicionar as seguintes etapas do pipeline a qualquer tabela:

- **Anexar** : Adiciona as linhas de uma tabela às linhas de outra tabela. Consulte [Anexar dados](append-data.htm "(Abre em uma nova guia ou janela)").
- **Atribuir linhas** : Adicionadas automaticamente ao usar Map Columns para mapear conjuntos de dados mestres com recursos de aprendizado de máquina e podem ser adicionadas novamente a tabelas válidas por meio do processo Add Step. Usa aprendizado de máquina e regras criadas pelo usuário para mapear os conceitos do site ATUM. Consulte [Atribuir pools de custos com aprendizado de máquina](assigncostpools.htm "(Abre em uma nova guia ou janela)").
- **Partição de data** Use datas do arquivo, em linhas ou colunas, para distribuir automaticamente os dados entre períodos de tempo. Consulte [Dados de partição por data](partition-data-by-date.htm "(Abre em uma nova guia ou janela)").
- **Filtro** : Remova linhas específicas com base nos valores de uma ou mais colunas.
- **Achatar hierarquia** : Oferece a maior flexibilidade ao usar fatiadores. Essa etapa do pipeline adiciona uma coluna para cada nível da hierarquia em uma tabela. Em seguida, você pode criar segmentações para cada uma das colunas. Consulte [Achatar uma hierarquia de dados](flatten-hierarchy.htm "(Abre em uma nova guia ou janela)").
- **Fórmulas** : Adicione novas colunas de fórmula com base nos dados, altere os tipos de coluna (por exemplo, altere um número para um rótulo) ou substitua os valores existentes. Consulte [Adicionar e editar colunas](add-edit-columns.htm "(Abre em uma nova guia ou janela)") e [Fórmulas e funções](../formulas-and-functions/introduction-to-formulas-and-functions.htm "(Abre em uma nova guia ou janela)").
- **Group (Grupo** ): Agrupa a tabela pelos valores em uma ou mais colunas de texto.
- **Hide and Rename (Ocultar e renomear** ): oculte ou renomeie colunas nos dados.
- **Unir** : Combinar dados de duas ou mais tabelas nas mesmas linhas com base em valores comuns em uma ou mais colunas. Consulte [Dados de união](join-data.htm "(Abre em uma nova guia ou janela)").
- **Map Columns (Mapear colunas** ): Conforma a saída da tabela para corresponder ao esquema ATUM e adiciona as linhas ao conjunto de dados mestre. Consulte [Colunas do mapa](mapcolumns.htm "(Abre em uma nova guia ou janela)").
- **Modelo** : Permite que a tabela seja usada como um objeto em um modelo no qual os usuários podem definir drivers e alocar valores. Consulte [Sobre os modelos](../model%20studio/about-models.htm "(Abre em uma nova guia ou janela)").
- **Pivotar** : Converte linhas em colunas. Consulte [Dados dinâmicos](pivot-tables.htm "(Abre em uma nova guia ou janela)").
- **Remover duplicatas** : Filtra as linhas de uma tabela que têm o mesmo valor em uma coluna ou conjunto de colunas.
- **Segurança em nível de linha** : Permite que os usuários filtrem tabelas e relatórios com base no usuário atual. Consulte [Aplicar segurança em nível de linha](apply-row-level-security.html "(Abre em uma nova guia ou janela)").
- **Desagrupar** : Converter colunas em linhas.
