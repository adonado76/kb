---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Veja o diagrama do modelo"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar modelos de custos"
  - "Noções básicas sobre modelos"
source_path: "studio/new-uc/howtoguides/build-cost-model/view-model-diagram.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Veja o diagrama do modelo

|  |  |
| --- | --- |
| **Tipo de Conteúdo** | Guia prático |
| **Público-alvo** | Analistas de negócios, equipes de TI e finanças, administradores |
| **Tempo estimado** | 5 a 10 minutos |
| **Pré-requisitos** | Pelo menos uma tabela foi adicionada ao modelo |

## Objetivo

Consulte o diagrama do modelo para compreender a estrutura geral do seu modelo de custos, veja como as tabelas se conectam por meio de alocações e acompanhe o fluxo de custos pela sua organização.

## Quando utilizar este procedimento

Consulte o diagrama do modelo sempre que precisar:

- Compreenda o fluxo de custos de ponta a ponta no seu modelo
- Integre os novos membros da equipe mostrando-lhes a estrutura do modelo
- Depure problemas de alocação rastreando caminhos de custo
- Documente o projeto do seu modelo para as partes interessadas
- Verifique se as tabelas recém-adicionadas estão conectadas corretamente

## Visualizações de modelos disponíveis

O TBM Studio oferece três maneiras de visualizar seu modelo:

**1. Modelador de Objeto Único (Diagrama de Sankey)**

Esta é a visualização padrão quando você clica na etapa "Modelo" no fluxo de transformação de uma tabela. A tela mostra a tabela selecionada no centro, com seus controladores à esquerda e os destinos de alocação à direita. Utilize esta visualização ao configurar drivers e alocações para uma tabela específica.

**2. Visão métrica modelada (diagrama completo do modelo)**

Esta visualização exibe todos os objetos do modelo e suas conexões em um diagrama semelhante ao do Visio. Ele mostra todo o fluxo de custos, desde as tabelas de origem, passando pelas camadas intermediárias, até os destinos finais. Use esta visualização para ter uma visão geral do seu modelo.

**3. Relatórios de modelo (visualização de Sankey em camadas)**

Os relatórios de modelo apresentam o modelo em um formato intuitivo, com níveis definidos (como Finanças, Grupos de Custos, Infraestrutura, Serviços). Esses relatórios foram concebidos para uso pelo usuário final e oferecem recursos de detalhamento.

## Passos: Visualizar o diagrama de métricas modeladas

Para visualizar o diagrama completo do modelo, mostrando todas as tabelas e suas conexões:

1. **Abra qualquer objeto de modelo.** No Project Explorer, selecione uma tabela que contenha uma etapa Model e, em seguida, clique na etapa **Model** no pipeline de transformação.
2. **Mude para a visualização “Métrica modelada”.** No menu **Exibir**, clique em **Métrica modelada**. O diagrama se expande para mostrar todos os objetos do modelo e suas relações.
3. **Navegue pelo diagrama.** Use os controles de zoom e panorâmica para explorar o modelo. Clique em qualquer objeto do modelo para destacar suas conexões e visualizar seus detalhes.
4. **Selecione uma métrica para visualizar.** Use o seletor de métricas na parte superior do diagrama para alternar entre Custo, Orçamento, Previsão ou outras métricas. O diagrama é atualizado para mostrar os valores da métrica selecionada.

## Interpretação do diagrama do modelo

O diagrama do modelo utiliza uma visualização no estilo Sankey, em que:

- Os retângulos representam objetos do modelo (suas tabelas)
- As linhas entre os retângulos representam alocações
- A largura da linha é proporcional ao valor — linhas mais grossas indicam um maior fluxo de custos por esse caminho
- O valor flui da esquerda para a direita (ou de baixo para cima em algumas visualizações)

**Interpretando o fluxo:** Comece pelos objetos mais à esquerda (ou na parte inferior) — esses são, normalmente, as fontes de custo, ou seja, de onde o dinheiro entra no modelo. Siga as linhas para a direita (ou para cima) para ver como os custos são distribuídos entre os objetos intermediários e, por fim, chegam aos destinos finais, como Unidades de Negócio ou Serviços.

## Padrões comuns de diagramas

**Fonte única, destinos múltiplos:** uma tabela de fontes de custo que faz a alocação para várias categorias de pool de custos (Mão de obra, Instalações, Hardware). As linhas de alocação se ramificam a partir da fonte.

**Várias fontes, um único destino:** vários componentes de infraestrutura (servidores, armazenamento, rede) que atendem às aplicações. As linhas convergem para o alvo.

**Alocações em cascata:** Origem de custo → Fornecedores → Serviços de tecnologia → Soluções → Unidades de negócios. Cada nível faz a alocação para o seguinte, criando um fluxo sequencial.

## Utilização do diagrama para resolução de problemas

**Conexões ausentes:** Se uma tabela aparecer isolada, sem linhas que a conectem, significa que a alocação não foi configurada. Verifique a etapa “Modelo” da tabela para adicionar alocações.

**Linhas finas inesperadas:** Se uma linha de alocação estiver muito mais fina do que o esperado, verifique os pesos de alocação ou os dados do driver. Pode haver registros sem correspondência, fazendo com que os custos permaneçam sem alocação.

**Rastreando custos específicos:** Clique em um objeto do modelo no diagrama para destacar suas conexões. Você pode rastrear os custos para a frente para ver para onde vão, ou para trás para ver de onde vêm.

**Dica:** O diagrama do modelo reflete a configuração do modelo atualmente implantada. As alterações feitas nas alocações só serão exibidas depois que você salvar, fazer o check-in e o projeto for recalculado.

## Navegando a partir do diagrama

O diagrama é interativo. Ao clicar em um objeto modelo, abre-se a visualização do Modelador de Objeto Único, onde é possível configurar drivers e alocações. Isso facilita a análise, permitindo passar de uma visão geral para os detalhes de uma tabela específica.

## O que vem a seguir

- Configure alocações para tabelas que ainda não estão conectadas — consulte a Seção 3.2.2
- Crie relatórios do modelo para disponibilizá-lo aos usuários finais — consulte a Seção 3.3
- Use os recursos de detalhamento para rastrear itens de custo específicos — consulte a Referência do Model Studio (Seção 5.2 )

## Conceitos relacionados

- [Arquitetura do modelo](../../concepts-architecture/model-architecture/model-concepts-overview.html) — Compreender como as alocações são executadas e como as métricas são geradas
- Relatórios de modelo (Seção 5.2 ) — Criação de visualizações de modelo destinadas ao usuário final

**Tópico principal:** [Noções básicas sobre modelos](../../../../studio/new-uc/howtoguides/build-cost-model/model-basics.html)
