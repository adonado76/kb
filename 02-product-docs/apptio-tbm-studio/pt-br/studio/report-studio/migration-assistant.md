---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "IBM Apptio Guia do Assistente de Migração de Relatórios"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "ApptioIBM Report Studio (Novo)"
  - "Configuração e personalização"
source_path: "studio/report-studio/migration-assistant.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# IBM Apptio Guia do Assistente de Migração de Relatórios

## Visão geral

Este guia explica como funciona o Assistente de Migração de Relatórios do IBM Apptio, o que é preservado, o que requer atualizações manuais e como planejar uma transição bem-sucedida. A migração do relatório cria uma nova versão do seu relatório no formato atualizado, mantendo o relatório original inalterado.

- Seu relatório atual não foi alterado
- Um novo relatório migrado é aberto em uma guia separada
- Você pode comparar a versão antiga com a nova lado a lado para validar os resultados e fazer atualizações
- Os relatórios são criados com o mesmo nome do original, seguido da indicação “(Migrado)”.

Este documento se aplica aos relatórios criados no Report Studio clássico que estão sendo migrados para o Report Studio d IBM Apptio. Migração do Report Studio clássico para o IBM Apptio O Report Studio é uma atividade gerenciada pelo cliente. Os clientes são responsáveis pela execução da migração e devem garantir que a pessoa encarregada da migração tenha permissões administrativas no TBM Studio. Como parte dessa evolução de modernização do IBM Apptio, o Report Studio clássico chegará ao fim de vida útil (EOL) em 31 de dezembro de 2027. Após essa data, os relatórios clássicos do Report Studio já existentes não estarão mais disponíveis.

Para facilitar a transição, o Assistente de Migração de Relatórios do IBM Apptio ajuda os clientes a transferir os relatórios existentes do Report Studio clássico para a nova interface. O processo de migração é amplamente automatizado, com a capacidade de transferir mais de 90% dos componentes dos relatórios, configurações de dados e layouts, permitindo que as equipes realizem a transição com eficiência, mantendo a continuidade. Embora a maioria dos elementos estruturais seja preservada, a formatação (incluindo cores, fontes, estilos e temas) não será totalmente transferida e exigirá ajustes no novo Report Studio.

Embora a migração tenha sido projetada para ser realizada pelos próprios clientes, aqueles que desejarem assistência ou não conseguirem concluir a migração podem entrar em contato com seu Gerente de Sucesso do Cliente (CSM) para definir um escopo de trabalho no âmbito de uma Declaração de Trabalho (SOW). IBM Apptio Os clientes do Essentials podem aproveitar o serviço TAS que está à sua disposição.

Os clientes também podem optar por utilizar os relatórios novos ou atualizados prontos para uso (OOTB), em vez de migrar suas coleções de relatórios existentes.

## Guia de Migração

Esta seção descreve o guia a ser aplicado

1. **Descoberta** :
   - O cliente analisa a lista de relatórios usados recentemente no CT Report Studio para escolher quais devem ser migrados.
