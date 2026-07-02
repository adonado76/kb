---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Instalação de novas soluções de custeio IBM Apptio em projetos de modelos mais antigos"
breadcrumb: []
source_path: "cost-transparency/configuration/install-apptio-ibm-costing-old-template.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Instalação de novas soluções de custeio IBM Apptio em projetos de modelos mais antigos

## Termos-chave

**Versão do servidor**

- Refere-se à versão do software IBM Apptio TBM Studio instalado. Determina os recursos e a compatibilidade da plataforma.
- Para verificar a versão atual, navegue até **Configurações** > **Sobre**
- Série atual: 12.11.1x

**Versão do modelo/componente**

- Refere-se à versão do conteúdo Out-of-the-Box (OOTB) (tabelas de dados, modelos, relatórios).
- Cada solução está vinculada a uma versão específica do componente.
- Para verificar a versão do componente, navegue até **TBM Studio** > **Project** > **Project Settings** > **Component Version**

Nota:

- Para instalar as novas soluções, não é necessário atualizar todos os componentes existentes.
- Consulte a seção **[Detalhes da versão da solução](#aicot__solutionversiontable "(Abre em uma nova guia ou janela)")** para identificar a versão do servidor e a versão do modelo necessárias para a solução desejada.

**Passos**

- **Verifique a versão do servidor** : Certifique-se de que a versão do servidor de sua instância seja igual ou mais recente do que a versão de lançamento da solução.
- **Identifique a versão necessária do componente** : Use **[os detalhes da versão da solução](#aicot__solutionversiontable "(Abre em uma nova guia ou janela)")** para encontrar a versão do componente (por exemplo, v120 ).
- **Alterar temporariamente a versão do componente** : Navegue até **Projeto** > **Configurações do projeto**. Altere a versão do componente para corresponder à versão da solução.
- **Instale os componentes da solução** : Navegue até a guia **Componentes** e instale os componentes necessários da solução.
- **Atualize os componentes existentes (se necessário)** : Reverta e reaplique as personalizações depois de atualizar os componentes ou aplique manualmente as alterações nas tabelas mestre, de acordo com o Guia de configuração.
- **Reverter a alteração das "Configurações do projeto"** : Retornar à versão original do componente para evitar avisos de atualização.

**Dicas profissionais**

- Documente as alterações personalizadas para facilitar a reaplicação.
- Consulte sempre o Guia de Configuração fornecido com a solução.
- Podemos ter várias versões de diferentes componentes em um projeto.

## Detalhes da versão da solução

Tabela 1. Detalhes da versão da solução

| IBM Apptio Cálculo de custos de novas soluções | Fundamentos do cálculo de custos | Padrão de cálculo de custos | Modelo | Versão do servidor |
| --- | --- | --- | --- | --- |
| Impacto do TCO da TI híbrida | - | Sim | v120 | 12.11.12 |
| TCO da nuvem pública | Sim | Sim | v120+v200 | 12.11.13 |
| Apptio - Integração Turbonômica (GA) | - | Sim | v120 | 12.11.13 |
| TCO e uso de IA | - | Sim | v120 | 12.11.14 |
| TCO do mainframe | - | Sim | v120 | 12.11.17 |
| Informações sobre os custos de manutenção do Maximo | N/A | N/A | v200 | 12.11.17 |
| Relatórios de tomada de custos | - | Sim | V120 | 12.11.17 |
| TCO do produto | - | Sim | v120 | A ser lançado |
