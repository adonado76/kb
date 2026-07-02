---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Lista de verificação da implementação"
breadcrumb:
  - "Billing"
  - "Como usar este guia"
source_path: "boit/billing/getting-started/checklist.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Lista de verificação da implementação

Para quem está planejando ou alterando uma implementação de faturamento, esta lista de verificação de alto nível reúne todas as informações do guia. As seções seguintes fornecem as etapas detalhadas.

**Confirme a edição de faturamento e os componentes em uso**

- Determine se a organização está usando o Billing Essentials ou o Billing Standard.
- Verifique se a versão correta do modelo de componente está selecionada. Consulte [as Notas de lançamento](../release-notes/whats-new.html "Esta seção descreve apenas as alterações no conteúdo de faturamento pronto para uso, não na plataforma subjacente. Para atualizações no nível da plataforma, como o comportamento do TBM Studio e do servidor cliente, os leitores devem revisar as Notas de lançamento do TBM Studio e considerar as alterações aplicáveis juntamente com o que está documentado aqui.") para saber quais são as versões aplicáveis.

**Requisitos para revisão**

- Verifique se o Cálculo de Custos está implantado e estável.
- Confirme se as tabelas mestras e os conjuntos de dados necessários existem ou se há um plano para preenchê-los.

**Alinhar funções e acesso**

- Identifique administradores, analistas, proprietários de serviços ou produtos, líderes seniores e outras partes interessadas.
- Confirme se o acesso apropriado foi concedido no front-end e, quando aplicável, no TBM Studio.

**Planeje ambientes e promoções**

- Decida como as alterações são desenvolvidas e testadas em Desenvolvimento e Preparação.
- Defina o processo de promoção e as aprovações para transferir compilações para a produção.

**Defina o ciclo de faturamento**

- Chegue a um acordo sobre os períodos de faturamento, prazos e pontos de verificação de validação.
- Defina quem valida, quem aprova e quem recebe os resultados finais.

**Escolha o caminho de configuração**

- Use [Configurando o Billing Essentials (Implementação)](../config-be/be-overvie.html "Esta seção descreve como o Billing Essentials é configurado em um projeto do Costing Essentials, desde a instalação dos componentes até as primeiras faturas utilizáveis. Presume-se que o Costing Essentials já esteja implantado e estável.") para o Billing Essentials.
- Utilize [a configuração do padrão de faturamento (implementação)](../config-bs/bs-overview.html "Esta seção descreve como o Padrão de Faturamento é configurado em um projeto Padrão de Custeio, desde a instalação dos componentes até as primeiras faturas ricas em domínios utilizáveis. Presume-se que o Padrão de Custeio já esteja implementado e estável.") para o padrão de faturamento.

**Planeje o treinamento e a integração**

- Use o [Guia de Treinamento Baseado em Funções](../role-based-tg/train-objectives.html "Esta seção descreve como treinar diferentes públicos para que o Billing seja realmente usado e confiável, e não apenas implantado tecnicamente. Use-o para planejar integrações, treinamentos recorrentes e transferências quando as pessoas mudarem de função.") para mapear quais funções precisam de quais seções e relatórios.

Uma vez que esses pontos estejam esclarecidos, o restante do guia pode ser lido seletivamente, usando as notas de edição e os resumos das seções para encontrar a profundidade necessária para uma determinada tarefa.
