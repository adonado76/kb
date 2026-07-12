---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Trabalhando com diferentes moedas"
breadcrumb:
  - "Planning"
  - "Trabalhando com planos"
source_path: "it-planning/planning/enter-display-line.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Trabalhando com diferentes moedas

Apptio O Planning suporta configurações em várias moedas, o que permite inserir, exibir e reconciliar dados financeiros em diferentes moedas. Isso é especialmente útil para organizações globais que gerenciam orçamentos em várias regiões.

## Habilitação de várias moedas

Observação: As funções de administrador ou proprietário do processo orçamentário são necessárias para editar as configurações do perfil da empresa.

1. Clique no ícone **de engrenagem** e abra **o Company Profile**.
2. Na seção **Currency (Moeda** ), marque **Enable Multi-Currency (Ativar várias moedas** ).
3. Defina a **moeda** padrão para seu ambiente.
4. *(Opcional)* Ative a opção **Show ISO Currency Codes instead of Symbols (Mostrar códigos de moeda ISO em vez de símbolos** ) se você preferir códigos ISO (por exemplo, USD, EUR) em vez de símbolos de moeda.
5. Clique em **Save (Salvar** ) para aplicar suas alterações.

## Configuração de taxas de câmbio em várias moedas

Quando a opção de várias moedas estiver ativada, você precisará configurar as taxas de câmbio para que o sistema possa converter com precisão os valores entre as moedas.

Apptio O planejamento usa duas tabelas de taxas de câmbio separadas:

- **Taxa de câmbio real** - aplicada a períodos históricos
- **Taxa de câmbio planejada** - aplicada ao período planejado e previsto

**Etapas para configurar as taxas de câmbio:**

1. Vá para **Configuração > Dados de referência > Taxa de moeda real** ou **Taxa de moeda planejada**.
2. Abra o **menu Elipses** e escolha uma das opções:
   1. **Export Template (Exportar modelo** ) para fazer o download de um modelo em branco, ou
   2. **Exportar** para fazer o download de dados de taxas existentes para atualização.
3. Preencha o arquivo e defina os seguintes campos:
   1. **De Moeda** - Código ISO da moeda base (moeda padrão definida no perfil da empresa)
   2. **To Currency -** Código ISO da moeda de destino
   3. **Taxa** - a taxa de conversão
   4. **Efetivo desde** - data de início da taxa. Use o formato de data AAAA-MM-DD ou MM-DD-AAAA.
4. Certifique-se de definir a **taxa básica** configurando a **moeda padrão** como ela mesma - por exemplo, USD → USD com uma taxa de 1.
5. **Importe** o arquivo atualizado e **publique** as alterações.

## Entrada de valores de itens individuais em moedas diferentes

- Quando o modo de várias moedas estiver ativado, cada item de linha incluirá uma **moeda**. Os itens de linha só podem ser editados quando o **menu global Moeda** (na barra de navegação superior) estiver definido como **Original**.
- É possível inserir valores em qualquer moeda definida em uma base por item de linha.
- Para visualizar os valores convertidos, selecione uma moeda no **menu global Moeda** - a tabela e os painéis de despesas converterão automaticamente todos os valores para a moeda selecionada usando a **taxa de câmbio** apropriada para esse período e tipo de dados (reais ou planejados).

## Configurar moedas padrão por departamento

Observação: As funções de administrador ou proprietário do processo orçamentário são necessárias para gerenciar os dados de referência.

Você pode definir uma moeda padrão para cada departamento para garantir que a entrada de dados esteja alinhada com os requisitos financeiros locais ou regionais.

**Passos:**

1. Abra a tabela de dados de referência **do departamento**.
2. **Exporte** os dados do departamento e insira o **código de moeda padrão** desejado na coluna **Moeda** para cada departamento.
3. Importe **novamente** o arquivo atualizado e **publique** as alterações.

Se um departamento não tiver uma moeda definida, a **moeda padrão** (definida no perfil da empresa) será usada ao acessar esse departamento.
