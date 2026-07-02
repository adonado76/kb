---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Casos de uso comuns do TBM"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Noções básicas sobre TBM"
source_path: "studio/new-uc/concepts-architecture/tbm-use-cases.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Casos de uso comuns do TBM

A metodologia TBM oferece suporte a vários casos de uso distintos, cada um deles atendendo a uma necessidade comercial diferente. Compreender esses casos de uso ajuda você a projetar a implementação do TBM Studio de forma a gerar o máximo de valor para a sua organização.

## Retorno

**O que é** o Showback?   
O Showback é a prática de comunicar os custos de TI às unidades de negócios para fins de transparência, sem, no entanto, faturá-los. As unidades de negócios têm acesso aos custos de consumo de TI, mas esses valores são meramente informativos — não afetam os orçamentos departamentais nem acionam transferências financeiras.

**Quando usar**  

- Sua organização está começando a adotar o TBM e deseja desenvolver a consciência de custos de forma gradual
- É preciso validar seu modelo de custos antes de associá-lo a consequências financeiras reais
- As unidades de negócios ainda não estão preparadas para assumir a responsabilidade pelos custos de TI
- Você quer promover mudanças de comportamento por meio da transparência, em vez de pressão financeira

**Vantagens e limitações**  

|  |  |
| --- | --- |
| **Benefícios** | **Limitações** |
| Uma forma de baixo risco para introduzir transparência nos custos | Não há incentivo financeiro para otimizar o consumo |
| Gera confiança nos dados de custos antes da aplicação da medida | As unidades de negócios podem ignorar os relatórios informativos |
| Dá tempo para aperfeiçoar os modelos de alocação | Exige um esforço contínuo sem retorno imediato sobre o investimento |

**Cenário**  
 de exemplo: A equipe de TI da Acme Corp elabora relatórios mensais de showback para cada unidade de negócios, apresentando os custos de TI alocados a cada uma delas. A divisão de Vendas constata que eles gastam $2.4M/month em serviços de TI. Embora não haja troca de dinheiro, o vice-presidente de vendas começa a questionar por que o sistema de CRM da empresa custa mais do que a média do setor, dando início a uma conversa produtiva sobre otimização.

Nota: **Por que isso é importante no TBM Studio**   
O TBM Studio oferece suporte ao showback por meio dos painéis do Report Studio, que exibem os custos alocados por unidade de negócios. A segurança por linha garante que cada líder de unidade de negócios veja apenas seus próprios dados de custos. Não é necessária nenhuma integração adicional de faturamento.

## Estorno

**O que é isso**  
? O Chargeback leva a transparência um passo adiante, cobrando efetivamente das unidades de negócios pelo seu consumo de TI. Os custos de TI são transferidos do orçamento de TI para os departamentos usuários por meio de transações financeiras formais, geralmente na forma de lançamentos contábeis internos ou cobranças entre departamentos.

**Quando usar**

- Sua organização possui modelos de custos maduros e validados
- As unidades de negócios assumiram a responsabilidade pelo consumo de TI
- É preciso criar incentivos financeiros para a otimização do consumo
- Sua equipe financeira dá suporte aos processos internos de transferência de custos

**Considerações sobre a implementação**

- **A precisão dos dados é fundamental:** erros no estorno afetam diretamente os orçamentos departamentais; portanto, seu modelo de alocação deve ser devidamente validado
- **A comunicação é essencial:** as unidades de negócios precisam entender por que estão sendo cobradas e como podem influenciar os custos
- **Resolução de disputas:** Estabelecer um processo claro para que as unidades de negócios contestem cobranças que considerem incorretas
- **Cronograma:** Alinhe os ciclos de estorno com o processo de fechamento financeiro da sua organização

**Cenário de exemplo**  
: Após um ano de sucesso com o showback, a Acme Corp passa a adotar o chargeback. A cada trimestre, os custos de TI são alocados às unidades de negócios e transferidos por meio de lançamentos contábeis. A divisão de Marketing, que agora paga $1.8M/quarter pelos serviços de TI, consolidou duas plataformas de análise redundantes, economizando $200K por ano.

