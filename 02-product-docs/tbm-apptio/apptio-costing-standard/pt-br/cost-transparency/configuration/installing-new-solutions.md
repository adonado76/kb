---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Instalação de novas soluções de custeio IBM Apptio em projetos de modelos mais antigos"
breadcrumb: []
source_path: "cost-transparency/configuration/installing-new-solutions.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Instalação de novas soluções de custeio IBM Apptio em projetos de modelos mais antigos

## Termos-chave que você deve conhecer

**Versão do servidor:**

- Refere-se à versão do software IBM Apptio TBM Studio instalado. Determina os recursos e a compatibilidade da plataforma.
- Os usuários podem verificar sua versão atual em: Configurações > Sobre
- Série atual: 12.11.1x

**Versão do modelo/componente:**

- Refere-se à versão do conteúdo Out-of-the-Box (OOTB) (tabelas de dados, modelos, relatórios).
- Cada solução está vinculada a uma versão específica do componente.
- Verifique-o em: TBM Studio > Projeto > Configurações do projeto > Versão do componente

Importante:

- Para instalar as novas soluções, NÃO é necessário atualizar todos os componentes existentes.
- Consulte a tabela na próxima página para identificar a versão do servidor e a versão do modelo necessárias para a solução desejada.

## Guia passo a passo

1. **Verifique a versão do servidor:** certifique-se de que a versão do servidor da sua instância seja igual ou mais recente do que a versão de lançamento da solução.
2. **Identifique a versão necessária do componente:** Use a tabela de versões de soluções para encontrar a versão do componente (por exemplo, v120 ).
3. **Alterar temporariamente a versão do componente:** Navegue até Projeto > "Configurações do projeto". Altere a versão do componente para corresponder à versão da solução.
4. **Instale os componentes da solução:** Vá para a guia Componentes e instale os componentes necessários da solução.
5. **Atualizar os componentes existentes (se necessário):** Reverter e reaplicar as personalizações depois de atualizar os componentes OU aplicar manualmente as alterações nas tabelas mestre de acordo com o Guia de configuração.
6. **Reverter a alteração das "Configurações do projeto":** retorne à versão original do componente para evitar avisos de atualização.

Para saber mais, assista ao vídeo: [Como instalar os novos componentes da solução de custeio IBM Apptio em projetos com versões mais antigas do modelo](https://community.ibm.com/community/user/viewdocument/how-to-install-new-ibm-apptio-costi?CommunityKey=2e85ed45-9b8a-486c-bd55-019253d466eb "(Abre em uma nova guia ou janela)")

Dica: Documente as alterações personalizadas para facilitar a reaplicação. Consulte sempre o Guia de Configuração fornecido com a solução.

## Detalhes da versão da solução

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| IBM Apptio Cálculo de custos  Novas soluções | Fundamentos do cálculo de custos | Padrão de cálculo de custos | Modelo | Versão do servidor |
| Impacto do TCO da TI híbrida | - | Sim | v120 | 12.11.12 |
| TCO da nuvem pública | Sim | Sim | v120 + v200 | 12.11.13 |
| Apptio - Integração Turbonômica (GA) | - | Sim | v120 | 12.11.13 |
| TCO e uso de IA | - | Sim | v120 | 12.11.14 |
| TCO do mainframe | - | Sim | v120 | 12.11.17 |
| Informações sobre os custos de manutenção do Maximo | N.A. | N.A. | v200 | 12.11.17 |
| Relatórios de tomada de custos | - | Sim | v120 | 12.11.17 |
| TCO do produto | - | Sim | v120 | 12.11.18 |
