---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Padrões de integração de dados"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Arquitetura de dados"
source_path: "studio/new-uc/concepts-architecture/data-architecture/data-integrations-patterns.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Padrões de integração de dados

Os dados podem ser importados para o TBM Studio por meio de vários métodos de integração. A escolha certa depende do volume de dados, da frequência de atualização, dos recursos técnicos e dos requisitos de governança.

## Integração baseada em arquivos

O upload de arquivos é a maneira mais comum e simples de importar dados para o TBM Studio.

**Carregamento manual de arquivos**

Os usuários criam uma tabela no Data Studio e enviam um arquivo do CSV ou do Excel por meio da interface do navegador. A plataforma analisa o arquivo, identifica o esquema e carrega os dados no pipeline de transformação.

- **Ideal para:** carregamentos iniciais de dados, dados de referência pontuais ou atualizações pontuais.
- **Formatos compatíveis:**CSV, TSV, XLS, XLSX. Os delimitadores suportados incluem vírgula, tabulação, barra vertical, til, dois pontos e ponto-e-vírgula.

Dica: os nomes dos arquivos devem conter apenas um ponto (antes da extensão). Por exemplo, example\_data.xlsx é válido, mas example.data.xlsx causará um erro de upload.

**Processamento programado de arquivos**

Para carregamentos de dados recorrentes, você configura o ciclo de atualização da tabela (versões mensais, versões anuais, etc.) e fazer uploads de arquivos regularmente. O TBM Studio monitora se os envios previstos foram realizados e pode enviar notificações por e-mail quando os dados estão atrasados.

- Ideal para: arquivos mensais do Razão, atualizações orçamentárias ou quaisquer dados que sejam alterados em um ciclo previsível.

**Considerações sobre formatos de arquivo**

O TBM Studio utiliza um analisador de Excel aprimorado (ativado automaticamente para novos clientes a partir da versão 12.11.16 ) que lê diretamente os valores numéricos brutos, ignorando a formatação do Excel. Isso garante maior precisão numérica e um tratamento consistente de data e hora por meio da conversão para o formato de época. Esteja ciente de que arquivos do Excel que contenham formatação especial ou macros podem não ser carregados corretamente — a formatação deve ser aplicada por meio de etapas de transformação após o carregamento.

## Integração baseada em API

A API da plataforma Apptio oferece uma alternativa programática ao envio manual de arquivos. Você pode automatizar o envio e o download de dados usando comandos simples do ` HTTP `, integrados a qualquer agendador de tarefas ou aplicativo.

A API utiliza uma interface baseada em ` URL `:

- **Upload:** Envie dados via POST para URL, especificando o domínio, o projeto, a tabela, o período e a ação (Anexar ou Substituir).
- **Download:** Obtenha dados de tabelas ou componentes de relatórios nos formatos Excel ou TSV.

As vantagens da integração por API incluem facilidade de implementação (sem necessidade de instalar software), compatibilidade com todos os sistemas de dados corporativos e automação por meio de agendadores de tarefas.

Nota:

**Quando usar a API em vez de arquivos**

Utilize a API quando precisar de carregamentos de dados automatizados e repetíveis que se integrem a pipelines de ETL ou agendadores de tarefas existentes. Utilize o upload manual de arquivos para carregamentos pontuais de dados ou quando a fonte de dados não for compatível com a extração automatizada.

## DataLink Conexões

DataLink (Classic) oferece uma estrutura de conectores gerenciados para importar dados de bancos de dados e aplicativos externos sem a necessidade de scripts personalizados. Inclui um agente independente que pode ser instalado localmente para acessar fontes de dados internas.

DataLink suporta:

- Conexões diretas com bancos de dados para extrair dados de sistemas corporativos
- Execução programada por horário ou por evento
- Integração com o ServiceNow e outras plataformas de ITSM para o envio de dados de TCO

DataLink é particularmente útil para organizações que buscam uma abordagem sem código para a integração de dados ou que precisam extrair dados de sistemas protegidos por firewalls.

## Tabelas editáveis como padrão de integração

Para pequenos volumes de dados de referência ou mapeamentos de classificação, as tabelas editáveis constituem um método de integração simples e ágil. Os usuários inserem os dados diretamente pela interface do relatório, e esses dados são encaminhados para o pipeline de transformação e para o modelo de custos por meio do mecanismo de publicação.

- Ideal para: atributos de centros de custo, mapeamentos de mão de obra, anotações orçamentárias e outros dados em que o julgamento humano é a fonte principal.

## Guia de Decisão sobre Integração

Use este guia para escolher a abordagem de integração adequada:

|  |  |  |
| --- | --- | --- |
| **Cenário** | **Abordagem recomendada** | **Consideração fundamental** |
| Carregamento de dados pontual ou ad hoc | Upload manual de arquivos | Simples, não requer configuração |
| Dados programados regularmente (contabilidade geral mensal) | Upload automático de arquivos ou API | Configurar o ciclo de atualização e o monitoramento da atualidade |
| Integração automatizada de pipelines ETL | API da plataforma | HTTP -baseado; integra-se com agendadores de tarefas |
| Acesso ao banco de dados local | DataLink (Clássico) | Requer a instalação de um agente local |
| Integração com ITSM (por exemplo, ServiceNow ) | DataLink conector | Conector pré-configurado para saída de dados de TCO |
| Pequenos conjuntos de dados de referência ou classificações | Tabelas editáveis | Inserido manualmente; pipeline de publicação de feeds |
| Exportar dados do modelo para ferramentas externas de BI | Tabelas publicadas | Ponto de extremidade de API estável; controlado por esquema |
