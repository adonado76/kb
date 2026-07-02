---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Requisitos de dados para o padrão de faturamento"
breadcrumb:
  - "Billing"
  - "Requisitos e integração de dados"
source_path: "boit/billing/datareq-integrate/data-bs.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Requisitos de dados para o padrão de faturamento

O Padrão de Faturamento utiliza um conjunto mais amplo de componentes e, portanto, um modelo de dados mais abrangente. Ainda precisa dos mesmos fundamentos básicos do Essentials, mas os distribui por vários domínios.

Observação: aplica-se apenas ao padrão de faturamento.

Tabelas mestras e conjuntos de dados de domínio comum:

- **Unidades e definições de unidades**
  - Unidades padronizadas utilizadas em todos os domínios (por exemplo, VM por mês, GB por mês, usuário nomeado por mês).
  - Usado para manter diferentes domínios consistentes e comparáveis.
- **Aplicativos**
  - Dados mestre da aplicação:
    - ID e nome do aplicativo.
    - Equipe ou função proprietária.
    - Status do ciclo de vida (ativo, em fase de descontinuação, aposentado).
  - Relações com:
    - Serviços ou ofertas.
    - Projetos e iniciativas.
    - Consumidores, em modelos de faturamento centrados em aplicativos.
- **da nuvem e híbrida**
  - **Servidores** : ID do servidor, tipo, ambiente, plataforma e propriedade.
  - **Armazenamento** : pool de armazenamento, camada e alocações de capacidade.
  - **Dispositivos do usuário final** : tipo de dispositivo, proprietário, localização e regras de alocação.

- **NUVEM**
  - Contas na nuvem ou IDs de assinatura.
  - Mapeamentos de provedores e níveis de serviço.
  - Tags ou etiquetas agrupadas em:
    - Serviços ou ofertas.
    - Consumidores.
    - Dimensões de alocação de custos.
- **Projetos**
  - ID e nome do projeto.
  - Tipo (capital, operacional, interno, externo).
  - Aplicativos, serviços ou produtos relacionados.
  - Mapeamentos entre o custo do projeto e os resultados de faturamento quando os projetos são faturados ou usados como consumidores.
- **Pessoas jurídicas e impostos**
  - Códigos de pessoas jurídicas e empresas.
  - Atributos fiscais e interempresariais.
  - Utilizado para preços de transferência e relatórios ao nível da entidade jurídica.
- **Tabelas mestre específicas para faturamento**
  - Catálogo de ofertas faturáveis e listas de preços, semelhante ao Essentials, mas alinhado com o modelo de domínio mais rico.
  - Configuração da taxa unitária e da variação por domínio.

Padrões de integração para o padrão de faturamento:

- As fontes de dados são mais amplas e geralmente incluem:
  - CMDB e sistemas de ativos.
  - Arquivos de faturamento e APIs do provedor de nuvem.
  - Ferramentas PPM (para dados do projeto).
  - Sistemas de RH ou diretório (para mapeamento de usuários e propriedade).
  - Sistemas financeiros para pessoas jurídicas e atributos fiscais.
- ETL e integração são:
  - Frequentemente implementado com o Datalink, plataformas de integração ou processos em lote no TBM Studio.
  - Normalmente regido por uma propriedade de dados e um controle de qualidade mais rigorosos, uma vez que há mais domínios e mais partes interessadas.

A intenção é modelar a tecnologia e a realidade financeira uma vez e, em seguida, reutilizar esses mestres de domínio em Cálculo de Custos e Faturamento, em vez de manter listas separadas e duplicadas.
