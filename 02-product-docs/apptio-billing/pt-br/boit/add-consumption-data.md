---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Adicionar dados de consumo para cálculos de Preço x Quantidade"
breadcrumb: []
source_path: "boit/add-consumption-data.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Adicionar dados de consumo para cálculos de Preço x Quantidade

Use os dados de consumo quando quiser cobrar das unidades de negócios com base no consumo de serviços, em vez de alocações de custos baseadas em fatores como o número de funcionários. Se nenhum dado de consumo adicional for conhecido, use uma lista das IDs de serviço, que pode ser fornecida anexando os dados brutos da biblioteca de serviços. Não anexe a tabela da biblioteca de serviços em si; no entanto, é permitido anexar os dados anexados à biblioteca de serviços.

Os dados de consumo geralmente são extraídos de várias fontes, como dados de clusters de VM e aplicativos CMDB. Ao carregar os dados de consumo, nomeie as tabelas com o nome do sistema que fornece os dados e coloque as tabelas em uma categoria de Consumo.

Depois de carregar os dados do feed de consumo, anexe as tabelas à tabela Dados mestre do feed de consumo. Consulte [Anexar dados](../studio/data_studio/append-data.html "Aplica-se a: TBM Studio 12.0 e posterior") para obter mais informações.

Seguem as descrições dos campos dos dados mestre do feed de consumo. Todos os campos são obrigatórios.

- **ID da unidade** de negócios: um identificador exclusivo para cada unidade de negócios no nível mais granular, correspondente ao Ident na tabela de dados mestre de alocação de unidades de negócios.
- **Publicado** : Campo específico do cliente para fornecer mais informações sobre a cobrança de uma linha individual, exposto apenas quando um usuário consulta os detalhes do consumo do serviço. Os valores válidos são "Yes" ou "No"
- **Quantidade** : O valor ou a quantidade usada para ponderar e distribuir os custos do serviço comercial do objeto Service Allocations Direct para a unidade de negócios. A quantidade depende da unidade de medida selecionada. Por exemplo, o e-mail pode ser alocado com base no número de caixas de correio por departamento ou na quantidade total de armazenamento de e-mail por departamento. Outros exemplos podem incluir o número de usuários de aplicativos de negócios por departamento.
- **ID do serviço** : O identificador exclusivo do nome do serviço no nível mais granular, correspondendo à ID do serviço na tabela Todos os serviços comerciais.
- **Fonte** : A tabela que está sendo anexada ao conjunto de dados mestre.
