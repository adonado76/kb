---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Os valores parecem errados ou suspeitos"
breadcrumb:
  - "Benchmarking"
  - "Relatórios de benchmarking"
  - "Solução de problemas e perguntas frequentes"
source_path: "it-benchmarking/troubleshooting/values-wrong.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Os valores parecem errados ou suspeitos

**Nosso valor é ordens de magnitude superior ou inferior ao dos nossos pares.**

Sintoma  
: uma métrica mostra que você está muito acima ou abaixo da faixa dos seus pares por um fator significativo, não apenas 10-20%.   
Causas prováveis

- Incompatibilidade de unidades (milhares vs unidades monetárias inteiras, GB vs TB, etc.)
- Erro de volume (contagens erradas, escopo errado)
- Incompatibilidade de escopo (você está incluindo custos que outros excluem, ou vice-versa)
- Dados relativos ao ano errado ou a parte do ano

O que verificar

1. Consulte a definição da métrica ( **[Referência de dados e metodologia](../home.html#benchmarking__data-methodology)** ): numerador e denominador.
2. Confirme se o total dos custos em Cálculo de custos corresponde ao Financeiro para esse ano.
3. Confirme se o volume vem do sistema correto e corresponde à realidade.
4. Verifique se há erros nas unidades (por exemplo, TB inserido como GB).
5. Verifique se o ano selecionado é um ano completo, e não um semestre.

Resposta curta que você   
pode enviar: Esse valor está fora do intervalo porque os dados de custo ou volume subjacentes não estão alinhados com a definição do benchmark. Estamos validando o escopo e as unidades e atualizaremos o mapeamento para que a comparação seja significativa.

**Nosso índice de gastos com TI é muito diferente dos números internos do departamento financeiro.**

A comparação dos gastos com TI da   
SymptomBenchmarking como porcentagem da receita difere da visão do departamento financeiro.   
Causas prováveis

- Âmbito de TI diferente (por exemplo, TI + telecomunicações vs. apenas TI)
- Diferentes escopos de receita (grupo vs. segmento, bruta vs. líquida)
- Diferenças cambiais ou de período
- A avaliação comparativa utiliza definições de TI alinhadas com o TBM; o departamento financeiro utiliza categorias internas

O que verificar

1. Compare o escopo de TI: quais pools de custos e funções estão incluídos em ambos os lados.
2. Confirme se o escopo e o período da receita correspondem ao escopo dos custos de TI.
3. Verifique a moeda e quaisquer pressupostos relativos às taxas.

Resposta curta que você pode enviar  
: A proporção difere porque o Benchmarking utiliza uma definição padrão de custos e receitas de TI alinhada com o TBM, que não corresponde exatamente à visão interna do departamento financeiro. Vamos conciliar o escopo e as definições e, em seguida, chegar a um acordo sobre uma visão única para comparações externas.

**A tendência de referência ano a ano salta inesperadamente**

Sintoma  
: uma métrica permanece estável durante anos e, de repente, sobe ou desce sem que tenha ocorrido nenhum evento operacional óbvio.   
Causas prováveis

- Alterações no modelo TBM (remapeamento, novas torres, alterações no escopo do projeto)
- Benchmarking apontando para um projeto ou escopo de custos diferente para aquele ano
- Mudança no perfil organizacional que altera o grupo de pares
- Atualização do conjunto de dados de referência que alterou a composição dos pares

O que verificar

1. Revisar os registros de alterações do TBM/custos em torno do ano bissexto.
2. Confirme se a análise comparativa está usando o mesmo projeto e escopo de cálculo de custos ao longo dos anos.
3. Verifique se o seu perfil mudou de setor, faixa de tamanho ou região nesse ano.
4. Se necessário, compare com os registros de alterações de benchmark anteriores para verificar se a cobertura mudou.

Resposta curta que você   
pode enviar: O salto é impulsionado principalmente por mudanças estruturais ou de configuração, não por um único evento operacional. Mudamos a forma como os custos são mapeados ou com quais pares nos comparamos, por isso marcaremos esse ano como uma ruptura estrutural, em vez de uma tendência suave.
