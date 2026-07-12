---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Guia de Início Rápido"
breadcrumb:
  - "TBM Studio"
  - "Introdução"
source_path: "studio/new-uc/getting-started/qsg.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guia de Início Rápido

## Seu primeiro modelo de custos

|  |  |
| --- | --- |
| **Tipo de Conteúdo** | Tutorial |
| **Público-alvo** | Novos usuários |
| **Tempo de conclusão** | 10 minutos |
| **Pré-requisitos** | Acesso a um projeto do TBM Studio (ambiente de desenvolvimento), conhecimentos básicos sobre conceitos de custos de TI, arquivo de dados de custos de exemplo (formato Excel ou CSV ) |

## O que você vai conseguir

Neste tutorial de 10 minutos, você conhecerá todo o fluxo de trabalho do TBM Studio ao:

- Carregando seu primeiro arquivo de dados de custos
- Criando uma transformação simples de dados
- Criação de uma alocação básica de custos
- Como gerar seu primeiro relatório de custos

No final, você verá como os custos de TI passam dos dados brutos, passando pelas alocações, até se transformarem em relatórios úteis.

## Antes de começar

Certifique-se de que você tem:

- Uma conta no TBM Studio com acesso a um projeto
- Um pequeno arquivo de dados de custos, pronto para ser enviado

Observação: Embora seja recomendado o uso de um modelo padronizado de dados de exemplo para este tutorial, talvez não haja um disponível no seu projeto no momento. Você pode usar qualquer arquivo simples de dados de custos (Excel ou CSV ) que contenha, no mínimo, as seguintes colunas: Origem do custo (por exemplo, “Folha de pagamento”, “Serviços em nuvem”), Departamento ou Unidade de negócios, Valor (valor numérico do custo) e Mês ou Data.

## Passo 1: Acesse o TBM Studio e acesse Data Studio

***Duração:*** *1 minuto*

1. Faça login no TBM Studio usando suas credenciais
2. No painel **Projetos**, selecione o projeto que lhe foi atribuído
3. Certifique-se de que está no ambiente **de desenvolvimento** (exibido na barra de navegação superior)
4. No painel **“Project Explorer”** à esquerda, expanda “ **Data Studio** ”

**Resultado esperado:** Você verá a estrutura de pastas ` Data Studio ` com as tabelas existentes (se houver) no seu projeto.

## Passo 2: Carregue seus dados de custos

***Duração:*** *2 minutos*

1. Clique na guia **"Página inicial"** na barra de ferramentas
2. Clique em **Novo** → **Tabela**
3. Digite o nome da tabela: *"Meus primeiros dados de custos"*
4. Insira uma categoria: *"Tutorial"* (isso ajuda a organizar as tabelas)
5. Clique **em OK**

A tabela é criada e o pipeline de transformação é aberto automaticamente.

1. Na etapa "**Fonte** ", clique em **"Carregar arquivo"**
2. Arraste seu arquivo de dados para a área de upload ou clique para procurar e selecioná-lo
3. O TBM Studio detecta automaticamente:
   - Linha de cabeçalho (geralmente a linha 1)
   - Tipos de coluna (Rótulo, Numérico, Estado/Data)
4. Verifique as configurações da etapa **de importação** :
   - Verifique se a opção **“Iniciar importação na linha”** está configurada corretamente (normalmente na linha 2 para os dados)
   - Analise a lista **de colunas** — verifique se os tipos de coluna foram detectados corretamente
   - Para todas as colunas numéricas de custo, certifique-se de que elas estejam definidas como do tipo "Número"
5. Clique em **“Salvar”** na guia “Página inicial”
6. Clique na etapa **“Tabela”** no fluxo de trabalho para visualizar seus dados

**Resultado esperado:** você verá os dados enviados exibidos em uma tabela, com todas as linhas e colunas visíveis. Os cabeçalhos das colunas correspondem ao seu arquivo, e os tipos de dados estão corretamente identificados.

**Problemas comuns** - Se os números aparecerem como texto, clique na coluna na etapa de importação e altere o tipo para "Número". Se você encontrar erros, verifique se o seu arquivo não contém linhas em branco no início.

## Passo 3: Criar uma transformação simples

