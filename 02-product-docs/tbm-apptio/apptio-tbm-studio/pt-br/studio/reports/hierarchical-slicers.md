---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Cortadores hierárquicos"
breadcrumb: []
source_path: "studio/reports/hierarchical-slicers.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep335.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Cortadores hierárquicos

**Aplica-se a** : TBM Studio 12.0 e posterior

Usando um fatiador hierárquico, os usuários podem se aprofundar em níveis crescentes de detalhes. Por exemplo, no fatiador mostrado na imagem a seguir, um usuário pode selecionar tipos de servidores. Os fatiadores hierárquicos podem ser usados em fatiadores compactos.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep335.png)

## Um fatiador hierárquico é baseado em um grupo

Um fatiador hierárquico é baseado em um grupo de perspectiva personalizado. A ordem das entradas no grupo determina a hierarquia. Por exemplo, o fatiador mostrado na Figura A foi criado usando um grupo de perspectiva personalizado com os seguintes campos: 01\_Type, 02\_SubType, 03\_OS. Os campos foram renomeados para criar a ordem correta.

## Criar um fatiador hierárquico

1. Na guia **Relatório**, clique em **Fatiador de linhas**.
2. Crie a perspectiva personalizada que será usada no fatiador. Para obter mais informações, consulte [Criar perspectivas personalizadas](creating-custom-perspectives.htm "(Abre em uma nova guia ou janela)").
3. Na área **Perspectivas** do **Project Explorer**, clique com o botão direito do mouse e crie um novo grupo.
4. Arraste os campos para o grupo recém-criado.
5. Arraste o grupo para a área **Slice By (Fatiar por** ) da caixa de diálogo.

## Ordenar os campos

Por padrão, os campos em um slicer hierárquico estão em ordem alfabética. Para alterar a ordem, renomeie os campos, adicionando números sequenciais à frente dos nomes. Para renomear um campo, clique com o botão direito do mouse no campo e clique em **Edit (Editar** ).

Observação: Não é possível usar traços (-) em um nome de campo. No entanto, você pode usar dois pontos e sublinhados.
