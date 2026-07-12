---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Criar tabelas em branco editáveis"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Trabalhar com dados"
  - "Entrada manual de dados"
source_path: "studio/new-uc/howtoguides/work-with-data/create-blank-et.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Criar tabelas em branco editáveis

## Objetivo

Crie uma tabela totalmente manual, na qual todas as linhas, colunas e dados sejam inseridos pelos usuários.

## Quando usar

- Pequenos dados de referência que não existem nos sistemas de origem (por exemplo, categorias de fornecedores, tabelas de mapeamento personalizadas)
- Tabelas de consulta com menos de 500 linhas
- Dados que mudam com pouca frequência e exigem curadoria manual
- Esquemas de classificação mantidos por usuários da empresa
- Mapeamentos pontuais ou dados de enriquecimento

## Quando NÃO usar

- Grandes conjuntos de dados (>500 linhas) que devem ser provenientes de sistemas de origem
- Dados disponíveis por meio de feeds automatizados
- Dados que precisam ser enriquecidos a partir de tabelas geradas pelo sistema existente (use, em vez disso, tabelas editáveis enriquecidas)

## Pré-requisitos

- Data Studio acesso com permissões para criar tabelas
- Compreensão das colunas e dos tipos de dados necessários
- Defina quem será responsável pela manutenção dos dados

**Tempo estimado:** 10 a 15 minutos

## Passos

1. **Crie a tabela editável**
   - Acesse **Data Studio**
   - Na guia **Página inicial**, no grupo **Documento**, selecione **Novo > Tabela editável**
   - Na caixa de diálogo “**Nova tabela inserida manualmente** ”, selecione **“Tabela em branco”**
   - Digite um nome descritivo para a tabela editável (por exemplo, “Categorias de fornecedores”, “Atributos do centro de custo”)
   - Clique **em OK**
2. **Configurar o esquema da tabela**
   - A tabela editável é aberta com uma coluna de chave primária padrão (.PK)
   - Vá para **Etapas > Configurar colunas** no pipeline
   - O sistema exibe sua área de trabalho de configuração de colunas
3. **Adicione colunas à sua tabela**
   - Clique em **“Adicionar uma nova coluna”**
   - Para cada coluna necessária, configure:
     - **Nome da coluna:** Insira um nome descritivo (por exemplo, “Nome do fornecedor”, “Categoria”)
     - **Descrição:** Fornecer contexto para os usuários que irão inserir dados
     - **Tipo de dados:** Selecione entre Rótulo (texto), Numérico, Data ou Booleano
     - **Nome de exibição:** como a coluna aparece nos relatórios (opcional)
4. **Definir propriedades da coluna** (opcional, mas recomendado)
   - **Valor padrão:** Preencher automaticamente novas linhas com um valor inicial
   - **Valor obrigatório:** marque esta caixa para impedir o salvamento de linhas sem um valor
   - **Permitir apenas valores únicos:** garantir que cada linha tenha um valor distinto
5. **Configurar menus suspensos** (se necessário para garantir a qualidade dos dados)
   - Consulte a seção 3.1.3.3 "Configurar menus suspensos e validação" para obter orientações detalhadas
   - Os menus suspensos impedem a inserção de texto livre e garantem a consistência dos valores
6. **Verifique seu esquema**
   - Verifique se os nomes, tipos e requisitos das colunas correspondem às suas necessidades de dados
   - Certifique-se de que a coluna da chave primária (.PK) permaneça configurada
7. **Salvar e fazer o check-in**
   - Clique em **“Salvar”** na guia **“Página inicial”**
   - Clique em **“Check-in”** para disponibilizar a mesa
   - Adicione um comentário ao fazer o check-in descrevendo a finalidade da tabela

## Resultados esperados

Agora você tem uma tabela editável vazia com um esquema definido. A tabela aparece na seção **Tabelas** do **Explorador de** Projetos, na pasta em que você a criou. Os usuários podem adicionar dados por meio de relatórios com componentes de tabela editáveis ou editando diretamente no Data Studio (para administradores). A tabela está pronta para ser incorporada às tabelas de transformação e ao seu modelo de custos.

## Armadilhas comuns

|  |  |
| --- | --- |
| **Problema** | **Solução** |
| **Foram definidas demasiadas colunas inicialmente** | Comece apenas com as colunas essenciais. Você pode adicionar mais colunas posteriormente, conforme for necessário. Colunas não utilizadas confundem os usuários responsáveis pela entrada de dados. |
| **Finalidade das colunas não está clara** | Sempre adicione descrições às colunas. Os usuários que inserem dados precisam saber o que cada campo representa. |
| **Sem validação de dados** | Sem validação ou listas suspensas, os usuários podem inserir dados inconsistentes (por exemplo, “Serviços de TI”, “Serviços de TI”, “Tecnologia da Informação”). Adicione menus suspensos para qualquer coluna utilizada nas alocações ou nas dimensões de relatórios. |
| **Tipo de dados incorreto selecionado** | Se você selecionar "Numérico", mas os usuários precisarem inserir valores como "N/A" ou uma combinação de texto e números, a coluna rejeitará as entradas válidas. Use o tipo "Etiqueta" quando os dados puderem incluir valores não numéricos. |

## O que vem a seguir

Depois de criar sua tabela em branco editável:

- [Criar uma tabela de transformação a partir da tabela editável](data-security.html)
- [Configurar a publicação de tabelas editáveis](setup-et-publish.html)
- [Adicionar tabelas aos relatórios](../create-reports/add-tables-report.html)
- [Configurar segurança no nível da linha](htg-arls.html)

**Tópico principal:** [Entrada manual de dados](../../../../studio/new-uc/howtoguides/work-with-data/manual-data-entry.html)
