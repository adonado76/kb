---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Representar um código de hierarquia em perspectivas"
breadcrumb: []
source_path: "studio/reports/hierarchy-codes-perspectives.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep219_151x368.png"
  - "resources/images/studio_images/studioimages/reports/rep220_151x369.png"
  - "resources/images/studio_images/studioimages/reports/rep221_150x369.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Representar um código de hierarquia em perspectivas

**Aplica-se a** : TBM Studio 12.0 e posterior

Quando você publica um campo em uma perspectiva personalizada na seção **Perspectivas** do **Project Explorer**, uma das opções na caixa de diálogo **Publicar campo** é **Representa um código de hierarquia**. Se você marcar essa opção, ela alterará o comportamento do campo quando ele for usado com um fatiador. Quando um usuário insere um texto no campo de pesquisa do fatiador, a opção encontra todos os valores que começam com o texto inserido mais um caractere adicional. Em seguida, ele cria uma entrada de grupo para cada um no fatiador.

## Exemplo

Suponha que você tenha o fatiador mostrado na imagem a seguir. Ele é definido usando um campo publicado sem a opção **Representa um código de hierarquia** definida. Se você digitar ABC no campo de pesquisa, obterá o resultado mostrado na imagem a seguir:

| Fatiador padrão | Resultado da procura | Resultado da pesquisa com o  conjunto de opções de hierarquia |
| --- | --- | --- |
| imagem Fatiador padrão | imagem Resultado da procura | imagem Resultado da pesquisa com o  conjunto de opções de hierarquia |
