---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Schemas"
breadcrumb:
  - "Planning"
  - "Configuração e administração"
source_path: "it-planning/planning/manage_schema.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Schemas

Os esquemas definem a estrutura dos dados no Apptio Planning. Eles especificam as tabelas, os campos e os relacionamentos que determinam como as informações são armazenadas, vinculadas e exibidas nas guias Despesas, como Trabalho, Contratos, Ativos e Finanças.

Observação: as funções Admin ou Proprietário do processo orçamentário são necessárias para gerenciar esquemas.

Na página **Schemas**, os administradores podem gerenciar:

- **Esquemas de itens** - Defina estruturas de dados para itens financeiros, reais, trabalhistas, contratos, ativos e atividades trabalhistas.
- **Dimensões padrão** - Dimensões prontas para uso, como **departamento**, **conta** ou **centro de custo**, usadas em todos os esquemas de itens de linha
- **Dimensões personalizadas** - Dimensões criadas pelo usuário (até 40 na versão 5.12 ) para dados específicos da organização.

Os esquemas garantem a consistência entre as dimensões e os itens de linha, permitindo que os usuários analisem os dados de forma integrada entre os planos.

## Gerenciamento de esquemas de itens

Apptio O planejamento suporta vários tipos de esquemas, cada um correspondendo a uma área de planejamento chave:

|  |  |
| --- | --- |
| **Tipo de item** | **Descrição** |
| Finanças | Captura despesas operacionais e de capital ( OpEx/CapEx ). Os dados desse esquema são exibidos nas guias **Resumo** e **Outros**. |
| Ativos | Rastreia as compras de ativos, a depreciação e o impacto financeiro ao longo do tempo. Os dados desse esquema são exibidos na guia **Assets (Ativos** ). |
| Contratos | Usado para gerenciar contratos de fornecedores e aplicar cronogramas de amortização. Os dados desse esquema são exibidos na guia **Contratos**. |
| Mão de Obra | Define o número de funcionários, a remuneração e as regras de alocação para o planejamento de custos de mão de obra. Os dados desse esquema são exibidos na guia **Trabalho**. |
| Atividade trabalhista | Usado para rastrear horas de trabalho do projeto e cobranças cruzadas. Os dados desse esquema são exibidos na guia **Atividade de trabalho**. |
| Dados reais | Armazena dados transacionais reais para previsão e análise de variação. Os dados desse esquema são exibidos no **Gerenciamento de despesas**. |

## Dimensões padrão e personalizadas

**As dimensões** são dados de referência compartilhados usados para categorizar e agrupar informações entre esquemas.

Apptio O planejamento oferece suporte a dois tipos:

- **Dimensões padrão** - Fornecidas prontas para uso, como **departamento**, **conta** e **centro de custos**. Eles são vinculados automaticamente a esquemas relacionados.
- **Dimensões personalizadas** - Dimensões criadas pelo usuário que permitem estender o modelo de dados para atender às suas necessidades comerciais. Você pode adicionar **até 40 dimensões personalizadas para o release 5.12**

Cada dimensão pode incluir **atributos** (colunas) que acrescentam contexto e detalhes, como "Região", "Gerente" ou "Unidade de negócios" Esses atributos estão disponíveis para filtragem, agrupamento e geração de relatórios.

Observação: quando uma dimensão é compartilhada entre vários tipos de esquema (por exemplo, "Número do pedido" aparece em Contratos e Finanças), os dados desses esquemas são automaticamente transferidos da **guia Contratos** para a **guia Resumo**.

Criar uma dimensão personalizada

1. Navegue até **Planning** > **Configuration** > **Schema.**
2. Selecione a guia **Custom Dimensions (Dimensões personalizadas** ).
3. Clique no botão **+** (Adicionar).
4. Preencha os seguintes campos:
   - **Nome** - Digite um nome para a nova dimensão.
   - **Descrição** - Forneça uma breve descrição da finalidade da dimensão.
   - **Adicionar a** - Selecione os esquemas de itens em que essa dimensão deve estar disponível.
5. Clique em **Add (Adicionar** ) para criar a dimensão personalizada.

Editar ou excluir uma dimensão personalizada

Para **editar** :

