---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Custo Total de Propriedade (TCO) de Centros de Dados - Introdução"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso de infraestrutura"
  - "Datacenters"
source_path: "cost-transparency/infra-use-cases/dc-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Custo Total de Propriedade (TCO) de Centros de Dados - Introdução

A solução de TCO para data centers permite que as organizações compreendam o custo total, a capacidade, a utilização e as restrições operacionais de sua infraestrutura de data center. Ele oferece visibilidade sobre os custos das instalações, o consumo de energia e refrigeração, a densidade dos racks e as alocações de infraestrutura, a fim de apoiar a otimização, a consolidação e o planejamento de investimentos de longo prazo.

## Instalação de componentes

**Custo total de propriedade (TCO) dos data centers**

O componente de Custo Total de Propriedade (TCO) dos Centros de Dados fornece a estrutura básica necessária para modelar, alocar e gerar relatórios sobre custos, capacidade, utilização e restrições operacionais dos centros de dados. O componente instala os conjuntos de dados, tabelas editáveis, métricas, lógica de alocação e estruturas de dados essenciais necessárias para analisar as operações do data center e estabelecer uma economia de unidade justificável entre locais e instalações.

Este componente é necessário antes de instalar qualquer um dos componentes de relatórios abaixo:

- **Relatórios de TCO de Centros de Dados** – Instala os relatórios clássicos para a elaboração de relatórios e análise do TCO de Centros de Dados
- **Relatórios de TCO de data centers no NX** – Instala os relatórios do NX para a geração de relatórios e análise do TCO de data centers.

Os clientes podem instalar o componente de relatórios Classic ou NX, de acordo com sua preferência em termos de experiência com relatórios. No entanto, o componente de TCO dos data centers básicos deve ser instalado primeiro em todos os cenários.

## Pré-requisitos

É necessário instalar os seguintes componentes antes de instalar a solução Data Centers TCO:

- CTF – Origem do custo
- CTF – IT Towers
- CTF – Trabalho
- CTF – Fornecedores

Os componentes opcionais incluem:

- Aplicativos CT – Servidores
- Aplicativos de tomografia computadorizada – Armazenamento
- Aplicativos CT – Mainframes
- Aplicativos de TC – Aplicativos
- Aplicativos de TC – Serviços
- Custo total de propriedade do produto

## Fontes comuns de dados

Os dados relativos a custos, utilização e operações dos data centers são normalmente obtidos a partir de:

- Contabilidade geral e sistemas financeiros
- Plataformas de gerenciamento de infraestrutura de data center (DCIM)
- Sistemas de monitoramento de energia e refrigeração
- CMDB e plataformas de gestão de ativos
- Sistemas de gestão de instalações
- Sistemas de fornecedores e compras

Essas fontes fornecem metadados financeiros, de capacidade, de infraestrutura e operacionais utilizados para alocação, análise de utilização e relatórios de economia de unidade.

## Conjuntos de dados

O principal conjunto de dados para a solução é a tabela “Data Centers Feed”. Carregue e mapeie os dados operacionais, financeiros e de capacidade do data center para os Dados Mestres de Data Centers fornecidos com o componente.

Os atributos comuns de conjuntos de dados incluem:

- ID e nome do data center
- Região e tipo de instalação
- Capacidade e utilização das unidades de rack
- Capacidade e consumo de energia
- Capacidade de refrigeração e utilização
- Área útil e espaço ocupado
- Gerente, Nível e Metadados Operacionais

Após carregar e mapear os dados, valide as alocações para garantir que os custos do data center sejam corretamente atribuídos aos objetos de computação, armazenamento e infraestrutura de suporte, a fim de permitir a geração de relatórios e análises posteriores.
