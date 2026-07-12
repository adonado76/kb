---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "DomainName função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/domainname.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# DomainName função

**Aplica-se a** : TBM Studio 12.0 e posterior

A função DomainName pode ser combinada com a função ProjectName para fornecer um nome totalmente qualificado: nome do domínio: nome do projeto. Por exemplo: acme.com:ABCPRoject. Além disso, DomainName pode ser usado com a função LookUpFromPath como parte do argumento Path.

## Onde usar

Essa função pode ser usada em:

- Conjuntos de dados
- Métricas calculadas e relatórios com colunas de métricas
- Colunas de fórmula em tabelas de relatórios
- Texto dinâmico

## Sintaxe

```
DomainName
        ( )
```

## Tipo de retorno

Texto

Consulte também:

- [ProjectName](projectname.htm "(Abre em uma nova guia ou janela)")
- [LookupFromPath](lookupfrompath.htm "(Abre em uma nova guia ou janela)")
