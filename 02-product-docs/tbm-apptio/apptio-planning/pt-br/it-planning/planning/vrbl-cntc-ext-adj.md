---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Extensões de contrato"
breadcrumb:
  - "Planning"
  - "Planejamento de contratos"
source_path: "it-planning/planning/vrbl-cntc-ext-adj.html"
images:
  - "resources/images/it_planning_images/2ndlast-ve.png"
  - "resources/images/it_planning_images/last-var-ext.png"
  - "resources/images/it_planning_images/new-ext.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Extensões de contrato

Apptio O planejamento suporta a extensão de contratos para além da data de término original, com diferentes recursos, dependendo se você estiver usando a **visualização herdada** ou a **nova visualização**.

## Legacy View (Extensão básica)

Na experiência legada, quando você clica em **Estender** e insere um **Ajuste de extensão (%)**, o site Apptio Planning irá:

- Aumentar **o valor do contrato** na porcentagem especificada
- **Prorrogar automaticamente o contrato até o final do plano**
- Aplicar a **taxa de ajuste** em todo o período de extensão

Isso proporciona um aumento simples, mas **não** oferece suporte à composição ou a várias extensões em etapas.

Etapas para prorrogar um contrato (visualização herdada)

1. Navegue até a guia **Despesas → Contratos**
2. No item de linha do contrato, marque a **caixa Estender**.
3. Insira o **Ajuste de extensão (%)** para aumentar o valor do contrato para o período de extensão.
4. Selecione o valor **do deslocamento da extensão** como **“Próximo dia”** ou “**Próximo mês** ”. Essa opção pode ser configurada quando o Método de amortização do contrato estiver definido como **“Linear por duração”** ou “**Linear por duração – calendário personalizado** ”.
   1. **No dia seguinte** – A prorrogação do contrato tem início no dia imediatamente seguinte à data de término do contrato atual.
   2. **No próximo mês** – A prorrogação do contrato tem início no mês seguinte à data de término do contrato atual.

## Nova visualização (extensões compostas)

A nova visualização apresenta extensões flexíveis e compostas. Agora você pode:

- Aplicar **várias extensões de contrato**, cada uma com sua própria taxa
- Escolha se os ajustes devem ser **compostos ao longo do tempo**
- Modelar com precisão os padrões de renovação plurianual ou os aumentos de preços

Isso permite uma modelagem mais realista dos contratos do mundo real, especialmente aqueles com renovações anuais, preços diferenciados ou taxas crescentes de fornecedores.

Etapas para estender um contrato (nova visualização)

1. Vá para a guia **Expenses → Contracts (Despesas → Contratos** ) com a opção New View (Nova visualização) ativada.
2. No item de linha do contrato, marque a **caixa Estender**.
3. Isso ativa o **botão Extend** na coluna **Extension Settings (Configurações de extensão** ) - clique nele.
4. Será exibida a caixa de diálogo **Configure Extension (Configurar extensão** ). Digite o seguinte:
   1. **Extend Until** - a nova data de término do contrato
   2. **Ajuste de extensão (%)** - taxa de aumento a ser aplicada à extensão
   3. **Deslocamento da extensão**
      - Configurável se o método de amortização do contrato for **“Linear por duração”** ou **“Calendário personalizado de duração linear”**
      - **No dia seguinte** – A prorrogação do contrato tem início no dia imediatamente seguinte à data de término do contrato atual.
      - **No próximo mês** – A prorrogação do contrato tem início no mês seguinte à data de término do contrato atual.
   4. **Enable Compounding (Ativar composição** ) - ative se cada extensão deve se basear no valor ajustado anterior
5. Clique em **Apply (Aplicar** ) para gerar a programação de extensão.
6. O sistema criará uma tabela de extensão mostrando as datas de início/fim calculadas.
7. Opcionalmente, você pode **adicionar comentários para cada período de extensão**.
8. Se a **composição estiver ativada**, você poderá ajustar a taxa individualmente por extensão.
9. Clique em **Submit** para finalizar e aplicar a extensão.

![imagem de novas extensões](../../../../../03-media/apptio-planning/resources/images/it_planning_images/new-ext.png)

Observação: Se você estender um contrato usando a Nova visualização e depois voltar para a Visualização herdada, a modificação da extensão na Visualização herdada a reverterá para o modelo de extensão básico (não composto) - todas as extensões compostas configuradas anteriormente serão perdidas.

Etapas para importar e exportar extensões de contrato (nova visualização)

***Contratos de exportação e extensões***

1. **Mude para a nova visualização**. (Entre em contato com o administrador se isso não estiver ativado)
2. Acesse a guia **Expenses → Contracts (Despesas → Contratos** ).
3. Abra o **menu** **da tabela Ellipses → Exportar contratos… → Exportar para reimportação**
4. Você receberá **dois arquivos** :
   1. \* **\_Contract.csv - dados do contrato principal**
   2. \* **\_Contract-Extensions.csv - todos os períodos de extensão e taxas de ajuste**

***Contratos de importação***

Os detalhes do contrato e os detalhes da extensão devem ser importados separadamente:

**Etapa 1 - Importar detalhes do contrato**

1. Vá para a guia **Expenses → Contracts (Despesas → Contratos** ) com a opção New View (Nova visualização) ativada.
2. Abra o **menu Elipses (...)** na tabela→ **Importar contratos... → Detalhes do contrato**
3. Selecione **Substituir tudo** (limpa todos os contratos) *ou* **Atualizar dados** (atualiza o código do item de linha correspondente/código externo)
4. Clique em **Importar**

**Etapa 2 - Importar detalhes da extensão do contrato**

1. Abra o **menu Elipses (...)** na tabela→ **Importar contratos... → Detalhes da extensão**
2. Selecione **Substituir tudo** (limpa todas as extensões de contrato) *ou* **Atualizar dados** (atualiza o código do item de linha/código externo correspondente)
3. Clique em **Importar**

Observação: A importação de detalhes do contrato por si só *não* importa as extensões. As extensões sempre devem ser carregadas separadamente.

![imagem de extensão variável](../../../../../03-media/apptio-planning/resources/images/it_planning_images/2ndlast-ve.png)

***Formato de arquivo de extensão de contrato***

Cada linha deve incluir:

- **Line Item Code** - vincula a extensão a um contrato específico
- **Número do ramal** - em ordem sequencial (1 = primeiro ramal, 2 = segundo, etc.)
- **Contract Extend Until** - deve ser o **mesmo para todas as extensões desse contrato**
- **Enable Compounding** - VERDADEIRO para permitir vários períodos ajustados
- **Percentual de ajuste** - inserido como um decimal (por exemplo, 0.05 para 5%)
- **Extension Comment (Comentário de extensão** ) - notas opcionais por extensão

![imagem da última extensão de var](../../../../../03-media/apptio-planning/resources/images/it_planning_images/last-var-ext.png)

**Opcional:** Extension Start Date (Data de início da extensão) - se omitida, o site Apptio a calculará automaticamente.
