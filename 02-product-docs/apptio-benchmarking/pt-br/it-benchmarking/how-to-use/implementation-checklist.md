---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Lista de verificação da implementação"
breadcrumb:
  - "Benchmarking"
  - "Como usar este guia"
source_path: "it-benchmarking/how-to-use/implementation-checklist.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Lista de verificação da implementação

Antes de começar

**Antes de começar**

- Confirme se os produtos estão visíveis no Frontdoor
  - A avaliação comparativa é visível.
  - O custo é visível, se você planeja integrá-lo (altamente recomendado).
- Se estiver integrando com o Cálculo de custos, identifique o projeto de Cálculo de custos do sistema de registro
  - Selecione qual projeto de cálculo de custos servirá como fonte para os gastos reais com TI.
  - A propriedade e o controle de alterações do projeto de Custeio são claros.
- Designar funções
  - Líder do Programa TBM/ITFM identificado.
  - TBMA primário/analista designado como proprietário da avaliação comparativa.
  - Apptio Administrador da plataforma identificado.
  - Proprietários de recursos-chave (por exemplo, computação, armazenamento, rede, etc.) identificados.

**Preparação dos dados**

- Dados do perfil organizacional disponíveis
  - **Receita** anual mais recente para o escopo da sua organização de TI que está sendo avaliada.
  - Último **FTE** (equivalente a tempo completo) anual para o mesmo âmbito.
  - Classificação **do setor** acordada associada à sua organização de TI.
  - **Região** acordada (global vs. região específica) e lógica da faixa de tamanho.
- Dados sobre gastos com TI disponíveis para pelo menos um ano completo
  - Gastos anuais com TI mapeados nos **grupos de custos** TBM.
  - Gastos anuais com TI mapeados nas **Torres de Recursos** da TBM.
- Volumes de infraestrutura (se estiver usando benchmarks de infraestrutura)\*
  - Contagem de dispositivos/capacidade por sub-torre, por exemplo:
    - Servidores (físicos/virtuais, conforme necessário)
    - Armazenamento (TB de capacidade utilizável)
    - Rede (portas, dispositivos ou unidades relevantes)
  - Contagem de FTE para funções de infraestrutura importantes, se você planeja usar métricas de eficiência de FTE.

\* *Se não for possível marcar todos os itens de infraestrutura, você ainda pode começar com os benchmarks Industry e OpEx e adicionar a infraestrutura posteriormente.*

**Ambiente e configuração**

- Acesso verificado
  - Os administradores da TBMA podem fazer login em **IBM Apptio Benchmarking**.
  - Se o Cálculo de Custos estiver integrado, os TBMA/administradores podem fazer login no projeto **de Cálculo de Custos** escolhido.
  - Os principais consumidores podem, pelo menos, ver os relatórios de benchmarking que se espera que utilizem.
- Conjunto de versões da taxonomia
  - Versão do TBM selecionada no Benchmarking para corresponder ao projeto de Cálculo de Custos.
  - Quaisquer torres de recursos/pools de custos não padronizados mapeados para equivalentes padrão ou exceções documentadas.
- Perfil organizacional configurado no Benchmarking
  - Receita e número de funcionários inseridos e correspondentes ao escopo da organização de TI.
  - Setor e região definidos corretamente.
  - Quaisquer fatores adicionais de complexidade preenchidos, se disponíveis.
- Dados de custos conectados ou carregados
  - Se integrado com o Cálculo de Custos:
    - A análise comparativa está apontando para o projeto de cálculo de custos correto.
    - Exercício fiscal/período correto selecionado para referências.
  - Se não estiver integrado:
    - Despesas anuais com TI por pool de custos e torre de recursos carregadas manualmente.
    - Moeda e ano fiscal claramente definidos.
- Dados de infraestrutura configurados (se aplicável)
  - Custo de infraestrutura mapeado para subtornis alinhadas com a taxonomia de referência.
  - Dados de volume/capacidade carregados para essas subtorres.
  - Unidades de medida validadas (GB vs TB, física vs virtual, etc.)
- Padrões do grupo de pares definidos
  - Grupo de pares padrão escolhido (setor, faixa de tamanho, região).
  - Quaisquer políticas de filtro adicionais acordadas (por exemplo, quando restringir ou ampliar).
  - Grupo de pares padrão documentado para reutilização em relatórios executivos.

**Validação e primeira utilização**

- Visualizações principais do teste de fumaça
  - Métricas do setor:
    - Despesas com TI em comparação com receitas e funcionários.
  - OpEx: de TI
    - Distribuições do Pool de Custos e da Torre de Recursos.
  - Infraestrutura:
    - Pelo menos uma métrica de custo unitário (se os dados de infraestrutura estiverem configurados).
- Verificações de sanidade aprovadas
  - Os totais de gastos com TI são reconciliados com o departamento financeiro para o ano selecionado.
  - Sem valores atípicos 10x evidentes devido a erros unitários ou mapeamento incorreto.
  - Todas as principais torres de recursos e pools de custos que você espera estão presentes e não são nulas.
  - O grupo de pares e o ano apresentados correspondem ao que você pretende discutir.
- Pacote inicial para as partes interessadas preparado
  - 3-5 gráficos selecionados:
    - 1 Visão do setor
    - 1 Distribuição de TI OpEx
    - 1-2 Visões da infraestrutura (se aplicável)
  - Breve narrativa redigida para cada um:
    - Onde estamos na fila.
    - Onde diferimos.
    - Onde pretendemos investigar mais a fundo.
- Sessão introdutória com o patrocinador realizada
  - O TBM lidera e o TBMA acompanha o patrocinador (CIO/VP/Finanças) através de:
    - O que é benchmarking.
    - Com quem nos comparamos.
    - Principais conclusões iniciais.
  - Decisões documentadas:
    - Métricas que iremos acompanhar.
    - Torres de recursos / áreas em que nos concentraremos.
    - Com que frequência iremos revisitar.

**Governança e operações em andamento**

- Cadência acordada
  - Anual:
    - Atualização completa dos dados e benchmarks alinhados ao ciclo de planejamento.
    - Revisão e confirmação por grupo de pares.
  - Trimestralmente:
    - Revisão das principais métricas de referência e lacunas da Torre de Recursos no QBR/direcionamento.
  - Ad hoc:
    - Use benchmarks para os principais casos de negócios e iniciativas da Resource Tower.
- Alterar políticas definidas
  - Requer aprovação (líder TBM) para:
    - Alteração da versão do TBM no Benchmarking.
    - Alteração do projeto de cálculo de custos principal.
    - Alterando as seleções padrão do grupo de pares.
    - Adicionar ou remover categorias de custos importantes do escopo da referência.
  - Permita a TBMA discricionariedade (com documentação) para:
    - Pequenas correções no mapeamento.
    - Visões experimentais com grupos de pares alternativos claramente identificados.
- Documentação em vigor
  - Página única salva que captura o seguinte:
    - Projeto de cálculo de custos utilizado
    - Versão TBM
    - Grupo de pares padrão
    - Cadência de atualização de dados
  - Notas de mapeamento para quaisquer decisões de escopo não óbvias, por exemplo:
    - “Os gastos com telecomunicações estão incluídos na torre de rede.”
    - “O serviço compartilhado X é alocado inteiramente para a Gestão de TI.”
  - Link para este guia de ajuda sobre benchmarking compartilhado com TBMAs, proprietários de torres de recursos e principais parceiros financeiros.

Se todas as opções acima estiverem marcadas, o Benchmarking não está apenas configurado tecnicamente, mas é realmente utilizável, explicável e controlado.
