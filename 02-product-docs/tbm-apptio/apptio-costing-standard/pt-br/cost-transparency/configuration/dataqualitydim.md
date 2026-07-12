---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Faça o upload dos dados das Dimensões de Qualidade de Dados"
breadcrumb: []
source_path: "cost-transparency/configuration/dataqualitydim.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Faça o upload dos dados das Dimensões de Qualidade de Dados

Para preencher as pontuações de validade no relatório de qualidade Data Dimensions, carregue as quatro tabelas de dados: Validade da fonte de custos, Validade da mão de obra, Validade dos projetos e Validade do fornecedor.

Aplica-se a: Costing Standard em TBM Studio 12.0 e posterior

## Introdução

A validade mede a correspondência entre a fonte de custos, a mão de obra, os projetos e os dados do fornecedor e um conjunto de valores aceitos para os dados. Os valores aceitos são armazenados em quatro tabelas de dados mestre na categoria Dimensões de qualidade de dados:

- Validade da fonte de custos
- Validade do trabalho
- Validade dos projetos (se estiver rastreando os custos do projeto)
- Validade do fornecedor (se estiver rastreando os custos do fornecedor)

Para cada tabela de dados mestre, você carrega um único conjunto de dados que é anexado e mapeado para o conjunto de dados mestre correspondente. O conjunto de dados carregado deve conter colunas que possam ser mapeadas para as colunas apropriadas na tabela de dados mestre.

## Descrições da coluna Validade da fonte de custos

As colunas do conjunto de dados mestre Validade da fonte de custos estão descritas na tabela abaixo. As colunas são listadas na ordem em que aparecem no conjunto de dados. As colunas obrigatórias são marcadas com um asterisco ( \* ). Os valores possíveis válidos para uma coluna diferenciam maiúsculas de minúsculas.

As abreviações abaixo são usadas na coluna Tipo.

- A = Rótulo
- # = Numérico
- D = Data
- ID = Identificador exclusivo
- K = Campo-chave usado na alocação entre objetos do modelo

| Coluna | Tipo | Descrição |
| --- | --- | --- |
| Conta | A | O nome ou identificador da conta. |
| Centro de custos | A | Um departamento ou outra unidade em uma organização para a qual os custos diretos ou indiretos são alocados. |
| Proprietário do centro de custo | A | O proprietário do centro de custo. |
| Pool de custos | A | O nome do pool de custos. Valores válidos: Hardware, Software, Mão de obra, Serviços externos, Energia das instalações, Telecomunicações, Outros |
| Subgrupo de custos | A | Uma subcategoria de despesas do pool de custos. Por exemplo, o HW-Maintenance Support é um elemento do subgrupo de custos do pool de custos de Hardware. Valores válidos: Consultoria, Mão de obra externa, Instalações e energia, HW-Depreciação, HW-Despesa, HW-Aluguel, HW-Manutenção e suporte, Mão de obra interna, Outros, Prestadores de serviços, SW-Amortização, SW-Despesa, SW-Aluguel, SW-Manutenção e suporte, Telecom. |
| Tipo de Despesas | A | O driver de métrica do modelo de objeto Fonte de custo que é preenchido pelos dados desse item de linha - os valores possíveis são: CapEx, OpEx, CapEx Budget (Orçamento) e OpEx Budget (Orçamento). |
| Fixo Variável | A | Designa se o custo deve ser categorizado como custo fixo ou custo variável. Os valores válidos são: Fixed (fixo), Variable (variável). |
| Proprietário | A | A pessoa responsável pelo item de linha. |
| Válidos | # | Esse é um campo do sistema. Não insira um valor. |

## Descrições das colunas da Validade do Trabalho

As colunas do conjunto de dados mestre da Validade do Trabalho estão descritas na tabela abaixo. As colunas são listadas na ordem em que aparecem no conjunto de dados. As colunas obrigatórias são marcadas com um asterisco ( \* ). Os valores possíveis válidos para uma coluna diferenciam maiúsculas de minúsculas.

As abreviações abaixo são usadas na coluna Tipo.

- A = Rótulo
- # = Numérico
- D = Data
- ID = Identificador exclusivo
- K = Campo-chave usado na alocação entre objetos do modelo

| Coluna | Tipo | Descrição |
| --- | --- | --- |
| Tipo de funcionário | A | O tipo do recurso de mão de obra, como Pessoal externo ou Pessoal interno. |
| Identificação do trabalho | A | Um identificador exclusivo definido pelo usuário para o conjunto de dados do Labor. Essa coluna não deve ter valores duplicados. |
| Nome do trabalhador | A | O nome do recurso de trabalho, como John Smith. |
| Local | A | O local associado ao recurso de mão de obra. |
| Posição | A | O nome do cargo do funcionário position.For exemplo: Helpdesk, suporte, administrador de desktop, administrador de armazenamento. |
| Região | A | A região geográfica associada a esse recurso de mão de obra. |
| Válidos | # | Esse é um campo do sistema. Não insira um valor. |

## Projetos Descrições das colunas de validade

As colunas do conjunto de dados mestre de Validade de Projetos estão descritas na tabela abaixo. As colunas são listadas na ordem em que aparecem no conjunto de dados. As colunas obrigatórias são marcadas com um asterisco ( \* ). Os valores possíveis válidos para uma coluna diferenciam maiúsculas de minúsculas.

As abreviações abaixo são usadas na coluna Tipo.

- A = Rótulo
- # = Numérico
- D = Data
- ID = Identificador exclusivo
- K = Campo-chave usado na alocação entre objetos do modelo

| Coluna | Tipo | Descrição |
| --- | --- | --- |
| Iniciativa empresarial | A | Projetos ou programas específicos realizados para atingir objetivos específicos em curto prazo, como reduzir custos, aumentar a eficiência e melhorar o desempenho das vendas. |
| Patrocinador comercial | A | Indivíduo ou entidade que organiza e se compromete com o desenvolvimento de um produto, programa ou projeto. |
| Proprietário do projeto de TI | A | O proprietário do projeto. |
| ID de Projeto | A | Um identificador para o projeto. |
| Gestor de Projeto | A | O contato principal para esse projeto dentro da empresa. |
| Nome do Projeto | A | Um nome exclusivo para o projeto, como Oracle v9 Migration ou Virtualization Deployment. O nome do projeto é usado nos relatórios para decompor os custos. |
| Portfólio de projetos | A | Uma categorização de alto nível do projeto. Um portfólio pode conter um ou mais projetos. |
| Tipo de despesa | A | A categorização de investimento das despesas ou do orçamento de TI.  Os valores válidos geralmente são: Executar o negócio, Mudar o negócio e Transformar o negócio.  Valores válidos: **RTB**, **CTB** ou **TTB** |
| Válidos | # | Esse é um campo do sistema. Não insira um valor. |

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
