---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Criar alocações em vários níveis"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar modelos de custos"
  - "Criar alocações"
source_path: "studio/new-uc/howtoguides/build-cost-model/create-multi-tier-allo.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Criar alocações em vários níveis

**Objetivo:** Criar um fluxo de custos completo que distribua os custos por várias camadas da sua organização — desde os custos de origem, passando por objetos intermediários, até os consumidores finais da empresa.

**Quando usar:** Seu modelo de custos requer várias etapas de alocação para refletir com precisão como os custos são distribuídos pela sua organização. A maioria das implementações de TBM utiliza de 4 a 6 camadas.

**Tempo estimado:** 45 a 60 minutos para um modelo de quatro camadas

## Compreendendo os fluxos de custos em vários níveis

Na modelagem de custos empresariais, os custos raramente fluem diretamente da origem até o destino final. Em vez disso, elas passam por camadas intermediárias que acrescentam contexto empresarial e permitem a geração de relatórios detalhados.

**Padrão comum de fluxo de custos de TBM:**

|  |
| --- |
| **Custos por fonte: valores reais**  *(Contabilidade geral, faturas, custos de mão de obra)*  ▼  **Mão de obra │ Fornecedores │ Instalações** (Nível 1)  ▼  **Serviços de Tecnologia** (Nível 2)  *(Computação, Armazenamento, Rede, Usuário final)*  ▼  **Inscrições** (Nível 3)  *( SAP, Salesforce, Aplicativos personalizados)*  ▼  **Unidades de Negócio** (Nível 4)  *(Vendas, Marketing, Operações, RH)* |

## Passo a passo: como criar um modelo de alocação de quatro níveis

**Cenário:** Criar um fluxo de custos completo, desde a fonte de custo, passando por mão de obra, serviços e aplicações, até as unidades de negócios.

## Fase 1: Definir a estrutura do modelo

1. **Certifique-se de que todas as tabelas tenham etapas do modelo**
   - Cada tabela no fluxo de custos precisa ter uma etapa “Modelo” adicionada ao seu pipeline de transformação.
   - Tabelas: Origem dos custos, Mão de obra, Serviços de tecnologia, Aplicações, Unidades de negócios.
2. **Planeje a sequência de alocação**
   - Fonte de custo → Mão de obra (por tipo de despesa = "Mão de obra")
   - Fonte de custo → Instalações (por tipo de despesa = "Instalações")
   - Mão de obra → Serviços de tecnologia (por percentual de alocação de tempo)
   - Serviços de Tecnologia → Aplicativos (por consumo de serviço)
   - Aplicativos → Unidades de Negócios (por responsável pelo aplicativo)
3. **Confira todas as tabelas**
   - Verifique todas as tabelas envolvidas na cadeia de alocação.

## Fase 2: Configurar alocações de Nível 1

Na Origem de custo, crie alocações separadas para cada objeto de primeiro nível:

1. **Alocação de mão de obra:** Adicionar a partir do filtro para Tipo de despesa = "Mão de obra"
2. **Alocação de instalações:** Adicionar filtro "De" para Tipo de despesa = "Instalações"
3. **Alocação de fornecedores:** Adicionar filtro "De" para Tipo de despesa NÃO INCLUÍDO EM ("Mão de obra", "Instalações")

## Fase 3: Configurar alocações de Nível 2

Para cada objeto de primeiro nível, atribua aos Serviços de Tecnologia:

- Mão de obra → Serviços de tecnologia: Relação de dados = Tipo de função → Categoria de serviço, Ponderado por = % de alocação de tempo
- Instalações → Serviços de Tecnologia: Custo por metro quadrado
- Fornecedores → Serviços de tecnologia: Relação de dados = Categoria de contrato → Categoria de serviço

**Fase 4: Configurar as alocações dos níveis 3 e 4**

- **Serviços de Tecnologia → Aplicativos:** Uso = Consumo, Coluna Consumo = Unidades consumidas, Coluna Capacidade = Capacidade total
- **Aplicativos → Unidades de Negócio:** Relação de dados = Proprietário do aplicativo → Código da unidade de negócio, Ponderado por = Número de usuários

**Fase 5: Validar o fluxo completo**

1. **Veja o diagrama do modelo**
   - Abra a visualização do diagrama do modelo para verificar se todas as linhas de alocação estão conectadas.
   - Verifique se há objetos órfãos ou conexões ausentes.
2. **Acompanhe um custo ao longo do modelo**
   - Selecione um único item de custo na seção "Fonte de custo".
   - Use o recurso de rastreabilidade para acompanhar o produto em cada etapa.
3. **Executar um cálculo do modelo**
   - Execute um cálculo do modelo para o período atual.
   - Analise o Relatório Modelo (visualização de Sankey) para visualizar o fluxo de custos.

## Melhores práticas para arquiteturas em camadas

**Alocar para baixo, não para cima**

- Sempre distribua os custos da fonte de custo para baixo ao longo do modelo.
- Os fluxos reversos geram complexidade e possíveis referências circulares.

**Manter uma granularidade consistente**

- Cada nível deve apresentar uma granularidade consistente dentro de si.
- Evite misturar dados altamente detalhados e altamente agregados no mesmo nível.

**Documentar o modelo**

- Adicione descrições a cada objeto do modelo explicando sua finalidade.
- Crie um diagrama visual do fluxo de custos previsto para a comunicação com as partes interessadas.

**Tópico principal:** [Criar alocações](../../../../studio/new-uc/howtoguides/build-cost-model/create-allocation.html)