1. Navegue até **Planning > Configuration > Schema**.
2. Selecione a guia **Custom Dimensions (Dimensões personalizadas** ).
3. Clique no nome da dimensão ou clique com o botão direito do mouse → **Edit**.
4. Atualizar os atributos disponíveis.

Para **excluir** :

1. Clique com o botão direito do mouse no nome da dimensão.
2. Selecione **Excluir**.

Importante: A exclusão de um atributo remove permanentemente todos os dados armazenados nesse campo em todos os planos.

## Atributos personalizados

Os atributos personalizados permitem que você estenda as dimensões incorporadas ou personalizadas com campos adicionais para capturar metadados relevantes para sua organização.

Por exemplo, você pode acrescentar:

- **"Programa"** ou **"Código WBS"** para uma dimensão **de projeto**.
- **"Região"** para uma dimensão **de Departamento**.
- **"PO Number"** em um esquema de **contrato**.

Você pode adicionar **até 60 atributos personalizados por dimensão**, e eles aparecerão como colunas adicionais nas tabelas de dados de referência relacionadas.

Tipos de atributos suportados

|  |  |
| --- | --- |
| **Tipo** | **Descrição** |
| Sequência | Armazena valores de texto, como nomes, descrições ou códigos. Suporta um máximo de 255 caracteres. |
| Data | Captura uma data de calendário específica (por exemplo, data de início do contrato ou data de contratação). |
| Número Inteiro | Armazena números inteiros sem decimais (por exemplo, número de funcionários, número de licenças). |
| Numérico | Armazena valores numéricos, inclusive decimais, para dados financeiros ou quantitativos (por exemplo, custo, taxa). |
| Percentual | Representa valores numéricos como porcentagens (por exemplo, taxa de alocação, utilização). |
| Memorando | Usado para texto longo ou notas, como comentários ou descrições detalhadas. Suporta um máximo de 1024 caracteres. |
| Lista | Fornece um conjunto predefinido de valores selecionáveis (por exemplo, região, tipo de departamento). |
| Usuário | Faz referência a um usuário no Apptio Planning, permitindo a atribuição de propriedade ou responsabilidade. |
| Booleano | Armazena valores verdadeiro/falso, usados para alternâncias ou indicadores binários (por exemplo, ativo/inativo, sim/não). |
| Link | Armazena URLs clicáveis que abrem em uma nova guia do navegador. Útil para fazer referência a recursos externos, como tíquetes do Jira, documentação ou painéis. |

Adicionar um atributo personalizado

1. Navegue até **Planning** > **Configuration** > **Schema**.
2. Selecione a guia apropriada - **Itens de linha**, **Dimensões padrão** ou **Dimensões personalizadas** - dependendo de onde deseja adicionar o atributo.
3. Clique no **tipo de item de linha** ou **dimensão** específica para abrir seus detalhes.
4. Na página **Atributos disponíveis**, clique em **Adicionar**.
5. Preencha os seguintes campos:
   - **Nome do campo** - Digite um nome para o novo atributo.
   - **Tipo de dados** - Escolha entre os tipos de atributos compatíveis.
   - **Valor padrão** - Opcionalmente, defina um valor padrão para o campo.
   - **Obrigatório para entrada de dados** *(somente esquemas de itens de linha)* - Exija que os usuários preencham esse campo ao inserir dados.
   - **Dados confidenciais** *(somente esquema de item de linha de mão de obra)* - Restringe a visibilidade a usuários autorizados (controlados por **[permissões de objeto de custo](manage-cost-object.html)** ).
   - **Acesso restrito** *(somente esquemas de itens de linha)* - Limite os direitos de edição a administradores ou usuários com a permissão ***EditRestrictedDimensions*** permissão.
6. Clique em **Add** para salvar o atributo personalizado.

Editar ou excluir um atributo personalizado

Para **editar** :

1. Navegue até **Planning > Configuration > Schema**.
2. Selecione a dimensão ou o tipo de item de linha.
3. Abra a caixa de diálogo **Atributos disponíveis**.
4. Clique no nome do atributo ou clique com o botão direito do mouse → **Edit**.
5. Atualize o nome ou o valor padrão e clique em **Save (Salvar** ).

Para **excluir** :

1. Clique com o botão direito do mouse no nome do atributo.
2. Selecione **Excluir**.

   Importante: A exclusão de um atributo remove permanentemente todos os dados armazenados nesse campo em todos os planos.
