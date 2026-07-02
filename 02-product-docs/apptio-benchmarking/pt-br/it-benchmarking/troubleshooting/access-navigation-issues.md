---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Problemas de acesso e navegação"
breadcrumb:
  - "Benchmarking"
  - "Relatórios de benchmarking"
  - "Solução de problemas e perguntas frequentes"
source_path: "it-benchmarking/troubleshooting/access-navigation-issues.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Problemas de acesso e navegação

**O usuário não consegue ver o Benchmarking Interativo na navegação**

Sintoma  
: O usuário faz login no Frontdoor e não vê o aplicativo ou bloco Benchmarking. Caso contrário, o usuário pode estar tentando acessar o Benchmarking a partir do Costing ou de outro produto IBM Apptio por meio da navegação no aplicativo   
. Causas prováveis

- Benchmarking não provisionado para sua empresa
- A função do usuário não inclui acesso ao endpoint de benchmarking interativo
- A função do usuário não inclui a permissão “ViewInteractiveBenchmarksAndCostData”.
- Usuário no ambiente errado (por exemplo, “sandbox” em vez de “main”)

O que verificar

1. Confirme se o Benchmarking está provisionado para sua empresa.
2. Verifique quais funções incluem acesso ao Benchmarking Interativo e se o usuário possui uma delas.
3. Verifique se a função atribuída tem a permissão “ViewInteractiveBenchmarksAndCostData”.
4. Verifique se o usuário está conectado ao ambiente Frontdoor correto.

Resposta curta que você pode enviar:   
Você não vê o Benchmarking porque suas permissões de usuário não têm acesso a esse aplicativo neste ambiente. Assim que você receber a função correta, o aplicativo Benchmarking aparecerá na sua navegação.

**O usuário pode abrir o Cálculo de custos, mas não pode acessar os relatórios de Benchmarking.**

Sintoma  
: O usuário visualiza a página inicial do Cálculo de custos, mas alguns blocos ou relatórios específicos do Benchmarking estão ausentes ou apresentam erros. Causas   
prováveis:

- O usuário não tem acesso aos relatórios **de custos** subjacentes
- O relatório foi removido, renomeado ou movido
- O acesso baseado em função para esse relatório é mais restritivo
- Os componentes de benchmarking não foram instalados no projeto de Cálculo de Custos

O que verificar

1. Abra o relatório você mesmo para verificar se ele existe e funciona.
2. Confirme de qual projeto de cálculo de custos ele depende e se o usuário pode acessar esse projeto.
3. Verifique todas as permissões no nível do relatório ou da pasta.
4. Verifique se os componentes “IT Spend Benchmarks” e, se aplicável, “Infra Benchmarks” estão instalados.

Resposta curta que você   
pode enviar: Você pode acessar o Costing, mas sua função atual não tem acesso ou o relatório não está disponível. Assim que o acesso for concedido e o relatório estiver disponível, ele será exibido.
