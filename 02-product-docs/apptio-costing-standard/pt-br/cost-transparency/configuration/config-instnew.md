---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Instalação de novas soluções de custeio IBM Apptio em projetos de modelos mais antigos"
breadcrumb:
  - "Costing Standard"
  - "Configuração"
source_path: "cost-transparency/configuration/config-instnew.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Instalação de novas soluções de custeio IBM Apptio em projetos de modelos mais antigos

## Termos-chave

**Versão do servidor**

- Refere-se à versão do software IBM Apptio TBM Studio instalado. Determina os recursos e a compatibilidade da plataforma.
- Para verificar a versão atual, navegue até **Configurações** > **Sobre.**
- Série atual: 12.11.1x

**Versão do modelo/componente**

- Refere-se à versão do conteúdo pronto para uso (OOTB) (Tabelas de dados, modelos, relatórios).
- Cada solução está vinculada a uma versão específica do componente.
- Para verificar a versão do componente, navegue até **TBM Studio** > **Projeto** > **Configurações do projeto** > **Versão do componente.**

Nota:

- Para instalar as novas soluções, você não precisa atualizar todos os componentes existentes.
- Consulte a seção **[Detalhes](#aicot__solutionversiontable "(Abre em uma nova guia ou janela)")** da versão da solução para identificar a versão do servidor e a versão do modelo necessárias para a solução desejada.

**Passos**

- **Verifique a versão do servidor** : certifique-se de que a versão do servidor da sua instância seja igual ou mais recente que a versão de lançamento da solução.
- **Identifique a versão do componente necessária** : use **[os detalhes da versão da solução](#aicot__solutionversiontable "(Abre em uma nova guia ou janela)")** para encontrar a versão do componente (por exemplo, v120 ).
- **Alterar temporariamente a versão do componente** : Navegue até **Projeto** > **Configurações do projeto**. Altere a versão do componente para corresponder à versão da solução.
- **Instale os componentes da solução** : navegue até a guia **Componentes** e instale os componentes necessários da solução.
- **Atualize os componentes existentes (se necessário)** : reverta e reaplique as personalizações após atualizar os componentes ou aplique manualmente as alterações nas tabelas mestras, conforme o Guia de Configuração.
- **Reverter alteração nas “Configurações do projeto** ”: Retorne à versão original do componente para evitar avisos de atualização.

**Dicas profissionais**

- Documente as alterações personalizadas para facilitar a reaplicação.
- Consulte sempre o Guia de Configuração fornecido com a solução.
- Podemos ter várias versões de diferentes componentes em um projeto.

## Detalhes da versão da solução

Tabela 1. Detalhes da versão da solução

| IBM Apptio Cálculo de custos de novas soluções | Fundamentos de Cálculo de Custos | Padrão de Custeio | Modelo | Versão do servidor |
| --- | --- | --- | --- | --- |
| Impacto do TCO da TI híbrida | - | Sim | v120 | 12.11.12 |
| Custo total de propriedade da nuvem pública | Sim | Sim | v120+v200 | 12.11.13 |
| Apptio - Integração com o Turbonomic (versão estável) | - | Sim | v120 | 12.11.13 |
| Custo total de propriedade (TCO) e uso da IA | - | Sim | v120 | 12.11.14 |
| Custo total de propriedade do mainframe | - | Sim | v120 | 12.11.17 |
| Informações sobre custos de manutenção do Maximo | N/A | N/A | v200 | 12.11.17 |
| Relatórios de redução de custos | - | Sim | V120 | 12.11.17 |
| Custo total de propriedade do produto | - | Sim | v120 | 12.11.18 |
| Custo total de propriedade (TCO) do data center | - | Sim | v120 | 12.11.22 |
| Relatórios OOTB modernizados – Lote 1 (Finanças, Fornecedores, Aplicativos, Mão de obra, Custo total de propriedade (TCO) da nuvem pública, Custo total de propriedade (TCO) do mainframe, Custo total de propriedade (TCO) da IA, Serviços) | - | Sim | v120 | 12.11.22 |