***Duração:*** *2 minutos*

Agora você vai adicionar uma transformação simples para limpar ou aprimorar seus dados.

1. No fluxo de trabalho **“Etapas de transformação** **”**, clique em “Adicionar etapa” (ícone +)
2. Selecione **“Filtro”** entre os tipos de etapa
3. Configure o filtro:
   - Clique **em “Adicionar condição”**
   - Selecione a coluna do valor do custo
   - Defina o operador como **>** (maior que)
   - Insira o valor: **0** (para excluir valores zero ou negativos)
4. Clique **em OK**
5. Clique na etapa **“Tabela”** para visualizar os resultados filtrados

**Resultado esperado:** Sua tabela agora mostra apenas as linhas em que o custo é maior que zero. O número de linhas pode ser menor do que no upload original.

Dica: Este é um exemplo básico. Em projetos reais, você pode adicionar etapas para unir dados, mapear valores ou aplicar fórmulas.

## Passo 4: Adicione sua tabela ao modelo

***Duração:*** *2 minutos*

Para alocar custos, sua tabela deve fazer parte do modelo de custos.

1. No fluxo de transformação, clique em **“Adicionar etapa”**
2. Selecione **“Modelo”** como tipo de etapa
3. Clique na nova etapa **“Modelo”** no fluxo de trabalho

A janela do Modelo de Tabela Única é aberta, exibindo sua tabela no centro.

1. Clique na sua mesa (o retângulo no centro)
2. No painel **“Linhas”**, marque as colunas-chave que identificam itens de custo exclusivos (por exemplo, Origem do custo, Departamento)
3. No painel **"Drivers"** à esquerda, clique em **"Adicionar driver de unidade"**
4. Configure o driver da unidade:
   - **Adicionar a** : Selecione a métrica de custo (geralmente "Custo")
   - **Usando** : Selecionar **coluna**
   - **Coluna** : Selecione a coluna de valor/custo
5. Clique **em OK**
6. Clique em **“Salvar”** na guia “Página inicial”
7. Clique em **“Check-in”** para salvar suas alterações

**Resultado esperado:** Sua tabela agora é um objeto modelo que pode receber ou enviar alocações de custos. Você pode ver os totais dos custos na visualização do modelo.

**Entendendo o que aconteceu:** você acabou de criar um “driver de unidade” — isso indica ao modelo de onde vêm os valores de custo na sua tabela.

## Etapa 5: Criar uma alocação básica (opcional)

***Duração:*** *2 minutos*

Observação: esta etapa requer uma segunda tabela ou objeto no seu modelo. Se o seu projeto já tiver um objeto de modelo (como “Unidades de Negócio” ou “Aplicativos”), você pode criar uma alocação simples.

**Se a tabela de destino existir:**

1. Na visualização Modelo, clique em **“Adicionar alocação”** no painel direito
2. Configure a alocação:
   - **Para** : Selecione o objeto de destino (por exemplo, "Unidades de Negócios")
   - **Condição** : Selecione uma coluna comum que exista em ambas as tabelas (por exemplo, Departamento)
3. Clique **em “Visualizar”** para ver como os custos serão alocados
4. Clique **em Salvar**

**Resultado esperado:** você verá os custos sendo transferidos da tabela de origem para a tabela de destino com base no driver selecionado.

**Se não houver nenhum destino:** ignore esta etapa por enquanto. Você já concluiu o upload dos dados principais e a integração do modelo. O próximo passo seria trabalhar com um administrador para definir metas de alocação.

## Passo 6: Gere seu primeiro relatório

***Duração:*** *3 minutos*

Agora você vai criar um relatório simples para visualizar seus dados.

1. No **Explorador** de Projetos, expanda **Relatórios**
2. Clique na guia **Página inicial** → **Novo** → **Relatório**
3. Digite o nome do relatório: *"Meu primeiro relatório de custos"*
4. Insira a descrição: *"Tutorial - Primeiro relatório de custos"*
5. Selecione "**Visível por** ": Escolha as permissões adequadas (ou mantenha as predefinidas)
6. Selecione o layout: **Padrão ( 1024px )** com **a opção “Adicionar título”** marcada
7. Clique **em OK**

O editor de relatórios é aberto.

