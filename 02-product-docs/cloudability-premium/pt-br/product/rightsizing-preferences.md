---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Preferências de dimensionamento correto"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Redimensionamento em Cloudability Premium"
  - "Dimensionamento correto"
source_path: "product/rightsizing-preferences.html"
images:
  - "images/preferences-screenshot_S3.jpg"
  - "images/preferences-screenshot_VM.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Preferências de dimensionamento correto

Navegue até Configurações > Preferências de dimensionamento de direitos.

Preferências do Compute ( VM )

Essa guia de preferências permite que você configure preferências globais para recomendações de dimensionamento de direitos.

![Captura de tela das preferências do Compute VM](../../../../03-media/cloudability-premium/images/preferences-screenshot_VM.jpg)

| Nome do Campo | Descrição |
| --- | --- |
| Gerações e instâncias | Opções para excluir tipos de instância não atuais ou para recomendar apenas dentro da família de instâncias existentes (por exemplo, para garantir a cobertura contínua com compromissos/reservas existentes) ao gerar recomendações de dimensionamento. |
| Arquitetura do processador | Escolha excluir tipos específicos de processadores das recomendações de dimensionamento e permitir recomendações entre arquiteturas. Certifique-se da compatibilidade da carga de trabalho antes de trocar o tipo de processador. |
| Redução de capacidade | Opções para incluir recomendações que resultariam em uma redução na capacidade do recurso (por exemplo, redução da memória total disponível) se as métricas de utilização da dimensão não forem fornecidas. |
| Limite de economia de custos | Configuração opcional para determinar as recomendações mínimas de economia que devem ser previstas para serem incluídas nas exibidas.  Valor mínimo de poupança de 30 dias - Um valor de zero indica que a configuração será ignorada. |
| Tempo de vida do recurso | Configuração opcional para eliminar recomendações para os recursos que ficaram inativos por um período de tempo especificado. Um valor de zero indica que a configuração será ignorada. |

Insira os dados nos campos apropriados e selecione o botão Save (Salvar ). A mensagem *Preferências salvas com sucesso* é exibida.

Várias maneiras de filtrar recomendações de dimensionamento de direitos

No site Cloudability, há muitas maneiras de filtrar as recomendações de dimensionamento de direitos. Primeiro, você pode filtrar as recomendações usando as preferências globais disponíveis na página Settings > Rightsizing Preferences. Outra maneira de filtrar é usar as opções disponíveis nas próprias páginas de dimensionamento de direitos em Optimize > Rightsizing. Há opções de filtragem adicionais fornecidas no painel "detalhes" para as próprias recomendações.

Object Storage ( S3 ) Preferências

Essa guia de preferências permite que você exclua classes específicas do site Object Storage para recomendações de redimensionamento.

Para excluir uma classe de armazenamento:

1. selecione o botão "Add Value" (Adicionar valor).
2. Adicionar um valor (classe de armazenamento) ao campo de entrada
3. Continuar a adicionar valores para excluir, conforme necessário

S3 classes de armazenamento:

- Standard
- Classificação inteligente por níveis
- Acesso padrão infrequente
- Uma vez Zona Acesso infrequente
- Recuperação instantânea de glaciares
- Recuperação Flexível de Glacier
- Arquivo do Glacier Deep

![captura de tela das preferências de armazenamento de objetos](../../../../03-media/cloudability-premium/images/preferences-screenshot_S3.jpg)

**Tópico principal:** [Redimensionamento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
