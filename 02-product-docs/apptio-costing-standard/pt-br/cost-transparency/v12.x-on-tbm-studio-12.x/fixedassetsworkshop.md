---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Workshop sobre ativos fixos"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/fixedassetsworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Workshop sobre ativos fixos

## Preparação de seus dados de ativos fixos

Você pode começar a preparar seus ativos fixos analisando os pontos de verificação abaixo:

1. Se ainda não tiver feito isso, carregue seu Registro de Ativo Fixo.
2. Seguindo as Apptio práticas padrão, categorize cada conjunto de dados brutos na categoria de Ativos fixos.
3. Se apropriado, aplique um filtro de data aos seus dados de ativos fixos.

## Sobre o identificador do Ledger do ativo fixo

O identificador do objeto do Ledger do ativo imobilizado é preenchido quando você mapeia os dados para o conjunto de dados mestre do ativo imobilizado. Considere o nível de detalhe de que você precisa para modelagem e relatórios e defina o identificador. Se você tiver um Registro de Ativo Fixo, ele normalmente lista cada ativo fixo individual e, portanto, você pode usar o ID para cada ativo.

## Sobre as chaves do ativo fixo

As chaves do conjunto de dados mestre do ativo imobilizado são todas geradas pelo sistema e não devem ser alteradas.

| Chave | A chave de campo é baseada em | Lógica |
| --- | --- | --- |
| **Fonte de custos\_Chave do ativo fixo** | Metacampo-chave da fonte de custos | Anexar o texto FA\_Key com o metacampo Cost Source Key |
| **Chave Asset\_Resource** | Torre de recursos de TI  Subtracção de recursos de TI | Anexar o texto Asset\_Resource com a torre de recursos de TI e a subnave de recursos de TI |
| **Chave Asset\_Storage** | Não há campos predefinidos | Considere usar a ID do ativo fixo, supondo que cada um de seus dispositivos de armazenamento use a mesma ID para identificar exclusivamente cada ativo. |
| **Chave do servidor de ativos** | Não há campos predefinidos | Considere o uso do ID do ativo fixo, supondo que cada um de seus servidores use o mesmo ID para identificar exclusivamente cada ativo. |

Você só precisa preencher a Asset\_Storage Key e a Asset\_Server Key se estiver implementando os componentes Storage e Servers. Caso contrário, essas chaves podem ser deixadas em branco.

## Colunas computadas comuns necessárias para ativos fixos

Não há nenhuma coluna computada específica que você precise criar. Isso varia de acordo com seus dados. No entanto, aqui estão alguns pontos a serem considerados:

- Pesquisa da torre de recursos de TI de um centro de custo para o conjunto de dados de mapeamento da torre de TI no conjunto de dados de ativos fixos
- Pesquisa da subnível de recursos de TI de um centro de custo para o conjunto de dados de mapeamento da torre de TI no conjunto de dados de ativos fixos

Conforme apropriado, crie as colunas computadas necessárias para mapear seus dados para o conjunto de dados mestre do ativo fixo. Lembre-se de que você pode consultar o conjunto de dados mestre para determinar qual coluna pode ser necessária.

Certifique-se de que esteja criando as colunas na transformação dos dados do ativo fixo (e não no conjunto de dados brutos).

## Mapear dados para os dados mestre de ativos fixos

Mapeie seus dados de ativos fixos para o conjunto de dados mestre de ativos fixos. A maior parte do mapeamento deve ser autoexplicativa neste ponto.

Se você tiver preenchido o metacampo Chave do ativo fixo no conjunto de dados mestre de origem de custos, certifique-se de preencher o valor correspondente no metacampo Chave da origem de custos no conjunto de dados mestre do ativo fixo. Em 12.7, agora você pode aproveitar a função Mapa de Colunas em seu conjunto de dados brutos para mapear os dados mestre do ativo fixo (Map Columns)

Pontos que devem ser levados em conta:

- Mapeie seu conjunto de dados de ativos fixos para o conjunto de dados mestre de ativos fixos.

## Revise o objeto do Ledger de ativos fixos nos modelos

| Modelo | Ações |
| --- | --- |
| **Custo** | Certifique-se de que os valores estejam fluindo do objeto Fonte de custos para o objeto Ledger de ativos fixos.  Da fonte de custos para o Ledger de ativos fixos, aloque usando a referência baseada em dados ponderada pelo valor da depreciação (essa é a configuração padrão). As chaves que unem os dois conjuntos de dados incluem os metacampos da chave Fonte de custos/Ativo fixo. |
| **Orçamento** | Certifique-se de que os valores estejam fluindo do objeto Fonte de custos para o objeto Ledger de ativos fixos.  Se os valores não estiverem fluindo, talvez seja necessário marcar a caixa de seleção Automatically create many to many relationship (Criar automaticamente muitos relacionamentos).  Da fonte de custos para o Ledger de ativos fixos, aloque usando a referência baseada em dados ponderada pelo valor da depreciação (essa é a configuração padrão). As chaves que unem os dois conjuntos de dados incluem os metacampos da chave Fonte de custos/Ativo fixo. |
| **Previsão** | Certifique-se de que os valores estejam fluindo do objeto Fonte de custos para o objeto Ledger de ativos fixos.  Se os valores não estiverem fluindo, talvez seja necessário marcar a caixa de seleção Automatically create many to many relationship (Criar automaticamente muitos relacionamentos).  Da fonte de custos para o Ledger de ativos fixos, aloque usando a referência baseada em dados ponderada pelo valor da depreciação (essa é a configuração padrão). As chaves que unem os dois conjuntos de dados incluem os metacampos da chave Fonte de custos/Ativo fixo. |

As Torres de TI ainda não foram mapeadas, portanto, nenhum valor fluirá para o objeto Torres de Recursos de TI.

## Relatórios de ativos fixos

Acompanhe a depreciação de ativos fixos e use os novos relatórios de depreciação de ativos fixos para tomar decisões mais informadas sobre os custos atuais de infraestrutura e os custos de substituição previstos.

O que Apptio responde:

- Qual é a depreciação restante para o ativo fixo existente por períodos de tempo?
- Quais ativos são totalmente depreciados?

Ativos fixos

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
