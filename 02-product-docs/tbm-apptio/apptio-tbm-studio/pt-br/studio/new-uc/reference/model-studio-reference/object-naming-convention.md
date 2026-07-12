---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Convenções de nomenclatura de objetos"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Model Studio"
  - "Objetos modelo"
source_path: "studio/new-uc/reference/model-studio-reference/object-naming-convention.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Convenções de nomenclatura de objetos

Uma nomenclatura consistente melhora a facilidade de manutenção do modelo e a compreensão do usuário.

**Padrões de nomenclatura recomendados**

|  |  |  |
| --- | --- | --- |
| **Padrão** | **Formato** | **Exemplo** |
| Fontes de custo | [Tipo] [Período/Qualificador] | Valores reais da fonte de custo, Orçamento da fonte de custo |
| Centros de custo | [Categoria] [Qualificador] | Dados reais de mão de obra, dados reais de instalações, ativos imobilizados |
| da nuvem e híbrida | [Tipo de recurso] | Servidores, Armazenamento, Rede, Centros de Dados |
| Serviços | [Categoria de serviço] | Serviços de Tecnologia, Aplicações Empresariais |
| Consumidores | [Tipo de consumidor] | Unidades de Negócios, Departamentos, Clientes |

**Melhores práticas de nomenclatura**

- Use nomes descritivos que indiquem a função do objeto no modelo
- Inclua o qualificador “Real”, “Orçamento” ou “Previsão” quando os objetos forem específicos de uma métrica
- Evite caracteres especiais que possam causar problemas em fórmulas ou relatórios
- Escolha nomes concisos, mas que não percam o sentido
- Descreva a finalidade do objeto no campo Descrição

**Observação:** os nomes dos objetos aparecem nos relatórios do modelo e são visíveis aos usuários finais. Escolha nomes que façam sentido para as partes interessadas.

**Problemas comuns**

|  |  |  |
| --- | --- | --- |
| **Problema** | **Causa** | **Resolução** |
| O objeto modelo não está visível | Etapa do modelo não adicionada à tabela | Adicionar etapa do modelo à transformação da tabela |
| Não é possível criar a alocação | Mesas não reservadas | Verifique tanto o texto de origem quanto o de destino |
| Não há dados no objeto modelo | Erros de transformação ou falta de ponto final | Verifique se a transformação Data Studio foi bem-sucedida |
| Valores de identificador duplicados | Configuração de identificador não exclusivo | Adicione colunas ao identificador para garantir a exclusividade |

*→ Consulte [a seção “Problemas comuns” para obter orientações detalhadas sobre o diagnóstico e a solução de problemas](../../ts-support/ds-issues.html)*

**Tópico principal:** [Objetos de modelo](../../../../studio/new-uc/reference/model-studio-reference/model-objects.html)
