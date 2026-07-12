---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Configurar várias moedas para a nuvem"
breadcrumb: []
source_path: "cost-transparency/configuration/multicurrency.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configurar várias moedas para a nuvem

Você pode ativar o suporte a várias moedas para os produtos do Apptio Cloud.

Aplica-se a: Cloud for Costing Standard em TBM Studio 12.4.1 e posterior; Apptio Cloud Business Management em TBM Studio 12.6 e posterior

## Introdução

Você pode ativar o suporte a várias moedas para os produtos do Apptio Cloud para fazer o seguinte:

- Converta notas na moeda base em seu projeto Apptio
- Exibir uma moeda de sessão nos relatórios

Para obter informações adicionais relacionadas ao recurso de várias moedas, consulte [Configurar várias moedas](../../studio/formulas-and-functions/functions/tablematch.html "Retorna um valor com base em uma tabela de regras que funciona como um conjunto de instruções IF. Cada linha da tabela de regras define uma regra. As condições na mesma linha são combinadas com AND, e os valores na mesma célula são tratados como condições OR.").

As instruções de configuração a seguir são específicas para a configuração dos arquivos de faturamento AWS e Azure para “ConvertToBase”.

Nota:

Para os produtos do Apptio Cloud, os valores da coluna Type nos dados que você carrega na tabela Currency Exchange devem ser rotulados como "Real" nos dados brutos para que o recurso de várias moedas funcione.

## Instruções para novos clientes

Para novos clientes, é necessária apenas uma etapa: Atualizar o Azure EA Detailed Bill Master Data.CurrencyCode com o código da moeda da fatura.

## Instruções para clientes existentes com CCM configurado

Faça as seguintes alterações:

## AWS Dados mestre da fatura de alocação de custos

Adicione as seguintes colunas:

- **Moeda base BlendedRate** =If(lookup( CurrencyCode,Currency Exchange,Currency Code,Type)="",BlendedRate,ConvertCurrencyToBase(BlendedRate,CurrencyCode,"Actual" ))
- **Moeda base CostBeforeTax** =If(lookup( CurrencyCode,Currency Exchange,Currency Code,Type)="",CostBeforeTax,ConvertCurrencyToBase(CostBeforeTax,CurrencyCode,"Actual" ))
- **Créditos de moeda base=If** (lookup( CurrencyCode,Currency Exchange,Currency Code,Type)="",Credits,ConvertCurrencyToBase(Credits,CurrencyCode,"Actual" ))
- **Base Currency TaxAmount=If** (lookup(CurrencyCode,Currency Exchange,Currency Code,Type)="",TaxAmount,ConvertCurrencyToBase(TaxAmount,CurrencyCode,"Actual" ))
- **Moeda base TotalCost** =If(lookup( CurrencyCode,Currency Exchange,Currency Code,Type)="",TotalCost,ConvertCurrencyToBase(TotalCost,CurrencyCode,"Actual" ))

Atualize o anexo nos dados mestre do provedor de serviços de nuvem:

Adicionar **Dados Mestres da Fatura de Alocação de Custos AWS** **TotalCost da Moeda Base)** aos **Data.Cost Mestres do Provedor de Serviços de Nuvem.**

## AWS RDS Dados mestre de compras do RI

Adicione as seguintes colunas:

- **Preço fixo da moeda base** =If(lookup(Currency Code,Currency Exchange,Currency Code,Type)="",Fixed Price,ConvertCurrencyToBase(Fixed Price,Currency Code, "Actual"))
- **Cobrança recorrente de moeda base** =If(lookup(Currency Code,Currency Exchange,Currency Code,Type)="",Hourly Recurring Charge,ConvertCurrencyToBase(Hourly Recurring Charge,Currency Code, "Actual"))
- **Preço de uso da moeda base** =If(lookup(Currency Code,Currency Exchange,Currency Code,Type)="",Usage Price,ConvertCurrencyToBase(Usage Price,Currency Code, "Actual"))

Modifique as seguintes colunas existentes:

- Efetivo UpFront Custo=Preço fixo da moeda base/((Prazo em Years\*31536000 )/Elapsed(Start,Expiration))
- Tarifa combinada = Tarifa inicial por hora + Tarifa recorrente na moeda base + Preço de uso na moeda base

Atualizar o anexo nos dados mestre das instâncias reservadas

- Anexar AWS RDS RI Purchases Master Data.Base Currency Recurring Charge into Reserved Instances Master Data.Recurring Charges
- Anexar AWS RDS RI Purchases Master Data.Base Currency Fixed Price into Reserved Instances Master Data.UpFront Cost

