---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Dimensionamento correto avançado"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Redimensionamento em Cloudability Premium"
source_path: "product/advanced-rightsizing-powered-by-turbonomic.html"
images:
  - "images/advanced-rightsizing-explorer.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Dimensionamento correto avançado

## Ações de otimização com tecnologia Turbonomic

Turbonomic O mecanismo que alimenta o Cloudability coleta métricas históricas de utilização de recursos para analisar o desempenho da carga de trabalho de forma holística e, em seguida, recomenda ações de otimização para dimensionar essas cargas de trabalho, a fim de garantir o desempenho ao menor custo possível.

Turbonomic O mecanismo gera ações de otimização para recursos de nuvem e Kubernetes em seu ambiente de nuvem pública, garantindo que seus aplicativos recebam a alocação precisa de recursos de computação, armazenamento e rede em todos os níveis da pilha de tecnologia. Ao otimizar continuamente a alocação de recursos, sua organização pode alcançar um desempenho garantido, economia significativa de tempo e otimização ideal de custos.

Atualmente, as ações do serviço de máquina virtual, disco e controlador de carga de trabalho em AWS, Microsoft Azure e Google Cloud são suportadas em Cloudability Premium, com tecnologia Turbonomic.

Observação: você precisa garantir que todas as credenciais de fornecedores existentes tenham as permissões relevantes exigidas pelo Turbonomic concedidas, sem as quais o mecanismo Turbonomic pode não ser capaz de gerar o conjunto correto de ações. Se você era um cliente Cloudability antes da atualização para Cloudability Premium, ainda precisa renovar todas as credenciais de fornecedor para conceder um conjunto adicional de permissões.

## Painel de controle avançado para redimensionamento

O painel do Advanced Rightsizing exibe a guia Explorer por padrão. O Rightsizing Explorer oferece uma visão geral das possíveis economias ou investimentos em todos os recursos de nuvem usados pela sua empresa. Você pode usar este painel para agrupar, filtrar e navegar pelas suas ações de otimização.

As guias adicionais em Redimensionamento avançado são ações de otimização para provedores de nuvem específicos.

[Explorador avançado de redimensionamento](advanced-rightsizing-explorer.html)

![](../../../../03-media/cloudability-premium/images/advanced-rightsizing-explorer.png)

## Perguntas frequentes sobre ações de otimização

Por que os períodos de ação são suportados?

Turbonomic suporta um período retroativo de 7 a 90 dias. Elas podem ser configuradas nas políticas globais ou de escopo.

Por que o gasto total nesta página não corresponde exatamente aos valores mostrados em Relatórios/Explorador de custo real?

As ações de otimização listam apenas os recursos para os quais foi encontrado pelo menos um recurso que permite economizar dinheiro, portanto, é provável que esses valores não correspondam exatamente.

Com que frequência as ações são atualizadas?

Atualizamos as ações de otimização a cada hora. Você pode acessar recomendações para recursos 24 horas após a criação do recurso, desde que haja dados de utilização suficientes.

Quais serviços em nuvem e quais ações são suportados atualmente no Cloudability Premium?

Os serviços de máquina virtual, volume/disco e controlador de carga de trabalho são suportados no Cloudability Premium até o momento. Em termos de ações, as ações de dimensionamento, redimensionamento e suspensão são suportadas para máquinas virtuais, as ações de dimensionamento e exclusão são suportadas para serviços de volume/disco e as ações de redimensionamento para serviços de controlador de carga de trabalho.

- **[Explorador avançado de redimensionamento](../product/advanced-rightsizing-explorer.html)**
- **[AWS EC2](../product/advanced-rightsizing-for-aws-ec2.html)**
- **[AWS EBS](../product/advanced-rightsizing-for-aws-elastic-block-store.html)**
- **[AWS RDS](../product/aws_rds.html)**
- **[Azure Calcular](../product/advanced-rightsizing-for-azure-compute.html)**
- **[Azure Disco](../product/advanced-rightsizing-for-azure-disks.html)**
- **[Azure SQL](../product/azure_sql.html)**
- **[GCP Google Compute Engine (GCE)](../product/advanced-rightsizing-for-gce.html)**
- **[GCP Google Disco persistente (GPD)](../product/advanced-rightsizing-for-gpd.html)**
- **[Redimensionamento avançado para contêineres d Kubernetes](../product/advanced-k8s-container-rightsizing.html)**
- **[Execução da ação](../product/action_execution.html)**
- **[Preferências de redimensionamento](../product/premium-rightsizing-preferences.html)**

**Tópico principal:** [Redimensionamento em Cloudability Premium](../product/rightsizing-in-cloudability-premium.html)
