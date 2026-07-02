---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Normalização e mapeamento"
breadcrumb:
  - "Benchmarking"
  - "Relatórios de benchmarking"
  - "Referência de dados e metodologia"
source_path: "it-benchmarking/data-and-methodology/normalization-mapping.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Normalização e mapeamento

É aqui que o seu modelo ganha ou perde a confiança.

**Alinhamento da taxonomia**   
 TBM Os benchmarks estão alinhados com o TBM padrão:

- Grupos de custos
- Torres de recursos e subtorres de recursos

O modelo do seu projeto de cálculo de custos deve:

- Mapeie contas GL, dados de fornecedores e outras fontes nos mesmos pools de custos
- Mapeie os custos em torres de recursos e subtorres de recursos que correspondam às definições de referência

Se você tem:

- Torres de recursos personalizadas
- Grupos de custos personalizados
- Categorias mistas que combinam vários conjuntos padrão

então você precisa de regras de mapeamento explícitas. O desalinhamento aqui é a principal causa de “esses benchmarks parecerem errados”

**Escopo e inclusões**   
Você deve decidir e documentar o que está dentro do escopo.   
Inclusões típicas para custos de TI:

- Mão de obra e prestadores de serviços para funções de TI
- Hardware, software e serviços em nuvem
- Serviços de fornecedores que oferecem suporte a serviços de TI
- Depreciação ou amortização de ativos tecnológicos

Exclusões típicas:

- Terceirização de processos de negócios em que a TI não é o principal impulsionador
- Despesas gerais corporativas não relacionadas à TI que não são alocadas à TI
- Encargos extraordinários únicos, se o provedor os excluir

Suas escolhas de escopo devem refletir, da forma mais fiel possível, como os colaboradores da referência são orientados a relatar.

**Normalização da moeda** Os   
benchmarks externos são relatados em uma moeda de referência.   
Seu ambiente:

- Deve-se usar uma única moeda de trabalho para os dados que você insere no Benchmarking
- É necessário garantir que tanto os custos de TI quanto as receitas utilizem a mesma moeda para o período

Se você opera com várias moedas:

- A conversão deve ocorrer na fase inicial do cálculo de custos ou antes da entrada manual
- Documento que indica as taxas e os prazos que você utiliza para a conversão

Misturar moedas silenciosamente é uma maneira confiável de produzir absurdos.

**Alinhamento**  
 temporal Não compare: Sua previsão para o ano atual com uma referência que reflete os resultados reais do ano passado. A menos que você esteja fazendo isso deliberadamente e afirmando isso claramente.

O padrão claro é: os resultados reais do ano fiscal N em comparação com o ano fiscal N de referência. Quando os exercícios fiscais diferem entre as organizações, o provedor de referência aplica suas próprias regras de alinhamento; você só precisa ser consistente.

**Trat** amento de capital versus  
 despesas Os benchmarks normalmente consideram os custos periódicos de TI, que incluem:

- Despesas operacionais
- Depreciação ou amortização de investimentos em tecnologia capitalizados
- Custos de arrendamento, dependendo da abordagem contábil

Se o seu modelo de custos de TI exclui a depreciação, enquanto os benchmarks a incluem, seus índices não corresponderão.   
Você deve:

- Alinhar o tratamento de CapEx e depreciação com as diretrizes de referência
- Ou, pelo menos, compreenda a diferença e evite chamar essas métricas de “gastos reais com TI” no sentido contábil interno
