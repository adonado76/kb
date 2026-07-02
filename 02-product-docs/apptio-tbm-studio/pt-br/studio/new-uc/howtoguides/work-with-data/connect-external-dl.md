---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Conectar-se a fontes de dados externas ( DataLink )"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Trabalhar com dados"
  - "Importação e gerenciamento de dados"
source_path: "studio/new-uc/howtoguides/work-with-data/connect-external-dl.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Conectar-se a fontes de dados externas ( DataLink )

**Objetivo:** Configurar a integração automatizada de dados entre o TBM Studio e sistemas externos utilizando conectores d DataLink, a fim de eliminar o envio manual de arquivos.

**Quando utilizar este procedimento:** Utilize o ` DataLink ` quando precisar:

- Automatizar carregamentos regulares de dados (diários, semanais, mensais)
- Acesse ServiceNow para a troca de dados sobre o custo total de propriedade (TCO) da aplicação
- Extrair dados de sistemas corporativos sem intervenção manual
- Manter fluxos de dados consistentes sem a necessidade de preparar arquivos manualmente

**Pré-requisitos:**

- Acesso de administrador ao TBM Studio e ao DataLink
- Credenciais para a fonte de dados externa (banco de dados ServiceNow,, etc.)
- Para a aplicação TCO do ServiceNow: Apps & Services instalada (versão de Quebec, Paris ou Orlando)
- Para uploads via API: autenticação da API configurada (consulte a seção 3.5.1 )

**Tempo estimado:** 20 a 30 minutos para a configuração inicial; 5 minutos para alterações na programação

## Passos

## Parte 1: Preparar o TBM Studio (Integração com o ServiceNow )

1. **Configurar relatórios de TCO no TBM Studio:** Crie os relatórios que enviarão dados para ServiceNow,, incluindo o relatório de TCO da aplicação (com composição do pool de custos) e o TCO da aplicação (com composição da torre de recursos de TI).
2. **Configure as colunas obrigatórias** nos seus relatórios:
   - **Modelo de custo:** definido como “Cálculo de custos de aplicações empresariais”
   - **Período fiscal:** Use a fórmula = "FY" & CurrentDate("YY" ) & "&"Q" & gettimeoffset("Quarter", "Start", "Year") + 1
   - **Aplicação de negócios:** Nome da aplicação (deve corresponder à tabela `cmdb\_ci\_business\_app` d ServiceNow )
   - **Valor:** Use a fórmula = QuarterToDate(Cost )
3. **Obter os URIs da API dos relatórios:** acesse cada relatório, clique com o botão direito do mouse, selecione “**Mostrar URI da API** ” e copie o URL no formato JSON.

## Parte 2: Configurar uma conexão com o DataLink

1. **Crie uma nova conexão:** Abra o DataLink,, clique em “**Nova conexão** ”, digite um nome para a conexão e clique em “**Avançar** ”.
2. **Selecione o conector:** escolha **o conector “ ServiceNow Apps & Services TCO Egress”** e clique em “**Avançar** ”.
3. **Selecione um agente:** escolha entre o agente baseado na nuvem (hospedado em Apptio, configuração mais rápida) ou o agente local (melhor desempenho para dados locais).
4. **Configurar a autenticação:**

Selecione o tipo de autenticação: Básica (nome de usuário/senha) ou OAuth 2.0 (baseada em token, apenas para agentes na nuvem)

**Para a autenticação básica:**

- Digite ServiceNow seguido de URL (por exemplo, https://. {instance}. service-now.com )
- Digite seu nome de usuário e senha

**Para autenticação OAuth 2.0 :**

- Primeiro, registre DataLink como um aplicativo cliente em ServiceNow
- Insira a autorização URL, o token URL, o ID do cliente e o segredo do cliente
- Especifique o escopo (LEITURA e GRAVAÇÃO ou apenas LEITURA)
- Clique em **“Obter token de acesso”**
  1. **Insira os detalhes do relatório:** selecione o host BIIT, selecione os relatórios, cole os URLs dos relatórios (formato JSON) e selecione o período.
  2. **Programe a conexão:** escolha “Programar por horário” (dias/horários específicos) ou “Programar por evento” (executar após a conclusão de outra conexão).
  3. **Teste a conexão:** execute a conexão manualmente para verificar a configuração, verifique se há erros nos registros e confirme se os dados aparecem em ServiceNow.

## Resultados esperados

- DataLink A conexão foi autenticada com sucesso no sistema externo
- Os dados são transferidos automaticamente entre os sistemas de acordo com o cronograma
- Os dados estão disponíveis nas tabelas do TBM Studio para uso em modelos e relatórios
- Os dados de TCO do ServiceNow: aparecem nos painéis do ServiceNow

## Problemas comuns e solução de problemas

**Problema:** Falha na autenticação

**Solução:** Verifique as credenciais, obtenha novamente o token d OAuth, caso tenha expirado, e certifique-se de que a conta de serviço possui as permissões necessárias em ambos os sistemas.

**Problema:** A conexão está ativa, mas não aparecem dados

**Solução:** Verifique se a URI da API do relatório está no formato JSON e foi copiada corretamente; verifique se o período selecionado contém dados; analise os registros do DataLink.

**Problema:** A conexão agendada não é executada

**Solução:** Verifique as configurações da programação, verifique o status do agente; no caso de programações baseadas em eventos, certifique-se de que a conexão de acionamento tenha sido concluída.

## O que vem a seguir

- Monitorar a atualidade dos dados: Configure alertas para dados ausentes ou atrasados (Seção 6.4 )
- [Transformar dados integrados](transform-enrich-data.html) : aplicar transformações para padronizar os dados (Seção 3.1.2 )
- Programar compilações coordenadas: Alinhar os cálculos do modelo com os cronogramas de integração (Seção 6.1 )

**Tópico principal:** [Importação e gerenciamento de dados](../../../../studio/new-uc/howtoguides/work-with-data/data-import-mgmt.html)
