---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Recomendação para todas as linhas"
breadcrumb: []
source_path: "studio/troubleshooting/studio-troubleshooting-all-rows-recommendation.html"
images:
  - "resources/images/studio_images/all-rows-recommdentation-1.png"
  - "resources/images/studio_images/all-rows-recommdentation-2.png"
  - "resources/images/studio_images/all-rows-recommdentation-3.png"
  - "resources/images/studio_images/all-rows-recommdentation-4.png"
  - "resources/images/studio_images/all-rows-recommdentation-5.png"
  - "resources/images/studio_images/all-rows-recommdentation.png"
  - "resources/images/studio_images/arr-1.jpg"
  - "resources/images/studio_images/arr-2.jpg"
  - "resources/images/studio_images/arr-3.jpg"
  - "resources/images/studio_images/arr-4.jpg"
  - "resources/images/studio_images/arr-5.jpg"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Recomendação para todas as linhas

Esse recurso simplifica o processo, fornecendo orientação passo a passo com base em recomendações de especialistas, garantindo tempos de cálculo mais rápidos e melhor desempenho. Você pode acessar documentos e automatizar alterações de configuração para otimizar seu fluxo de trabalho. O sistema verificará automaticamente as alterações e marcará os problemas como resolvidos.

Navegue até **TBM Studio** > guia **Recommendations (Recomendações** ) e selecione **Troubleshoot All Identified Problems (Solucionar todos os problemas identificados** ).

![Solução de todos os problemas identificados](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/arr-1.jpg)

Mude para o espaço de trabalho **Development** e selecione **Next**.

![Assistente de recomendações](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/arr-2.jpg)

Clique no ícone **Next**.

![Próximo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/arr-3.jpg)

Selecione **Set Automatic!ALL\_ROWS\_Assignment** botão.

![TODAS AS LINHAS](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/arr-4.jpg)

Selecione **Next** e, em seguida, selecione **Checkin** na última página.

![Check-in](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/arr-5.jpg)

Habilite a opção 'Automatically handle!Opção "ALL\_ROWS" na [configuração do projeto](../admin/edit-project-settings.html "Aplica-se a: TBM Studio 12.0 e posterior. Algumas configurações estão disponíveis em versões posteriores do TBM Studio, conforme indicado abaixo."). Com essa configuração ativada, o TBMA não precisa mais criar perspectivas para lidar com ALL\_ROWS. Ele adiciona e remove permissões quando necessário e, portanto, elimina a necessidade de marcar a caixa Todas as linhas nas perspectivas.

## Método antigo: Recuperação de todas as linhas em uma consulta baseada em tempo

![Recuperação de todas as linhas em uma consulta baseada em tempo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/all-rows-recommdentation.png)

Essa opção pode ser configurada ao publicar uma coluna em uma perspectiva. Ele adicionará um ALL\_ROWS! Item para um caminho de dados, que garantirá que, ao usar um agregado de tempo como =YearToDate( ) ou Annual(), todas as linhas da tabela sejam incluídas no cálculo. Em dados que variam ao longo do tempo, será necessário usar ALL\_ROWS para garantir que as informações corretas sejam calculadas. Isso nem sempre é incluído por motivos de desempenho.

Supondo que você tenha dados estruturados desta forma.

![recomendação de linha](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/all-rows-recommdentation-1.png)

O valor de =Annual() para A e B é 12, e para C é 1. No entanto, se você executasse essa função nos meses de fevereiro a dezembro, teria apenas os identificadores A e B em sua tabela, veja o exemplo abaixo.

![Recomendações de linha 2](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/all-rows-recommdentation-2.png)

Como o identificador C não está presente nos dados de fevereiro a dezembro, essas linhas não estão presentes na tabela do mês atual, o que faz com que o cálculo anual mostre o total geral incorreto. Para solucionar esse problema, você deve criar uma perspectiva da coluna e marcar a opção "Show all rows in time-based query" (Mostrar todas as linhas na consulta baseada em tempo)

![campo de publicação](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/all-rows-recommdentation-3.png)

Colocar essa nova perspectiva na configuração faz com que a linha C seja exibida e levada em conta no total.

![recomendações de linhas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/all-rows-recommdentation-4.png)

Ao usar "Time" em Columns, ALL\_ROWS não é necessário, porque os intervalos de tempo criam uma estrutura de dados diferente chamada TREND\_APPEND, que pega os dados de cada mês e os anexa. Um não é necessariamente melhor do que o outro, depende de qual visão específica do relatório está tentando ser alcançada. Abaixo, você pode ver as duas tabelas, que mostram os mesmos dados, mas têm caminhos de dados diferentes e nomenclatura/formatação ligeiramente diferente.

![recomendações de linhas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/all-rows-recommdentation-5.png)

## Conclusão

- ALL\_ROWS não é necessário e não será adicionado aos caminhos de dados que estão usando os intervalos de tempo (TREND\_APPEND)
- ALL\_ROWS não é necessário se os agregados de tempo não estiverem sendo usados.
- ALL\_ROWS é necessário se os dados subjacentes variarem ao longo do tempo e os agregados de tempo estiverem sendo usados.
