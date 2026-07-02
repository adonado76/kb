---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Criar e gerenciar políticas"
breadcrumb:
  - "Cloudability Premium"
  - "Governança"
source_path: "admin/governance-create-and-manage-policies.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Criar e gerenciar políticas

A governança permite que as equipes apliquem as práticas recomendadas do FinOps por meio de políticas de governança:

## Tipos de políticas

1. **Políticas de marcação** : Garantir que os recursos tenham as tags necessárias (por exemplo, "Ambiente: Produção").
2. **Políticas de tipo de recurso ( AWS / Azure Resource)** : Definem regras para os atributos dos recursos (por exemplo, determinam o tamanho da instância e a memória).
3. **Barreiras de custo** : Defina deltas de custo máximos permitidos para alterações no site IaC.

## Níveis de aplicação

- **Recomendações** : Essas falhas de política não bloqueiam o fluxo de trabalho do Pull Request. Um aviso é exibido, permitindo que o fluxo de trabalho prossiga sem interrupção. **Recomendamos usar esse nível de aplicação como um ponto de partida.**
- **Bloqueado** : Essas falhas de política interrompem o fluxo de trabalho do Pull Request quando combinadas com a configuração no repositório do Github para bloquear o PR para execuções de verificação de governança com falha. Os usuários com a função de aprovador de PR de governança Cloudability podem substituir e continuar o fluxo de trabalho na página Governance Pull Request Details.

## Implicações para clientes do HCP Terraform ou Terraform Enterprise

O HCP Terraform aplica seu próprio nível de imposição às Run Tasks, que pode ser definido como **Advisory** ou **Mandatory**. Às vezes, essa configuração pode entrar em conflito com os níveis de aplicação definidos nas políticas do site Cloudability.

Recomendamos configurar o nível de aplicação do HCP Terraform Run Task como **Advisory**. Por exemplo:

- Se uma política **de consultoria** do Cloudability falhar, o PR não será bloqueado e os engenheiros ainda poderão aplicar a alteração no HCP Terraform.
- Se uma política Cloudability **Gated** falhar, o PR será bloqueado e os engenheiros não poderão aplicar a alteração no HCP Terraform até que o problema seja resolvido.
  - Depois que a alteração for revisada e aprovada em Cloudability, os engenheiros poderão mesclar o PR, e uma nova execução deverá ser acionada no HCP Terraform para aplicar a alteração.
  - Esse fluxo de trabalho de aprovação **não** funciona se a tarefa de execução do HCP estiver definida como **Obrigatória**, porque o site Cloudability não pode substituir o status do HCP.

## Aplicativo de política

As políticas podem ser aplicadas no:

- **Nível da organização** : Aplica-se a todos os fluxos de trabalho.
- **Nível de projeto** : Aplica-se a implementações específicas.

Os resultados da avaliação de políticas são exibidos como comentários de PR, destacando recursos e regras com falhas.

Observação: as políticas em nível de organização têm como escopo a organização de capacidade de nuvem; a organização GitHub não é relevante, ou seja, uma política em nível de organização afetará todas as implantações, independentemente da organização GitHub à qual estejam associadas.

## Criação de uma política

Navegue até a página "Policies" (Políticas) e selecione "Resource & Tag" (Recursos e Etiquetas). Siga as 4 etapas:

- **Criação de política** : Selecione um nome de política e um tipo de política (fornecedor ou marcação)
- **Tipo de apólice** :

  - Selecione um dos dois níveis de aplicação.

    Você tem a opção de aplicar as políticas selecionadas em todos os recursos existentes definidos no código de infraestrutura dentro desse diretório, e não apenas nos recursos que foram alterados no PR.
  - **Para o tipo de política de marcação:** você pode adicionar chaves de marcação e valores de marcação. Você pode deixar o campo "tag values" vazio se quiser permitir todos os valores

    **Exemplo:** Chave da tag: "Aplicativo"
  - **Para Resource Type Policy:** você pode criar regras selecionando tipos de recursos, atributos, operadores e um ou mais valores. Você pode inserir vários valores e separá-los com uma vírgula. **Exemplo:** Tipo de recurso = "Instância de computação ( EC2 )"; Atributo = "Tipo de instância"; Operador: "Not In"; Valor: “t4g.medium, t4g.small, t3a.medium”
- **Escopo da implantação** : Selecione pelo menos um projeto ou toda a organização
- **Detalhes da visão geral** : Revisar e validar as informações inseridas

## Criação de uma barreira de proteção de custos

Navegue até a página "Policies" e selecione "Cost Guardrails". Você pode definir um nome, selecionar um nível de aplicação e especificar um limite de custo/ delta máximo permitido para cada alteração
