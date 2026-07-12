---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Administração de Projetos"
breadcrumb:
  - "TBM Studio"
  - "Administração"
source_path: "studio/new-uc/admin/project-admin.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Administração de Projetos

**Tipo de conteúdo:** Conceitual / Guia prático

**Público-alvo:** Administradores, usuários avançados

**Pré-requisitos:** função de administrador ou usuário avançado, acesso à guia Projeto

A administração de projetos abrange todas as atividades relacionadas à criação, configuração e manutenção de projetos no TBM Studio. Isso inclui criar projetos, definir configurações de horário, gerenciar configurações em todo o domínio e estabelecer políticas de governança.

## Entendendo os projetos

Os projetos são a unidade organizacional básica no TBM Studio. Um projeto reúne conjuntos de dados, métricas, modelos e relatórios em um espaço de trabalho integrado. Cada projeto tem sua própria configuração, ajustes de tempo e permissões de usuário.

**Principais características do projeto:**

- Os projetos contêm todas as tabelas de dados, transformações, objetos de modelo, métricas e relatórios
- Cada projeto possui configurações de tempo independentes, que definem o calendário fiscal e os períodos ativos
- Os projetos podem ser baseados em modelos padrão (Modelo de Cálculo de Custos) ou em configurações personalizadas
- É possível ter vários projetos dentro de um único domínio
- Só é possível ter um projeto aberto por vez no aplicativo

**Observação:** *Somente administradores do sistema podem criar ou excluir projetos. Entre em contato com o administrador do sistema do Apptio caso precise criar um novo projeto ou excluir um projeto existente.*

## Configurando as definições do projeto

As configurações do projeto controlam o comportamento em nível de projeto no que diz respeito a cálculos, formatação e apresentação. Acesse as configurações do projeto na guia Projeto clicando em Configurações do projeto no grupo Configuração do projeto.

**Configurações principais do projeto:**

|  |  |
| --- | --- |
| **Configuração** | **Descrição** |
| **Moeda base** | Moeda padrão para exibir valores nos relatórios. Os usuários podem alterar essa configuração em seu perfil. |
| **Localidade** | Define os formatos de números, moedas e datas utilizados em todo o projeto. |
| **Compactação de números** | Abreviaturas para milhares (K), milhões (M), bilhões (B) e trilhões (T). |
| **Versão dos componentes** | Especifica qual versão do conteúdo deve ser usada para atualizações e instalações de componentes. |
| **Cálculo automático** | Quando ativada, a aplicação atualiza automaticamente os documentos após o check-in. Desative esta opção em projetos grandes para melhorar o desempenho. |
| **Descrições obrigatórias para o check-in** | Exige que os usuários insiram uma descrição a cada check-in. Recomendado para registros de auditoria. |

**Dica:** *Para projetos com bancos de dados grandes cujos cálculos demoram bastante tempo, desative o cálculo automático e permita que os usuários acionem manualmente as atualizações quando necessário.*

## Configurando as definições de hora

As configurações de data e hora definem o seu calendário fiscal, controlam quais períodos estão ativos e determinam quais períodos de dados os usuários veem por padrão. A configuração correta das definições de hora é fundamental para a precisão dos relatórios e para um desempenho ideal.

**Para configurar as definições de hora:**

1. Vá para **Projeto > Configurações de tempo**.
2. Configure a definição do exercício fiscal (calendário gregoriano, 13 períodos ou variante personalizada 4-5-4).
3. Defina as datas de início e término do projeto para definir o período de cálculo.
4. Configure o período padrão que os usuários verão ao abrir relatórios.
5. Defina períodos encerrados para impedir alterações nos dados de períodos finalizados.

**Aviso:** *Depois de ativar o registro de horas para um projeto, não é possível desativá-lo. A data de início do projeto não pode ser alterada após a configuração inicial. Planeje cuidadosamente suas configurações de tempo antes de confirmar.*

**Melhores práticas para configurações de hora**

- Defina o período padrão como o mês mais recente totalmente encerrado para garantir que os usuários vejam dados validados.
- Fechar os períodos assim que os dados forem validados, para evitar alterações acidentais.
- Limite as datas de início e término do projeto apenas aos períodos necessários para melhorar o desempenho dos cálculos.
- Atualize o período padrão após a conclusão de cada fechamento mensal.

## Configurações do domínio

As configurações de domínio controlam as configurações gerais do ambiente, que se aplicam a todos os projetos na sua instância do Apptio. Acesse as configurações de domínio na guia Projeto clicando em Configurações de domínio.

**As principais configurações do domínio incluem:**

- **Projeto padrão** - O projeto que é aberto quando os usuários fazem login sem especificar um projeto
- **Serviço Multimoeda** - Gestão centralizada de câmbio em todos os produtos d Apptio
- **Serviço de Calendário Fiscal** - Definições de calendário fiscal compartilhadas entre produtos

## Ativação de recursos opcionais

O TBM Studio oferece vários recursos opcionais que podem ser ativados de acordo com as necessidades da sua organização. Acesse essas opções na guia Projeto clicando em Ativar recursos.

|  |  |
| --- | --- |
| **Funcionalidade** | **Descrição** |
| Gerenciamento de prioridades do Calc | Priorize os cálculos entre projetos com base na importância ou na urgência |
| Gestão de Cálculos | Ativar/desativar cálculos de preparação no nível do projeto |
| Publicação recorrente | Programar a publicação automática de dados de tabelas editáveis para transformações |
| Mostrar documentos não utilizados | Identifique tabelas, métricas e relatórios que não são utilizados em nenhuma parte do projeto |
| Mostrar painel de anomalias | Detecção de anomalias na exibição para padrões de cálculo incomuns |
| Interface do usuário do Apex | Ative a experiência de interface de usuário modernizada |
