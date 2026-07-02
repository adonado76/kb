---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Guia para o Gerenciador de Compromissos Legados"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Guia para a gestão de compromissos"
source_path: "product/commitment-manager.html"
images:
  - "images/commit_manager_acct_sel.jpg"
  - "images/commit_manager_click_2_nav.jpg"
  - "images/commit_manager_cred_detail.jpg"
  - "images/commit_manager_def_rec.jpg"
  - "images/commit_manager_range.jpg"
  - "images/commit_manager_rec_applied.jpg"
  - "images/commit_manager_rec_opt.jpg"
  - "images/commit_manager_savings.jpg"
  - "images/commit_manager_serv_sel.jpg"
  - "images/commit_manager_subnav.jpg"
  - "images/commit_manager_usage_analysis.jpg"
  - "images/details.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Guia para o Gerenciador de Compromissos Legados

O Gerenciador de Compromissos do Apptio Cloudability ajuda você a ter uma visão global de como os instrumentos de gastos comprometidos (por exemplo, Instâncias Reservadas, Planos de Economia) podem ajudá-lo a otimizar seus gastos com nuvem. Este artigo descreve os recursos do Commitment Manager e sua capacidade de ajudar a aproveitar os instrumentos de gastos comprometidos como parte de uma estratégia geral de otimização financeira na nuvem.

Introdução

Antes de começar, certifique-se de que as permissões necessárias tenham sido ativadas.

Observação: Risco: Os usuários do Cloudability podem analisar diferentes níveis de compromisso com base no risco

Para verificar o status das credenciais necessárias, siga as etapas a seguir