## AWS Dados mestre de compras do RI

Adicione as seguintes colunas:

- **Preço fixo da moeda base** =If(lookup(Currency Code,Currency Exchange,Currency Code,Type)="",Fixed Price,ConvertCurrencyToBase(Fixed Price,Currency Code, "Actual"))
- **Cobrança recorrente de moeda base** =If(lookup(Currency Code,Currency Exchange,Currency Code,Type)="",Hourly Recurring Charge,ConvertCurrencyToBase(Hourly Recurring Charge,Currency Code, "Actual"))
- **Preço de uso da moeda base** =If(lookup(Currency Code,Currency Exchange,Currency Code,Type)="",Usage Price,ConvertCurrencyToBase(Usage Price,Currency Code, "Actual"))

Modifique as seguintes colunas existentes:

- **Taxa de adiantamento por hora** =IF( RowCount(AWS RI Modifications Master Data)>0,Effective UpFront Cost/(Elapsed(Start,Expiration)/3600),((Base Currency Fixed Price/Term in Years)/8760))
- Tarifa **combinada** = Tarifa inicial por hora + Tarifa recorrente na moeda base + Preço de uso na moeda base
- **Upfront Price Helper** =if(Base Currency Fixed Price=0,SumIf(Parent,Reserved Instance ID,Base Currency Fixed Price)\*Footprint Weighting,Base Currency Fixed Price)

Atualize o anexo nos dados mestre das instâncias reservadas:

- Anexar AWS RI Purchases Master Data.Base Currency Recurring Charge into Reserved Instances Master Data.Recurring Charges
- Anexar AWS RI Purchases Master Data.Base Currency Fixed Price into Reserved Instances Master Data.UpFront Cost

## Recomendações Dados mestre

Reverta os seguintes conjuntos de dados de volta ao OOTB no componente Cloud - Recommendations:

Recomendações Conjunto de dados mestre

Se houver modificações existentes, faça as seguintes alterações:

- Adicionar nova coluna **Currency Code** = "USD"
- Modificar a **economia mensal estimada** =If(lookup(Currency Code,Currency Exchange,Currency Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency Code, "Actual"))

## Amazon EC2 Transformação de otimização de instâncias reservadas

**Custo inicial** alterado para o tipo = Numérico

## Otimização de instâncias reservadas do Amazon EC2 com prazo

Adicionar nova coluna Currency Code = "USD"

Modifique as seguintes colunas existentes:

- **Fatura estimada (RIs atuais)** =If(lookup(Currency Code,Currency Exchange,Currency Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency Code, "Actual"))
- **Fatura estimada (RIs atuais)\_|\_1** =If(lookup(Currency Code,Currency Exchange,Currency Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency Code, "Actual"))
- **Fatura estimada (RIs otimizadas)** =If(lookup(Currency Code,Currency Exchange,Currency Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency Code, "Actual"))
- **Fatura estimada (RIs otimizadas)\_|\_1** =If(lookup(Currency Code,Currency Exchange,Currency Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency Code, "Actual"))
- **Economia mensal estimada** =If(lookup(Currency Code,Currency Exchange,Currency Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency Code, "Actual"))
- **Estimativa mensal Savings\_|\_1** =If(lookup(Currency Code,Currency Exchange,Currency Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency Code, "Actual"))
- **Upfront Cost** =If(lookup(Currency Code,Currency Exchange,Currency Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency Code, "Actual"))
- **Upfront Cost\_|\_1=If** (lookup(Currency Code,Currency Exchange,Currency Code,Type)="",$\_,ConvertCurrencyToBase($\_,Currency Code, "Actual"))

## Azure EA Dados mestre detalhados da fatura

Adicione as seguintes colunas:

- **CurrencyCodeNOTE** Acrescente um valor a esse campo para definir a moeda de sua fatura Azure.
- **Moeda base ResourceRate** =If(lookup( CurrencyCode,Currency Exchange,Currency Code,Type)="",ResourceRate,ConvertCurrencyToBase(ResourceRate,CurrencyCode,"Actual" ))
- **BaseCurrency ExtendedCost** =If(lookup( CurrencyCode,Currency Exchange,Currency Code,Type)="",ExtendedCost,ConvertCurrencyToBase(ExtendedCost,CurrencyCode,"Actual" ))

Atualize o anexo nos dados mestre do provedor de serviços de nuvem:

Adicionar **Data.Base mestres de faturas detalhadas Azure EA. Moeda base ExtendedCost** aos **Data.Cost mestres do provedor de serviços de nuvem. Custo**

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
