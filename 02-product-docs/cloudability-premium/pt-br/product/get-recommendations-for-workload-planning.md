---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Obter recomendações para o planejamento da carga de trabalho"
breadcrumb:
  - "Cloudability Premium"
  - "Planejar"
  - "Planejamento da carga de trabalho"
source_path: "product/get-recommendations-for-workload-planning.html"
images:
  - "images/3-dots.jpg"
  - "images/drop-down.jpg"
  - "images/edit-icon.jpg"
  - "images/modify-delete.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Obter recomendações para o planejamento da carga de trabalho

O Workload Planning ajuda a otimizar a arquitetura da carga de trabalho e a melhorar a precisão do planejamento financeiro entre os fornecedores de nuvem.

Será possível:

1. Modele suas cargas de trabalho.
2. Obtenha uma recomendação de recursos e uma estimativa de custo para um conjunto de tipos de serviços (máquina virtual, banco de dados gerenciado, armazenamento de objetos e blocos, balanceador de carga) com base em seus requisitos.
3. Obtenha estimativas para um fornecedor de nuvem ou compare recursos entre fornecedores de nuvem para escolher o destino ideal para a nuvem.

## Casos de uso para o planejamento de cargas de trabalho

Aqui estão os principais casos de uso para clientes que utilizam o recurso de Planejamento de Cargas de Trabalho do Cloudability :

1. **Estimativa e comparação de custos antes da implantação**
   - Comparação entre provedores de nuvem: os clientes podem simular o custo de uma carga de trabalho planejada em diferentes provedores de nuvem ( AWS, Azure, GCP, OCI etc.) para determinar a opção mais econômica para suas necessidades específicas. Isso é fundamental para estratégias multicloud.
   - Avaliação de regiões e tipos de recursos: Antes da implantação, os usuários podem comparar as implicações de custo decorrentes da implantação de uma carga de trabalho em diversas regiões e do uso de diferentes tipos de recursos (por exemplo, diferentes famílias de VM, opções de armazenamento) para encontrar a configuração ideal.
   - Planejamento de cenários para novos projetos: Engenheiros e gerentes de produto podem estimar rapidamente os custos da infraestrutura em nuvem para novos aplicativos, serviços ou recursos, permitindo que as equipes financeiras compreendam o impacto no orçamento e tomem decisões de investimento baseadas em dados.
2. **Otimização das cargas de trabalho existentes (redimensionamento e migração para novas plataformas)**
   - Análise de ajuste de recursos: Ao inserir os requisitos de carga de trabalho existentes, os clientes podem ver recomendações de instâncias ou serviços mais econômicos que atendam às necessidades de desempenho sem provisionamento excessivo. Isso ajuda a eliminar o desperdício decorrente de recursos ociosos ou subutilizados.
   - Análise de opções de contratação (Instâncias Reservadas, Planos de Economia, Spot): O Planejamento de Cargas de Trabalho ajuda os clientes a compreender a economia de custos associada a diferentes modelos de contratação (Sob Demanda, Instâncias Reservadas, Planos de Economia, Instâncias Spot) e os orienta na escolha da opção mais adequada para cargas de trabalho previsíveis ou interrompíveis.
   - Planejamento de migração: Ao planejar a migração de um aplicativo do ambiente local para a nuvem, ou entre provedores de nuvem, o Planejamento de Carga de Trabalho pode simular os custos no novo ambiente, garantindo uma estratégia de migração financeiramente viável.
3. **Orçamento e Previsão Colaborativos**
   - Compreensão comum dos custos da nuvem: A capacidade de salvar, compartilhar e comentar planos de carga de trabalho promove a colaboração entre as equipes de engenharia, FinOps, e finanças, criando uma compreensão comum dos gastos futuros com a nuvem.
   - Previsões precisas: Ao utilizar o Planejamento de Carga de Trabalho para estimar implantações futuras, os clientes podem elaborar previsões de nuvem mais precisas e fundamentadas, reduzindo a variação entre os gastos planejados e os gastos reais.
   - Responsabilidade e senso de propriedade: Quando as equipes participam do processo de planejamento e conseguem perceber as implicações financeiras de suas decisões arquitetônicas, isso promove um maior senso de responsabilidade pelos gastos com a nuvem.
