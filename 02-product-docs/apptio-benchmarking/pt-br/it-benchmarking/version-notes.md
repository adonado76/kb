---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Apêndice B: Notas sobre versão e compatibilidade"
breadcrumb:
  - "Benchmarking"
  - "Introdução"
source_path: "it-benchmarking/version-notes.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Apêndice B: Notas sobre versão e compatibilidade

Este apêndice explica como o IBM Apptio Benchmarking se alinha às versões do TBM e como ele interage com o Costing.

Use isto quando alguém perguntar:

- "Em que versão estamos?"
- Por que as coisas mudaram após a última atualização?
- Podemos reutilizar nossa antiga configuração de benchmarking?

## Alinhamento da taxonomia TBM

IBM Apptio A análise comparativa utiliza a taxonomia e as estruturas da TBM para interpretar seus dados e compará-los com referências externas.

Seleção da versão do TBM

Na configuração do Interactive Benchmarking, você seleciona uma versão do ATUM (correspondente à versão da taxonomia TBM à qual seus dados estão alinhados). Essa escolha controla:

- Quais pools de custos, torres de recursos e subtorres de recursos existem
- Como as métricas de infraestrutura são agrupadas e rotuladas
- Quais definições e mapeamentos de referência estão disponíveis

Diretrizes:

- Combine a versão do ATUM com a versão do TBM que seu projeto de cálculo de custos está usando.
- Se você estiver migrando para uma nova versão..
  - Confirme que o Interactive Benchmarking é compatível com a nova versão do TBM.
  - Se for compatível, conclua a migração no lado do Cálculo de Custos antes de alterar as versões do Interactive Benchmarking ( configuration.Changing ) sem coordenação, pois isso prejudicará as comparações e confundirá as tendências.

Impacto nas métricas e na estrutura

As alterações de versão podem:

- Adicionar, remover ou renomear torres de recursos e subtorres de recursos
- Mova elementos de custo entre torres de recursos ou pools de custos
- Alterar quais métricas estão disponíveis para cada área

Do ponto de vista do usuário:

- Antes da mudança, as métricas são baseadas na estrutura antiga
- Após a alteração, as métricas são baseadas na nova estrutura
- Em alguns casos, não há tradução direta entre os dois

Implicações práticas:

- Marque o ano da mudança de versão como uma nova linha de base.
- Não finja que os valores pré-alteração e pós-alteração são diretamente comparáveis sem reapresentação.

## Relação com o cálculo de custos

Benchmarking e cálculo de custos estão intimamente relacionados, mas não são a mesma coisa.

**Com integração de custos**

Quando a Avaliação Comparativa Interativa é integrada ao Cálculo de Custos:

- A comparação interativa extrai os custos anuais de TI de um projeto de cálculo de custos selecionado.
- Esse projeto deve usar conjuntos de custos e torres de recursos do TBM que estejam alinhados com a versão selecionada do TBM.
- Os benchmarks de infraestrutura dependem dos mapeamentos no nível da subtorre de recursos, caso você deseje métricas de custo unitário.

Benefícios:

- Você obtém números consistentes entre o cálculo de custos e a análise comparativa.
- Você pode detalhar desde lacunas de benchmark até contas, fornecedores, aplicativos ou serviços.
- Você pode manter um único sistema de registro para os custos de TI.

Riscos em caso de desalinhamento:

- Os benchmarks refletirão um subconjunto ou uma visão distorcida dos custos de TI.
- As conversas executivas ficarão paralisadas na reconciliação, em vez de decisões.

**Sem integração de custos**

Você pode usar o Benchmarking sem Cálculo de Custos carregando os custos anuais manualmente ou por meio de um arquivo.

Você ainda pode:

- Use benchmarks de TI e de setor OpEx
- Use alguns benchmarks de infraestrutura se você fornecer custo e volume por subtorre de recursos

Limitações:

- Sem retorno ao GL, fornecedores ou serviços dentro do Cálculo de custos
- A atualização dos dados é mais manual e demorada
- Mais espaço para inconsistências de escopo e mapeamento

Essa abordagem pode ser adequada para um piloto. Para uso contínuo, a integração com o Costing é altamente recomendada.

**Manter a análise comparativa em sincronia com o cálculo de custos**

Quando o custo muda de forma a afetar a análise comparativa:

- Torres novas ou reestruturadas
- Principais reclassificações
- Alterações no escopo (por exemplo, adição de nuvem, telecomunicações ou novas unidades de negócios)

Você deve:

- Revisar a configuração e os mapeamentos de benchmarking.
- Revalidar um pequeno conjunto padrão de visualizações de referência.
- Documente que ocorreu uma alteração na modelagem para esse ano.

Se você ignorar isso, verá saltos inexplicáveis nas visualizações de benchmark que são, na verdade, mudanças no modelo, e não mudanças operacionais.
