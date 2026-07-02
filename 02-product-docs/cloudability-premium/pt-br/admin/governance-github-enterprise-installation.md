---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "GitHub Enterprise Instalação do aplicativo no servidor (local)"
breadcrumb:
  - "Cloudability Premium"
  - "Governança"
  - "Configurar Cloudability Governança"
source_path: "admin/governance-github-enterprise-installation.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# GitHub Enterprise Instalação do aplicativo no servidor (local)

Este guia explica como registrar um aplicativo do GitHub no Cloudability para uso com o GitHub Enterprise Server (GHES). Esse processo permite que você conecte e gerencie seus repositórios GHES dentro do fluxo de trabalho de governança do Cloudability.

## Pré-requisitos

- Acesso a uma instância do **Cloudability** com permissões de governança.
- Acesso administrativo à sua instância do **GitHub Enterprise Server**.

## Instruções passo a passo

1. **Acesse a seção Configuração**

   Na barra lateral do Cloudability, acesse **Governança** > **Configuração**. Selecione a guia **“Integrações”** e escolha “ **GitHub Enterprise** ” no menu à esquerda.
2. **Iniciar o cadastro**

   Clique no botão “**Registrar o aplicativo GitHub** ”, localizado no canto superior direito da seção “ GitHub Enterprise ”.
3. **Insira os detalhes do aplicativo**

   Aparecerá uma janela modal intitulada “Registrar um novo aplicativo do GitHub ”. Forneça as seguintes informações:

   - **Tipo de conta:** Selecione *“Conta pessoal”* ou “*Conta de organização* ”.

     - Ao selecionar `Organization Account`, o usuário também deverá inserir o identificador exclusivo da sua organização GitHub.
   - **Nome do aplicativo:** Digite um nome exclusivo para o seu aplicativo.
   - **URL HTML:** Indique o endereço base URL do seu servidor GitHub Enterprise.
   - **URL da API:** Insira o endpoint da API do seu servidor (normalmente `https://[your-ghes-domain]/api/v3`).

   Clique em **Enviar** para continuar.
4. **Faça a autenticação em GitHub Enterprise**

   O sistema irá redirecioná-lo para o seu servidor GitHub Enterprise.

   - Se solicitado, faça login usando suas credenciais corporativas ou seu provedor de identidade (SSO).
   - Após a autenticação, você verá uma página de confirmação do GitHub. Clique em **“Criar um aplicativo d GitHub ” para [Seu nome/Organização]**.
5. **Concluir a integração**

   Depois de clicar em “Criar”, você será redirecionado automaticamente de volta para a interface do Cloudability. Uma mensagem de sucesso (“Aplicativo d GitHub Enterprise o criado com sucesso”) aparecerá por alguns instantes.
6. **Verificar o cadastro**

   O novo aplicativo agora estará listado na coluna “ **GitHub Enterprise** ”. Você pode clicar em **“Instalar”** ao lado do nome do aplicativo para selecionar repositórios específicos para integração.

## Resolução de problemas

- **Problemas com o redirecionamento:** Se o seu navegador não o redirecionar automaticamente durante as etapas de autenticação, procure os links “clique aqui” exibidos nas telas de transição.
- **Erros na API URL :** Certifique-se de que o endereço da API URL inclua o `/api/v3` sufixo, pois isso é necessário para que o Cloudability se comunique com o GitHub Enterprise Server.

**Tópico principal:** [Configuração da governança d Cloudability](../admin/governance-setup-cldy-governance.html)
