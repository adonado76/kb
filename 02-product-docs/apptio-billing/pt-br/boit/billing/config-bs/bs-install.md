---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Instalando componentes padrão de faturamento"
breadcrumb:
  - "Billing"
  - "Configurando o padrão de faturamento (implementação)"
source_path: "boit/billing/config-bs/bs-install.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Instalando componentes padrão de faturamento

O Padrão de Faturamento é fornecido como um conjunto de componentes instalados no projeto Padrão de Custeio existente. O endpoint Billing Standard na interface do usuário exibe o conteúdo criado por esses componentes.

Componentes típicos (os nomes podem variar ligeiramente de acordo com a versão):

- financeira
- Unidades
- Serviços/Ofertas (frequentemente parte da Fundação)
- Aplicativos
- Servidores
- Armazenamento
- Dispositivos do usuário final
- NUVEM
- Projetos
- Preço
- Variação de custos
- Variação do plano
- Preços de transferência entre empresas

Etapas de alto nível:

1. Abra o **projeto Padrão de Custeio** no TBM Studio.
2. Navegue até a área de gerenciamento de componentes.
3. Selecione e instale os componentes necessários do Padrão de Faturamento.
4. Confirme a instalação:
   - Adiciona os modelos, conjuntos de dados, tabelas e métricas esperados.
   - Cria coleções de relatórios que serão exibidas no endpoint Padrão de Faturamento.

Verificações pós-instalação:

- Todos os modelos padrão de faturamento são compilados com sucesso em Desenvolvimento.
- As tabelas de domínios principais (Aplicativos, Servidores, Armazenamento, Nuvem, Projetos, Dispositivos, Pessoas jurídicas, Unidades, Preço) estão visíveis no modelo de dados.
- O endpoint do Padrão de Faturamento é provisionado e vinculado ao projeto, mesmo que os relatórios ainda não tenham sido promovidos.
