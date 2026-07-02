---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Mecanismo de temas"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "ApptioIBM Report Studio (Novo)"
  - "Trabalhando com relatórios"
source_path: "studio/report-studio/theme-engine.html"
images:
  - "resources/images/studio_images/apply-them-eng.png"
  - "resources/images/studio_images/def-theme-eng.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Mecanismo de temas

## Visão geral

O Mecanismo de Temas do novo Report Studio permite manter a consistência de estilo e formatação em todos os relatórios, aplicando um conjunto predefinido de configurações visuais, como cores, tipografia, espaçamento e estilos de componentes.

Os temas ajudam a padronizar a aparência dos relatórios, reduzem o trabalho de formatação manual e aceleram a migração do Report Studio Clássico para o Novo Report Studio.

## O que é um tema?

Um tema é um conjunto reutilizável de configurações de formatação que controla a aparência visual dos relatórios.

Um tema pode incluir:

- Paletas de cores
- Tipografia (família de fontes, tamanho da fonte)
- Estilo dos componentes
- Espaçamento
- Fronteiras

Os temas garantem a consistência visual entre os relatórios, permitindo ao mesmo tempo que os usuários façam personalizações específicas para cada relatório, quando necessário.

## Comportamento padrão do tema

![mecanismo de tema padrão](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/def-theme-eng.png)

**Tema no nível do projeto** - No Report Studio Clássico, na seção **Configurações do projeto**, é possível configurar um **tema de relatório**.

- O tema padrão está definido como **Core**
- Além do Core, estão disponíveis outros quatro temas prontos para uso
- Os usuários podem selecionar um desses temas como padrão no nível do projeto

**Aplicação automática do tema** - O tema padrão do projeto é aplicado automaticamente a:

- Relatórios recém-criados no New Report Studio
- Relatórios migrados do Classic Report Studio

Isso garante um ponto de partida consistente para a formatação do relatório.

## Como aplicar ou alterar um tema para um relatório

No Novo Studio de Relatórios, os usuários podem aplicar ou alterar um tema no nível do relatório.

![aplicar tema no mecanismo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/apply-them-eng.png)

Vá até o menu Arquivo -> Aplicar tema

**Substituição no nível do relatório** - Quando um tema é alterado a partir do menu Arquivo:

- O tema selecionado se aplica apenas ao relatório atual
- Isso substitui o tema padrão do projeto para esse relatório

Isso permite flexibilidade para relatórios que exigem estilos visuais diferentes.

## Formatação por nível de componente

Mesmo depois de aplicar um tema, os usuários podem continuar personalizando os componentes individuais do relatório.

Exemplos:

- Alterar as cores do gráfico
- Ajustar o tamanho da fonte de uma visualização
- Alterar o espaçamento ou as bordas de componentes específicos

Essas alterações de formatação no nível do componente substituem as configurações do tema correspondentes apenas para esse componente específico.

## Boas Práticas

- Use temas no nível do projeto para manter a consistência entre os relatórios
- Utilize substituições no nível do relatório apenas quando um relatório exigir uma identidade visual ou estilo exclusivos
- Minimize as substituições excessivas no nível dos componentes para preservar a consistência
- Aplique temas antes de atividades de migração em grande escala para reduzir o trabalho manual
