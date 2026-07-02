---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Uso de códigos externos para identificar recursos de trabalho"
breadcrumb:
  - "Planning"
  - "Planejamento de atividades de trabalho do projeto"
source_path: "it-planning/planning/iip/unique-labor-resource-identification.html"
images:
  - "resources/images/it_planning_images/extla-1.png"
  - "resources/images/it_planning_images/extla-s2.png"
  - "resources/images/it_planning_images/extla-s3.png"
  - "resources/images/it_planning_images/lap-5.22release.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Uso de códigos externos para identificar recursos de trabalho

Importante: *Disponível com a* *assinatura* ***do Apptio Planning Standard***

Lembre-se: *o recurso de Planejamento Integrado de Investimentos (IIP) está ativado.*

Por padrão, os recursos de mão de obra são identificados na **Atividade de Mão de Obra** por **Nome do Recurso**. Quando dois ou mais recursos compartilham o mesmo nome, torna-se difícil distingui-los durante a alocação. Isso cria desafios tanto na interface do usuário quanto na importação de dados de atividades laborais.

![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/extla-1.png)

Para garantir que cada recurso seja identificável de forma única, Apptio o Planejamento permite atribuir um **Código Externo** (como ID do funcionário ou ID do cargo) a cada recurso de mão de obra. Quando ativado, os recursos aparecem como **<Código externo> – <Nome>**, permitindo uma alocação precisa do projeto, importações limpas e sincronização confiável com sistemas externos de gerenciamento de mão de obra.

## Configurando código externo

Para identificar recursos de forma exclusiva, você pode ativar **o Código Externo** e atribuir um identificador exclusivo do seu sistema de RH ou trabalho.

**Etapa 1 — Habilitar código externo**

Observação: *as funções de administrador ou responsável pelo processo orçamentário são necessárias para realizar esta tarefa.*

1. Navegue até **Configurações (ícone de engrenagem)** → **Perfil da empresa**.
2. Habilite a opção **Código Externo**.
3. A coluna **Código externo** aparecerá em **Despesas** → **Mão de obra**.

Para mais detalhes, consulte [Códigos externos](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=configuration-external-unique-identifier "(Abre em uma nova guia ou janela)").

**Etapa 2 — Atribuir códigos externos aos recursos de mão de obra**

Na guia **Despesas** → **Mão de obra**, atribua um **Código externo** exclusivo para cada recurso de mão de obra:

- **Funcionários existentes:** use o ID do funcionário, o número do funcionário ou outro identificador exclusivo do seu sistema de RH.
- **Trabalho planejado:** use o ID da posição ou um código de espaço reservado exclusivo.
  - Quando a vaga for preenchida, substitua o ID da vaga pelo ID real do funcionário.

![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/extla-s2.png)

**Etapa 3 — Visualizar códigos externos na atividade de trabalho**

Na guia **Despesas** → **Atividade de mão de obra**, o menu suspenso **Recurso** agora exibirá os recursos como:

**<Código externo> – <Nome>**

Isso garante que nomes idênticos possam ser distinguidos claramente.

![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/extla-s3.png)

Observação: após selecionar um recurso, a coluna **Recurso** exibirá apenas o nome do recurso. O Código Externo permanece visível na coluna **Recurso: Código Externo**.

## Utilização de códigos externos de recursos em importações

- Ao exportar um modelo de Atividade de Trabalho, o arquivo incluirá a coluna **Código Externo do Recurso**.
- **Para importar** linhas de atividade de mão de obra usando o Código Externo de Recurso, siga as etapas abaixo:
  1. Insira um código externo (por exemplo, ID do funcionário) para os itens de mão de obra.
  2. Crie um arquivo de importação de atividades de mão de obra CSV, certificando-se de que a coluna “Recurso: Código externo” esteja preenchida com o código externo correspondente para cada recurso de mão de obra.
  3. Acesse Despesas > Atividade de mão de obra e, no menu Ações, selecione Importar atividade de mão de obra.
  4. Na caixa de diálogo “Importar arquivo”, selecione “Atualizar dados”.
  5. Selecione “Recurso: Código externo” no menu suspenso.
  6. Clique em Importar.
- Resultado da importação:
  - O sistema atualizará as linhas de atividade de mão de obra no plano, comparando os registros com base nos valores de “Recurso: Código Externo” no arquivo “ CSV ”.
  - Se houver várias linhas de atividade de mão de obra utilizando o mesmo Código Externo de Recurso e o usuário estiver importando com a opção “Atualizar Dados”, será utilizada uma combinação do Código Externo de Recurso e do Código da Linha de Item para identificar de forma exclusiva as linhas a serem atualizadas.

    ![imagem da importação usando códigos externos](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/lap-5.22release.png)

Observação: a importação de dados de atividades de mão de obra usando **o recurso “Código Externo”** não é compatível, no momento, com importações realizadas por meio do Cálculo de Custos do Apptio através do Gerenciador de Dados Automatizado.
