---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Etapa 6: Faça upgrade de todos os outros componentes na ramificação Upgrade"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/upgrade-guide-v103-to-latest/step6.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Etapa 6: Faça upgrade de todos os outros componentes na ramificação Upgrade

Todos os componentes instalados precisam ser atualizados para a nova versão do modelo. Recomenda-se que você comece com os componentes de nível inferior (por exemplo, componentes CTF-, depois aplicativos CT etc.). No entanto, não é necessário seguir uma ordem exata. Para este exemplo, os componentes instalados são para uma configuração de base de CT no modelo v103.

Observação: Se você abrir o projeto Costing Standard durante o processo de atualização, perceberá que alguns dos links de navegação estão quebrados na ramificação de atualização. Isso será resolvido quando todos os componentes tiverem sido atualizados.

Repita as etapas 4 e 5 para continuar atualizando todos os outros componentes. A ordem a seguir é recomendada; no entanto, talvez você não tenha todos esses componentes instalados em seu ambiente:

- Componente de **revisão da TBM** :
  - Desativar o componente.
  - Verifique a alteração, "Revisão da TBM: desativar componente"
- **ATUM v2.0** componente:
  - Desativar o componente.
  - Verifique na alteração, " ATUM v2.0: disable component."
- **CTF- Componente de fonte de custo** :
  - Reverter qualquer métrica calculada ou personalizações de relatórios.
  - Atualize o componente.
  - Remapeie os arquivos de origem para o conjunto de dados mestre de origem de custos, se você reverteu as alterações do conjunto de dados.
  - Verifique a alteração, "CTF- Cost Source: reverter métricas calculadas, atualizar componente"
- **CT- Componente de qualidade** :
  - Reverter qualquer métrica calculada ou personalizações de relatórios.
  - Atualize o componente.
  - Verifique a alteração, "CT- Quality: upgrade component"
- Componente **CTF-Trabalho** :
  - Reverter qualquer métrica calculada ou personalizações de relatórios.
  - Atualize o componente.
  - Remapeie os arquivos de origem para o conjunto de dados mestre da mão de obra, se você reverteu as alterações no conjunto de dados.
  - Verifique a alteração, "CT- Labor: upgrade component"
- **CTF- Componente Torres de TI** :
  - Reverter qualquer métrica calculada ou personalizações de relatórios.
  - Atualize o componente.
  - Remapeie os arquivos de origem para o conjunto de dados mestre da Torre de Recursos de TI.
  - Verifique a alteração, "CTF- IT Towers: reverter métricas calculadas, atualizar componente"
- **CTF - Componente de Rastreamento de Tempo** :
  - Reverter qualquer métrica calculada ou personalizações de relatórios.
  - Atualize o componente.
  - Remapeie os arquivos de origem para o conjunto de dados mestre de controle de tempo, se você reverteu as alterações do conjunto de dados.
  - Verifique a alteração, "CTF- Controle de tempo: componente de atualização"
- **CTF- Componente de Projetos** :
  - Reverter qualquer métrica calculada ou personalizações de relatórios.
  - Atualize o componente.
  - Reajuste os arquivos de origem para o conjunto de dados mestre de projetos, se você reverteu as alterações do conjunto de dados.
  - Verifique a alteração, "CTF-Projetos: componente de atualização"
- **CTF - Componente do Serviço em Nuvem** :
  - Reverter qualquer conjunto de dados, métrica calculada ou personalizações de relatório.
  - Atualize o componente.
  - Verifique a alteração, "CTF- Cloud Service: reverter métricas calculadas, atualizar componente"
- **CTF- Amazon Web Services** component:
  - Reverter qualquer conjunto de dados, métrica calculada ou personalizações de relatório.
  - Atualize o componente.
  - Verifique a alteração, "CTF- Amazon Web Services : componente de atualização"
- **CTF- Azure** component:
  - Reverter qualquer conjunto de dados, métrica calculada ou personalizações de relatório.
  - Atualize o componente.
  - Verifique a alteração, "CTF- Azure : componente de atualização"
- **CT Apps - Componente de aplicativos** :
  - Reverter qualquer métrica calculada ou personalizações de relatórios.
  - Atualize o componente.
  - Remapeie os arquivos de origem para o conjunto de dados mestre de aplicativos, caso tenha revertido as alterações no conjunto de dados.
  - Verifique a alteração, "Aplicativos CT - Aplicativos: reverter métricas calculadas, atualizar componente"
- **CT - Componente Unidades de Negócios** :
  - Reverter qualquer métrica calculada ou personalizações de relatórios.
  - Atualize o componente.
  - Reajuste os arquivos de origem para o conjunto de dados mestre da unidade de negócios, se você reverteu as alterações do conjunto de dados.
  - Verifique a alteração, "CT- Unidades de negócios: reverter métricas calculadas, atualizar componente"

## Informações relacionadas

- ![](../../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
