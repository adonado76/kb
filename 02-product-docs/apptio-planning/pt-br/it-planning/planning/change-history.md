---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Histórico de alterações"
breadcrumb:
  - "Planning"
  - "Fluxos de trabalho e colaboração"
source_path: "it-planning/planning/change-history.html"
images:
  - "resources/images/it_planning_images/chnghist.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Histórico de alterações

O Change History fornece uma trilha de auditoria das principais ações executadas no ambiente de planejamento. Ele permite que as organizações mantenham a transparência, atendam aos requisitos de conformidade e solucionem problemas de planejamento, rastreando quem alterou o quê, quando e como.

Observação: As funções de administrador ou de proprietário do processo orçamentário são necessárias para acessar o Change History.

## Onde acessar o histórico de alterações

Vá para **Change History → Event Log** usando a navegação à esquerda.

- Use filtros para detalhar os tipos de eventos, intervalos de datas, usuários ou escopos (planos, departamentos, contas).
- Use a função **Exportar** para baixar um CSV do registro de auditoria para análise ou arquivamento externo.

## Tipos de eventos

O Change History captura uma variedade de tipos de eventos. As categorias comuns incluem:

- **Eventos do plano** : Criação do plano, alterações de estado (Novo → Final), arquivamento, controle de versão.
- **Eventos de entrada de dados** : Edições de itens de linha, inserção/exclusão de registros, operações de importação.
- **Eventos de aprovação** : Envio, aprovação, devolução, comentário.
- **Eventos de dados de referência** : Alterações de dimensão (por exemplo, contas, departamentos), atualizações de configuração.
- **Eventos de função e permissão** : Atribuição de função de usuário, alterações de acesso.

Consulte a lista completa de [tipos de eventos](event-types.html "O Change History captura uma ampla gama de eventos do sistema no Apptio Planning, permitindo que você analise quem fez o quê, quando e como. Cada evento é categorizado por tipo, área, contêiner, tipo de item e alterações de atributo.") para obter detalhes e descrições completos.

## Exportação do histórico de alterações

- Na página Change History (Histórico de alterações), clique no **menu Elipses →Exportar** **para CSV.**
- O arquivo inclui todos os filtros selecionados e os dados do evento: registro de data e hora, usuário, plano, departamento, tipo de evento, descrição e valores antes/depois, quando disponíveis.
- Use a exportação para auditorias de conformidade, revisões de processos ou integração com sistemas de BI/relatórios.

## Ver detalhes do evento

Você pode visualizar informações adicionais sobre qualquer evento no Histórico de alterações abrindo o painel **Propriedades**.

**Para abrir as propriedades de um evento:**

- Clique no **ícone Propriedades** ao lado do evento no Registro de Eventos.

O painel Propriedades inclui duas guias:

- **Info** - Mostra informações gerais sobre o evento (como tipo de evento, usuário e registro de data e hora).
- **Details (Detalhes** ) - Exibe alterações específicas, incluindo valores anteriores e posteriores para todos os atributos afetados.

![imagem do registro de eventos](../../../../../03-media/apptio-planning/resources/images/it_planning_images/chnghist.png)

- **[Tipos de eventos](../../it-planning/planning/event-types.html)**  
   O Change History captura uma ampla gama de eventos do sistema no Apptio Planning, permitindo que você analise quem fez o quê, quando e como. Cada evento é categorizado por tipo, área, contêiner, tipo de item e alterações de atributo.
