---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Gerenciar a configuração de pontuação"
breadcrumb: []
source_path: "it-planning/planning/pfp/score-manage.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Gerenciar a configuração de pontuação

◆ Aplica-se a: Apptio Planning aplicativos com [Project Financial Planning](gs-project-financial.html "◆ Aplica-se a: Planejamento com planejamento financeiro de projetos."). As tarefas abaixo exigem que você licencie o site Project Financial Planning. Para ativar os recursos do site Project Financial Planning , consulte [Editar o perfil da empresa](../edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning.").

As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.

|  |  |
| --- | --- |
| ícone da câmera | Assista a este vídeo do site Apptio Education Services: [Configuração de dados de referência: Project Financial Planning Dimensions (Dimensões](https://community.apptio.com/videos/1995 "(Abre em uma nova guia ou janela)") ).  Ou veja todos os [recursos de vídeo e treinamento do site Apptio Planning](https://community.apptio.com/viewdocument/apptio-products-video-catalog?CommunityKey=1bdb1f0b-9524-43d4-b987-5d2b8595eebf "(Abre em uma nova guia ou janela)") . |

## Gerenciar a pontuação

A tabela de dados de Pontuação define o valor de Pontuação aplicado aos projetos quando a opção **Ativar pontuação automática do projeto** estiver ativada. Consulte [Editar o perfil da empresa](../edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning."). O valor de Pontuação é calculado usando as dimensões de dados de Pontuação que você especificar. Cada linha da tabela de dados Score constitui uma cláusula da fórmula. A fórmula usa os seguintes valores que você define por atributo:

- Fator de normalização - Um número usado para ajustar valores de atributos grandes a um intervalo utilizável.
- Ponderação - A contribuição relativa do atributo. Uma ponderação menor que 1 reduz a contribuição do atributo. 1 não tem efeito sobre a ponderação, e um valor maior que 1 amplia a contribuição relativa.

Por exemplo, os seguintes dados de pontuação:

| Atributo | Fator de normalização | Ponderação |
| --- | --- | --- |
| Risco | 2 | 2 |
| Prioridade | 1 | 3 |

Resultados dessa fórmula de pontuação:

> ```
> Score = 4/5 + 3/5
>           = 7/5 = 1.4
> ```

Para gerenciar o Score:

1. No painel de navegação esquerdo, selecione Configuration > Score
2. Atualize os valores da dimensão conforme necessário. Você pode especificar cada cláusula de sua fórmula Score por linha:
   - Atributo - Selecione a dimensão do projeto para a qual você deseja definir a cláusula Score. Os tipos de dimensão compatíveis incluem: Booleano (o valor verdadeiro é igual a 1 e o valor falso é 0), Número, Inteiro, Enum (o ordinal é igual ao valor em que o primeiro item é igual a 1, o segundo é igual a 2 e assim por diante).

     Observação: As dimensões Memo, String e Date não são permitidas para dimensões de atributo no Score.
   - Type (Tipo ) - Esse é o tipo de dados do atributo selecionado.
   - Fator de normalização - Insira um valor numérico.
   - Ponderação - Digite um valor numérico.
3. Clique em Publicar para tornar os dados disponíveis no planejamento e no gerenciamento de despesas.

Dica: Ao visualizar a Pontuação nas tabelas de dados do projeto (na visualização Resumo, por exemplo), você pode fazer o seguinte:

- Substituir um Score calculado por um valor numérico inserido manualmente.
- Substituir um valor inserido manualmente pela pontuação calculada. Para fazer isso, clique no ícone Reverter pontuação do projeto ao lado do valor da pontuação.