1. No painel **de configuração de** componentes, arraste uma **tabela** para a área de trabalho do relatório
2. Configure a tabela:
   - **Fonte de dados** : Selecione seu objeto de modelo (por exemplo, "Meus primeiros dados de custo")
   - **Linhas** : Arraste sua dimensão-chave (por exemplo, Origem de custo ou Departamento) para a área Linhas
   - **Valores** : Arraste sua métrica de custo para a área Valores
3. A tabela é preenchida com seus dados
4. Adicione um **filtro** para interatividade:
   - Arraste o componente **Slicer** para cima da sua tabela
   - Configure-o para filtrar por uma de suas dimensões (por exemplo, Departamento)
5. Clique **em Salvar**
6. Clique em **"Fazer check-in"**

**Resultado esperado:** Você tem um relatório funcional que mostra seus custos de acordo com a dimensão selecionada. O filtro permite que os usuários filtrem os dados de forma interativa.

Dica: clique nos valores do filtro para filtrar a tabela — você acabou de criar um relatório interativo!

## Confirme seu sucesso

Você concluiu com sucesso o guia de início rápido se conseguir:

- Veja os dados que você enviou em Data Studio
- Visualize sua tabela no Model com um driver de unidade configurado
- Acesse seu relatório e veja os dados de custos exibidos
- Use o filtro para filtrar o relatório

**Parabéns!** Você acabou de concluir todo o fluxo de trabalho do TBM Studio: Dados → Modelo → Relatório.

## O que fazer em seguida?

Agora que você já entende o fluxo de trabalho básico, explore estas próximas etapas:

**Próximos passos imediatos**

- **Conheça a interface** : consulte a seção 1.4 (Navegar pela interface) para entender melhor a área de trabalho
- **Compreenda os conceitos básicos** : Leia a seção 1.2 (Conceitos básicos) para obter uma compreensão mais aprofundada sobre tabelas, modelos e métricas

**Desenvolvendo suas habilidades**

- **Para o trabalho com dados** : consulte a seção 3.1 (Trabalho com dados) para conhecer técnicas avançadas de upload e transformação
- **Para modelagem de custos** : consulte a seção 3.2 (Criar modelos de custos) para criar alocações em vários níveis
- **Para relatórios** : consulte a seção 3.3 (Criar relatórios) para criar visualizações sofisticadas

**Caminhos baseados em funções**

- **Analistas de negócios** : Seção 2.1 (Percurso de aprendizagem para analistas de negócios)
- **Equipes de Finanças de TI** : Seção 2.2 (Percurso de Aprendizagem para Finanças de TI)
- **Administradores** : Seção 2.3 (Percurso de aprendizagem para administradores)

## Obter ajuda

- Se você encontrar erros, consulte a seção 7.1 (Problemas comuns e soluções)
- Para obter informações detalhadas sobre qualquer recurso, consulte a Seção 5 (Referência)

## Resolução de problemas

| **Problema** | **Solução** |
| --- | --- |
| **Não consigo enviar o arquivo** | Verifique o formato do arquivo (deve ser.xlsx,.xls ou.csv) e certifique-se de que o nome do arquivo não contenha caracteres especiais (use apenas letras, números, sublinhados e hífens) |
| **Colunas exibidas com o tipo incorreto** | Na etapa de importação, altere manualmente o tipo da coluna clicando na coluna e selecionando o tipo correto no menu suspenso |
| **Não vejo a opção “Etapa do modelo”** | Certifique-se de ter salvo sua tabela primeiro. A etapa "Modelo" só pode ser adicionada após a criação da tabela |
| **O relatório não apresenta dados** | Certifique-se de ter feito o check-in das alterações na tabela e no modelo. Os relatórios mostram apenas os dados dos objetos registrados |
| **Não consigo fazer o check-in** | Você deve salvar suas alterações primeiro (clique em “Salvar” na guia “Página inicial”) e, em seguida, poderá fazer o check-in |
| **Atualizar área de trabalho** | Verifique a guia “Página inicial” da barra de fitas para ver se a opção “Atualizar área de trabalho” está ativada. Se estiver ativado, clique no ícone para atualizar sua área de trabalho e garantir que você veja as atualizações mais recentes. |