4. **Aquisição estratégica de recursos em nuvem**
   - Decisões de compra bem fundamentadas: o Planejamento de Carga de Trabalho fornece os dados necessários para tomar decisões inteligentes sobre compromissos de compra, como Instâncias Reservadas ou Planos de Economia, garantindo que eles estejam alinhados às necessidades reais de carga de trabalho e maximizem os descontos.
   - Identificação de oportunidades de redução de custos: Ao modelar diversos cenários, os clientes podem identificar proativamente oportunidades para consolidar recursos, aproveitar diferentes modelos de precificação ou realizar mudanças na arquitetura a fim de reduzir os gastos gerais com a nuvem.
5. **Conformidade e Governança**
   - Padronização do provisionamento de recursos: o planejamento de cargas de trabalho pode ajudar a estabelecer as melhores práticas para o provisionamento de recursos, oferecendo um caminho claro e com custos otimizados para novas implantações, contribuindo para uma melhor governança da nuvem.
   - Acompanhamento e relatórios de custos planejados versus custos reais: Embora não seja um recurso direto de geração de relatórios, os planos criados no Planejamento de Carga de Trabalho servem como uma linha de base em relação à qual os gastos reais com nuvem podem ser medidos, auxiliando no monitoramento do desempenho e na identificação de desvios.

Em essência, o Planejamento de Carga de Trabalho do Cloudability permite que os clientes passem de uma gestão reativa de custos para um planejamento financeiro proativo, possibilitando-lhes tomar decisões estratégicas que otimizem os gastos com a nuvem desde o início.

## Antes de começar

Atualize suas preferências de planejamento de carga de trabalho

Os administradores definem as opções que aparecem no Workload Planning. Visite [Preferências de planejamento de carga de trabalho](workload-planning-preferences.html) para obter mais informações.

Entenda os preços personalizados:

- Para AWS, Azure e OCI, todos os preços no Workload Planning incluem preços personalizados por padrão. Nenhuma configuração é necessária para esses fornecedores.
- Para o “ GCP ”, é necessário habilitar a exportação de dados de preços personalizados da sua conta de faturamento do “ GCP ”. Acesse [a página “Configurando o suporte a preços personalizados para o GCP ”](gcp-rightsizing-custom-pricing-support.html) para obter mais informações.

Defina sua moeda padrão (clientes não americanos):

- Configure uma moeda padrão em Cloudability para que os preços sejam exibidos com a moeda correta.
- Carregue uma tabela de taxas de câmbio em Cloudability para exibir a taxa de conversão correta.

Revisar as cargas de trabalho existentes

Você pode visualizar todas as suas cargas de trabalho na guia List (Lista ). Selecione uma carga de trabalho para ver os detalhes.

- Selecione ![suspenso](../../../../03-media/cloudability-premium/images/drop-down.jpg) para modificar o status de qualquer carga de trabalho.
- Selecione ![3 pontos](../../../../03-media/cloudability-premium/images/3-dots.jpg) para ver suas outras opções. Você pode excluir, duplicar ou exportar uma carga de trabalho ou salvá-la como um modelo.

## Criar uma carga de trabalho

Para criar uma carga de trabalho:

1. Faça login em Cloudability.
2. No menu principal, selecione Plan > Workload Planning.
3. Selecione o botão New Workload ou a guia Builder.
4. Registre as informações comuns da sua carga de trabalho.
5. Adicione seus recursos.

   Observação: é possível adicionar apenas 30 recursos por plano.
6. Visualize suas recomendações.
7. Revise o resumo de sua recomendação.

## Registre as informações comuns da sua carga de trabalho

1. Digite um nome e uma descrição para sua carga de trabalho.
2. Analise os provedores de serviços permitidos. (Se não encontrar o provedor de serviços que está procurando, peça ao administrador para adicioná-lo em Preferências de planejamento de carga de trabalho)
3. Para qualquer provedor de serviços para o qual você queira recomendações, marque a caixa de seleção Incluir na estimativa.
4. No menu suspenso Preferred Region (Região preferida ), selecione a região em que você deseja implantar sua carga de trabalho. Você pode selecionar até cinco regiões para cada fornecedor de nuvem. Você também pode alterar a região posteriormente ao adicionar recursos.
5. Selecione seu tipo de leasing preferido. Sua seleção ajuda a escolher o tipo de arrendamento e o tipo de preço corretos quando você chega à etapa de recomendação.

   Observação: o preço On-Demand corresponde ao preço personalizado On-Demand, incluindo o preço personalizado.
