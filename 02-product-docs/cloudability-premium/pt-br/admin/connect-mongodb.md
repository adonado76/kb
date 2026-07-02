---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Conectar MongoDB"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
source_path: "admin/connect-mongodb.html"
images:
  - "images/MongoDB-API.jpeg"
  - "images/MongoDB-CLDY.jpeg"
  - "images/MongoDB-Organization.jpeg"
  - "images/MongoDB-Permissions.jpeg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conectar MongoDB

**Visão geral**

Este guia explica passo a passo como conectar seu **MongoDB** ao IBM Cloudability. Depois de conectado, você terá acesso aos dados de custo e uso do MongoDB no site Cloudability.

**Pré-requisitos**

- Você deve ser um administrador do Cloudability.
- Você deve ter permissões de administrador no console do MongoDB Atlas.

Observação: Se você adquiriu o “ MongoDB ” por meio da loja de um provedor de nuvem e estiver adicionando dados de custo e uso do “ MongoDB ” com essa integração, os custos serão exibidos duas vezes nos relatórios do “ Cloudability ”. Por exemplo, se você comprou o jogo “ MongoDB ” na loja do AWS, verá o seguinte:

- A rubrica de alto nível para AWS
- Os itens com custos detalhados do MongoDB, nos quais “ AWS Marketplace” aparece como vendedor.

Se você quiser ocultar os custos do seu marketplace, configure um filtro.

Os custos do Marketplace não são incluídos na cobrança.

MongoDB O processo de credenciamento de contas envolve algumas etapas que exigirão que você realize ações tanto no console MongoDB quanto no site Cloudability em diversas fases.

Durante esse processo, Cloudability utilizará sua MongoDB OrganizationID para se conectar à sua conta e obter os dados de custo e uso.

**Etapa 1 – Console do MongoDB**

**Obtenha o ID da sua organização**

1. Acesse o console do MongoDB Atlas.
2. Clique no perfil do usuário e, em seguida, em “Organizações”.
3. Clique no **nome** da organização
4. Clique no ícone de engrenagem ao lado das configurações **da organização**.
5. Copie o ID da sua organização e guarde-o para usar mais tarde.

   ![](../../../../03-media/cloudability-premium/images/MongoDB-Organization.jpeg)

**Criar uma chave de API da organização**

1. Acesse a página do Access Manager no console do MongoDB Atlas.
2. Clique em “Aplicativos” e selecione a aba “API”
3. Clique em “**Criar chave de API** ”.
4. Insira as informações **da chave da API**.
   - Na caixa **“Descrição”**, insira uma descrição (por exemplo, “ Cloudability Access”).
   - No menu “**Permissões da** organização”, selecione a função “**Visualizador de faturamento da organização** ”.
5. Clique em “**Avançar** ”.
6. Copie as chaves pública e privada

   ![](../../../../03-media/cloudability-premium/images/MongoDB-Permissions.jpeg)

   ![](../../../../03-media/cloudability-premium/images/MongoDB-API.jpeg)

**Etapa 2 – Cloudability**

1. Abra Cloudability em uma nova aba ou janela.
2. No site Cloudability, acesse **Configurações** > **Credenciais de fornecedor**.
3. Na seção do **Ingress**, selecione o bloco “ **MongoDB** ”. O painel **“Adicionar conta do MongoDB ”** é exibido.
4. Leia as informações apresentadas e clique no botão **“Avançar”** quando estiver pronto para continuar.
5. Cole o ID da organização copiado no campo “**ID da** organização”.
6. Cole a **chave pública** e **a chave privada** nos respectivos campos.
7. No campo “**Modelo de assinatura** ”, selecione se sua organização utiliza o **Marketplace** ou se realiza compras **diretamente** em MongoDB.
8. Clique no botão “**Salvar** ”.
9. Clique em “Verificar credenciais”.

![](../../../../03-media/cloudability-premium/images/MongoDB-CLDY.jpeg)

Uma notificação verde indica que a credencial foi verificada com sucesso.

Observação: Após se conectar ao site MongoDB,, pode levar até 24 horas para que seus dados iniciais de custo e uso apareçam no site Cloudability.

Por padrão, o MongoDB restringe o acesso à API por meio da Lista de Acesso por IP da API de Administração do Atlas. Se essa função não estiver desativada na sua organização, use os seguintes intervalos de IP para conceder acesso a MongoDB ao site Cloudability :

- **185.115.88.0/22**
- **103.195.128.0/22**
- **129.41.0.0/22**

Para obter mais detalhes sobre como incluir endereços IP na lista de permissões, entre em contato com as equipes de suporte da IBM.

**Perguntas Frequentes**

- **Qual versão do site MongoDB é compatível com o Cloudability?**
  - MongoDB Atlas
- **Quando devo optar pelo Marketplace em vez da assinatura?**
  - Se você comprou o livro “ MongoDB ” em um **site de vendas** como AWS ou Azure, use esta opção
  - Se você comprou “ MongoDB **” diretamente** no site MongoDB, selecione “Direct”
