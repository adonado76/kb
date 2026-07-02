---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Imposto sobre valor agregado"
breadcrumb:
  - "Planning"
  - "Planejamento de contratos"
source_path: "it-planning/planning/value-added-tax.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Imposto sobre valor agregado

Apptio O Planning suporta a modelagem do **imposto sobre valor agregado (IVA)** para itens de linha do contrato, permitindo que as organizações representem com precisão o total de despesas do contrato, incluindo ou excluindo impostos. O IVA é um imposto sobre o consumo aplicado a bens e serviços e, dependendo das políticas contábeis de sua organização, pode ser recuperável ou não recuperável.

Esse recurso permite que os usuários:

- Incluir o IVA como parte dos custos totais do contrato.
- Acompanhe o IVA separadamente do valor do contrato básico.
- Configure como o IVA deve ser calculado e exibido nos itens de linha do contrato.

## Conceitos-chave

**Quantia**

Representa o custo antes dos impostos do contrato ou do item de linha (por exemplo, taxa de assinatura de software, aluguel de hardware).

**Taxa de IVA**

Especifica a porcentagem de imposto aplicada ao valor base.

Exemplos:

- 0% - Não tributável
- 10% - Taxa reduzida de IVA (por exemplo, determinados serviços)
- 20% - Taxa padrão de IVA

**Valor com IVA**

Representa o custo total incluindo o IVA.

Calculado como: **Valor com IVA =** Valor + (Valor × Taxa de IVA)

## Como o IVA é calculado

O IVA é calculado com base no **local** selecionado em cada item de linha do contrato:

- Quando um item de linha de contrato é inserido e um **Local** é especificado,
- Apptio O Planning procurará **a taxa de IVA** na tabela de dados de referência,
- E calcular automaticamente o **valor com IVA** (calculado como: *Valor + (Valor × Taxa de IVA)* )
- O IVA não é amortizado - somente o valor original (antes do IVA) é usado para amortização.

Exemplo

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Nome do contrato** | **Valor do contrato** | **Taxa de IVA** | **Valor do IVA** | **Valor com IVA** |
| Licença de software | $10.000 | 20% | $2.000 | R$ 12.000 |
| Contrato de manutenção | $8.000 | 10% | $800 | R$ 8.800 |
| Serviços de consultoria | US$ 5.000 | 0% | $0 | US$ 5.000 |

## Configurar o imposto sobre valor agregado

Para ativar os cálculos de IVA, vá para **Configurações → Perfil da empresa** e ative a opção **Incluir imposto sobre valor agregado (IVA)**. A ativação dessa configuração criará automaticamente uma tabela de dados de referência de **taxas de IVA**.

**Etapas de configuração**

**Antes de importar as taxas de IVA**, certifique-se de que seus **dados de referência de local** incluam todos os locais relevantes onde o IVA deve ser aplicado.

1. Vá para **Settings** (ícone de engrenagem) **→ Company Profile**.
2. Ative **Include Value-Added Tax (VAT) (Incluir imposto sobre valor agregado** ) e clique em **Save and Exit (Salvar e sair** ).
3. Navegue até **Configuration → Reference Data → VAT Rates**.
4. Exportar o modelo e preencher os campos-chave:
5. **Localização** - O identificador de localização usado para determinar a taxa de IVA aplicável.
6. **Taxa de IVA** - A taxa de imposto a ser aplicada, inserida como um decimal (por exemplo, insira 0.20 para 20%).
7. Importar o CSV atualizado
8. Clique no **menu Elipses** e **publique** as alterações para que elas fiquem disponíveis para os planos.

**Aplicar IVA aos itens de linha do contrato**

Ao inserir ou importar dados do contrato:

1. Especifique o **valor** do contrato para cada item de linha.
2. Selecione um **local.**
3. A **taxa de IVA** é preenchida automaticamente com base em suas taxas de IVA configuradas.
4. Apptio O planejamento calcula automaticamente o **valor com IVA** **.**
