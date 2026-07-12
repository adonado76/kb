---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Gerenciar dados de referência do grupo de projetos"
breadcrumb: []
source_path: "it-planning/planning/iip/manage-project-group-data-ref.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Gerenciar dados de referência do grupo de projetos

Importante: *Disponível com a* *assinatura* ***do Apptio Planning Standard***

Os dados de referência do Grupo de Projetos representam a estrutura hierárquica do projeto ou do portfólio de sua organização.

1. No menu de navegação, selecione Dados de referência > Dimensões padrão > Grupo de projetos.
2. Atualize os valores da tabela de dados conforme necessário:
   - Código - O identificador exclusivo de um grupo de projetos.
   - Nome - O nome do grupo de projetos.
   - Código pai - Representa a hierarquia do seu grupo de projetos. Um valor de código pai é o valor de código de sua conta pai ou de nível imediatamente superior (se houver).
   - Código da moeda - A moeda comum do grupo de projetos. Esse valor é necessário quando o suporte a várias moedas está ativado no perfil da empresa. O valor da moeda comum deve ser o código ISO de três letras da moeda. Se nenhum código de moeda for inserido, será usada a moeda comum padrão.
   - Código do centro de custo - O identificador dos centros de custo correspondentes. Ao importar os dados reais, eles são alocados por centro de custo e, em seguida, mapeados para o objeto de custo ou dimensões dependentes. Um projeto pode ser associado a vários centros de custo e pode incluir itens de linha (volumes, mão de obra ou despesas) registrados em mais de um centro de custo. Adicione vários centros de custo à célula da tabela usando uma vírgula para separá-los.
