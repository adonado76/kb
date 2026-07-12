---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Códigos externos"
breadcrumb:
  - "Planning"
  - "Configuração e administração"
source_path: "it-planning/planning/external-unique-identifier.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Códigos externos

Quando você importa ou atualiza dados de despesas (por exemplo, mão de obra, atividade de mão de obra, contratos, ativos) de sistemas externos (sistemas de RH, bancos de dados de fornecedores, etc.), Você precisa de um identificador consistente e exclusivo para corresponder as linhas do seu plano aos registros no sistema de origem.

Por padrão, Apptio utiliza seus próprios identificadores internos ( [códigos de itens de linha](line-item-codes.html) ), mas esses não correspondem aos sistemas externos. O recurso **Código Externo** resolve essa lacuna. Quando ativado, cada linha de despesas pode conter um identificador exclusivo definido externamente (como ID do funcionário, ID do fornecedor, ID do cargo, etc.). Isso garante que os dados importados ou atualizados sejam mapeados corretamente nas linhas existentes, evitando duplicatas, registros ausentes ou incompatibilidades de dados.

## Habilitar código externo

Observação: *as funções de administrador ou responsável pelo processo orçamentário são necessárias para realizar esta tarefa.*

1. Vá para **Configurações (ícone de engrenagem) → Perfil da empresa**.
2. Marque a opção **Ativar código externo**.
3. Clique em **Salvar e sair**.

   Após a ativação, a coluna Código Externo fica disponível nas tabelas de despesas.

## Como funcionam os códigos externos

- Uma nova coluna **Código externo** fica disponível nas guias de despesas (Mão de obra, Atividade de mão de obra, Contratos, Ativos, Outros). Pode estar oculto por padrão — você pode exibi-lo na visualização.
- Na guia **Resumo**, você verá novas colunas: **Código externo** e **Código externo de origem.**
- Os valores **do Código Externo** inseridos nas guias Despesas (Mão de obra, Atividade de mão de obra, Contratos, Ativos, Outros) serão resumidos na coluna **Código Externo** da guia **Resumo**.
- Você pode renomear a coluna Código externo em **Configuração → Esquema** — mas isso se aplica a todos os planos.
- O código externo pode ser tornado **obrigatório** no esquema, caso se deseje garantir que cada linha tenha uma referência externa exclusiva.
- Ao criar um novo plano a partir de uma linha de base, os valores existentes do Código Externo são transferidos.

Observação: Como o Código Externo é usado para agregar dados financeiros gerados na guia Resumo, a restrição de exclusividade para o Código Externo não é aplicada nas guias Resumo e Outros. Para todas as outras guias, o sistema exige que os dados de código externo tenham IDs exclusivos.

**Códigos externos de origem**

**Um Código Externo de Origem** identifica o Código Externo do item de linha de origem quando uma linha é criada a partir de outra fonte, como:

- **Delegações** (para contratos ou ativos) criadas pelo item original
- **Finanças geradas** (para ativos, contratos, mão de obra e atividades de mão de obra)

Os códigos externos aparecem quando um item de linha não é criado manualmente. O código externo de origem remete ao item de linha de origem.

Se [a Resumo de mão de obra](labor-summarization.html "O recurso Summarize Labor Financials permite determinar como os dados de custo de mão de obra são agregados e apresentados na guia Summary (Resumo). Ele controla quais dimensões (por exemplo, centro de custo, conta, local) são usadas para agrupar e agrupar linhas de custo de mão de obra, garantindo que você obtenha o nível certo de visibilidade e confidencialidade para as finanças da mão de obra.") estiver ativada:

- Uma única linha financeira resumida pode ter origem em várias linhas de mão de obra
- Nesse caso, tanto o Código Externo quanto o Código Externo de Origem podem exibir **“varia”**

## Permissões para editar código externo

- Somente usuários com permissão **canEditExternalCode** podem adicionar ou modificar valores de Código Externo. Por padrão, usuários com funções de administrador e proprietário do processo orçamentário têm essa permissão.
- Se você deseja restringir a edição, atribua essa permissão seletivamente. Isso evita alterações não autorizadas ou o uso de identificadores incorretos.

## Usando código externo com importações de dados

Ao importar dados de despesas pelo site CSV :

- Use o modo **Atualizar dados** (não Substituir tudo) — isso permite a correspondência de linhas com base no Código externo (ou Código do item da linha, quando presente).
- Lógica de correspondência:
  - Se uma linha no upload corresponder a um código de item de linha existente, as atualizações serão feitas com base nisso.
  - Se o código do item da linha estiver faltando, mas o código externo corresponder, o sistema será atualizado com base no código externo.
- Os códigos externos devem ser **únicos por tipo de linha de despesa** dentro de um plano. As importações serão rejeitadas se forem encontradas duplicatas.

## Alinhamento dos dados reais e das previsões utilizando código externo

Os dados reais são importados para o " Apptio " a partir de sistemas ERP externos, enquanto os orçamentos e as previsões são criados no próprio " Apptio ". Essa separação pode dificultar o alinhamento dos valores reais com as rubricas da previsão ou do orçamento.

O recurso " **Código Externo** " resolve essa questão, permitindo que você defina identificadores únicos específicos para cada usuário, que podem ser utilizados de forma consistente em todos os sistemas. Por exemplo, se um *ID de ativo* for utilizado como código externo em linhas de orçamento ou previsão, e esse mesmo ID de ativo existir nos dados reais do sistema ERP, isso permite um alinhamento preciso dos dados reais com as previsões por meio desse identificador comum.

**Passos para habilitar e usar código externo para alinhamento**

1. Ative o recurso **“Código Externo”** no Perfil da Empresa.
2. Ativar [configurações de compactação de dados reais](actual-summarization.html "Esta funcionalidade descreve como as partidas individuais de dados reais são segregadas, com base nas colunas selecionadas para a compactação.") **por código externo**.
3. Atribua códigos externos às partidas individuais de despesas do seu plano.
4. Certifique-se de que os mesmos códigos externos estejam presentes nos dados reais do seu sistema ERP.
5. No Plano de Previsão, acesse **Despesas > Resumo** e agrupe as partidas individuais pela coluna Código Externo para visualizar a comparação entre a previsão e os valores reais.

## Códigos externos no histórico de alterações

Os códigos externos aparecem no **Log** de Eventos na coluna **Detalhes** quando uma linha com um código externo é alterada.

Quando uma linha se origina de outra linha (por exemplo, gerada a partir de mão de obra, ativos ou contratos), o Código Externo de Origem é exibido — vinculando-se à linha original.

Para mais detalhes, consulte [o Histórico de alterações](change-history.html "O Histórico de alterações fornece uma trilha de auditoria das principais ações realizadas no seu ambiente de planejamento. Permite que as organizações mantenham a transparência, apoiem os requisitos de conformidade e resolvam problemas de planejamento, rastreando quem alterou o quê, quando e como.").
