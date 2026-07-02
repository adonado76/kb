---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Adicionar dados da unidade de negócios"
breadcrumb: []
source_path: "boit/business-unit-data.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Adicionar dados da unidade de negócios

Se o componente **CT - Unidades de negócios** tiver sido instalado e configurado na Transparência de custos, ignore esta etapa. Se o componente não tiver sido instalado, você deverá adicionar dados à tabela Dados mestre de alocação de unidades de negócios.

1. Faça upload de um arquivo que contenha os dados comerciais em uma tabela no projeto Billing Standard . Coloque a tabela na categoria **General** e nomeie-a como `Business Unit
   Data` . Consulte [Carregar um arquivo de dados](../studio/data_studio/upload-data-file.html "Aplica-se a: TBM Studio 12.0 e posterior. O TBM Studio aceita dados de arquivos simples nos formatos separados por vírgula, tabulação, pipe, til, dois pontos e ponto e vírgula. Antes de fazer upload de dados, você deve criar uma tabela na qual os dados serão carregados, caso ela ainda não exista.") para obter mais informações.
2. Anexar a tabela de dados da unidade de negócios à tabela de dados mestre de alocação da unidade de negócios. Consulte [Anexar dados](../studio/data_studio/append-data.html "Aplica-se a: TBM Studio 12.0 e posterior") para obter mais informações.

Dados necessários dos dados mestre de alocação de unidades de negócios

- **Unidade de negócios** - Um elemento lógico ou segmento de uma empresa que representa uma função comercial específica e um lugar no organograma. A unidade de negócios está sob o domínio de um gerente. Em Billing Standard, a Unidade de Negócios é o nível 1 na hierarquia da organização e o Departamento é o nível 2.
- **Ident** - Um identificador exclusivo para cada unidade de negócios.

Dados recomendados dos dados mestre de alocação de unidades de negócios

- **Headcount de contratados** - O número de contratados externos que trabalham na unidade de negócios.
- Número de **funcionários** - O número de funcionários em tempo integral ou mão de obra não contratada trabalhando na unidade de negócios.
- **Localização** - A localização física/geográfica da unidade de negócios. Nos relatórios de unidades de negócios, a localização é usada para agrupar dados e fornecer um nível adicional de granularidade.

Dados opcionais dos dados mestre de alocação de unidades de negócios

- **Órgão** dirigente - O órgão dirigente é uma entidade de nível mais alto na estrutura da organização do que a unidade de negócios.   
   **Exemplos** : entidades operacionais, entidades internacionais.
