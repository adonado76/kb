---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Gerenciar dados de referência do projeto"
breadcrumb: []
source_path: "it-planning/planning/iip/manage-project-data-ref.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Gerenciar dados de referência do projeto

Importante: *Disponível com a* *assinatura* ***do Apptio Planning Standard***

As informações a seguir descrevem os campos das dimensões do projeto.

1. No menu de navegação, selecione Dados de referência > Dimensões padrão > Projeto.
2. Atualize os valores da tabela de dados conforme necessário:
   - Código - O identificador exclusivo de um projeto.
   - Nome - O nome do projeto.
   - Código pai - Representa a hierarquia do seu projeto. Um valor de código pai é o valor de código de sua conta pai ou de nível imediatamente superior (se houver).
   - Allow Any Cost Center (Permitir qualquer centro de custo) - Um valor VERDADEIRO permite que você atribua o projeto a qualquer centro de custo. Um valor FALSO tem como padrão o centro de custo atual.
   - Centro de custo padrão - O valor padrão, a menos que seja fornecido um valor de código de centro de custo diferente.
   - Descrição - Um resumo do projeto.
   - Código do centro de custos - O identificador dos centros de custos correspondentes. Ao importar os dados reais, eles são alocados por centro de custo e, em seguida, mapeados para o objeto de custo ou dimensões dependentes. Um projeto pode ser associado a vários centros de custo e pode incluir itens de linha (volumes, mão de obra ou despesas) registrados em mais de um centro de custo. Adicione vários centros de custo à célula da tabela usando uma vírgula para separá-los.
