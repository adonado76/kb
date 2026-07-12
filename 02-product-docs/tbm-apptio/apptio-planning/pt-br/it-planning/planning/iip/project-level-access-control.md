---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Permissões de projeto"
breadcrumb:
  - "Planning"
  - "Planejamento de projetos"
source_path: "it-planning/planning/iip/project-level-access-control.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Permissões de projeto

Importante: *Disponível com a* *assinatura* ***do Apptio Planning Standard***.

Lembre-se: *o recurso de Planejamento Integrado de Investimentos (IIP) está ativado.*

O Planejamento Integrado de Investimentos (IIP) oferece suporte a diferentes modelos de propriedade orçamentária em todas as organizações. Como as estruturas de orçamento operacional e de projetos variam, Apptio o Planning oferece **controles de acesso** flexíveis em nível de projeto que se alinham à hierarquia organizacional, ao modelo de responsabilidade de custos e ao fluxo de trabalho de planejamento.

Este guia descreve casos de uso comuns de planejamento de projetos e explica como configurar permissões no nível do projeto usando **Projetos → Permissões** e **Permissões de Objetos de Custo**.

## Caso de uso 1: Os gerentes de projeto são responsáveis por todos os custos do projeto (departamentos dedicados a projetos)

**Visão geral**

Usado quando cada projeto tem seu próprio centro de custos dedicado e é theProjectManageris o único responsável por todos os custos desse projeto.

**Meta**

Os gerentes de projeto planejam e gerenciam todas as despesas dos projetos sob sua responsabilidade.

**Estrutura organizacional**

- Os projetos têm centros de custos dedicados que se reportam a um “Departamento de Projetos” distinto
- Os responsáveis pelo orçamento do projeto são distintos dos responsáveis pelo orçamento operacional do departamento.

**Requisitos de acesso**

- Os gerentes de projeto podem visualizar/editar apenas os departamentos de seus projetos.
- Os gerentes de projeto podem inserir os gastos diretamente nos centros de custo do projeto.
- Os gerentes de projeto podem enviar orçamentos para aprovação.

**implementação**

- Atribua aos gerentes de projeto a função de proprietário do centro de custos (ou equivalente) no Frontdoor.
- Conceda acesso de edição aos centros de custo do projeto usando as permissões de objeto de custo.
- Use “departamentos de consolidação de projetos” para separar as finanças exclusivas do projeto.

**Resultado**

- Os gerentes de projeto podem inserir os custos do projeto dentro do departamento ao qual estão atribuídos.
- O acesso continua restrito aos departamentos específicos do projeto.

## Caso de uso 2: Proprietários de centros de custo gerenciam custos operacionais e de projetos

**Visão geral**

Usado quando um único responsável pelo orçamento gerencia as despesas operacionais e de projetos do seu departamento.

**Meta**

Os responsáveis pelos centros de custo gerenciam todos os gastos — operacionais e de projetos — em seus departamentos.

**Estrutura organizacional**

- Sem personas separadas; os proprietários dos centros de custos são responsáveis por todos os custos.
- Os projetos podem atribuir custos a qualquer centro de custos.

**Requisitos de acesso**

- Os proprietários podem visualizar/editar apenas seus próprios departamentos.
- Os proprietários podem enviar orçamentos por meio do fluxo de trabalho padrão.

**implementação**

- Atribua aos proprietários do centro de custos a função **de proprietário do centro de custos**.
- Conceda permissões de edição aos departamentos relevantes por meio **das Permissões de Objeto de Custo**.
- Habilite a opção "Permitir qualquer centro de custo" nos projetos se for necessária uma alocação entre departamentos.

**Resultado**

- Uma única pessoa é responsável por todas as atividades relacionadas ao orçamento.
- Acesso total às despesas operacionais e de projetos em nível departamental.

**Limitação**

- Não é possível restringir um proprietário de centro de custos apenas às despesas do projeto. Eles verão todas as despesas do seu departamento.

## Caso de uso 3: Modelo híbrido — Proprietários de departamento + gerentes de projeto (custos compartilhados do projeto)

**Visão geral**

Utilizado quando os gerentes de projeto contribuem com as despesas do projeto para os departamentos, enquanto os proprietários dos departamentos permanecem responsáveis pelas despesas operacionais e pela aprovação das alocações do projeto.

**Meta**

- Os responsáveis pelos departamentos planejam as despesas operacionais e aprovam as alocações dos projetos.
- Os gerentes de projeto inserem apenas as despesas do projeto em todos os departamentos.

**Estrutura organizacional**

- Tanto os Departamentos como os Projetos têm centros de custo.
- Os gerentes de projeto alocam os gastos a qualquer centro de custo permitido.
- Os responsáveis pelos departamentos aprovam as alocações de projetos dentro de seus departamentos.

**Requisitos de acesso**

- **Proprietários de departamento:** acesso total a todas as despesas em seus departamentos.
- **Gerentes de projeto:** restritos a visualizar/editar apenas as despesas dos projetos que lhes foram atribuídos.
- Ambas as personas devem ver apenas os dados relevantes do projeto/departamento.

**implementação**

- Atribua aos proprietários do centro de custos a função **de proprietário do centro de custos**.
- Conceda permissões de edição aos departamentos relevantes por meio **das Permissões de Objeto de Custo**.
- Atribua aos gerentes de projeto a função **de gerente de projeto IIP** ou a função **de gerente de portfólio IIP**. Os gerentes de portfólio do IIP podem gerenciar a lista de projetos e as permissões dos projetos.
- Habilite a opção "Permitir qualquer centro de custo" nos projetos se for necessária uma alocação entre departamentos.

**Resultado**

- Os proprietários do departamento visualizam todas as despesas (projeto + operacionais).
- Os gerentes de projeto veem apenas as linhas em que **Projeto = projeto atribuído**.
- Os gerentes de projeto podem adicionar/editar/excluir despesas do projeto.
- Os responsáveis pelos departamentos continuam a apresentar os orçamentos.

**Limitações**

- O acesso do gerente de projeto é sempre filtrado para despesas exclusivas do projeto.

## Funções e permissões do projeto

**Funções padrão:**

- **Gerente de Portfólio IIP**
  - Acesso para editar/visualizar todo o portfólio do projeto.
  - Pode gerenciar permissões no nível do projeto.
- **Gerente de Projetos do IIP**
  - Edite/visualize apenas as despesas dos projetos atribuídos.

    |  |  |
    | --- | --- |
    | **Permissão** | **Descrição** |
    | **IIPProjectExpenseEdit** | Visualizar/editar despesas apenas para projetos atribuídos. |
    | **IIPProjectPermissionManage** | Gerencie as permissões em Projetos → Permissão. |
    | **IIPProjectManage** | Criar e excluir projetos. |

Os usuários precisam de permissões tanto em Permissões de projetos quanto em Permissões de objetos de custo:

|  |  |
| --- | --- |
| **Área de permissão** | **Por que é necessário** |
| **Projetos** → **Permissão** | Determina quais projetos o usuário gerencia. |
| **Permissão de objeto de custo** | Controla o acesso aos departamentos onde esses custos do projeto são acumulados. |
