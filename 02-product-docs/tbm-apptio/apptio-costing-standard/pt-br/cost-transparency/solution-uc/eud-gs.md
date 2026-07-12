---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Dispositivos do usuário final Introdução"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso da solução"
  - "Usuário final"
source_path: "cost-transparency/solution-uc/eud-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Dispositivos do usuário final Introdução

O componente Dispositivos do usuário final permite que as organizações compreendam o custo total de propriedade dos dispositivos da força de trabalho, como PCs, laptops, smartphones, tablets e outros equipamentos de computação do cliente. Este componente permite a alocação precisa dos custos dos dispositivos dos usuários finais aos serviços e unidades de negócios que os utilizam.

## Instalação de componentes

**Aplicativos de TC – Dispositivos do usuário final**

O componente CT Apps – Dispositivos do usuário final instala as estruturas de dados fundamentais, conjuntos de dados e estratégias de alocação recomendadas necessárias para calcular o TCO do dispositivo do usuário final. Ele oferece suporte à alocação de custos de dispositivos para serviços de usuários finais e serviços comerciais específicos, nos quais são utilizados recursos de computação distribuídos.

## Pré-requisito

Você deve instalar os seguintes componentes antes de instalar o componente Dispositivos do usuário final:

CTF - Fonte de custos

CTF - Torres de TI

## Fontes comuns de dados

Os dados relativos aos custos e ao inventário dos dispositivos dos usuários finais são normalmente obtidos a partir de sistemas de contabilidade geral, plataformas de gestão de ativos, ferramentas de gestão de terminais e sistemas de aquisição. Essas fontes determinam o nível de detalhes disponíveis para a análise de custo, propriedade e alocação do dispositivo.

## Conjuntos de dados

Quando você instala o componente CT Apps – Dispositivos do usuário final, um novo grupo Dispositivos do usuário final é criado com as seguintes tabelas:

• Dispositivos do usuário final (tabela de modelos)

• Dados principais dos dispositivos do usuário final

Após carregar os dados do dispositivo do usuário final, mapeie o conjunto de dados para a tabela Dados Mestres dos Dispositivos do Usuário Final. Uma vez mapeados, os custos fluem das Torres de Recursos de TI e Comunicações para os Dispositivos dos Usuários Finais e, dos Dispositivos dos Usuários Finais, para os serviços comerciais consumidores dentro do modelo de custos.
