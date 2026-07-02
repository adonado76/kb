---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Relatório por e-mail da Revisão de Variações Financeiras ( v104 )"
breadcrumb: []
source_path: "it-planning/reports-itfmf-ctv104/itfmf-ct_financialvariancereviewemail104.html"
images:
  - "resources/images/it_planning_images/itfmf-ct_images/itfmf-ct_financialvariancereview_email.jpg"
  - "resources/images/it_planning_images/itfmf-ct_images/itfmf-ct_financialvariancereview_emailbutton.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Relatório por e-mail da Revisão de Variações Financeiras ( v104 )

aplica-se a: Planning e Costing
Standard em TBM Studio 12.3 e posterior, com o modelo v104 e posterior

O relatório por e-mail Finance Variance Review o ajuda a entender a variação do orçamento e a concentrar seus esforços para garantir que você cumpra seu plano financeiro para o ano fiscal. A função de e-mail é limitada aos analistas financeiros com permissões de administrador, permitindo que eles enviem o relatório de variação com comentários aos proprietários de departamentos e outras partes interessadas.

## Exibir o relatório

1. Faça login em Apptio e navegue até Planning > Costing
   Standard.
2. Na página inicial, clique em IT Financials.

   O relatório Revisão financeira é aberto.
3. No relatório Financial Review, clique no ícone Send Financial Budget Variance Email (Enviar e-mail de variação do orçamento financeiro ).

   OBSERVAÇÃO : esse ícone de e-mail só é exibido para usuários com permissões de administrador.

   ![imagem](../../../../../03-media/apptio-planning/resources/images/it_planning_images/itfmf-ct_images/itfmf-ct_financialvariancereview_emailbutton.jpg)

   O relatório de e-mail Financial Variance Review é aberto.

1. Faça login em Apptio e navegue até Costing Standard.
2. Na página inicial, clique em IT Financials.

   O relatório Revisão financeira é aberto.
3. No relatório Financial Review, clique no ícone Send Financial Budget Variance Email (Enviar e-mail de variação do orçamento financeiro ).

   OBSERVAÇÃO : esse ícone de e-mail só é exibido para usuários com permissões de administrador.

   ![imagem](../../../../../03-media/apptio-planning/resources/images/it_planning_images/itfmf-ct_images/itfmf-ct_financialvariancereview_emailbutton.jpg)

   O relatório de e-mail Financial Variance Review é aberto.

DICA : se estiver tendo problemas para abrir esse relatório, faça o seguinte:

- Certifique-se de que você está no ambiente de produção, verificando se ele é exibido na barra de ferramentas. O recurso de e-mail não está disponível nos ambientes de desenvolvimento ou de teste.
- Verifique as configurações de seu navegador. Por exemplo, você pode ter problemas no Chrome se a opção **Bloquear cookies de 3rd Party** estiver ativada. Como alternativa, considere adicionar " [https://[\*.]apptio.com](https://apptio.com/ "(Abre em uma nova guia ou janela)") " aos sites permitidos no Chrome, ou uma configuração semelhante em outros navegadores.

## Elementos-chave

O relatório contém os seguintes elementos.

alt![imagem](../../../../../03-media/apptio-planning/resources/images/it_planning_images/itfmf-ct_images/itfmf-ct_financialvariancereview_email.jpg)

(1) Configurar o e-mail

- Tabela de outliers de filtro - (Opcional) Use as seguintes configurações para configurar a tabela de outliers :
  - % Variance - Define uma porcentagem mínima de variação. À medida que você ajustar esse valor, o relatório mostrará os valores discrepantes que excedem o limite percentual.

    Por exemplo, uma configuração de "0%" retorna todos os resultados, independentemente da porcentagem de variação. Uma configuração de "50%" retorna tudo com uma variação absoluta maior que 50%.
  - $ Variance - Defina um valor mínimo de variação em dólares. O relatório mostrará os valores discrepantes que excedem o limite de dólares.

    Por exemplo, uma configuração de "0" retorna todos os resultados, independentemente do valor em dólares. Uma configuração de "3000" retorna itens com uma variação absoluta acima de $3000.
  - Principais resultados - Defina o número de valores discrepantes que você deseja incluir no relatório.

    Por exemplo, uma configuração de "10" retornará os 10 principais desvios.

    Os resultados exibidos na tabela Outliers são o acúmulo dessas configurações. Por exemplo, as configurações de "50%", "5000" e "10", respectivamente, retornarão os 10 principais resultados que têm uma variação absoluta maior que US$ 5.000 e maior que 50%.
- Recipients (Destinatários ) - (Opcional) Clique no campo Add Recipients (Adicionar destinatários ) para inserir um endereço de e-mail da pessoa que você deseja que receba esse relatório e pressione Enter. Repita quantas vezes forem necessárias.

  Após terminar de inserir todos os comentários, clique em Send (Enviar ) para distribuir o e-mail para a lista de destinatários. Os botões Adicionar comentário e Salvar agora estão desativados e os filtros estão inativos. Para enviar outro e-mail, clique em Reset (Redefinir ), o que permite que você edite novamente os filtros, faça comentários e envie o relatório para um novo destinatário. Clique em Save (Salvar ) para salvar suas alterações sem enviar o e-mail.

  OBSERVAÇÃO : Normalmente, você enviará apenas um e-mail de revisão da variação financeira por mês. O filtro de outlier e os destinatários de e-mail que você definir persistirão nos períodos de tempo seguintes até que sejam alterados novamente e salvos.

(2) Campos de comentários (opcional)

Você pode adicionar comentários em qualquer lugar onde houver um botão Adicionar comentário. A seção superior serve para inserir uma mensagem geral sobre a análise financeira do mês. Normalmente, você deseja incluir uma declaração de alto nível sobre a situação do orçamento e, possivelmente, explicações para variações significativas. O campo é limitado a 400 caracteres.

Para editar um comentário salvo, clique em Edit Comment (Editar comentário ). Para excluir um comentário, clique em **Editar comentário**, remova o texto da caixa de comentário e clique em Salvar.

(3) Despesas operacionais no acumulado do ano

Essa seção exibe o orçamento e a variação no nível mais alto.

(4) Variação orçamentária acumulada

Esta seção exibe a variação orçamentária por período (coluna) e a variação orçamentária acumulada no acumulado do ano (linha de tendência). O ideal é que a variação cumulativa se aproxime ou tenha tendência a zero para cumprir o plano financeiro.

(5) Responsabilidade

Essa seção exibe a variação do seu orçamento por proprietário, normalmente o nível CIO-1. Um comentário pode ser adicionado para explicar qualquer variação nesse nível.

(6) Valores atípicos

Essa seção exibe o desvio do orçamento por centro de custo e subgrupo de contas usando os parâmetros definidos no painel Configurar e-mail (elemento 1). Opcionalmente, você pode inserir explicações para cada uma delas.

(7) Detalhes

Ao clicar no link Questions (Perguntas ) da mensagem de e-mail recebida, você acessará o relatório de revisão de variação orçamentária em Apptio.

## Perguntas respondidas

Você pode usar esse relatório para responder às seguintes perguntas:

- Quais centros de custos estão gerando variação de gastos em relação ao planejado?
- Quais contas dentro da responsabilidade do centro de custo estão gerando a maior variação (acima ou abaixo)?