2. **Migração** :
   - Para cada relatório:
     - O usuário deve “fechar” o relatório
     - O usuário clica no botão “Migrar relatório” no TBM Studio. Isso gera um novo relatório com o mesmo nome do relatório antigo, seguido da indicação “(Migrado)”, por exemplo, “Análise Financeira (Migrado)”. Este novo relatório é gerado em uma nova guia.
     - O usuário acessa o novo relatório no Report Studio do IBM Apptio, verifica se a configuração dos dados está correta e aplica as opções de formatação desejadas para que o relatório fique com a mesma aparência do antigo.
   - O que esperar após a migração
     - [Aqui](#migasst__What_will_be) está uma lista dos componentes/widgets que serão migrados. A tabela também inclui uma lista de widgets/recursos que não serão migrados para a nova experiência.
     - Os widgets não compatíveis serão exibidos como um espaço reservado. Os marcadores de lugar só podem ser excluídos.
     - A navegação do Drill não será migrada.
     - As cores podem variar.
     - A migração de um único relatório não deve demorar mais do que alguns minutos.
     - Se você quiser inserir logotipos personalizados, pode usar um componente HTML com uma tag de imagem, por exemplo, <img src="https://logos.apptio.com/myLogo.jpg" >.
3. **Fluxo de trabalho recomendado após a migração**
   - Abra os dois relatórios lado a lado
     - Original (retirada para permitir a visualização da configuração)
     - Versão migrada (editável)
   - Validar os dados
     - Verificar se as métricas e os resultados correspondem
   - Validar componentes
     - Abra o painel Camadas para visualizar todos os componentes e identificar aqueles que possam estar ocultos.
   - Revisar espaços reservados
     - Identifique componentes não compatíveis através do painel de camadas
     - Remova ou recrie, conforme necessário
   - Corrigir a formatação
     - Ajustar cores, fontes e layout
     - Alinhar componentes usando ferramentas de layout
   - Recriar interações
     - Recriar a navegação do exercício manualmente
4. **Teste de aceitação do usuário** :
   1. Depois que todos os relatórios de um cliente forem migrados, o cliente analisa as atualizações.
      - O usuário ajusta os relatórios com base no feedback
5. **Passagem de bola** :
   - O usuário renomeia todos os relatórios aceitos para remover a marcação “(Migrado)” e faz o check-in dos novos relatórios.
   - Os relatórios existentes criados no CT Report Studio podem continuar a coexistir até que o usuário se sinta à vontade com o IBM Apptio Report Studio

## O que será migrado e o que não será

|  |  |  |  |
| --- | --- | --- | --- |
| Será migrado | Não será migrado | A ser migrado posteriormente (data a definir) | Em análise |
| - Configurações de dados (métricas, dimensões, filtros) - Tipos de componentes (compatíveis) - Estrutura do layout - Localização (aproximada) - Dimensionamento dos componentes (exato) - Resultados dos dados (os números permanecem os mesmos) - Nome do relatório (com a menção “(Migrado)” anexada) - Botão - Gráficos   - Barras   - Coluna   - Linha   - Sobreposição: Coluna + Linha   - Sobreposição: Coluna empilhada + Linha   - Sobreposição: Linha + Linha   - Gráfico de pizza   - Barra empilhada   - Coluna empilhada - Seletor de colunas - Fatiador compacto - Tabela editável - Grupo - HTML - KPI - Mudança rápida de direção - Upload simplificado - Fatiador - Tabela - Guias | - Tabela   - a demanda   - Lista de tarefas   - o Anotações de células - Símbolo   - Medidor   - Símbolo - Formatação (cores, fontes, estilo, temas) - Configurações de perfuração (os caminhos de perfuração não são migrados devido a diferenças na identificação dos relatórios (caminhos antigos vs. novos IDs exclusivos)) - Componentes sem suporte / obsoletos - Alinhamento exato (podem ocorrer pequenas alterações no layout) - Mapeador GL - Grelha de mapeamento - Diagrama do modelo - Nota - Carregamento de tabela - Coleções de relatórios - Estrutura de pasta | - Gráfico   - Mapa de árvore - Ícone - Texto - Queda de água | - Gráfico   - Bolha   - Radar |

## Relatório de perfis de complexidade

Use esses perfis para definir as expectativas em relação ao esforço de migração:

**Relatórios simples**

- Gráficos e tabelas básicos
- Formatação mínima
- Poucos ou nenhum componente personalizado
- Resultado esperado:
- Limpeza rápida
- Principalmente ajustes de formatação

**Relatórios de complexidade média**

- Combinação de gráficos, KPIs e filtros
- Algumas formatações personalizadas
- Complexidade moderada do layout
- Resultado esperado:
- Requer correções de formatação e uma pequena recompilação
- Alguns espaços reservados a serem preenchidos

**Relatórios complexos**

- Layouts avançados e ampla personalização
- Componentes HTML, botões ou widgets antigos
- Trajetórias de perfuração e interatividade
- Resultado esperado:
  - É necessário um refinamento manual significativo
  - Pode ser necessário recompilar vários componentes
  - A lógica de interação deve ser recriada

Nota:

- Migre os relatórios de destino antes dos relatórios de origem. Como a navegação por detalhamento precisa ser adicionada novamente após a migração, pode ser mais eficiente migrar seus relatórios clássicos de baixo para cima. Dessa forma, ao definir os detalhes do relatório de origem, os destinos estarão disponíveis para você escolher.
- A posição dos componentes pode variar dependendo da visibilidade do cabeçalho clássico dos componentes. Nos relatórios clássicos, os títulos ou cabeçalhos dos componentes ficam fora das bordas dos componentes, enquanto nos novos relatórios ficam dentro delas. Quando os componentes clássicos de relatório têm cabeçalhos ocultos, os autores dos relatórios tendem a ajustá-los para cima a fim de reduzir o espaço em branco. Assim, ao migrar os relatórios, nós os movemos para baixo.

## Problemas conhecidos

A seguir estão listados os problemas conhecidos do Assistente de Migração de Relatórios na versão 12.11.21 (abril de 2026). A maioria ou todas essas questões serão abordadas na revista “ 12.11.22 ” (maio de 2026)

- As fatiadoras compactas que incluem várias fatiadoras em um único componente são transferidas para um grupo de fatiadoras individuais. Esse agrupamento torna os segmentadores ineficazes, pois altera seu escopo. Basta desagrupar os segmentadores para resolver isso.
- As tabelas em árvore com configurações entre objetos (linhas, colunas, valores ou filtros envolvendo dois ou mais objetos do modelo) podem não funcionar. Isso será abordado em 12.11.22.

**Tópico principal:** [Configuração e personalização](../../studio/report-studio/config-custom.html)
