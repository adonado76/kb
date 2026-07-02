---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "ProjectName função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/projectname.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ProjectName função

**Aplica-se a** : TBM Studio 12.0 e posterior

Retorna o nome do projeto atual.

A função ProjectName pode ser combinada com a função DOMAINNAME para fornecer um nome totalmente qualificado: nome do domínio: nome do projeto. Por exemplo: acme.com:ABCPRoject. Além disso, o endereço ProjectName pode ser usado com a função LOOKUPFROMPATH como parte do argumento "path".

## Onde usar

Essa função pode ser usada em:

- Conjuntos de dados
- Métricas calculadas e relatórios com colunas de métricas
- Colunas de fórmula em tabelas de relatórios
- Texto Dinâmico

## Sintaxe

`ProjectName( )`

## Tipo de retorno

Texto

Consulte também:

- [DomainName](domainname.htm "(Abre em uma nova guia ou janela)")
- [LookupFromPath](lookupfrompath.htm "(Abre em uma nova guia ou janela)")
- [ProjectExists](project-exists-function.htm "(Abre em uma nova guia ou janela)")