Nota:

**Por que isso é importante no TBM Studio**

O recurso de tabelas publicadas do TBM Studio ( Data Studio ) permite o reembolso de custos por meio da exportação de dados de custos alocados em um formato estruturado, adequado para importação em seu ERP ou sistema financeiro. As métricas de orçamento e previsão, juntamente com os custos, permitem o acompanhamento de variações para a reconciliação de cobranças retroativas.

## Otimização de custos

Os dados do TBM servem de base para identificar e aproveitar oportunidades de redução de custos. Ao compreender o custo real dos serviços de TI e como os custos se distribuem pela organização, é possível identificar ineficiências, redundâncias e oportunidades de otimização que ficariam ocultas sem dados estruturados sobre custos.

**Padrões comuns de otimização**

- **Eliminação de redundâncias:** Identificar serviços duplicados ou recursos subutilizados nas unidades de negócios
- **Dimensionamento adequado:** ajustar a capacidade da infraestrutura à demanda real por meio da análise de métricas de consumo
- **Consolidação de fornecedores:** utilize a visibilidade dos custos por fornecedor para negociar contratos mais vantajosos ou consolidar fornecedores
- **Otimização na nuvem:** compare os custos locais com os custos na nuvem para cargas de trabalho específicas
- **Eficiência da mão de obra:** analisar os custos de mão de obra por serviço para identificar oportunidades de automação ou melhoria de processos

Nota:

**Por que isso é importante no TBM Studio**

O Relatório de Modelos do TBM Studio (visualização de Sankey) oferece uma visualização intuitiva dos fluxos de custos, facilitando a identificação de alocações desproporcionais. As métricas calculadas permitem a análise de variações e a detecção de tendências. Os recursos de detalhamento permitem rastrear qualquer custo até sua origem para a análise da causa raiz.

## Linha de base para testes

A análise comparativa compara seus custos de TI com pontos de referência — sejam eles parâmetros internos, organizações semelhantes ou padrões do setor. Uma análise comparativa eficaz ajuda a responder à pergunta: “Estamos gastando a quantia certa?”

**Tipos de benchmarking**

- **Comparação entre períodos:** acompanhe os custos mês a mês ou ano a ano para identificar tendências
- **Comparação entre unidades de negócios:** compare os custos por usuário ou por transação entre as divisões
- **Análise comparativa do setor:** compare seus índices de custos com os de outras empresas do setor utilizando categorias padronizadas da taxonomia TBM

Nota:

**Por que isso é importante no TBM Studio**

O recurso de gerenciamento de períodos do TBM Studio permite visualizar dados de custos ao longo de vários meses para a análise de tendências. As métricas calculadas permitem determinar a variação em relação ao período anterior, e o alinhamento com a taxonomia padronizada da plataforma facilita a comparação com referências externas.

## Orçamento e previsão

Os dados do TBM orientam o planejamento do orçamento de TI, fornecendo uma visão detalhada e ascendente dos custos de TI. Em vez de definir orçamentos com base nos gastos do ano anterior acrescidos de uma porcentagem, o TBM permite a elaboração de orçamentos por nível de serviço, em que cada serviço de TI tem sua própria meta de custo.

**Principais recursos**

- **Análise de variação:** compare os custos reais com o orçamento em cada período para identificar excedentes com antecedência
- **Orçamentos por serviço:** definir e acompanhar orçamentos para serviços de TI específicos, em vez de categorias gerais
- **Cenários hipotéticos:** simular o impacto de mudanças (adição de usuários, desativação de aplicativos, migração para a nuvem) nos custos gerais de TI

Nota:

**Por que isso é importante no TBM Studio**

O TBM Studio oferece suporte a várias métricas de modelo simultaneamente — normalmente Custo, Orçamento e Previsão. Todas as três métricas passam pelo mesmo modelo de alocação, garantindo uma metodologia consistente. Os painéis do Report Studio podem exibir comparações entre o orçamento e os resultados reais, e as tabelas editáveis permitem que as equipes financeiras insiram e ajustem as premissas orçamentárias.
