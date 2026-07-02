---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Grupo de pares e métodos estatísticos"
breadcrumb:
  - "Benchmarking"
  - "Relatórios de benchmarking"
  - "Referência de dados e metodologia"
source_path: "it-benchmarking/data-and-methodology/peer-group-statistical-method.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Grupo de pares e métodos estatísticos

Os benchmarks não mostram organizações individuais. Eles mostram como é a distribuição dos pares.

## Construção de grupos de pares

Um grupo de pares é normalmente definido por:

- Indústria
- Faixa de tamanho (normalmente receita)
- Região ou geografia

Regras aplicadas em segundo plano:

- Tamanhos mínimos de amostra antes de uma métrica ser relatada
- Exclusão ou corte de valores extremos em alguns conjuntos de dados
- Anonimização que impede a identificação de colaboradores individuais

## Percentis e quartis

Estatísticas comuns:

- Mediana – o 50º percentil
- Quartil inferior – o percentil 25
- Quartil superior – o percentil 75
- Mínimo e máximo, às vezes com valores atípicos excluídos

Os gráficos geralmente representam:

- Mediana como linha ou ponto
- Intervalo interquartil como uma faixa ou caixa
- Sua organização como um marcador separado

Interpretação:

- Se você está próximo da mediana, você é típico
- Dentro da faixa, você está dentro de um intervalo normal
- Fora da banda, você é estruturalmente diferente e deve saber por quê

  ![Gráfico de caixa de benchmarking interativo](../../resources/images/it%20benchmarking_images/indistry-specific-distribution.png)

## Arquétipos

Arquétipos são padrões derivados do agrupamento de organizações com base na sua estrutura de gastos.

Tipos suportados com dados de benchmarking interativo:

- **Centrado na tecnologia de hardware:** Um modelo operacional de tecnologia em que a entrega depende fortemente da infraestrutura própria ou gerenciada diretamente. As características típicas incluem:
  - Maior espaço físico no local ou em colocation, mais infraestrutura física para operar.
  - Mais gastos com plataformas de infraestrutura e pilhas de tecnologia subjacentes.
  - Frequentemente, operações mais gerenciadas internamente (ou pelo menos propriedade do hardware), mesmo que parte da mão de obra seja terceirizada.
- **Centrado em tecnologia de software:** Um modelo operacional de tecnologia em que a entrega depende fortemente de plataformas de software, ferramentas e licenças, em vez de hardware próprio. As características típicas incluem:
  - Maior uso de assinaturas de plataformas de software como serviço ( SaaS, ), ferramentas de automação e pacotes de software empresarial.
  - A infraestrutura pode ser abstraída (nuvem ou gerenciada), tirando a ênfase da propriedade do hardware.
  - Mais gastos com segurança, observabilidade, ITSM, colaboração, plataformas de desenvolvimento e aplicativos empresariais.
- **Centrado no fornecedor:** Um modelo operacional de tecnologia em que grande parte do trabalho é realizado por terceiros. As características típicas incluem:
  - Serviços gerenciados pesados, integradores de sistemas, parceiros de terceirização e prestadores de serviços.
  - As equipes internas se concentram mais em governança, arquitetura, gestão de fornecedores e propriedade do produto.
  - A capacidade de entrega é dimensionada pelos fornecedores mais do que pela contratação.
- **Centrado nas pessoas:** Um modelo operacional de tecnologia em que a capacidade é fornecida principalmente por funcionários internos. As características típicas incluem:
  - Equipes internas maiores de engenharia e operações.
  - Forte responsabilidade interna pelas atividades de entrega e execução.
  - Podem existir fornecedores, mas as equipes internas realizam a maior parte do trabalho.

Casos de uso:

- Compreender a que padrão geral a sua organização se assemelha.
- Explicar que você parece diferente da média porque segue intencionalmente um arquétipo diferente.

![Gráficos de radar arquetípicos que aparecem no relatório "Industry & OpEx Benchmarks" em Custos.](../../resources/images/it%20benchmarking_images/archetype-radar-chart.png)
