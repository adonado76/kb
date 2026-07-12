---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Criar tabelas editáveis com recursos avançados"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Trabalhar com dados"
  - "Entrada manual de dados"
source_path: "studio/new-uc/howtoguides/work-with-data/create-eet.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Criar tabelas editáveis com recursos avançados

**Objetivo:** Criar uma tabela editável cujas linhas sejam geradas automaticamente a partir de uma tabela de transformação existente, permitindo que os usuários enriqueçam os dados com classificações ou anotações adicionais.

**Quando usar**

- Você possui dados gerados pelo sistema que exigem classificação manual (por exemplo, atribuir etiquetas a instâncias de nuvem com os projetos responsáveis)
- Mapeamento de contas do razão geral para categorias de custos de TI
- Incorporando contexto empresarial aos feeds de dados automatizados
- Mapeamento da força de trabalho (associação de funcionários a estruturas e serviços de TI)
- Casos em que as linhas devem corresponder a um sistema de origem, mas precisam de campos adicionais preenchidos pelo usuário

**Quando NÃO usar**

- Para pequenas tabelas de consulta sem fonte de origem (use tabelas em branco editáveis)
- Quando os usuários precisam adicionar ou excluir linhas livremente (as tabelas enriquecidas herdam as linhas da fonte)
- Para dados totalmente automatizados, sem necessidade de enriquecimento humano

Atenção: Nas tabelas editáveis enriquecidas, as linhas provêm da tabela de transformação de origem e não podem ser excluídas pelos usuários. Os usuários só podem adicionar colunas e preencher os valores dessas colunas. Se a tabela de origem adicionar uma linha, essa linha aparecerá automaticamente na tabela enriquecida. Se a tabela de origem remover uma linha, ela desaparecerá da tabela enriquecida.

## Pré-requisitos

- Uma tabela de transformação existente que servirá como fonte de dados
- Identificar quais colunas da tabela de origem os usuários precisam visualizar
- Planeje quais colunas adicionais os usuários preencherão
- Data Studio acesso com permissões para criar tabelas

**Tempo estimado:** 15 a 20 minutos

**Passos**

1. **Criar a tabela editável com recursos avançados**
   - Acesse **Data Studio**
   - Na guia **Página inicial**, selecione **Novo > Tabela editável**
   - Na caixa de diálogo “**Nova tabela inserida manualmente** ”, selecione **“Tabela enriquecida”**
   - Digite um nome descritivo (por exemplo, “Mapeamento de contas contábeis”, “Ajustes de mão de obra”)
   - Clique **em OK**
2. **Selecione a tabela de transformação de origem**
   - Acesse **Etapas > Gerado** no pipeline
   - Clique **em “Configurar tabela de origem”**
   - No menu suspenso “**Tabela de origem** ”, selecione a tabela de transformação cujos dados irão preencher esta tabela editável
   - O sistema carrega todas as colunas e linhas da tabela de origem
3. **Selecione as colunas de origem a serem incluídas**
   - Verifique a lista de colunas disponíveis na tabela de origem
   - Selecione quais colunas os usuários precisam ver ao inserir dados
   - **Prática recomendada:** inclua colunas de identificação (nomes, IDs, descrições), mas exclua campos calculados
   - **Observação:** essas colunas de origem são somente para leitura; os usuários não podem editá-las
4. **Adicionar colunas editáveis**
   - Vá para **Etapas > Configurar colunas**
   - Clique em **“Adicionar uma nova coluna”** para cada campo que os usuários preencherão
   - Colunas editáveis comuns: campos de classificação, destinos de mapeamento, métricas inseridas pelo usuário, comentários
5. **Configure cada coluna editável**
   - **Nome da coluna:** Use nomes claros e adequados ao contexto empresarial
   - **Descrição:** Explique o que os usuários devem inserir e por quê
   - **Valores possíveis:** Defina menus suspensos para controlar a qualidade dos dados (altamente recomendado)
   - **Valor obrigatório:** Verifique se os usuários devem fornecer um valor antes de publicar
6. **Configure as dependências entre colunas** (se necessário)
   - Para menus suspensos em cascata (por exemplo, Torre → Serviço → Subserviço), configure as fórmulas de "Valores possíveis"
   - Defina **o contexto** de valores possíveis como “Linha atual” para cenários de menus suspensos dependentes
7. **Verifique a pré-visualização dos dados**
   - Clique na etapa **“Tabela”** para ver como fica a tabela aprimorada
   - Verifique se as colunas de origem aparecem corretamente e se há colunas editáveis
8. **Salvar e fazer o check-in**
   - Clique em **“Salvar”** na guia **“Página inicial”**
   - Clique em **“Fazer check-in”** e adicione um comentário descritivo

## Resultados esperados

Sua tabela editável aprimorada agora contém todas as linhas da tabela de transformação de origem (sincronizadas automaticamente), colunas somente leitura da tabela de origem para referência do usuário e colunas editáveis vazias, prontas para receber dados inseridos pelo usuário. Quando a tabela de transformação de origem é atualizada, a tabela editável enriquecida reflete automaticamente essas alterações, preservando os dados inseridos pelo usuário nas colunas editáveis.

**Armadilhas comuns**

|  |  |
| --- | --- |
| **Problema** | **Solução** |
| **Os usuários estão confusos sobre quais colunas podem editar** | Nos relatórios, identifique claramente ou agrupe as colunas editáveis e as de leitura exclusiva. Considere usar a propriedade "Nome de exibição" para adicionar "(Somente leitura)" às colunas de origem. |
| **Linhas da tabela de origem excluídas, dados de enriquecimento do usuário perdidos** | Esse é o comportamento esperado. Se os dados de origem forem removidos, o enriquecimento dessas linhas desaparecerá. Mantenha a estabilidade da tabela de origem ou documente que o enriquecimento pode ser perdido. |
| **Os usuários esperam poder adicionar novas linhas manualmente** | Não é possível adicionar linhas manualmente em tabelas enriquecidas. Se os usuários precisarem dessa funcionalidade, certifique-se primeiro de que todas as linhas necessárias estejam presentes na tabela de transformação de origem ou utilize, em vez disso, uma tabela editável em branco. |
| **As colunas editáveis não possuem menus suspensos** | Para qualquer coluna utilizada em alocações ou relatórios, adicione restrições ao menu suspenso. As entradas de texto livre levam a classificações inconsistentes. |

## O que vem a seguir

Depois de criar sua tabela editável com recursos avançados:

- [Configurar menus suspensos e validação](config-dd-valid.html)
- [Configurar a publicação de tabelas editáveis](setup-et-publish.html)
- [Criar relatórios para a entrada de dados pelo usuário](../create-reports/create-basic-report.html)
- [Guia prático 1: Como aplicar segurança no nível da linha às tabelas](htg-arls.html)

**Tópico principal:** [Entrada manual de dados](../../../../studio/new-uc/howtoguides/work-with-data/manual-data-entry.html)