6. Se for o caso, selecione o tipo de compromisso, o prazo do compromisso e a opção de pagamento.

   Observação: Esses campos se aplicam apenas ao preço comprometido para os serviços de computação AWS, Azure e GCP. Eles não se candidatam à OCI. Se você selecionar posteriormente On-Demand ou Spot Price, esses campos não terão mais efeito.
7. Selecione o botão Next (Avançar ) para adicionar recursos.

Observação: o preço comprometido corresponde ao preço dos planos de economia ou das instâncias reservadas para os recursos do AWS Compute. Para Azure, corresponde ao preço das instâncias reservadas ou ao plano de economia. Para o ` GCP `, isso corresponde ao preço com desconto por uso comprometido com base em recursos. O preço comprometido não é usado para OCI.

Por padrão, o status da carga de trabalho é definido como "Em andamento" (você pode alterar esse status posteriormente na guia Lista, depois de criar a carga de trabalho).

## Adicione seus recursos

Forneça seus requisitos de recursos para a carga de trabalho. O Planejamento de carga de trabalho usa os dados inseridos para procurar recursos que tenham necessidades iguais ou superiores à quantidade solicitada.

Você pode inserir os detalhes do recurso manualmente ou importá-los.

Para importar os detalhes de seus recursos:

1. Para adicionar vários recursos de uma só vez, selecione o botão Importar.

   Observação: A importação de recursos substitui os recursos existentes.
2. No menu suspenso, escolha se deseja importar um arquivo JSON ou um arquivo Excel.
3. A gaveta de importação é aberta. Use os links na gaveta para baixar um modelo com exemplos de requisitos de recursos ou uma lista dos recursos existentes.

   Observação: nos arquivos JSON, os nomes de todos os serviços devem estar presentes no arquivo. Se não houver necessidade de recurso ou requisito para um determinado tipo de serviço, insira-o entre colchetes vazios. Por exemplo, para balanceador de carga, o formato é "loadbalancer": [].
4. Selecione o botão Next (Avançar ).
5. Arraste seu arquivo para a área de upload ou use o link procurar um arquivo para pesquisá-lo.
6. Selecione o botão Next (Avançar ).
7. O Workload Planning exibe um resumo do seu arquivo. Selecione o botão Concluído quando estiver pronto para continuar.

Você também pode adicionar recursos manualmente. Para fazer isso:

1. Na etapa do fluxo de trabalho Adicionar recursos, selecione o botão Adicionar recurso.
2. Selecione o tipo de serviço e forneça um nome de recurso.

   Observação: o tipo de serviço "Managed Database" (Banco de dados gerenciado) não está disponível para a OCI.
3. Se você selecionou Service Type Virtual Machine, Managed Database, Object Storage ou Armazenamento adicional :
   - Insira requisitos genéricos se não estiver analisando um tipo de recurso específico, OU
   - Ative o botão de alternância Pesquisar tipo de recurso para selecionar o recurso desejado. Se o Workload Planning encontrar recursos mais baratos com requisitos semelhantes, ele os recomendará primeiro. Para comparação entre várias nuvens, o Workload Planning usa os requisitos associados ao recurso selecionado para gerar recomendações para outros fornecedores de nuvem. Essa opção também permite que você selecione até cinco regiões diferentes para o seu recurso.
4. Insira todos os seus requisitos personalizados.
5. Depois de inserir todos os requisitos, selecione o botão Add (Adicionar ). A tela de requisitos de recursos é exibida. Para modificá-los ou excluí-los, selecione ![ícone suspenso](../../../../03-media/cloudability-premium/images/drop-down.jpg)e, em seguida, escolha ![Excluir símbolo](../../../../03-media/cloudability-premium/images/modify-delete.jpg).
6. Selecione o botão Next (Avançar ).

## Visualize suas recomendações

Quando você passa para a etapa do fluxo de trabalho Recomendação, uma janela pop-up é exibida para mostrar que a ferramenta está gerando a recomendação. Enquanto estiver gerando, você pode ir para a guia Lista para definir uma nova carga de trabalho. O site Cloudability continuará a gerar a recomendação nos bastidores.

Quando o site Cloudability tiver terminado de gerar a recomendação, a janela pop-up será fechada e você será levado à etapa do fluxo de trabalho da recomendação.

Para fazer uma comparação entre nuvens, selecione uma opção no menu suspenso “Serviço” para visualizar recomendações para cada tipo de serviço ( AWS, Azure, GCP e OCI).

