---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Perguntas frequentes sobre o inventário de recursos"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
  - "Inventário de recurso"
source_path: "product/resource-inventory-faqs.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Perguntas frequentes sobre o inventário de recursos

## Por que não consigo selecionar os últimos 3 dias no seletor de intervalo de datas do inventário de recursos?

No Inventário de Recursos, não é possível selecionar os últimos 3 dias no intervalo de datas, pois algumas métricas podem levar até 72 horas para serem refletidas no relatório de inventário e a integridade dos dados não é garantida.

Você verá uma mensagem no seletor de datas mostrando o intervalo de datas disponível, com um lembrete de que os últimos 3 dias estão excluídos.

## Por que os números no meu relatório salvo mudam com o tempo?

Pode haver alguns motivos para os números parecerem diferentes:

- Se você executar um relatório salvo cuja data ultrapasse 90 dias, o sistema redefinirá automaticamente a data para 7 dias. Isso serve para garantir que o relatório seja carregado com sucesso. Nesse caso, você também verá uma mensagem de aviso em destaque.
- Se o seu relatório tivesse a opção “Data móvel” ativada e o critério fosse os últimos 90 dias, os números podem mudar todos os dias.

## Por que alguns recursos aparecem com o status "Indisponível"

O Inventário de Recursos pode exibir o estado como **“Indisponível”** nos seguintes cenários:

- Permissões ausentes – Se a autenticação avançada não estiver configurada, o Inventário de Recursos obterá os detalhes do recurso a partir dos dados de custo, que não conterão todos os metadados, incluindo o estado do recurso.
- Recursos de curta duração – O Inventário de Recursos coleta dados em intervalos definidos. Se um recurso for criado e encerrado entre dois ciclos de coleta, seus detalhes de estado e utilização podem não ser registrados e, portanto, o estado não constará.
- Instantâneos – Não há informações de estado disponíveis para recursos de instantâneo.
- Recursos de transferência de dados – Certos recursos (por exemplo, a transferência de dados do NAT Gateway) não possuem um estado associado e aparecerão como “Indisponível”.
- Azure recursos encerrados – No Azure, uma vez que um recurso é encerrado, mesmo que não seja um recurso de curta duração, as informações sobre seu estado não estão mais disponíveis e são exibidas como “Indisponível”.

**Tópico principal:** [Inventário de recursos](../product/resource-inventory.html)
