---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configuração e personalização"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "ApptioIBM Report Studio (Novo)"
source_path: "studio/report-studio/config-custom.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuração e personalização

## Conformidade com acessibilidade

O New Report Studio foi projetado para oferecer suporte à acessibilidade e está em conformidade com as normas de acessibilidade da seção 508. A experiência inclui suporte para navegação por teclado, leitores de tela e padrões de interface do usuário acessíveis para garantir que os relatórios possam ser criados e visualizados por usuários com diversas necessidades de acessibilidade.

## Localização

O novo Report Studio agora inclui suporte à localização, permitindo que usuários de todas as regiões tenham uma experiência de interface consistente e integrada em seu idioma e formato preferidos.

A seção abaixo explica como a localização funciona em vários aspectos do Report Studio.

- Localização de texto estático: Todos os elementos de texto estático (rótulos, botões, itens de menu e mensagens) no novo Report Studio agora são localizáveis.
  - Atualmente, a tradução para japonês é suportada.
  - Quando você altera o idioma do aplicativo para japonês, todo o texto estático no Report Studio aparecerá automaticamente em japonês.
- Dados e configuração: O novo Report Studio oferece suporte total a dados e configurações em idiomas diferentes do inglês.
  - Você pode usar caracteres que não sejam do alfabeto inglês em nomes de relatórios, filtros ou campos de dados.
  - Configurações como nomes de colunas, filtros ou rótulos personalizados podem incluir texto localizado sem afetar a funcionalidade do relatório.
- Formatação específica da localidade: a formatação de números, datas e outros dados sensíveis à localidade segue automaticamente as convenções da localidade selecionada pelo usuário.
  - Por exemplo, usuários com a localidade japonesa verão números formatados com vírgulas e marcadores decimais, de acordo com as convenções japonesas.
- Manipulação de moedas: O novo Report Studio suporta projetos com moedas únicas diferentes do dólar americano.
  - Os projetos configurados com uma moeda base específica exibirão todos os valores monetários usando o símbolo e a formatação da moeda correspondente.
  - Exemplo: um projeto definido para ienes japoneses exibirá todos os valores monetários com o símbolo do iene nos relatórios.

## Configurações multimoedas

Se a opção multimoeda estiver ativada para o seu projeto, os relatórios poderão ser visualizados e testados em diferentes moedas e tipos de taxa (real ou planejada).

**Multimoedas no Report Studio (Admin)**

Os administradores podem testar relatórios em diferentes moedas diretamente no Report Studio antes de publicá-los ou compartilhá-los.

Como alterar a moeda no Report Studio?

1. Abra o relatório no Report Studio.
2. Clique no menu Avançado.
3. Selecione Configurações de várias moedas.
4. Escolha:
   1. Uma moeda
   2. Um tipo de taxa (real vs. planejado)

Cada moeda ativada suporta os tipos de taxa real e planejada.

O relatório será imediatamente recalculado com base na moeda e no tipo de taxa selecionados.

**Quando usar isso**

- Valide a precisão dos relatórios em todas as moedas
- Cenários de plano de teste versus taxa real
- Visualizar em moedas alternativas
- Certifique-se de que a formatação e os totais sejam exibidos corretamente

**Multimoeda no Visualizador de Relatórios (Usuários finais)**

Se o projeto tiver a opção de múltiplas moedas ativada, um seletor de moeda aparecerá no relatório no Visualizador de Relatórios.

**Comportamento padrão**

- Os relatórios são abertos na moeda e no tipo de taxa preferidos pelo usuário.
- O relatório é gerado automaticamente usando essas configurações.

**Alterar a moeda no Visualizador**

1. Use o menu suspenso do seletor de moeda no relatório
2. Escolha qualquer moeda habilitada
3. Selecione o tipo de taxa desejado (Real ou Planejada)

O relatório é renderizado instantaneamente usando as configurações selecionadas.

**Persistência da sessão**

- A moeda e o tipo de taxa selecionados permanecem durante toda a sessão de visualização da moeda do usuário.

**Comportamento de exportação**

A moeda e o tipo de taxa selecionados aplicam-se às exportações:

- **A exportação para PDF** reflete a moeda selecionada no momento.
- **A exportação para o Excel** (componentes individuais) reflete a moeda selecionada atualmente.

- **[Etapas para ativar relatórios OOTB modernizados (NX) em uma instância](../../studio/report-studio/ootb-report-pp.html)**  
   do cliente Este documento descreve as **etapas necessárias para ativar relatórios OOTB modernizados (New Experience (NX))** em uma instância do cliente. Esses relatórios oferecem maior visibilidade, melhores insights e uma experiência mais intuitiva, mantendo o uso dos **mesmos conjuntos de dados do Classic TBM Studio**.
- **[IBM Apptio Guia do Assistente de Migração de Relatórios](../../studio/report-studio/migration-assistant.html)**