Você pode selecionar qualquer tipo de preço. Os preços On-Demand, Committed e Spot são calculados como preço mensal por unidade. O preço comprometido é calculado com base nos dados exibidos na etapa [Informações comuns](#common).

Para visualizar o custo total de sua carga de trabalho e comparar os custos entre os provedores de nuvem lado a lado, selecione o botão Next (Avançar ).

Para obter uma recomendação diferente:

- Selecione o ![Editar ícone](../../../../03-media/cloudability-premium/images/edit-icon.jpg) ícone para atualizar seus requisitos; OU
- Selecione o botão Voltar para ir para a etapa anterior. Essa opção permite que você modifique vários requisitos de uma só vez.

## Revise o resumo de sua recomendação

Na etapa de fluxo de trabalho Resumo, o site Cloudability exibe suas recomendações em duas guias: Summary (Resumo ) e Analysis (Análise ).

Explore a guia Resumo

A guia Resumo exibe um resumo das informações associadas à sua carga de trabalho. Para comparações entre nuvens, selecione o provedor escolhido. Cloudability atualiza seu custo total (mensal) adequadamente.

Ao examinar os recursos adicionados à sua carga de trabalho, selecione Detalhes para ver informações adicionais.

Explore a guia Análise

A guia Analysis (Análise) visualiza o detalhamento do custo por tipo de serviço e provedor de serviços no caso de comparação entre nuvens.

Compartilhe seu resumo

Selecione ![ícone de três pontos](../../../../03-media/cloudability-premium/images/3-dots.jpg) uma das guias “Resumo” ou “Análise” para exportar o resumo da carga de trabalho como um arquivo do CSV (PDF), duplicar a carga de trabalho ou compartilhá-la com outras pessoas.

Você sempre pode voltar às etapas anteriores nas guias Resumo ou Análise para fazer qualquer alteração. Quando terminar de definir sua carga de trabalho, selecione o botão Done (Concluído ). Cloudability retorna à tela List.

## **Perguntas Frequentes**

1. Por que devo selecionar o provedor de serviços em nuvem e as preferências de compra na seção “**Informações gerais > Provedores de serviços** ”?

   Escolha o provedor de nuvem e seus tipos preferidos de contrato de locação e de compromisso na seção **“Informações comuns > Provedores de serviços”,** para que você receba recomendações mais precisas com base nessas preferências definidas aqui.
2. Quantas regiões posso selecionar na seção **“Informações gerais” > “Prestadores de serviços** ”? Por que eu deveria selecioná-los aqui?

   Você pode selecionar até 5 regiões para cada provedor de nuvem; com base nisso, receberá recomendações de preços para cada uma dessas regiões
3. Por que não consigo ver o tipo de contrato de locação ou o tipo de compromisso que desejo em **“Informações comuns” > “Prestadores de serviços”**?

   Isso pode ter ocorrido porque o administrador pode ter desativado esses tipos de contrato de locação ou tipos de compromisso na seção “Preferências” do Work.Planning.
4. Por que estou vendo essa mensagem ao editar uma carga de trabalho existente? *Esta carga de trabalho não está em conformidade com as preferências de planejamento de carga de trabalho. Os tipos de contrato e/ou as preferências de compromisso definidos pelo seu administrador não correspondem à sua carga de trabalho. Você pode clicar em “Editar carga de trabalho” para atualizá-las.*

   Isso pode ocorrer porque alguns dos conceitos definidos em sua carga de trabalho (por exemplo: provedor de nuvem, tipo de contrato de locação, tipo de compromisso etc.) foram atualizadas pelo seu administrador na seção “Preferências” do Work.Planning
5. Como o recurso recomenda recursos se eu não selecionar o tipo exato de recurso (usando a opção de pesquisa por tipo de recurso) ao adicionar um novo recurso?

   Se você não tiver selecionado o tipo exato de recurso (use a opção de pesquisa por tipo de recurso) ao adicionar um novo recurso, o recurso recomendará os 30 recursos mais econômicos de cada provedor de nuvem selecionado, com base na configuração do recurso que você inseriu.
6. Como o recurso sugere recursos se eu escolher o tipo exato de recurso (usando a opção de busca por tipo de recurso) ao adicionar um novo recurso?

   Se você tiver selecionado o tipo exato de recurso (use a opção de pesquisa por tipo de recurso) ao adicionar um novo recurso, o recurso fixará esse recurso específico no topo como a primeira recomendação, seguido por 29 recursos com boa relação custo-benefício em cada um dos provedores de nuvem selecionados, com base na configuração do recurso que você inseriu.
7. O que devo fazer para que as recomendações de recursos levem em conta meus EDPs ou outras formas de precificação personalizadas?

   Você não precisa fazer nada para que as recomendações de recursos levem em conta seus EDPs ou outros preços personalizados. Cloudability já obtém suas informações de preços personalizadas, caso existam, e os descontos seriam incorporados às recomendações do Planejamento de Carga de Trabalho por padrão.
8. Preciso definir os preços personalizados da minha organização no campo “Desconto adicional / Aumento %” na seção “Preferências” d Work.Planning?

   Nº Cloudability já obtém suas informações de preços personalizadas, caso existam, e seus descontos serão considerados nas recomendações do Planejamento de Carga de Trabalho por padrão.

   A % de Desconto/Aumento adicional refere-se a quaisquer outros descontos aplicáveis aos custos de todos os recursos recomendados, excluindo “Outros custos”. Quando definido, esse desconto/reajuste seria somado a qualquer preço personalizado já exibido pelo Cloudability
9. Por que estou percebendo uma diferença entre os preços nas recomendações do Planejamento de Carga de Trabalho e os da calculadora de preços do provedor de nuvem?

   Se você notar uma diferença entre os preços apresentados nas recomendações do Planejamento de Carga de Trabalho e os da calculadora de preços do provedor de nuvem:

   - Verifique se o tipo de recurso, a região e outras configurações correspondem exatamente entre a calculadora de preços e o Planejamento de Carga de Trabalho
   - Verifique se a opção “Multimoeda” está ativada em Cloudability e, caso esteja, verifique se a taxa de câmbio que você definiu para sua moeda preferida no módulo “Multimoeda” corresponde à taxa de câmbio considerada pelo provedor de serviços em nuvem
   - Verifique se você fez login na calculadora de preços do provedor de serviços em nuvem usando a conta da sua organização que tem a opção de preços personalizados ativada. Se você estiver verificando sem fazer login na calculadora de preços do provedor de serviços em nuvem, provavelmente estará vendo preços de varejo na calculadora e preços personalizados no Workload Planning
   - Verifique se o seu administrador definiu algum desconto adicional que se aplique aos custos de todos os recursos recomendados na seção **Preferências de Planejamento de Work.Planning**
10. Para a importação em massa de recursos, qual é o número máximo de recursos que posso adicionar para um serviço específico?

    Você pode adicionar até 30 recursos no arquivo ` CSV ` ao realizar uma importação em massa
11. Como faço para definir o tipo de recurso no arquivo ` CSV ` ao realizar uma importação em massa?

    Você verá que as informações sobre a CPU e a RAM também estão incluídas na interface de usuário do Planejamento de Carga de Trabalho. Ao realizar uma importação em massa, ignore as informações sobre CPU e RAM e utilize apenas a primeira parte do nome do tipo de recurso. Por exemplo, para o tipo de recurso exibido como “ D2s\_v6 — 2 CPU/s, 8 RAM” na interface de usuário do Workload Planning, use “ D2s\_v6 ” como nome do tipo de recurso no arquivo de importação do CSV. Como alternativa, você também pode baixar todos os tipos de recursos compatíveis na seção “Pesquisar tipo de recurso”, em “Adicionar recurso”, e utilizar esses nomes de tipos de recursos diretamente no seu arquivo de importação em massa CSV.
12. Preciso definir as informações sobre CPU e RAM no arquivo de importação em massa CSV ao definir um tipo de recurso?

    Nº Se você estiver definindo um tipo específico de recurso, pode deixar todos os outros campos de configuração do recurso em branco, pois eles serão preenchidos automaticamente de acordo com o tipo de recurso definido. Mesmo que você insira seus próprios detalhes de configuração de recursos, eles seriam substituídos pelos detalhes de configuração definidos pelo provedor de nuvem
13. Como posso editar uma carga de trabalho criada por outro usuário?

    O autor da carga de trabalho deve compartilhá-la com permissões de edição para que você possa editar a carga de trabalho de outro usuário. Isso se aplica mesmo se você for um usuário administrador — se você for um administrador, poderá visualizar todas as cargas de trabalho criadas na sua organização, mas só poderá editar a carga de trabalho de outro usuário se ele a tiver compartilhado com você com acesso de edição.
