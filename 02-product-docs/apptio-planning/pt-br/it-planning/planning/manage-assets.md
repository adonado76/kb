---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Visão geral do planejamento de ativos"
breadcrumb:
  - "Planning"
  - "Planejamento de ativos"
source_path: "it-planning/planning/manage-assets.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Visão geral do planejamento de ativos

O módulo Asset Planning permite orçar, prever e gerenciar investimentos de capital em ativos fixos. Os ativos fixos são recursos tangíveis de longo prazo, como servidores, hardware ou equipamentos, que uma empresa possui e usa durante vários anos. Esses ativos são capitalizados e depreciados ao longo do tempo, em vez de serem contabilizados imediatamente como despesas.

Com o Planejamento de Ativos, você pode:

- Acompanhe **as compras no site CapEx** e a transição para a **depreciação no site OpEx** assim que os ativos forem colocados em serviço.
- Modelar o **ciclo de vida completo do ativo** - desde a aquisição até a depreciação, manutenção e aposentadoria.
- Alocar **despesas de depreciação** por departamento ou centro de custo para obter relatórios financeiros precisos.
- Aplicar **regras e métodos de depreciação** para prever impactos de custo de longo prazo em períodos futuros.

## Configurar planejamento de ativos

Observação: São necessárias as funções de administrador ou proprietário do processo orçamentário.

**Habilitar ativos**

- Verifique se o recurso **Assets** está ativado em: **Configurações** (ícone de engrenagem) **→ Perfil da empresa**.

**Dados de referência de classe de ativos**

A classe de ativos é uma dimensão fundamental que controla como as aquisições e a depreciação são tratadas.

- Vá para **Configuration → Reference Data → Asset Class**.
- Você pode exportar um modelo: **Menu de três pontos→** **Exportar modelo**.
- Preencher ou atualizar colunas no arquivo.csv:
- **Classe de ativos** - Nome da categoria de ativos. Deve ser exclusivo.
- **Conta de depreciação** - OpEx conta usada para depreciação.
- **Conta de compra** - CapEx conta usada para aquisição de ativos.
- **Método de depreciação** - Selecione o método usado para depreciar o ativo. (por exemplo, Linha Reta, Declínio Duplo ou Saldo Declínio). Consulte Métodos de depreciação para obter mais detalhes.
- **Vida útil do ativo (meses)** - Vida útil do ativo em meses
- **Valor residual %** - A taxa do custo original do ativo que se espera que permaneça no final de sua vida útil (também conhecido como valor residual). Digite como um decimal - por exemplo, 1 = 100%, 0.1 = 10%.
- **Taxa de saldo %** - A taxa para depreciar o ativo. Usado para o método de saldo decrescente. Digite como um decimal - por exemplo, 1 = 100%, 0.1 = 10%.
- Importe o arquivo atualizado e **publique**.

## Entrada e gerenciamento de itens do imobilizado

- Abra seu plano e navegue até a guia **Assets (Ativos** ) na página **Expenses (Despesas)**.
- Adicione um novo ativo:
- Usando a **linha vazia** na parte inferior da tabela, ou
- **Clique com o botão direito do mouse** e selecione **Inserir linha**
- Insira os seguintes detalhes para cada ativo:
- **Classe do ativo -** Selecione a categoria que define como o ativo será capitalizado e depreciado. Isso determina as regras e contas de depreciação padrão.
- **Centro de custos -** Escolha o centro de custos que será financeiramente responsável pelo custo e pela depreciação do ativo.
- **Fornecedor** (opcional) - Especifique o fornecedor ou vendedor associado à compra do ativo. Isso é opcional, mas útil para relatórios
- **Método de depreciação** - A regra de depreciação que determina como o custo do ativo é debitado ao longo do tempo. Isso é atribuído automaticamente com base na classe de ativos, mas pode ser substituído manualmente, se necessário.
- **Data de compra -** A data em que o ativo foi adquirido ou capitalizado.
- **Data de entrada em serviço -** A data em que o ativo se torna operacional. A depreciação começa a partir dessa data.
- **Preço de compra -** O custo de capital do ativo que está sendo comprado. Esse valor é usado para calcular a depreciação e o impacto financeiro total.
- **Quantidade -** o número de unidades de ativos que estão sendo compradas.

Depois de inserido, o Apptio Planning gerará automaticamente o cronograma de depreciação com base nas entradas de ativos e no método de depreciação. Você verá os valores de depreciação distribuídos nas colunas de período de tempo.

Na guia **Summary (Resumo** ), o Apptio Planning cria duas entradas financeiras automaticamente:

- Uma **entrada de compra** usando a *conta de compras* configurada
- Uma **entrada de depreciação** usando a *conta de depreciação* configurada

## Depreciação cobrada em um centro de custo diferente

Se a despesa de depreciação tiver que ser atribuída a um centro de custo diferente daquele que possui o ativo, você poderá usar o campo **Centro de custo de depreciação**. Isso redireciona o custo de depreciação para um centro de custo alternativo.

Isso é útil em cenários como quando um ativo é comprado por um centro de custo de projeto, mas a manutenção contínua é financiada por um centro de custo diferente.

Nesse caso, o ativo continua pertencendo ao centro de custo original, enquanto a depreciação é cobrada em outro lugar.
