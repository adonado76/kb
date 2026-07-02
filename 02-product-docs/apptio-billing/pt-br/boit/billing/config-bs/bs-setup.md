---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Configuração de serviços e ofertas"
breadcrumb:
  - "Billing"
  - "Configurando o padrão de faturamento (implementação)"
source_path: "boit/billing/config-bs/bs-setup.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Configuração de serviços e ofertas

O catálogo do que é faturado é central, independentemente da edição, mas o Padrão de Faturamento frequentemente precisa de uma ligação mais rica com os domínios.

Passos:

1. **Revisar o catálogo de serviços/produtos existente**
   - Reutilize o que já está definido em Cálculo de custos, sempre que possível.
   - Confirmar:
     - Os nomes são significativos para as partes interessadas nos negócios.
     - Cada serviço/produto pode ser mapeado para objetos de domínio subjacentes (aplicativos, nuvem, servidores, etc.) onde necessário.
2. **Preencha ou atualize a tabela de serviços**
   - Para cada serviço ou produto:
     - Atribua um ID de serviço/oferta estável.
     - Defina um nome e uma descrição claros.
     - Defina a unidade de medida.
     - Defina o status (ativo/aposentado) e os sinalizadores faturáveis.
3. **Vincule serviços a domínios**
   - Dependendo do design:
     - Mapeie serviços para aplicativos (para visualizações centradas em aplicativos).
     - Mapeie serviços para servidores ou pools de armazenamento.
     - Mapeie serviços para contas na nuvem/agrupamentos de tags.
     - Mapeie os serviços para projetos ou portfólios, se for o caso.

Sugestões de design:

- Evite um serviço por cada pequeno componente técnico. Agrupe os componentes técnicos em serviços que façam sentido para os negócios.
- Use links de domínio para enriquecer a análise, não para complicar demais o catálogo.
