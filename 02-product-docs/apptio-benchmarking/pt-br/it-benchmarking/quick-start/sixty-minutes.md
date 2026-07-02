---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "“Primeiros 60 minutos” com Benchmarking"
breadcrumb:
  - "Benchmarking"
  - "Iniciação rápida"
source_path: "it-benchmarking/quick-start/sixty-minutes.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# “Primeiros 60 minutos” com Benchmarking

O passo a passo abaixo pressupõe que você é o administrador, TBMA ou analista responsável pela configuração inicial.

1. **Abra o Benchmarking Interativo, identifique seu ponto de partida** e selecione **Configurações** > **Configuração.**

   ![Configuração de benchmarking](../../resources/images/it%20benchmarking_images/config-settings.png)

     
   Você deve ser capaz de responder: Onde posso alterar a configuração?
2. **Insira ou valide os dados do perfil organizacional**  
   . Os dados do perfil organizacional são necessários para o setor e muitas métricas de TI OpEx. Não é extraído do Cálculo de Custos. É inserido manualmente.   
   Entradas:
   - Receita da organização (anual)
   - Organização (Anual) OpEx
   - Número de funcionários como FTE (equivalente a tempo inteiro) para a organização apoiada  
   Diretrizes
   - Use valores que correspondam ao escopo dos custos de TI. Se a organização de TI apoiar exclusivamente a América do Norte, não utilize a receita global.
   - Use o último ano fiscal concluído, em vez de um ano previsto ou gastos anualizados.
   - Se você tiver várias entidades jurídicas, mas uma única função/organização de TI, alinhe seu perfil com a forma como os custos de TI são definidos.   
     Você pode refinar posteriormente. O primeiro objetivo é estar direcionalmente correto, portanto, estimativas aproximadas são aceitáveis.
3. **Forneça dados anuais sobre custos de TI, volumes e FTEs.** Você tem duas opções:  
   - **CAMINHO 1** Conectar ao Cálculo de Custos (recomendado)   
     Na configuração de Benchmarking Interativo:
     - Integre-se à plataforma de custos selecionando “Transparência de custos”.
     - Valide a conexão.
     - Selecione o projeto de cálculo de custos principal que contém seus gastos reais com TI.
     - Selecione o período fiscal do ano fiscal que deve ser usado para seus benchmarks de referência.
     - Recuperar os dados.

     ![Apptio Configuração da fonte para integração com IBM Projeto de cálculo de custos Apptio](../../resources/images/it%20benchmarking_images/path1-benchmarking.png)

     Uma vez conectado, o Benchmarking se conectará ao ambiente de produção do seu projeto de cálculo de custos e
     - Calcule o custo anual de TI por pool de custos.
     - Obtenha os custos anuais de TI por torre de recursos e, quando mapeados, por subtorre.

     Observação: certifique-se de que o projeto de cálculo de custos utilize os conjuntos de custos e torres de recursos da TBM alinhados com a versão selecionada da TBM definida na Avaliação Comparativa Interativa.
   - **PATH 2** Entrada manual de custos (se o cálculo de custos não estiver pronto ou não for utilizado)

     Se ainda não for possível integrar com o Cálculo de custos, abra a área Configuração e
     - Insira manualmente os dados na seção Dados de Custos.
     - Insira manualmente os dados na seção Volumes.
     - Insira manualmente os dados na seção FTEs.

       ![Configuração interativa de benchmarking – Pools de custos, volumes de torres de recursos e FTEs](../../resources/images/it%20benchmarking_images/manual-cost-input-benchmarking.png)

     Independentemente do método de integração:
     - Confirme se o custo total de TI carregado no Benchmarking está de acordo com o Financeiro para o ano selecionado.
     - Confirme se todas as principais torres que você espera realmente têm valores diferentes de zero.
     - Se algum valor estiver faltando ou você achar que merece ser substituído, insira os valores manualmente e salve-os antes de continuar.
4. **Execute uma comparação básica de benchmark**

   Agora, teste a configuração para verificar se produz resultados utilizáveis.

   Em Benchmarking Interativo:
   - Escolha até três grupos de pares que reflitam seu conjunto de comparação.
     - Setor semelhante.
     - Faixa de receita semelhante.
     - Região apropriada.
   - Abra a visualização de referências do setor.
     - Verifique métricas como gastos com TI como porcentagem da receita ou gastos com TI por funcionário.
     - Verifique se a métrica real da sua organização aparece no gráfico.   
       Dica: procure as linhas pontilhadas.

       ![Referências do setor – Gastos com TI como % da receita](../../resources/images/it%20benchmarking_images/benchmarking-views.png)
   - Selecione “ OpEx es de TI” no menu de coleção de relatórios.
     - Veja as distribuições por pool de custos e por torre de recursos.
     - Confirme se os valores parecem plausíveis e se as torres de recursos estão presentes.

       ![Benchmarks de TI ( OpEx ) – Por pool de custos](../../resources/images/it%20benchmarking_images/itopex-benchmarking.png)
   - Se os custos e volumes de infraestrutura foram fornecidos, abra os “Benchmarks de infraestrutura” no menu de coleta de relatórios e analise os custos unitários, como custo por servidor ou custo por TB e eficiência FTE.
     - Você ainda não está ajustando, apenas verificando se há valores atípicos absurdos causados por problemas de unidade ou volume.

       ![#: Referências de infraestrutura – Custos unitários](../../resources/images/it%20benchmarking_images/infrastructure-benchmarking-unit-cost.png)

     Nesta etapa, você está procurando problemas óbvios:
     - Gráficos em branco onde deveria haver dados.
     - Números que estão a ordens de magnitude de distância.
     - Filtros de pares que não correspondem à história que você deseja contar.

     Se algo parecer estar com defeito, anote e, posteriormente, use as seções Guia de configuração e Solução de problemas e perguntas frequentes para corrigir ou solucionar o problema.
5. **Marque e compartilhe as visualizações iniciais**

   Depois de ter algumas visualizações que façam sentido:
   - Capture um pequeno conjunto de capturas de tela ou exportações para sua primeira conversa com as partes interessadas.

     Pacote inicial mínimo:
     - Uma visão comparativa do setor que mostra os gastos com TI em relação à receita.
     - Uma visão de distribuição de TI ( OpEx ) que mostra a estrutura de custos por pool de custos ou torre de recursos.
     - Uma visualização da infraestrutura, se disponível, que mostre uma torre onde você suspeita que existam lacunas interessantes.

     O importante não é ser perfeito. O importante é ter um conjunto pequeno e consistente de pontos de vista aos quais você possa recorrer e sobre os quais possa refletir.
