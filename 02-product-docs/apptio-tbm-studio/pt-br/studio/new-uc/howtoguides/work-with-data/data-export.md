---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Exportação de dados"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Trabalhar com dados"
source_path: "studio/new-uc/howtoguides/work-with-data/data-export.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Exportação de dados

**Tipo de conteúdo:** Guia prático

**Público-alvo:** equipes de TI e finanças, administradores, desenvolvedores

**Tempo de execução:** 30 a 45 minutos (varia de acordo com o método)

**Pré-requisitos:** Acesso ao TBM Studio com as permissões adequadas; familiaridade com os conceitos básicos do Data Studio (consulte a seção 3.1.1 )

## Visão geral

O TBM Studio oferece recursos robustos para exportar seus dados de custos do sistema para ferramentas externas, como data warehouses, plataformas de inteligência de negócios e aplicativos personalizados. Esta seção aborda dois métodos principais para exportação de dados:

- [Tabelas publicadas](htg-config-pt.html) : conjuntos de dados pré-configurados e com esquema estável, projetados para extração programada por sistemas externos
- [Acesso à API](htg-api.html) : recuperação programática de dados para integrações personalizadas e automação

Saber quando utilizar cada método garante que você implemente a estratégia de exportação de dados mais eficiente e fácil de manter para a sua organização.

## Escolhendo o método de exportação

Antes de iniciar a configuração, determine qual método de exportação é o mais adequado para o seu caso de uso. A decisão depende dos usuários dos seus dados, dos requisitos de atualização e das capacidades técnicas.

## Guia de decisão: Tabelas publicadas vs. API

Use este guia para determinar a abordagem mais adequada para o seu caso:

**Selecione “Tabelas publicadas” quando:**

- Você precisa enviar dados para ferramentas externas de BI, como Power BI ou Tableau
- Os usuários de dados precisam de um esquema estável e previsível, que não mude com frequência
- Você deseja que os dados sejam atualizados automaticamente após cada ciclo de cálculo
- Vários sistemas a jusante precisam do mesmo conjunto de dados selecionado
- Você está substituindo as exportações manuais pontuais de relatórios por uma automação controlada
- Sua equipe de BI prefere conectar-se a um ponto de extremidade conhecido em vez de criar consultas personalizadas

**Escolha o acesso à API quando:**

- Você precisa de flexibilidade para consultar diferentes tabelas ou relatórios sempre que necessário
- Sua integração requer lógica personalizada ou recuperação condicional de dados
- Você está desenvolvendo um aplicativo personalizado que utiliza dados do TBM Studio
- Você precisa de extrações de dados pontuais ou esporádicas
- Seu pipeline de ETL já lida com a transformação e o agendamento de dados
- Você precisa de dados de várias tabelas combinados de maneiras personalizadas

**Escolha ambas as opções quando:**

- As tabelas publicadas alimentam seus painéis principais de BI (estáveis, programadas)
- Suplementos à API com consultas ad hoc ou extrações de tabelas que não valem a pena publicar

## Referência rápida: Comparação de métodos

|  |  |  |
| --- | --- | --- |
| **Característica** | **Tabelas publicadas** | **API** |
| **Uso primário** | Transferências programadas para ferramentas de BI e data warehouses | Recuperação programática de dados sob demanda |
| **Estabilidade do esquema** | Fixado até que seja explicitamente alterado | Depende da tabela de origem/relatório |
| **Atualidade dos dados** | Atualizações após cada cálculo | Em tempo real (consulta de dados atuais) |
| **Configuração** | Configuração via interface do usuário | Código de script ou de aplicativo |
| **Manutenção** | Baixo (configure e esqueça) | Médio (requer manutenção do código) |
| **Ideal para** | Power BI, Tableau, Snowflake feeds | Aplicativos personalizados, ferramentas ETL, automação |

## Tarefas relacionadas

- [Importar dados](data-import-mgmt.html) : Importar dados de arquivos
- [Transformar dados](transform-enrich-data.html) : Transformar e limpar dados
- [Relatórios de compilação](../create-reports/report-basic.html) : consulte a seção 3.3 (Criar relatórios)
- Referência detalhada da API: consulte a seção 5.5 (Referência da API)

- **[Guia prático: Configurar tabelas publicadas](../../../../studio/new-uc/howtoguides/work-with-data/htg-config-pt.html)**
- **[Guia prático: Como exportar dados via API](../../../../studio/new-uc/howtoguides/work-with-data/htg-api.html)**
