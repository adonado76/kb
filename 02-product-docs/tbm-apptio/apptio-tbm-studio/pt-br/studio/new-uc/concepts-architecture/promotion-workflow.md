---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Fluxo de trabalho de promoção"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Ciclo de vida de compilação e implantação"
source_path: "studio/new-uc/concepts-architecture/promotion-workflow.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Fluxo de trabalho de promoção

A promoção é o processo de transferência de conteúdo validado do ambiente de teste para o ambiente de produção. O TBM Studio oferece dois modos de promoção: sob demanda e recorrente.

**Promoções sob demanda**

A promoção sob demanda é o modo padrão em que os administradores promovem as compilações conforme necessário. O fluxo de trabalho é o seguinte:

1. **Validar:** O administrador analisa e valida a compilação atual no ambiente de teste.
2. **Bloqueio:** O administrador bloqueia o projeto para impedir novos check-ins durante a promoção.
3. **Promover:** O administrador promove usando as opções “Promover agora” ou “Promover mais tarde”.
4. **Desbloquear:** O administrador desbloqueia o projeto para retomar as operações normais.

**Bloqueio de um projeto:** Quando a etapa está bloqueada:

- Os usuários podem retirar documentos, mas não podem devolvê-los
- O menu suspenso "Ambiente" exibe o status "Bloqueado"
- Somente administradores podem promover para o ambiente de produção

Para bloquear ou desbloquear um projeto: selecione o ambiente de teste e, na guia Compilação, selecione Bloquear (ou Desbloquear, se já estiver bloqueado).

**Opções de promoção:**

|  |  |
| --- | --- |
| **Opção** | **Comportamento** |
| **Divulgue agora** | Promove o projeto imediatamente. Desativado quando desbloqueado ou quando outra compilação ainda estiver em execução. |
| **Promover mais tarde** | Agenda uma promoção para uma data específica. As opções incluem: promover assim que a compilação for concluída (e não após o tempo especificado) ou promover no horário especificado, caso a compilação já tenha sido concluída. |
| **Promoção forçada** | ( v.12.11.0+ ) Promove a última compilação calculada sem bloquear o Stage. Use para atualizações urgentes quando não for possível bloquear o sistema. |

**Promoções recorrentes**

A promoção recorrente é um modo avançado para equipes com rotinas já estabelecidas. Ele promove automaticamente nos horários programados. Pré-requisitos para usar promoções recorrentes:

- A equipe tem um ritmo bem estabelecido de reuniões de acompanhamento e validação, seguindo um cronograma
- A equipe deseja que a Produção receba atualizações em intervalos regulares para análise
- Os membros da equipe se coordenam entre si quanto ao horário do check-in

Importante:

O bloqueio não pode ser usado com promoções recorrentes. Se o projeto estiver bloqueado durante o período programado para a promoção, a promoção falhará. Não misture o bloqueio sob demanda com programações recorrentes.
