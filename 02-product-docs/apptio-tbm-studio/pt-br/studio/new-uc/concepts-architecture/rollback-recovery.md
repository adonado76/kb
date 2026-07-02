---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Reversão e recuperação"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Ciclo de vida de compilação e implantação"
source_path: "studio/new-uc/concepts-architecture/rollback-recovery.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Reversão e recuperação

Às vezes, é preciso reverter as alterações — talvez uma configuração esteja causando problemas de desempenho ou o conteúdo tenha sido implementado prematuramente. O TBM Studio oferece recursos de reversão para essas situações.

**Quando usar o Rollback**

Considere usar o recurso de reversão quando:

- Uma configuração registrada está causando problemas de desempenho
- O conteúdo foi implementado no ambiente de produção prematuramente
- Você precisa voltar rapidamente a um estado em que tudo funcione corretamente

Aviso:

O rollback não deve ser usado de ânimo leve. Todos os check-ins realizados após o ponto de reversão serão descartados. Se houver alterações nessas versões que você queira manter, será necessário reimplementá-las após a reversão.

**Como funciona o Rollback**

Quando você executa uma reversão:

1. Todos os cálculos em andamento para o projeto são interrompidos
2. Um novo cálculo é iniciado utilizando a configuração do check-in selecionado
3. Todos os check-ins posteriores ao ponto selecionado são descartados (as operações de ramificação estão isentas)
4. É executado um cálculo completo do Stage, o que pode demorar algum tempo, dependendo da complexidade da configuração

**Executando uma reversão**

1. Selecione qualquer documento no Explorador de Projetos.
2. Na guia "Build", selecione "Histórico de check-in".
3. Clique com o botão direito do mouse no check-in para o qual deseja reverter e selecione “Reverter para”.
4. Insira um motivo descritivo para a reversão e clique em “Reversão do check-in”.
5. Após a conclusão da compilação, atualize todas as áreas de trabalho com documentos retirados selecionando Página inicial > Atualizar área de trabalho.

Dica:

Se o conteúdo tiver sido implantado no ambiente de produção prematuramente, considere usar um ramo de correção (hotfix) em vez de reverter a implantação. Uma correção pode ser mais rápida e não descarta check-ins intermediários.
