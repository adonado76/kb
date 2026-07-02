---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Configurações de pré-requisitos"
breadcrumb: []
source_path: "cost-transparency/technology-integration/pre-requisite.html"
images:
  - "resources/images/ct_images/trb-prereq-1.jpg"
  - "resources/images/ct_images/trb-prerq.jpg"
  - "cost-transparency/technology-integration/clip_image002_69970998.gif"
  - "cost-transparency/technology-integration/clip_image004_1503612513.gif"
  - "cost-transparency/technology-integration/clip_image006_-595341153.gif"
  - "cost-transparency/technology-integration/clip_image008_-537983876.gif"
  - "cost-transparency/technology-integration/clip_image010_-1349679255.gif"
  - "cost-transparency/technology-integration/clip_image012_672310785.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configurações de pré-requisitos

Para iniciar a integração entre IBM Turbonomic e IBM Apptio, os seguintes pré-requisitos devem ser configurados:

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-prerq.jpg)

## Configuração do IBM Apptio Datadrop

A integração dos dados do IBM Turbonomic no IBM Apptio utiliza o Datadrop do IBM Apptio, um servidor de protocolo de transferência segura de arquivos (SFTP) baseado em nuvem.

Para obter instruções detalhadas de configuração, consulte [Configurar uma conexão Datadrop](../../datalink/datalink_datadrop.dita "(Abre em uma nova guia ou janela)").

## Configuração em IBM Turbonomic

Depois que o IBM Apptio Datadrop for provisionado, siga as etapas abaixo para configurar o IBM Apptio como um destino no IBM Turbonomic:

1. Navegue até IBM Turbonomic e selecione **Settings (Configurações** ) na coluna da esquerda.
2. Selecione **New Target (Novo alvo** ) no canto superior direito.
3. Escolha *Gerenciamento de TI* como a **Categoria de destino**.
4. Entre os **tipos de destino** disponíveis, selecione *IBM Apptio*. ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/trb-prereq-1.jpg)
5. Na janela de configuração, insira os dados nos campos necessários:
   - **Endereço** : Digite o nome do host de destino ou o endereço IP associado ao IBM Apptio account.Example: ` datadrop.apptio.com `
   - **Nome de exibição** : Forneça um nome de exibição de sua escolha para esse alvo.
   - **Porta** : Defina o número da porta como 22.
   - **Nome de usuário** : Digite o nome de usuário associado a essa conta IBM Apptio.
   - **Nome do host do Turbonomic** : Especifique o endereço da instância de origem do IBM Turbonomic.
6. Criar chaves para conectar o Turbo e o Apptio Datadrop
   1. **Criar par de chaves públicas/privadas no formato.PEM**
      1. Faça o download do site OpenSSL aqui: [https://sourceforge.net/projects/openssl-for-windows/](https://sourceforge.net/projects/openssl-for-windows/ "(Abre em uma nova guia ou janela)")
      2. Execute os seguintes comandos separadamente na linha de comando OpenSSL :
         - genrsa -out private-key.pem
         - rsa -in private-key.pem -pubout -out public-key.pem

           ![](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image002_69970998.gif)
   2. **Configuração das chaves do Turbonomic**
      1. Cole o texto da chave PEM privada no Turbonomic. *Amostra conforme abaixo:*

         ![](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image004_1503612513.gif)

         Observação: A chave privada não pode ter uma frase secreta. Se uma ferramenta como o Putty estiver sendo usada para gerar a chave privada, é provável que ela esteja no formato PPK errado.
      2. Faça o download da chave pública PGP na seção de configurações do datalink

         ![](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image006_-595341153.gif)
      3. Cole a chave pública PGP na chave GPG no Turbonomic
   3. **Configuração de chaves de lançamento de dados**
      1. O Datadrop só aceita chaves formatadas em OpenSSH, portanto, precisamos converter a chave privada na etapa anterior.
      2. Baixe o utilitário de geração de chaves RSA/DSA do Putty: [https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html "(Abre em uma nova guia ou janela)")
      3. Inicie o gerador de chaves e carregue sua chave privada no formato.PEM. Isso criará uma chave pública no formato OpenSSH. *Amostra conforme abaixo:*

         ![](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image008_-537983876.gif)
      4. Copie a chave pública e cole-a na chave pública do seu nome de usuário turbo nas configurações do Datadrop

      Amostra da janela Apptio Target Type totalmente preenchida no Turbonomic:

      ![Uma captura de tela de uma caixa branca Descrição gerada automaticamente](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image010_-1349679255.gif) ![Uma captura de tela de um computador Descrição gerada automaticamente](../../../../../03-media/apptio-costing-standard/cost-transparency/technology-integration/clip_image012_672310785.gif)
