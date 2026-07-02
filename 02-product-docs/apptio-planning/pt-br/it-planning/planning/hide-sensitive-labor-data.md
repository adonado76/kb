---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Ocultar dados trabalhistas confidenciais"
breadcrumb:
  - "Planning"
  - "Planejamento trabalhista"
source_path: "it-planning/planning/hide-sensitive-labor-data.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Ocultar dados trabalhistas confidenciais

Os administradores podem restringir a visibilidade de colunas específicas na guia Trabalho, como nome do funcionário, salário ou outros detalhes de remuneração, para que os usuários sem a permissão necessária possam visualizar as entradas de trabalho sem ver os campos confidenciais.

Observação: As funções de administrador ou de proprietário do processo orçamentário são necessárias para configurar dados confidenciais.

**Por que você o usaria**

- Proteja a confidencialidade dos funcionários e, ao mesmo tempo, permita que os proprietários dos centros de custo analisem os custos relacionados à mão de obra em todos os departamentos.
- Garantir a conformidade com as políticas internas de privacidade ou de RH, ocultando detalhes confidenciais de remuneração de públicos mais amplos.
- Permitir o planejamento financeiro colaborativo sem expor informações sobre salários ou bônus individuais.

## Como ela funciona

1. Os dados de mão de obra são visíveis para os usuários com base em suas permissões e acesso a objetos de custo.
2. As colunas marcadas como *Dados confidenciais* no esquema de trabalho (como *Nome do funcionário*, *Remuneração base*, *Outras remunerações* ) podem ser ocultadas para usuários que não têm a permissão **Exibir colunas confidenciais** ou **Exibir finanças confidenciais**.
3. Os usuários sem permissão verão os itens de linha de mão de obra, mas as colunas confidenciais ficarão ocultas, enquanto outras informações de custo (por exemplo, função, quantidade, centro de custo, custo totalmente onerado) permanecerão visíveis.
4. Os administradores gerenciam quais colunas são marcadas como confidenciais em **Configuration → Schema → Labor**.
5. As permissões de objeto de custo determinam a visibilidade dos dados confidenciais de mão de obra por meio das seguintes configurações:
   1. **View Sensitive Columns (Exibir colunas confidenciais** ) - Permite que os usuários visualizem e editem atributos marcados como *Sensitive Data (Dados confidenciais* ) na guia Labor (Trabalho).
   2. **View Sensitive Financials (Exibir finanças confidenciais** ) - Permite que os usuários visualizem as finanças trabalhistas geradas na guia Summary (Resumo).

## Instruções de configuração

**1. Marcar colunas sensíveis**

1. Vá para **Configuration → Schema → Labor**.
2. Selecione o(s) atributo(s) que contém(êm) dados privados (por exemplo, *nome do funcionário*, *remuneração base* ).
3. Ative a caixa de seleção **Dados confidenciais**.
4. Salve as alterações no esquema.

***2. Atribuir permissões de objeto de custo***

1. Navegue até **Configuration → Cost Object Permissions**.
2. Para cada departamento, atribua visibilidade concedendo uma ou ambas as permissões a seguir:
3. **View Sensitive Columns (Exibir colunas confidenciais** ) - Para exibir ou editar dados confidenciais de mão de obra na guia Labor (Mão de obra).
4. **View Sensitive Financials (Exibir finanças confidenciais** ) - Para exibir finanças confidenciais do trabalho na guia Summary (Resumo).
5. Os usuários sem essas permissões não verão as colunas confidenciais na guia Trabalho ou os dados financeiros relacionados ao trabalho na guia Resumo.

***3. Verificar o comportamento***

1. Fazer-se passar por um usuário sem acesso a dados confidenciais.
2. Abra um plano e navegue até **Despesas → Trabalho**.
3. Confirme isso:
4. As linhas de trabalho ficam visíveis, mas as colunas confidenciais (por exemplo, *Nome do funcionário*, *Remuneração base* ) ficam ocultas.
5. A **guia Resumo** não exibe detalhes financeiros confidenciais do trabalho.

Para obter mais informações, consulte [Perguntas frequentes: Ocultar dados trabalhistas confidenciais](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=planning-faq-hide-sensitive-labor-data "(Abre em uma nova guia ou janela)").
