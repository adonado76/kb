---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Exportar e imprimir relatórios"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar relatórios"
  - "Relatórios avançados"
source_path: "studio/new-uc/howtoguides/create-reports/export-print-rep.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Exportar e imprimir relatórios

**Objetivo:** Gerar relatórios para distribuição por meio de exportação para PDF, envio por e-mail, impressão e assinaturas automáticas.

**Quando usar:** Ao compartilhar relatórios com partes interessadas fora do TBM Studio, ao criar distribuições programadas de relatórios ou ao produzir materiais impressos para reuniões e apresentações.

**Tempo estimado:** 10 a 20 minutos por relatório

## Configurar o layout de impressão

Antes de exportar ou imprimir, configure o layout de impressão para definir como o relatório será exibido no papel ou em PDF:

1. Dê uma olhada no relatório.
2. Na guia Página inicial, clique em Exibir e selecione Layout de impressão. O relatório passa para o modo de layout de impressão.
3. Clique na guia “Layout de impressão” para acessar as opções de layout.
4. Configurar as opções de página:
   - **Tamanho da página:** Selecione entre os tamanhos de papel padrão
   - **Orientação:** retrato ou paisagem
   - **Margens:** Definir margens da página
   - **Escala:** Nível de zoom para a impressão
5. Configurar o fluxo de componentes:
   - **Manual:** Os componentes permanecem onde você os coloca
   - **Vertical:** os componentes são dispostos em uma única coluna
   - **Horizontal:** os componentes são dispostos em fileiras
6. Configurar cabeçalhos e rodapés:
   - **Cabeçalho:** Adicione texto, formatação HTML ou texto dinâmico. Pode aparecer em todas as páginas ou apenas na primeira página.
   - **Rodapé:** Adicione um texto personalizado ao rodapé (observação: os rodapés não suportam texto dinâmico)
7. Para componentes individuais:
   - **Fixar/Desfixar:** Mover componentes (como segmentadores) para o final do relatório
   - **Mostrar/Ocultar:** Controle quais componentes aparecem na impressão
8. Clique em “Salvar” na guia “Layout de impressão” para salvar suas configurações.
9. Clique em “Sair do modo de layout de impressão” para voltar ao modo de edição normal.
10. Confira o relatório.

Dica: use texto dinâmico nos cabeçalhos para incluir o período atual. Por exemplo: <%=CurrentDate( )%> exibe automaticamente o período do relatório.

## Configurar a impressão de tabelas com várias páginas

Para tabelas grandes que ocupam várias páginas:

1. Entre no modo de layout de impressão.
2. Mova a tabela para uma página separada (as tabelas ficam melhores na impressão quando ocupam uma página exclusiva).
3. Selecione a tabela e, na guia “Layout de impressão”, clique em “Redimensionar componente para página inteira”.
4. Com a tabela selecionada, vá para a subguia Tabela e marque a opção Imprimir todas as páginas.
5. Salve e saia do modo de layout de impressão.

## Exportar para PDF

1. Exiba o relatório que deseja exportar.
2. Na guia Página inicial, clique em Exportar e, em seguida, clique em PDF. Aparece a caixa de diálogo “Exportar para PDF”.
3. Selecione uma opção de exportação:
   - **Baixar PDF diretamente:** abre ou baixa o PDF para o seu computador
   - **Incluir um link para o PDF em um e-mail:** envia um e-mail com um link para o PDF armazenado no TBM Studio
   - **Anexar o PDF a um e-mail:** envia o PDF como anexo de e-mail
4. Para as opções de e-mail, insira o endereço de e-mail do destinatário.
5. Clique em OK para gerar e exportar/enviar por e-mail o PDF.

Observação: quando você compartilha um link de relatório por e-mail, o destinatário visualiza o relatório no mesmo contexto em que você o compartilhou. Quaisquer filtros, segmentadores e seleções de intervalo de datas são mantidos.

## Criar assinaturas de e-mail

