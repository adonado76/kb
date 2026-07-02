---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Conectando-se com AWS - Atualizando os clientes existentes de Cloudability para Cloudability Premium"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
  - "Conexão com AWS - Guia de integração do cliente"
source_path: "admin/aws-credentialing-premium-upgrading.html"
images:
  - "images/alert.png"
  - "images/turbo.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conectando-se com AWS - Atualizando os clientes existentes de Cloudability para Cloudability Premium

Se você atualizou para Cloudability Premium, suas credenciais atuais de Cloudability continuarão funcionando em Cloudability — mas não em Turbonomic. Para que as duas ferramentas funcionem em conjunto, você precisará atualizar as credenciais das suas contas do AWS. Isso ocorre porque são necessárias mais permissões de IAM para que o Turbonomic funcione perfeitamente com o Cloudability.

1. Em Cloudability, navegue até **Settings > Vendor Credentials > AWS**
2. Selecione uma conta consolidada existente clicando no ícone.
3. Selecione o ícone de lápis para abrir Editar uma credencial.
4. Escolha as opções avançadas de redimensionamento: **“Somente leitura”** ou **“Automatizar ações”**
   - A seleção **"Somente leitura"** significa que você está concedendo permissões de monitoramento para Cloudability cost, Turbonomic cost e Turbonomic para que elas possam ler seu ambiente, mas não realizar ações.
   - A seleção **da opção “Automatizar ações”** implica que você está concedendo todas as permissões de Cloudability e Turbonomic, incluindo aquelas relacionadas às ações automatizadas, ou seja, a execução de Turbonomic e a execução de cobrança em Turbonomic.
5. Clique em Salvar para fazer o download do modelo.
6. Atualize as permissões de IAM existentes executando o modelo no console AWS de acordo com esta seção (link para Credenciamento automatizado de contas vinculadas)
7. Verifique novamente a conta por meio da interface do usuário Cloudability.
8. A verificação bem-sucedida será indicada com um tique verde.

Isso precisa ser feito tanto para a conta consolidada quanto para as contas vinculadas.

Observação: Em suas contas vinculadas individuais, o status de Automate Actions (Automatizar ações) será exibido como:

- **DESATIVADO** se a opção **“Advanced Rightsizing”** tiver sido definida como **“Somente leitura”** (herdada da conta consolidada)
- **ATIVADO** se a opção **“Ajuste avançado”** tiver sido selecionada como **“Automatizar ações”** (novamente, herdado da conta consolidada)
- AWS o status das contas vinculadas não pode ser alterado em contas vinculadas individuais quando se opta pelo Credenciamento automatizado

Observação: Se o credenciamento automatizado não estiver ativado.

- Tanto a conta consolidada quanto as contas vinculadas podem ter diferentes status **ON/OFF** em Automate Actions.
- O status **ON/OFF** pode ser alterado individualmente sem qualquer dependência entre a conta consolidada e as contas vinculadas.

Observação: ao mudar de **“Automatizar ações”** para **“Somente leitura”**, é exibida uma notificação pop-up solicitando confirmação.

![alerta](../../../../03-media/cloudability-premium/images/alert.png)

Exibição das permissões do ` Turbonomic `

Conforme mencionado anteriormente, há permissões adicionais do Turbonomic que foram adicionadas para as categorias Básico (Dados de cobrança), Avançado (Dados de utilização) e Ações de automação (para executar ações), as quais estão documentadas em detalhes na seção IBM Turbonomic dos documentos da Central de Ajuda. <INSERIR LINK AQUI, POR FAVOR>. Depois que suas permissões do IAM forem atualizadas e todas as contas forem verificadas, a lista de permissões poderá ser visualizada selecionando a opção **Detalhes** em cada conta AWS listada em Cloudability.

![turbo](../../../../03-media/cloudability-premium/images/turbo.jpg)

Vale ressaltar que, conforme a captura de tela acima, é possível selecionar a opção “ Turbonomic ” (Monitorar) para visualizar as permissões de LEITURA definidas, enquanto a opção “ Turbonomic ” (Executar) permite visualizar as permissões de EXECUÇÃO definidas.

**Tópico principal:** [Conexão com AWS - Guia de integração do cliente](../admin/aws-credentialing-premium-home.html)
