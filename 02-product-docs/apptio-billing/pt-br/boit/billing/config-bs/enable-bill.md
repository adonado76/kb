---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Habilitando o endpoint do padrão de faturamento e o acesso ao relatório"
breadcrumb:
  - "Billing"
  - "Configurando o padrão de faturamento (implementação)"
source_path: "boit/billing/config-bs/enable-bill.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Habilitando o endpoint do padrão de faturamento e o acesso ao relatório

Com o conteúdo validado no Staging, o endpoint e os relatórios podem ser preparados para os usuários.

Passos:

1. **Confirmar ligação do terminal padrão de faturamento**
   - Certifique-se de que o ponto final aponte para o projeto e os ambientes corretos do Padrão de Cálculo de Custos.
2. **Promova os relatórios necessários para o terminal**
   - Decida quais coleções de relatórios estão dentro do escopo para a entrada em operação:
     - Serviços e consumidores.
     - Nuvem.
     - Aplicações.
     - Infraestrutura.
     - Projetos.
     - Variação/preços.
     - Revistas.
     - Publique-os e categorize-os adequadamente.
3. **Configurar acesso ao relatório**
   - Alinhe o acesso aos relatórios com as funções:
     - Administradores e analistas: acesso amplo.
     - Proprietários de serviços ou produtos: visualizações relevantes para seus domínios.
     - Finanças: relatórios de taxa unitária, variação e diário.
4. **Teste o endpoint**
   - Faça login com um perfil de usuário típico.
   - Confirmar:
     - Os relatórios são abertos e respondidos.
     - Os filtros e as pesquisas detalhadas funcionam.

A segurança funciona conforme o esperado.
