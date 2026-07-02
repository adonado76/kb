---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Configuração dos dados de custos"
breadcrumb:
  - "Benchmarking"
  - "Guia de configuração"
source_path: "it-benchmarking/configuration/cost-data-configuration.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Configuração dos dados de custos

## Conectando-se ao Cálculo de Custos

Os dados de custos indicam ao Interactive Benchmarking o que deve ser comparado. Você pode alimentá-lo diretamente a partir do Cálculo de Custos ou por meio de entrada manual.   
Nas configurações de benchmarking:

1. Integre-se à plataforma de custos selecionando “Transparência de custos”.
2. Valide a conexão.
3. Selecione o projeto de cálculo de custos principal que contém seus gastos reais com TI.
4. Selecione o período fiscal do ano fiscal que deve ser usado para seus benchmarks de referência.
5. Recuperar os dados.

![Conecte-se ao Cálculo de Custos](../../resources/images/it%20benchmarking_images/connect-to-costing.png)

Cheques:

- Confirme se o custo total de TI está alinhado com o orçamento financeiro para esse ano.
- Confirme se todas as principais Torres de Recursos têm valores diferentes de zero.
- Se algum valor estiver faltando ou você achar que merece ser substituído, insira os valores manualmente e salve-os antes de continuar.

**Entrada**  
 manual de custos Use a entrada manual apenas quando:

- Você não implementou um projeto de cálculo de custos ou ele não está disponível.
- Você está realizando um piloto com dados simplificados.
- Você está carregando dados de um modelo externo semelhante ao TBM.

Este método é adequado para começar, mas planeje integrá-lo com o IBM Apptio Costing se desejar um uso contínuo e controlado.

**Verifique as**   
configurações de moeda e ano fiscal. Certifique-se de que:

- A moeda utilizada para os custos e receitas de TI é a mesma.
- O período utilizado para a comparação é um ano fiscal completo, não um semestre ou um período misto.
- Se o Cálculo de Custos utilizar várias moedas, a conversão ocorre antes de os dados chegarem ao Benchmarking.

Nas configurações do Interactive Benchmarking, defina a moeda padrão.

![Configuração interativa de benchmarking – Moeda padrão](../../resources/images/it%20benchmarking_images/currency-fiscal-year.png)

## Grupos de custos TBM

O suporte ao Cost Pool está disponível até a versão 4 do TBM e anteriores. Os detalhes dos pools de custos aparecem na tabela abaixo:

Tabela 1.

| Pool de custos | Descrição |
| --- | --- |
| Mão de obra externa | Honorários de prestadores de serviços externos, viagens e despesas. |
| Instalações e energia | Espaço do centro de dados, energia, segurança e outras despesas operacionais. |
| Hardware | Despesas com hardware. |
| Mão de obra interna | Salários, benefícios, despesas e ocupação dos funcionários. |
| Outros | Despesas diversas ou não padronizadas. |
| Serviços externos | Provedores externos de serviços gerenciados. |
| Software | Despesas com software de compras de software não capitalizadas. |
| Telecomunicações | Despesas com conectividade de rede de voz e dados, incluindo despesas com circuitos e uso. |

Observação: O custo compartilhado de “Instalações e energia” é específico para instalações de data center. Exclui despesas com escritórios e outras instalações. Normalmente, as instalações do escritório devem ser atribuídas ao grupo de custos “Mão de obra interna”.