Configure o envio automático e recorrente de relatórios por e-mail:

1. Acesse o relatório que você deseja assinar.
2. Clique no ícone Exportar e selecione Assinatura por e-mail. Esta opção está disponível para administradores do TBM.
3. Na caixa de diálogo “Assinatura por e-mail”, configure a assinatura:
   - **Nome da assinatura:** Um nome descritivo para a assinatura
   - **Destinatários:** Endereços de e-mail (devem pertencer a domínios autorizados em seu ambiente)
   - **Frequência:** entrega diária, semanal ou mensal
   - **Incluir visualização do layout de impressão:** anexar o PDF com o layout de impressão configurado
   - **Incluir link com as seleções do filtro:** Incluir um hiperlink para o relatório com os filtros já aplicados
4. Clique em Salvar para criar a assinatura.

Aviso: a segurança no nível da linha (RLS) não se aplica às assinaturas de e-mail. Todos os destinatários têm acesso aos dados completos do relatório. Leve isso em consideração ao distribuir relatórios com informações confidenciais.

## Gerenciar assinaturas de e-mail

Para visualizar e gerenciar assinaturas existentes:

1. No relatório, clique em Exportar > Assinatura por e-mail.
2. Clique em “Gerenciar assinaturas”.
3. A partir daqui, você pode:
   - Ver todas as assinaturas do relatório
   - Editar configurações de assinatura
   - Ativar ou desativar assinaturas
   - Cancelar assinaturas

## Exportar para o Excel

Para exportar os dados do relatório para o Excel para análise posterior:

1. Exiba o relatório.
2. Na guia Página inicial, clique em Exportar e, em seguida, clique em Excel.
3. Os dados do relatório são exportados para uma pasta de trabalho do Excel. A ordem das colunas corresponde à configuração do relatório.

Observação: o Excel limita os nomes das planilhas a 31 caracteres. Os nomes de relatórios que excedam esse limite são truncados e têm “ "-0" ” acrescentado ao final.

## Exportar tabelas da visualização em árvore

Ao exportar tabelas em estrutura hierárquica para o Excel:

- Todas as linhas pai e filho são exportadas
- A primeira coluna exibe indicadores de recuo (símbolos >>) para representar o nível hierárquico
- A exportação para o Excel é uma tabela plana (não uma estrutura em árvore que pode ser recolhida)

## Requisitos do navegador

Para que os recursos de exportação para PDF funcionem corretamente:

- Permita pop-ups do site Apptio URL nas configurações do seu navegador
- Os PDFs podem abrir em uma nova guia ou aparecer na barra de downloads do seu navegador, dependendo das configurações do navegador

**Resultados esperados**

- As exportações para PDF utilizam as configurações de layout de impressão definidas
- As assinaturas por e-mail enviam relatórios de acordo com a programação definida
- Os links compartilhados para relatórios preservam o contexto (filtros, intervalo de datas) existente no momento em que o link foi criado
- As exportações para o Excel incluem todos os dados visíveis da tabela, com as colunas na ordem configurada

**Armadilhas comuns**

- **O PDF não está sendo exibido corretamente:** verifique se o layout de impressão está configurado. Visualize clicando em “Exportar para PDF” na guia “Layout de impressão” antes de fazer o check-in.
- **Falha na assinatura por e-mail:** verifique se os endereços de e-mail dos destinatários pertencem a domínios autorizados para o seu ambiente.
- **Cabeçalhos/rodapés não aparecem:** Os cabeçalhos e rodapés não ficam visíveis no Modo de Layout de Impressão. Exporte para PDF para visualizá-los.

## Tarefas relacionadas

- Configurar permissões de relatórios (Seção 3.4 )
- Criar coleções de relatórios (Seção 3.3.1 )
- Configure compilações recorrentes (Seção 6.1 )

**Tópico principal:** [Relatórios avançados](../../../../studio/new-uc/howtoguides/create-reports/adv-rep.html)
