---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Tabelas de versões para dados mensais"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Trabalhar com dados"
  - "Importação e gerenciamento de dados"
source_path: "studio/new-uc/howtoguides/work-with-data/version-tables-monthly-data.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tabelas de versões para dados mensais

**Objetivo:** Configurar tabelas para manter conjuntos de dados separados para cada período, permitindo o acompanhamento histórico e a análise comparativa entre períodos.

**Quando utilizar este procedimento:** Utilize o controle de versão mensal quando:

- Os valores dos dados mudam a cada mês (por exemplo, razão geral, custos reais, utilização do servidor)
- É necessário preservar os valores históricos para a análise de tendências
- Seus processos de negócios exigem o fechamento do mês e o bloqueio do período
- Estruturas de dados ou valores diferentes se aplicam a períodos de tempo diferentes

**Não utilize o controle de versão mensal quando:**

- Os dados são estáticos ou mudam com pouca frequência
- Você só precisa dos dados mais recentes
- Os dados são informações de referência ou consulta (por exemplo, mapeamentos de grupos de custos)

**Pré-requisitos:**

- O tempo já foi habilitado para o projeto
- Compreensão do calendário fiscal da sua organização
- Conhecimento sobre a criação e o envio de tabelas
- Permissões para editar tabelas (função AccessDev )

**Tempo estimado:** 15 minutos para a configuração inicial; 5 minutos por período para os uploads contínuos

## Passos

**Parte 1: Configurar o controle de versões mensal para uma nova tabela**

1. **Criar uma nova tabela:** No **Explorador** de Projetos, clique **em Novo** → **Tabela**, insira um Nome (por exemplo, “Dados Reais Mensais do Razão”), insira uma Categoria e clique **em OK**.
2. **Selecione o controle de versão mensal:** na parte superior da tela, localize o menu suspenso **“Ciclo de atualização de dados”** e selecione “**Versões mensais; Atualizar mensalmente** ”.

**Entendendo as opções de controle de versão mensal:**

- **Versões mensais; Atualização mensal:** novos dados adicionados mensalmente; dados dos meses anteriores mantidos
- **Versões anuais; Atualização mensal:** 12 meses carregados mensalmente (ano contínuo)
- **Versões anuais; Atualização no início do ano:** envio anual; conteúdo estático até o próximo ano
- **Versões anuais com transferência de dados:** upload anual com transferência automática dos valores do ano anterior
  1. **Carregue os** **dados do primeiro mês:** certifique-se de que o seletor de datas mostre o período desejado, clique **em “Carregar arquivo** ”, carregue seu arquivo de dados, configure as opções de importação, clique em “**Salvar** e **registrar** ”.
  2. **Configurar notificações de expiração de dados** (opcional): **Clique aqui para configurar notificações** e ativar alertas por e-mail quando os dados não forem atualizados conforme o cronograma.

**Parte 2: Carregar dados para períodos subsequentes**

1. **Faça o check-out da tabela:** vá até a tabela, clique com o botão direito do mouse e selecione “**Check-out** ”.
2. **Mude para o período desejado:** use o **seletor de datas** para selecionar o período dos novos dados. Aparece um espaço reservado na etapa de upload.
3. **Carregue os** **dados do** período: clique no espaço reservado, procure o arquivo ou arraste-o para cá. O sistema cria uma nova versão para esse período.
4. **Verificar e salvar:** clique na etapa **“Tabela”** para visualizar, verificar os valores, clicar em **“Salvar”** e “**Confirmar** ”.

## Resultados esperados

- A tabela contém conjuntos de dados separados para cada período
- Ao alterar os períodos no seletor de datas, o conjunto de dados correspondente é exibido
- Os dados históricos são preservados e estão disponíveis
- É possível fazer comparações entre períodos nos relatórios
- Os alertas de atualização de dados avisam quando faltam uploads mensais

## Problemas comuns e solução de problemas

**Problema:** erros de “dados ausentes” no modelo ou nos relatórios

- **Motivo:** Não foram carregados dados para todos os períodos entre o início do projeto e a data atual
- **Solução:** Carregue os arquivos de dados de todos os períodos exigidos. Considere ajustar a data de início do projeto, utilizar o controle de versão por transferência ou criar conjuntos de dados provisórios.

**Problema:** Carregado no período errado

**Solução:** Verifique sempre o seletor de datas antes de fazer o upload. Exclua o upload incorreto selecionando esse período, finalizando a transação e removendo o arquivo da etapa de upload.

**Problema:** as alterações no esquema não foram aplicadas aos períodos anteriores

- **Motivo:** as alterações no esquema só se aplicam a partir do período selecionado
- **Solução:** Esse é o comportamento esperado. Para atualizar períodos anteriores, selecione cada período usando o seletor de datas, faça as alterações e salve.

## O que vem a seguir

- [Configurar particionamento por data](transform-enrich-data.html) : para arquivos do Razão com colunas mensais, adicione etapas de transformação de particionamento por data
- Configurar períodos encerrados: Bloquear períodos finalizados para evitar alterações acidentais (Seção 6.1 )
- Agendar compilações automatizadas: Alinhar os cálculos do modelo com os processos de fechamento do mês (Seção 6.1 )
- [Crie relatórios de tendências](../create-reports/report-basic.html) : utilize dados mensais para análises comparativas entre períodos

**Tópico principal:** [Importação e gerenciamento de dados](../../../../studio/new-uc/howtoguides/work-with-data/data-import-mgmt.html)
