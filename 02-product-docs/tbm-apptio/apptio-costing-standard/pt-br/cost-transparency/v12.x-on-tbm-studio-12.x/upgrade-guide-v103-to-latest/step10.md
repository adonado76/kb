---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Etapa 10: Mesclar todos os outros componentes"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/upgrade-guide-v103-to-latest/step10.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Etapa 10: Mesclar todos os outros componentes

Repita a Etapa 9 para continuar mesclando até 5 ramificações de upgrade individuais (de uma só vez) e os check-ins subsequentes do Tronco (em desenvolvimento) na mesma ordem recomendada na [Etapa 6: Atualize todos os outros componentes na ramificação de upgrade](step6.html) :

- Mesclar 1 (até 5 itens de mesclagem)
  - **Configurações do projeto** : Altere para a nova versão do modelo, como v104.

    Observação: Esse deve ser o primeiro item na primeira mesclagem.

    Verifique no Trunk se as configurações do projeto foram alteradas no desenvolvimento e na preparação.
  - **Revisão da TBM** : Desativar o componente.

    Verifique no Trunk se o componente TBM Review não está mais instalado para o desenvolvimento e a preparação.
  - **ATUM v2.0** : Desativar o componente.

    Verifique no Trunk se o componente ATUM v.2.0 não está mais instalado para desenvolvimento e preparação.
  - **CTF - Origem do custo** : Reverter as métricas calculadas e atualizar o componente.

    Verifique no Tronco se nenhuma seta de atualização é exibida no componente CTF- Cost Source em Desenvolvimento e preparação.
  - **Parâmetros** : Alterar para a página inicial do Service Costing.

    Acesse o aplicativo Costing Standard . Você deverá ver a nova página de destino da versão selecionada. (Saiba mais)

    Observação: esta etapa só é necessária se você tiver instalado o componente TBM Review disponível em v103.
- Mesclar 2 (até 5 itens de mesclagem)
  - **CT- Qualidade** : Atualize o componente.

    Verifique no Trunk se não há nenhuma seta de atualização no componente CT-Quality em Development and Staging.
  - **CT- Trabalho** : Atualizar o componente.

    Verifique no Trunk se não há nenhuma seta de atualização no componente CTF- Labor em Development and Staging.
  - **CTF - Torres de TI** : Reverter as métricas calculadas e atualizar o componente.

    Verifique no Trunk se não há uma seta para cima no componente CTF- IT Towers em Development and Staging.
  - **CTF - Controle de tempo** : Atualize o componente.

    Verifique no Trunk se não há nenhuma seta de atualização no componente CTF- Time Tracking em Development and Staging.
  - **CTF- Projetos** : Atualizar o componente.

    Verifique no Trunk se não há nenhuma seta de atualização no componente CTF-Projetos em Desenvolvimento e Preparação.
- Mesclar 3 (até 5 itens de mesclagem)
  - **CTF - Serviço de nuvem** : Reverter as métricas calculadas e atualizar o componente.

    Verifique no Trunk se não há nenhuma seta de atualização no componente CTF- Cloud Services em Desenvolvimento e Preparação.
  - **CTF- Amazon Web Services** : Atualize o componente.

    Verifique no Trunk se há uma seta de noupgrade no componente CTF- AWS em Desenvolvimento e Preparação.
  - **CTF- Azure** : Atualize o componente.

    Verifique no Trunk se não há nenhuma seta de atualização no componente CTF- Azure em Development and Staging.
  - **Aplicativos CT - Aplicativos** : Reverta as métricas calculadas e atualize o componente.

    Verifique no Trunk se não há nenhuma seta de atualização no componente Aplicativos em Desenvolvimento e Preparação.
  - **CT- Unidades de negócios** : Reverter as métricas calculadas e atualizar o componente.

    Verifique no Trunk se não há nenhuma seta de atualização no componente CT- Business Units em Development and Staging.

## Informações relacionadas

- ![](../../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
