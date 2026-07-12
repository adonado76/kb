---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Fluxo de trabalho de check-out e check-in"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Ciclo de vida de compilação e implantação"
source_path: "studio/new-uc/concepts-architecture/checkin-checkout-workflow.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Fluxo de trabalho de check-out e check-in

No TBM Studio, todos os elementos — incluindo tabelas de dados, métricas, perspectivas, modelos e relatórios — são documentos. Para editar qualquer documento, você deve primeiro fazer o check-out. Este mecanismo de bloqueio exclusivo evita conflitos quando vários usuários trabalham no mesmo projeto.

**Retirar um documento**

Ao fazer o check-out de um documento, você estabelece um bloqueio exclusivo que impede que outras pessoas o editem simultaneamente. Para retirar um documento:

1. Selecione o documento no Explorador de Projetos.
2. Na guia Página inicial, no grupo Documento, clique em Retirar.
3. Um ícone de check-out aparece ao lado do nome do documento, e o nome do documento será exibido em laranja na guia na parte inferior da área de trabalho.

Enquanto o arquivo estiver em seu controle, você pode salvar as alterações sem que isso acione um recálculo. Isso permite que você faça várias edições de forma eficiente antes de compartilhá-las com a equipe.

**Registrar um documento**

Quando você faz o check-in de um documento, o bloqueio é liberado e é acionado um recálculo. Suas alterações ficam visíveis para os outros usuários no ambiente de teste. Para registrar um documento:

1. Na guia Página inicial, no grupo Documento, clique em Arquivar.
2. O documento é enviado para o Staging, e os cálculos são iniciados.

Aviso:

Sempre valide suas alterações antes de fazer o check-in. Analise as tabelas de dados em busca de erros, verifique os impactos na alocação e teste os relatórios afetados. Check-ins mal validados podem causar problemas de desempenho ou cálculos incorretos no Staging.

**Desfazer, Refazer e Reverter**

Enquanto os documentos estiverem retirados, você tem várias opções para gerenciar as alterações:

**As funções "Desfazer" e "Refazer"** são úteis para reverter pequenas alterações isoladas, tais como:

- Posicionamento dos elementos de relatório dentro de um relatório
- Alterações pontuais na configuração dos elementos (texto dos botões, conteúdo HTML)
- Alterações nas fórmulas na etapa de fórmulas de uma tabela

**A opção "Reverter alterações"** descarta todas as alterações feitas nos documentos selecionados que estavam em check-out e cancela totalmente o check-out. Para reverter:

1. Na guia Página inicial, no grupo Documento, clique em Reverter alterações.
2. Selecione os documentos que deseja reverter e clique em “Reverter check-out”.

**Melhores práticas para o check-in**

Seguir uma rotina consistente de verificações ajuda a manter a estabilidade do projeto:

|  |  |
| --- | --- |
| **Prática** | **Por que isso é importante** |
| Verifique os dados antes de fazer o upload | Verifique se os arquivos contêm dados, estão corretamente delimitados e possuem as colunas esperadas |
| Ativar a validação de cardinalidade | Identifica problemas de qualidade dos dados logo no início, antes que se espalhem pelo modelo |
| Validar os impactos da alocação | Alterações nos dados ou na configuração podem afetar as alocações de maneiras inesperadas |
| Testar os relatórios afetados | Verifique se os relatórios são carregados corretamente e exibem os valores esperados |
| Coordenar check-ins | Combine horários de verificação (por exemplo, na hora do almoço e no final do dia) para minimizar as filas de cálculo |
| Não faça o check-in durante as promoções | Certifique-se de que ninguém esteja aguardando a promoção para o ambiente de produção antes do seu check-in |
