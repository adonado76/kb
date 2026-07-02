---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Segurança de dados"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Trabalhar com dados"
source_path: "studio/new-uc/howtoguides/work-with-data/data-security.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Segurança de dados

**Tipo de conteúdo:** Guia prático

**Público-alvo:** Administradores, Analistas de Negócios

**Pré-requisitos:** Conhecimento sobre tabelas de transformação e noções básicas de gerenciamento de usuários

**Seções relacionadas:** Seção 4.4 (Modelo de segurança), Seção 6.3 (Segurança e conformidade)

## Introdução

A segurança por linha (RLS) permite controlar quais linhas de dados cada usuário pode visualizar nas tabelas e nos relatórios. Em vez de restringir o acesso a tabelas inteiras, o RLS permite filtrar os dados de forma granular com base no usuário que está visualizando as informações. Por exemplo, um gerente regional pode ver apenas os dados de custos da sua unidade de negócios, enquanto um diretor financeiro tem acesso aos dados de todas as unidades.

Esta seção oferece orientações práticas e passo a passo para a implementação do RLS na camada de dados. Para uma compreensão conceitual de como a segurança funciona no TBM Studio, consulte **a seção “Modelo de segurança do 4.4:** ”. Para obter informações sobre a configuração de segurança no nível de administrador e questões relacionadas à conformidade, consulte **a seção Segurança e conformidade do 6.3:**.

**Conceitos-chave**

- **Segurança em nível de linha (RLS):** Um mecanismo de filtragem de dados que restringe as linhas visíveis com base no usuário atual. Anteriormente chamado de "Filtros de visualização" no TBM Studio 11.
- **Tabela de mapeamento:** uma tabela que define quais usuários podem acessar quais itens de dados. Contém os IDs dos usuários e os itens que eles têm permissão para visualizar.
- **Projeto de Segurança em Nível de Linha:** Um projeto de sistema dedicado onde são armazenadas as tabelas de mapeamento. Este projeto é criado automaticamente quando uma nova instância do Apptio é instalada e atende a todos os projetos do domínio.
- **Etapa RLS:** Uma etapa de pipeline adicionada para transformar tabelas que fazem referência a tabelas de mapeamento, a fim de aplicar filtros de segurança.

## Compreendendo a arquitetura do RLS

Antes de implementar o RLS, é útil entender como os componentes funcionam em conjunto:

1. **As tabelas de mapeamento** definem as relações entre o usuário e os dados. Eles estão no projeto dedicado à Segurança em Nível de Linha e mapeiam os IDs dos usuários aos valores de dados específicos (como unidades de negócios, centros de custo ou regiões) aos quais cada usuário tem acesso.
2. São adicionadas **etapas RLS** para transformar pipelines. Cada etapa faz referência a uma tabela de mapeamento e especifica qual coluna da sua tabela de dados deve ser filtrada com base nesse mapeamento.
3. **Durante a execução**, quando um usuário visualiza uma tabela ou um relatório, o sistema compara o ID do usuário com a tabela de mapeamento para determinar quais linhas devem ser exibidas.

Importante: As tabelas não herdam automaticamente as configurações de RLS. É necessário adicionar uma etapa RLS a cada tabela que exija filtragem de segurança. Se o seu modelo tiver várias tabelas (por exemplo, “Cost Source” e “IT Resource Towers”), você precisará configurar o RLS em cada uma delas separadamente.

Aviso: A segurança no nível da linha afeta todos os usuários, exceto os administradores. Os administradores têm acesso ao modo Studio e podem criar relatórios que contornam o RLS, adicionar-se às tabelas de mapeamento ou desativar completamente o RLS. Não confie apenas no RLS para proteger dados confidenciais dos usuários administradores.

- **[Guia prático 1: Como aplicar segurança no nível da linha às tabelas](../../../../studio/new-uc/howtoguides/work-with-data/htg-arls.html)**
- **[Aplicar segurança no nível](../../../../studio/data_studio/apply-row-level-security.html)**   
   da linha ◆ Aplicável a: TBM Studio 12.2 e versões posteriores
- **[Guia prático 2: Controle de acesso com mapeamento de usuários](../../../../studio/new-uc/howtoguides/work-with-data/htg-cacc.html)**
- **[Melhores práticas para segurança no nível da linha](../../../../studio/new-uc/howtoguides/work-with-data/bp-rls-wn.html)**
