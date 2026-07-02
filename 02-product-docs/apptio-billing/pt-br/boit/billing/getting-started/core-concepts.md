---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Conceitos fundamentais: serviços, unidades, taxas, recuperação, diários"
breadcrumb:
  - "Billing"
  - "Introdução"
  - "Introdução ao faturamento"
source_path: "boit/billing/getting-started/core-concepts.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Conceitos fundamentais: serviços, unidades, taxas, recuperação, diários

O restante deste guia baseia-se em um pequeno conjunto de conceitos recorrentes. Compreendê-los aqui reduz a confusão mais tarde.

## Serviços, produtos e ofertas

O faturamento precisa de algo **para ser faturado**. Isso é normalmente modelado como um catálogo de serviços ou produtos.

Padrões comuns:

- **Serviço** : Uma oferta de tecnologia consumida por unidades de negócios (por exemplo, “E-mail e colaboração”, “Banco de dados gerenciado”, “Servidor virtual”).
- **Produto** : Uma oferta de tecnologia padronizada, geralmente com versões, níveis ou pacotes definidos.
- **Oferta** : Um termo genérico para qualquer item faturável que possa ser apresentado em uma linha da fatura.

Cada oferta geralmente tem:

- Um **nome** reconhecido pelos stakeholders do setor empresarial.
- Uma **unidade de medida** (por exemplo, GB por mês, usuário por mês, VM por mês).
- Uma ou mais **taxas** e **fatores** utilizados para calcular os encargos.

No Billing Essentials, as ofertas são normalmente gerenciadas por meio de tabelas e relatórios que definem quais itens são faturáveis e a que taxa.

No Padrão de Faturamento, as ofertas são frequentemente mapeadas em vários domínios (serviços, aplicativos, infraestrutura, nuvem, projetos) para uma análise mais detalhada.

## Unidades e consumo

Uma **unidade** é a quantidade mensurável de uma oferta consumida em um período:

- Número de usuários.
- Capacidade de armazenamento.
- Horas de CPU.
- Bilhetes tratados.
- Horas ou pontos do projeto.

**O consumo** é o registro dessas unidades por consumidor e período. O faturamento depende de:

- **Chaves** consistentes (por exemplo, consumidor, período, oferta).
- Um **intervalo de tempo** (normalmente mensal).
- Mapeamento claro para o catálogo de ofertas faturáveis.

Conceitualmente:

Unidades × Taxa = Cobrança para uma determinada oferta, consumidor e período.

**Taxas e métodos de precificação**

Uma **taxa** é o valor cobrado por unidade. As taxas podem ser definidas de várias maneiras:

- **Baseado no custo** : Defina como igual ao custo unitário do Cálculo de custos.
- **Custo mais** : Adicione uma margem de lucro ou uma porcentagem de despesas gerais.
- **Baseado no preço** : use um preço definido que pode ser superior ou inferior ao custo.
- **Baseado no orçamento** : defina taxas para recuperar um orçamento alvo em vez do custo atual.
- **Híbrido** : Combine abordagens, por exemplo, com base no custo para alguns serviços e com base no preço para outros.

O Billing Essentials concentra-se na classificação direta PxQ e nos ajustes básicos.

O Padrão de Faturamento suporta cenários de tarifas mais complexos e análises de tarifas específicas do domínio (por exemplo, visualizações de tarifas unitárias por tipo de infraestrutura ou serviço em nuvem).

## Consumidores e estorno vs. showback

Um **consumidor** é a entidade que recebe a fatura:

- Unidade de negócios ou função.
- Região ou geografia.
- Centro de custos ou departamento.
- Projeto ou linha de produtos, dependendo do design.

O faturamento suporta ambos:

- **Showback** : Fornecer visibilidade das despesas sem transferência financeira real.
- **Estorno** : Registrar cobranças em sistemas financeiros e tratá-las como receita e despesa internas.

A mesma configuração de faturamento pode suportar showback, chargeback ou uma combinação de ambos, dependendo de como os diários são usados e quais acordos existem com o departamento financeiro.

## Contas, diários e arquivos

As saídas de faturamento geralmente se enquadram em três categorias:

- **Contas / Faturas**
  - Visualizações detalhadas ou resumidas das cobranças por oferta, consumidor e período.
  - Utilizado por unidades de negócios e proprietários de serviços ou produtos para compreender e discutir cobranças.
- **Diários**
  - Dados estruturados que representam a visão contábil das cobranças.
  - Utilizado pelo departamento financeiro para lançar entradas no livro razão ou em outros sistemas financeiros.
- **Archives**
  - Instantâneos dos resultados de faturamento para um determinado período.
  - Utilizado para auditoria, conformidade e análise histórica.

O Billing Essentials concentra-se em visualizações no estilo de faturas, tabelas mestre de faturamento simples e arquivos.

O padrão de faturamento adiciona camadas de visualizações específicas do domínio e análises de variação além desses fundamentos básicos.
