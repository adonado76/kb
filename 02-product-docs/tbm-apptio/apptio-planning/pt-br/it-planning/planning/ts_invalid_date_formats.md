---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Solucionar problemas de formatos de data inválidos no Planning"
breadcrumb:
  - "Planning"
  - "Solução de problemas e perguntas frequentes"
source_path: "it-planning/planning/ts_invalid_date_formats.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Solucionar problemas de formatos de data inválidos no Planning

## Sintoma

Você não consegue importar valores de data para o site Planning devido a uma formatação inválida e não tem certeza de quais formatos de data estão corretos.

## O que está acontecendo

Planning tem requisitos rigorosos para a formatação de datas que são mais específicos do que outros produtos Apptio.

## Solução: Sintaxe

Você pode usar os seguintes formatos de data:

| América do Norte | Internacional | Ásia Oriental |
| --- | --- | --- |
| MM-DD-AAAA | DD-MM-AAAA | AAAA-MM-DD |
| MM/DD/AAAA | DD/MM/AAAA | AAAA/MM/DD |

Você deve usar um formato de data de forma consistente em todo o seu projeto Planning .

Os formatos de data devem atender aos seguintes requisitos de sintaxe:

- O mês deve ser representado por números inteiros numéricos. O texto é inválido. Por exemplo, para o mês de agosto, 10 é válido, mas agosto ou AUG não é.
- O mês e o dia devem conter um ou dois dígitos.
- O ano deve usar todos os 4 dígitos: YYYY.
- Pode usar "-" ou "/" para separar números na data, desde que a pontuação selecionada seja consistente.
- A ordem do mês e do dia depende de suas configurações regionais.

## Solução: Configurações de idioma do navegador

Planning puxa o suporte ao formato de data do navegador ou das configurações do sistema. Localize seu navegador na seção a seguir e verifique se as configurações do navegador estão definidas corretamente.

## Google Chrome

Google Chrome usa a formatação de data definida pelas configurações do navegador.

1. No navegador Google Chrome, abra o menu do Chrome no canto superior direito e selecione Configurações.
2. Selecione Avançado > Idiomas > Idioma.
3. Altere suas configurações de idioma para que seu idioma preferido fique no topo da ordem de idiomas.

Suas configurações são salvas automaticamente.

Para obter mais informações, acesse [Google Chrome Help Center](https://support.google.com/chrome/?p=help "(Abre em uma nova guia ou janela)").

## Microsoft Edge

Os navegadores da Microsoft usam o formato de data definido nas configurações regionais do Windows.

1. Abra o Painel de controle e selecione Alterar formatos de data, hora ou número.
2. Na caixa de diálogo Region (Região), na guia Formats (Formatos), selecione as configurações de data e hora de sua preferência e, em seguida, selecione Apply (Aplicar) e OK.
3. Limpe os cookies e o cache do navegador.
