---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Resolução de problemas e perguntas frequentes"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "ApptioIBM Report Studio (Novo)"
source_path: "studio/report-studio/faq.html"
images:
  - "resources/images/studio_images/rep-faq.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Resolução de problemas e perguntas frequentes

## Perguntas frequentes gerais

**Qual é o contexto?**

![imagem de contexto do novo estúdio de relatórios](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rep-faq.png)

- O CT Report Studio (um dos componentes do TBM Studio) precisa ser “modernizado” para oferecer uma experiência de usuário simples e fácil.
- O resultado pretendido com este projeto de modernização é aliviar os desafios enfrentados pelos nossos usuários na aprendizagem da ferramenta, na navegação dentro da ferramenta e na obtenção de insights a partir das informações apresentadas pela ferramenta.

**Que desafios isso aborda?**

- Simplifica a integração e o TTV
- Melhora os tempos de integração do administrador e do usuário final, fornecendo uma plataforma inteligente e intuitiva que antecipa as necessidades do usuário, apresentando automaticamente ferramentas essenciais e opções de configuração com base em suas ações imediatas
- Reduz o número de cliques e orienta a geração de relatórios
- Permite a criação mais rápida de relatórios; cria relatórios elegantes e consistentes com menos esforço
- Utiliza uma biblioteca diversificada de componentes visuais para comunicar informações e insights de forma rápida e eficaz

**Por que o Modelo ou o Data Studio não foram implementados e quando serão implementados?**

Dada a necessidade de abordar os aspectos mais críticos dos pontos fracos atuais dos usuários, as funcionalidades do Report Studio e do End User foram priorizadas. Implementaremos uma experiência perfeita tanto para o Model quanto para o Data Studio nas próximas fases.

**O que não é compatível com o Novo Report Studio?**

- Perspectivas - A funcionalidade será substituída por Fórmulas Publicadas
- Global Slicers – A funcionalidade será substituída pelo recurso Saved Views (Visualizações salvas).
- Tabelas herdadas em tabelas e tabelas editáveis
- Tabelas editáveis - Funções “Definir todas as linhas como” e “Adicionar linha”
- Data de início do relatório
- Atualizar configurações - Opção para definir atualização manual ou automática a cada 3 segundos
- Componente Notas – Anteriormente, permitia aos usuários criar notas nos relatórios e controlar a visibilidade (por exemplo: “Somente eu” ou funções específicas).
- Blueprints – Criação de relatórios com base em modelos

## Perguntas frequentes sobre relatórios

**Por que meu relatório está demorando mais para carregar no novo Report Studio?**

Durante a pré-visualização pública, os relatórios V2 não são pré-calculados. Isso significa que o sistema recupera e processa os dados sob demanda cada vez que você abre ou atualiza um relatório. Como resultado, você poderá notar tempos de carregamento mais lentos em comparação com a experiência clássica.