1. Acesse Configurações > Credenciais de fornecedores.
2. Na visualização das contas principais da guia “ AWS ”, qualquer pagador mestre ou conta vinculada que seja titular ou que possa vir a ser o titular pretendido de compromissos (instâncias reservadas ou planos de economia) deve apresentar uma caixa verde com um indicador de status de marcação branca na se ção “Recursos avançados”.
3. ou, no caso de uma conta com indicadores de status diferentes da caixa verde com uma marca de seleção branca, selecione ![ícone de detalhes](../../../../03-media/cloudability-premium/images/details.jpg) para verificar as credenciais individuais.
4. Cloudability oferecerá a você uma visão geral de todas as suas reservas feitas em AWS, Azure ou GCP. Se, por qualquer motivo, todas as suas contas não estiverem devidamente credenciadas, talvez você não consiga visualizar todos os seus compromissos de reserva no gerenciador de compromissos.
5. Se as permissões na subseção “Reservas” apresentarem um X vermelho, elas precisarão ser atualizadas (por meio [da regeneração e aplicação dos modelos d CloudFormation](../admin/manage-aws-credentials.html#manage-aws-credentials__Regenerate_a_Cloud_Formation_template) ) para que todas as informações no Gerenciador de Compromissos sejam exibidas corretamente.

   ![Captura de tela com detalhes das credenciais do gerente de compromissos](../../../../03-media/cloudability-premium/images/commit_manager_cred_detail.jpg)

Nota:

Se não houver permissões para os Planos de Poupança, as economias futuras projetadas dos planos existentes não serão exibidas no gráfico principal do Gerenciador de Compromissos. Se não houver permissões para as Instâncias Reservadas, nem as economias históricas nem as projetadas para o futuro serão exibidas.

Acessando o Gerenciador de Compromissos

Para acessar o Gerenciador de Compromissos, vá até Otimizar > Gerenciador de Compromissos.

Opções de visualização e recomendação

A barra de subnavegação do Gerenciador de Compromissos exibe as opções para personalizar a visualização dos compromissos de sua responsabilidade, bem como a forma como as recomendações são geradas.

![captura de tela com detalhes da recomendação](../../../../03-media/cloudability-premium/images/commit_manager_subnav.jpg)

Análise de uso

A configuração de análise de uso determina qual parte do histórico de uso deve ser levada em consideração na geração de recomendações.

No menu suspenso, selecione 7, 30 ou 60 dias de uso anterior, e o gráfico se ajustará para exibir o uso projetado resultante e as recomendações associadas.

![captura de tela da análise de uso](../../../../03-media/cloudability-premium/images/commit_manager_usage_analysis.jpg)

Linha do tempo

A configuração da linha do tempo permite que os usuários determinem o intervalo de datas que desejam que apareça no gráfico, tanto no passado quanto no futuro.

Para ajustar a linha do tempo, selecione a seção Linha do tempo na subnavegação para exibir o seletor de intervalo de datas. Selecione o intervalo de tempo desejado e, em seguida, atualize. A área visível do gráfico se ajustará automaticamente para mostrar apenas o intervalo de datas selecionado.

![captura de tela da linha do tempo](../../../../03-media/cloudability-premium/images/commit_manager_range.jpg)

Nota:

Não é obrigatório selecionar um intervalo de datas que inclua a data de hoje, mas selecionar um intervalo de datas exclusivamente do passado resultará em um gráfico sem recomendações, mesmo que elas ainda estejam sendo geradas. Da mesma forma, ao selecionar um intervalo de datas que inclua apenas datas futuras, serão exibidas apenas as projeções de utilização futura dos compromissos existentes.

Conta

A configuração “Conta” permite que o usuário visualize e gere recomendações no nível da conta principal. Para maximizar a utilização e a economia, as recomendações são feitas, por padrão, no nível do pagador principal. No Gerenciador de Compromissos, só são permitidas seleções de contas pagadoras principais. Se você quiser restringir o uso e a visualização a contas vinculadas específicas, poderá fazer isso nas guias “Recomendado” do Planejador de Instâncias Reservadas e dos Planos de Economia. O uso, as recomendações e o gráfico são atualizados automaticamente para a conta selecionada.

Saiba mais sobre [os Planos de Poupança da AWS](analyze-data-for-your-aws-savings-plans.html)

![CM captura de tela dos detalhes da conta](../../../../03-media/cloudability-premium/images/commit_manager_acct_sel.jpg)

Nota:

A seleção “Conta” não deve ser usada como filtro de recomendações. Isso restringe a análise de uso considerada pelo serviço de recomendações apenas ao da conta selecionada ao gerar recomendações de compra e modificação, partindo do princípio de que o usuário deseja que as recomendações abranjam apenas o uso dessa conta. Por esse motivo, as recomendações geradas dessa forma não serão necessariamente um subconjunto daquelas feitas quando o pagador principal é selecionado. Provavelmente serão recomendações totalmente diferentes.

Serviços em nuvem

Por padrão, o Commitment Manager gera uma visão global do uso e da cobertura dos gastos comprometidos em todos os serviços do AWS credenciados na plataforma Apptio Cloudability; no entanto, a seleção de serviços em nuvem permite que os usuários visualizem serviços individuais ou grupos de serviços, conforme a preferência de cada usuário.

Na seção “Serviços em nuvem” da subnavegação, marcar e desmarcar os serviços irá adicioná-los e removê-los do gráfico, tanto para o uso e cobertura passados quanto para o uso e cobertura previstos para o futuro, além das recomendações.

![captura de tela com detalhes dos serviços em nuvem](../../../../03-media/cloudability-premium/images/commit_manager_serv_sel.jpg)

Nota:

É necessário selecionar pelo menos um serviço. Se a opção “Planos de Poupança” for selecionada nas “Opções de Recomendação” e alguns dos serviços selecionados não forem aplicáveis aos Planos de Poupança, o Gerenciador de Compromissos continuará a gerar recomendações de Instâncias Reservadas para esses serviços específicos.

Opções de recomendação

As opções de recomendação permitem que os usuários personalizem suas preferências de recomendação de compra, incluindo o instrumento de compromisso (ou seja, Planos de Poupança ou Instâncias Reservadas), o tipo (por exemplo, “ EC2 ” ou “Compute” para Planos de Poupança), o prazo e o modelo de pagamento. As recomendações relativas à troca e modificação de instâncias reservadas manterão os mesmos termos do compromisso original, conforme exigido pelo documento “ AWS ”.

![recomendação opções detalhes captura de tela](../../../../03-media/cloudability-premium/images/commit_manager_rec_opt.jpg)

Nota:

No caso do “ AWS ”, nem todos os serviços podem ser cobertos pelos Planos de Poupança. Se os Planos de Economia forem selecionados, o Gerenciador de Compromissos continuará a gerar recomendações de Instâncias Reservadas para serviços que não possam ser cobertos pelos Planos de Economia.

Como usar o gráfico principal do Gerenciador de Compromissos

Base de custo

A configuração padrão do Commitment Manager apresenta o uso sob demanda, a cobertura de compromissos e recomendações por custo, sem aplicar as recomendações disponíveis. Nesta visualização, a área sombreada em azul representa o uso sob demanda, sobreposta à área sombreada em verde, que representa o uso coberto por compromissos.

Uma linha vertical vermelha representa o dia mais recente de consumo real registrado; a área à esquerda da linha vermelha representa o consumo histórico e a cobertura de compromisso, enquanto a área à direita da linha vermelha projeta o consumo futuro com base na cobertura de compromisso já adquirida. Nesta visualização, as recomendações são representadas por um sombreado em linhas diagonais sobreposto ao uso futuro projetado sob demanda.

![captura de tela com detalhes da base de custo](../../../../03-media/cloudability-premium/images/commit_manager_def_rec.jpg)

Custo projetado com as recomendações aplicadas

Para visualizar os custos projetados com as recomendações aplicadas, mova o controle deslizante no canto superior esquerdo da área do gráfico para a posição “Aplicar recomendações” e o gráfico se ajustará para exibir os custos projetados após a implementação das recomendações.

![captura de tela de aplicação das recomendações](../../../../03-media/cloudability-premium/images/commit_manager_rec_applied.jpg)

Economias

Além de visualizar a cobertura histórica e projetada em termos de custo, os usuários podem optar por visualizar sua cobertura representada graficamente em termos de economia. Para visualizar por poupança, selecione “Poupança” no seletor localizado acima do centro do gráfico. Quando selecionada, a visualização “Economias” mostra apenas as economias históricas geradas pelos compromissos assumidos no passado e as economias futuras esperadas, tanto dos compromissos assumidos quanto dos recomendados.

![captura de tela com detalhes da poupança](../../../../03-media/cloudability-premium/images/commit_manager_savings.jpg)

Visualização dos detalhes das recomendações de ações em carteira e de compromissos

Para visualizar os detalhes dos compromissos existentes de sua propriedade, selecione/clique na área sombreada em verde para ser direcionado à carteira de reservas ou ao inventário do plano de poupança.

Para visualizar os detalhes das recomendações com base nas preferências definidas, clique na área sombreada em azul, na diagonal, à direita da linha vermelha no gráfico, para ser direcionado ao Planejador de Reservas ou às Recomendações do Plano de Poupança.

![Clique na captura de tela com a linha diagonal](../../../../03-media/cloudability-premium/images/commit_manager_click_2_nav.jpg)

Referência

Para obter mais informações sobre como gerenciar seus compromissos do AWS com o Apptio Cloudability, consulte:

- [Entendendo como os planos de poupança “ AWS ” afetam sua conta](understanding-how-aws-plans-affect-your-cloud-bill.html)
- [O que os planos de poupança “ AWS ” significam para você](https://www.apptio.com/blog/aws-savings-plans/ "(Abre em uma nova guia ou janela)")
- [Instâncias Reservadas](https://www.cloudability.com/product/features/reservations/ "(Abre em uma nova guia ou janela)")

**Tópico principal:** [Guia de gerenciamento de compromissos](../product/guide_to_commitment_management.html)
