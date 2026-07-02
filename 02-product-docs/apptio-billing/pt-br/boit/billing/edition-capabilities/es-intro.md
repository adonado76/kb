---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Visão geral e resumo das edições"
breadcrumb:
  - "Billing"
  - "Administração e Operações"
  - "Edição e recursos"
source_path: "boit/billing/edition-capabilities/es-intro.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Visão geral e resumo das edições

O faturamento está disponível em duas edições: **Faturamento Básico** e **Faturamento Padrão**.

Eles resolvem o mesmo problema central, mas com diferentes níveis de escopo e flexibilidade.

- Uma determinada organização utiliza **uma edição de faturamento por vez**, alinhada com seu projeto de cálculo de custos.
- **O Billing Essentials** é fornecido por meio do modelo de componente **versão 200** em conjunto com uma implementação **do Costing Essentials**.
- **O Padrão de Faturamento** é fornecido por meio de modelos de componentes **versão 120 e anteriores,** em conjunto com uma implementação **do Padrão de Cálculo de Custos**.

## Resumo da edição

**Fundamentos de faturamento**

- Concentra-se em implementar um **processo de faturamento ou showback ( PxQ** ) limpo e repetível.
- Aparece como uma **coleção de relatórios de faturamento** no mesmo projeto que executa o Costing Essentials.
- A personalização é limitada aos relatórios.
- Enfatiza:
  - Contas simples e compreensíveis.
  - Definição simples de tarifas e cálculo de encargos.
  - Área de configuração mínima.

## Padrão de faturamento

- Inclui todos os recursos essenciais do Billing Essentials.
- Adiciona um **conjunto mais amplo de componentes** para oferecer suporte:
  - Visualizações específicas do domínio (nuvem, servidores, armazenamento, aplicativos, projetos, dispositivos do usuário final).
  - Análise e otimização da taxa unitária.
  - Análise de variação de custo vs. plano vs. preço.
  - Relatórios entre empresas e entidades jurídicas.
- Exibido por meio de um **endpoint de faturamento separado**, além do endpoint do projeto Padrão de Custeio.

**Comparação de recursos** A tabela abaixo resume como as edições se comparam em áreas típicas de recursos.

| **Área de capacidade** | **Exemplos** | **Fundamentos de faturamento** | **Padrão de faturamento** |
| --- | --- | --- | --- |
| **Classificação do núcleo PxQ** | Multiplique as unidades pelas taxas para calcular os encargos por período | Sim | Sim (inclui comportamento Essentials) |
| **Gestão de taxas básicas** | Manter tabelas de tarifas e marcar ofertas como faturáveis | Sim | Sim (com visualizações adicionais de taxas específicas do domínio) |
| **Geração de contas/faturas** | Relatórios, exportações e arquivos online no formato de fatura | Sim | Sim (mais detalhamentos adicionais por domínio) |
| **Validação e revisão de contas** | Valide as cobranças antes da liberação, investigue anomalias | Sim | Sim (com detalhamento mais específico por domínio) |
| **Preparação do diário** | Exportar dados prontos para o diário para Finanças | Sim | Sim |
| **Visualizações de faturamento específicas da nuvem** | Taxas unitárias de nuvem, detalhamento por provedor e por serviço | Limitado\* | Pronto para uso (nuvem e componentes relacionados) |
| **Visões centradas em aplicativos** | Cobranças por aplicativo, família de aplicativos ou portfólio | Limitado\* | Pronto para uso (aplicativos e relatórios relacionados) |
| **Visões do domínio de infraestrutura** | Servidores, armazenamento, dispositivos do usuário final, etc. | Limitado\* | Pronto para uso (servidores, armazenamento, dispositivos do usuário final) |
| **Visões centradas no projeto** | Encargos e recuperação por projeto, programa ou iniciativa | Limitado\* | Pronto para uso (Projetos e visualizações relacionadas) |
| **Análise e otimização da taxa unitária** | Tendências, variação e análise dos fatores determinantes para as taxas unitárias | Limitado\* | Análise ampliada e específica do domínio |
| **Custo vs. plano vs. variação de preço** | Compare o custo real, o custo planejado e o preço/recuperação | Limitado\* | Fora da caixa (variação de custo, variação do plano, preço) |
| **Preços de transferência e entidades jurídicas** | Fluxos entre empresas, visão da entidade jurídica sobre encargos e efeitos fiscais | Não | Pronto para uso (preços de transferência entre empresas, dados fiscais) |
| **Suporte a cenários/previsões** | Compare diferentes taxas, volumes ou pressupostos de serviço | Limitado\* | Ampliado (planejamento mais estruturado e uso de variações) |

\* Conteúdo limitado pronto para uso. Personalizações permitidas apenas para relatórios.
