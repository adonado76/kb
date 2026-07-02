---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Identificadores de alteração"
breadcrumb:
  - "Planning"
  - "Configuração e administração"
source_path: "it-planning/planning/change-identifier.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Identificadores de alteração

O recurso Identificadores de alteração permite que os administradores atualizem os identificadores do sistema (códigos) usados pelas dimensões dos dados de referência, como Centros de custo, Contas, Projetos e Departamentos.

Observação: as funções de administrador ou responsável pelo processo orçamentário são necessárias para alterar identificadores.

Os identificadores atuam como chaves exclusivas voltadas para o sistema que o Planning usa para referenciar e conectar dados entre planos, importações, APIs e integrações. Embora os nomes descritivos sejam voltados para o usuário e possam mudar, os identificadores proporcionam estabilidade e consistência.

## Comportamento importante

- Alterar um identificador não atualiza o nome de exibição do valor da dimensão.
- Os planos existentes, independentemente do estado (Novo, Aberto ou Final), são automaticamente remapeados para o novo identificador.
- Os identificadores devem permanecer únicos dentro da dimensão.

## Dimensões suportadas

O recurso Identificadores de alteração se aplica à maioria das dimensões padrão e personalizadas, incluindo:

- Conta
- Centro de custo
- Departamento
- Tipo de atividade laboral
- Local
- Projeto
- Grupo do Projeto
- Função do Trabalho no Projeto
- Fator de variação
- Fornecedor
- Dimensões personalizadas

## Como alterar identificadores

**1. Exportar o modelo de identificadores de alteração**

1. Navegue até **Configuração** → **Dados de referência**.
2. Selecione a dimensão que deseja atualizar.
3. Abra os **pontos de suspensão (...) menu** e selecione **Modelo de identificadores**.
4. Exporte o modelo de identificadores como um arquivo CSV.

**2. Atualize os identificadores**

No CSV exportado:

- Deixe os registros **de código** existentes intactos.
- Atualize a coluna **Novo Código** com os novos códigos que deseja aplicar.
- **Não** altere valores que não pretende alterar.

**3. Importe o modelo atualizado**

1. Abra os **pontos de suspensão (...) menu** e selecione **Alterar identificadores**.
2. Importe o arquivo CSV atualizado.
3. Analise os resultados da validação.

**4. Revise e aplique as alterações**

Se tudo estiver correto, confirme a alteração.
