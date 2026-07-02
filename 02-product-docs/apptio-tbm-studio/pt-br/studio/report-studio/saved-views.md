---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Visualizações salvas"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "ApptioIBM Report Studio (Novo)"
  - "Visualizador de relatórios"
source_path: "studio/report-studio/saved-views.html"
images:
  - "resources/images/studio_images/sv-create.png"
  - "resources/images/studio_images/sv-qs.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Visualizações salvas

## Visão geral

As visualizações salvas permitem que os usuários criem instantâneos personalizados de um relatório no Visualizador de Relatórios. Uma visualização salva captura o estado atual do relatório, incluindo os filtros e as interações aplicados a ele.

As visualizações salvas facilitam o retorno a um relatório configurado exatamente da maneira que você prefere, sem precisar reaplicar filtros ou repetir as ações todas as vezes. As visualizações salvas são privadas para o usuário que as criou e não ficam visíveis para outros usuários.

Observação: as visualizações salvas estão disponíveis apenas em ambientes de produção.

## Iniciação rápida

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/sv-qs.png)

Use as visualizações salvas para personalizar a forma como você visualiza os relatórios.

Será possível:

- Crie uma visualização salva após aplicar filtros ou interações.
- Mantenha várias visualizações do mesmo relatório para diferentes necessidades de análise.
- Defina uma visualização inicial para que o relatório seja aberto com a configuração de sua preferência.
- Marque a visualização URL como favorita para acessá-la rapidamente mais tarde.

Cada usuário pode criar até 5 visualizações salvas por relatório.

## Criando uma visualização salva

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/sv-create.png)

Para criar uma visualização salva:

1. Abra um relatório no Visualizador de Relatórios.
2. Aplique os filtros ou interações desejados.
3. Clique no **ícone do olho** na barra de ações na parte superior do relatório.
4. Selecione “**Salvar visualização** ”. Aparece uma caixa de diálogo onde você pode inserir:
   1. Nome da visualização
   2. Descrição opcional
   3. Opção para definir como página inicial
5. A visualização é criada e você é redirecionado automaticamente para a visualização recém-criada.

## Atualização ou criação de visualizações adicionais

**Salvar Visualizar**

Quando você estiver em uma visualização salva:

- Ao clicar em **“Salvar visualização”,** a visualização atual é atualizada com as últimas interações e filtros do relatório.
- Use esta opção para criar uma visualização salva pela primeira vez para um determinado relatório.

**Salvar como**

Use **“Salvar como visualização”** para criar uma nova visualização com base no estado atual do relatório.

Passos:

1. Modificar filtros ou interações no relatório
2. Clique no ícone do olho
3. Selecione **“Salvar como”**
4. Digite um novo nome para a exibição

Isso cria uma visualização salva separada, mantendo a visualização original inalterada.

**Alternar entre visualizações**

Para alternar entre as visualizações:

1. Clique no ícone do olho na barra de ferramentas do relatório.
2. Selecione uma visualização da lista. A lista inclui:
3. O Relatório Padrão
4. Todas as visualizações salvas criadas por você

Ao selecionar uma visualização, essa versão do relatório é carregada.

**Gerenciamento de visualizações salvas**

Cada visualização salva inclui um menu de opções (três pontos) que permite realizar as seguintes ações:

- Detalhes da visualização - Veja o nome e a descrição da visualização.
- Editar - Modifique o nome ou a descrição da visualização.
- Excluir - Remover definitivamente a visualização.

**Excluindo uma visualização**

- Se você excluir a visualização que está visualizando no momento, será redirecionado para a Visualização de Página de Destino.
- Se não houver nenhuma visualização de página de destino, você será redirecionado para o Relatório Padrão.

**Marcar visualizações**

Cada visualização salva possui um endereço URL exclusivo que inclui o ID da visualização.

Isso permite que você:

- Adicione o site URL aos favoritos do seu navegador
- Salve o link para consultar mais tarde
- Voltar diretamente para a mesma configuração do relatório

## Conceitos-chave

1. **Relatório padrão** - O relatório padrão é a versão original do relatório, tal como foi criada pelo autor ou administrador do relatório.
   1. Aparece na lista de Visualizações Salvas com um ícone de casa.
   2. Não inclui filtros ou interações salvos.
   3. Permite que você volte à versão básica do relatório a qualquer momento.
2. **Visualização salva** - Uma visualização salva é uma versão personalizada do relatório criada por um usuário.
   1. Ele captura o estado atual do relatório, incluindo:
      1. Filtros aplicados
      2. Interações com visualizações de relatórios
   2. O relatório geral é atualizado no momento em que a visualização é salva
   3. Ao visualizar uma visualização salva:
      1. O ícone do olho na barra de ferramentas aparece em negrito.
      2. O título da trilha de navegação do relatório inclui o nome da visualização entre parênteses.
   4. Exemplo: **Relatório de Análise de Custos (Visão do Departamento Financeiro)** — Aqui, o relatório padrão é o Relatório de Análise de Custos, e a visão é a Visão do Departamento Financeiro
3. **Visualização inicial** - Uma visualização inicial é a visualização salva que se abre automaticamente quando você acessa o relatório.
   1. Identificado por um ícone de estrela.
   2. Apenas uma visualização por relatório pode ser definida como a visualização inicial para um usuário.
   3. Definir uma visualização inicial ajuda você a começar com a configuração de relatório que usa com mais frequência.
4. **Visualização divergente** – Uma visualização divergente ocorre quando o relatório base é modificado após a criação da visualização. Como a estrutura do relatório mudou, a visualização salva pode não corresponder mais totalmente à versão mais recente do relatório.
   1. Um ícone de aviso aparece ao lado da visualização.
   2. Uma mensagem indica que a visualização divergiu do relatório base.

**Atualizando uma visualização divergente**

Para atualizar uma visualização divergente:

1. Abrir a visualização expandida
2. Clique no menu de opções (três pontos) para acessar a visualização
3. Selecione **“Atualizar a partir do relatório base”**

Ao atualizar a visualização:

- Sincronize-o com a versão mais recente do relatório
- Remova todos os filtros e interações existentes
- Redefina a exibição para corresponder ao relatório base

Você pode então aplicar novos filtros ou interações e salvar a visualização novamente.

Observação: não é possível criar visualizações adicionais a partir de uma visualização divergente.

**Limites e regras**

- As visualizações salvas estão disponíveis apenas em ambientes de produção.
- As visualizações salvas são específicas de cada usuário e não podem ser vistas por outros usuários.
- Cada usuário pode criar até 5 visualizações salvas por relatório.
- Os usuários não podem criar visualizações adicionais a partir de uma visualização divergente.
- A atualização de uma visualização divergente remove os filtros e interações existentes.

## Guia de ícones

|  |  |
| --- | --- |
| **Ícone** | **Significado** |
| Ícone de olho | Acesse o menu “Visualizações salvas” |
| Ícone de olho em negrito | Indica que você está visualizando uma visualização salva |
| Ícone de casa | Relatório padrão |
| Ícone de estrela | Vista da aterrissagem |
| Ícone de Aviso | A opinião divergiu do relatório original |
