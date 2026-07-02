---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Dados ausentes ou incompletos"
breadcrumb:
  - "Benchmarking"
  - "Relatórios de benchmarking"
  - "Solução de problemas e perguntas frequentes"
source_path: "it-benchmarking/troubleshooting/missing-data.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Dados ausentes ou incompletos

**Gráficos ou tabelas inteiros estão em branco**

Sintoma  
: uma exibição é carregada, mas todos os valores da sua organização estão em branco.   
Causas prováveis

- Sem dados de custo ou perfil de TI para o ano selecionado
- A análise comparativa está indicando o ano errado ou o projeto de cálculo de custos
- As configurações do grupo de pares excluem sua organização ou ocultam a métrica
- Domínio (Setor/ OpEx /Infra) não totalmente habilitado

O que verificar

1. Confirme se o perfil da sua organização e os dados de custos existem para esse ano.
2. Verifique a configuração do Benchmarking para o ano ativo e o projeto de Cálculo de custos.
3. Relaxe os filtros (setor, tamanho, região) para ver se a métrica reaparece.
4. Confirme se o domínio relevante está habilitado e não está em estado de erro.

Resposta curta que você   
pode enviar: Este gráfico está em branco porque não há dados comparativos para nós no ano e grupo de pares selecionados. Assim que atualizarmos os dados subjacentes ou ajustarmos o grupo de pares, os valores serão exibidos.

**Algumas torres de recursos ou pools de custos estão com gastos em falta**

Sintoma  
: Você sabe que há gastos em determinadas torres de recursos ou pools de custos no cálculo de custos, mas eles não aparecem na comparação.   
Causas prováveis

- Esses custos são mapeados para torres de recursos personalizadas ou pools de custos que não estão alinhados com as categorias padrão do TBM
- A despesa está em um projeto de cálculo de custos que o Benchmarking não está usando
- O conjunto de dados de referência não suporta essa Torre de Recursos para o grupo de pares escolhido

O que verificar

1. Em Cálculo de custos, confirme se essas Torres de recursos/Pools de custos têm custo diferente de zero para o ano selecionado.
2. Verifique o mapeamento das estruturas locais para os pools de custos/torres de recursos padrão usados pela análise comparativa.
3. Verifique qual projeto de custeio o Benchmarking está configurado para usar e se os gastos estão nesse projeto.

Resposta curta que você pode enviar  
: A Torre de Recursos ou o Pool de Custos não estão sendo exibidos porque estão mapeados para uma categoria não padrão que não se alinha com a taxonomia de benchmark ou porque estão em um projeto de Cálculo de Custos que o Benchmarking não está usando. Depois de alinharmos o mapeamento e a fonte, isso será exibido nas visualizações de benchmark.

**As métricas de infraestrutura não aparecem, mas OpEx aparece.**

Sintoma: As   
visualizações de indústria e TI ( OpEx ) mostram dados, mas as visualizações de infraestrutura estão vazias.   
Causas prováveis

- Dados de volume ou capacidade ausentes para subtorres de recursos relacionadas à infraestrutura
- Subtorres de recursos não mapeadas corretamente para as definições de referência

O que verificar

1. Verifique os dados de custo **e** volume das subtorres de recursos de infraestrutura (servidores, armazenamento, rede, etc.).
2. Verifique as unidades (por exemplo, TB vs GB, servidores físicos vs virtuais).

Resposta curta que você pode enviar  
: Os benchmarks de infraestrutura ainda não estão disponíveis porque não concluímos o mapeamento de custos e volumes para as torres de recursos de infraestrutura. Assim que isso estiver pronto, as métricas de custo unitário da infraestrutura serão preenchidas.
