---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Conectar dados personalizados (FOCUS Ingress)"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
source_path: "admin/connect-custom-data-focus-ingress.html"
images:
  - "images/focus.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conectar dados personalizados (FOCUS Ingress)

O FinOps Open Cost and Usage Specification ( FOCUS) é um esforço conduzido pela comunidade para desenvolver um esquema padrão para nuvem, SaaS, e outros dados de faturamento. O principal objetivo da especificação FOCUS é facilitar a compreensão, a geração de relatórios e o gerenciamento dos custos da nuvem. A especificação FOCUS foi criada para ser adaptável a uma variedade de provedores de serviços em nuvem e fontes de produtos SaaS e define colunas (dimensões e métricas), requisitos específicos da coluna e atributos (requisitos de toda a especificação).

Você pode trazer quaisquer dados de custo e uso de fontes de dados adicionais, desde que tenham sido formatados no esquema FOCUS e sigam as colunas necessárias, conforme definido pela especificação.

Nota:

- Não recomendamos o uso do FOCUS para dados do CSP, pois o conjunto de dados de custos atual que o Cloudability obtém nativamente (CUR/ Azure exports/ GCP Billing etc.) é muito mais detalhado do que o conjunto de dados do FOCUS. Usando o FOCUS, obtemos apenas dados de custo; as integrações atuais do CSP também trazem dados de utilização que são usados em vários casos de uso de otimização.
- Se você já tiver autenticado sua(s) conta(s) CSP por meio do conector nativo, não utilize a mesma conta para se conectar pelo conector FOCUS.
- Para garantir total compatibilidade e suporte, siga as etapas de conexão descritas. Não são suportadas configurações personalizadas. Se tiver alguma dúvida, entre em contato com **o suporte** do IBM.

As especificações do FOCUS podem ser [consultadas aqui](https://focus.finops.org/ "(Abre em uma nova guia ou janela)"), com colunas específicas [disponíveis também aqui](https://focus.finops.org/focus-columns/ "(Abre em uma nova guia ou janela)").

Cloudability atualmente suporta

1. Versão FOCUS 1.0
2. Versão FOCUS 1.1

Observação: a opção de credenciamento “Dados personalizados” não deve ser usada para CSPs que já oferecemos suporte nativamente (por exemplo, AWS, Azure, etc.), pois alguns recursos, como o rightsizing, não serão suportados.

Etapas para a integração

![captura de tela do custom dat ingres](../../../../03-media/cloudability-premium/images/focus.jpg)

Gerenciamento de fontes de dados

Todos os dados carregados para qualquer um dos serviços de armazenamento devem ser os dados completos do mês até a data.

Além disso, os dados devem seguir uma estrutura específica, como:

`<Root
Directory>/<Optional_Sub_Directories>/<Vendor>/<Report_Period>/<Epoch Time
Folder>/<prefix>-Manifest.json`

O M em Manifest deve ser sempre maiúsculo.

- Diretório raiz : Um prefixo como AWS bucket name, Azure container name ou GCS bucket name
- Subdiretórios opcionais : um campo opcional para o cliente. Eles podem ou não ter subdiretórios adicionais
- Fornecedor : Um nome de fornecedor que ajudaria a identificar o tipo de fornecedor
- Período do relatório : Período do relatório para o qual os dados estão disponíveis. Ele deve estar no formato AAAAMMDD-AAAAMM(+1)DD. Por exemplo, para o período do relatório 2023-02, o nome seria →20230201-20230301.
- Epoch Time Folder : Será usado para identificar a última queda dos dados acumulados no mês.
- Manifesto : arquivo json de metadados que contém detalhes do conjunto de dados específico do período do relatório.

Todas as fontes de dados personalizadas por meio desse recurso precisam estar de acordo com as especificações do FOCUS.

Exemplo de arquivo de manifesto

```
{
		"compression": "GZIP",
		"content_type": "Parquet",
		"report_id": "uuid-f431e214843b3c19756368",
		"root_dir": "byod-input-prod",
		"all_report_keys": [
		"<complete/path/excluding/root_dir>/cost-and-usage-report-00001.snappy.parquet",
		"<complete/path/excluding/root_dir>/cost-and-usage-report-00002.snappy.parquet"
		],
		"updated_at": "2024-04-04T05:00:22Z",
		"focus_version": "1.0"
	}
```

Tipo de conteúdo do arquivo : JSON

| Cabeçalho / Campo | Definição de cabeçalho/campo | Valor: Obrigatório / Opcional |
| --- | --- | --- |
| compressão | CSV : gzip  Parquet : Todos os que são suportados pelas estruturas Java Hadoop. | Opcional |
| Tipo de conteúdo | Parquet ou CSV | Necessário |
| iD do relatório | Identificador de relatório exclusivo gerado aleatoriamente. | Opcional |
| root\_dir | S3 Bucket ou Azure Diretório ou bucket do GCS para buscar o relatório. Isso dependerá do tipo de credenciais escolhidas. | Necessário |
| todas as chaves de relatório | É um JSON aninhado, que é a lista de apenas novos caminhos absolutos de arquivos, excluindo o diretório raiz. | Necessário |
| atualizado em | Hora da última atualização do relatório. | Opcional |
| versão de foco | Versão do FOCUS conforme [https://finops.dev/focus-spec](https://finops.dev/focus-spec "(Abre em uma nova guia ou janela)") A versão deve corresponder exatamente à versão da especificação do FOCUS. por exemplo, 1.0 ou 1.1 | Necessário |

Etapas de integração

Observação: Assim que o processo de credenciamento no site Cloudability for concluído (conforme descrito abaixo), você verá uma marca de seleção verde ao lado dos detalhes do seu credenciamento, mas o site Cloudability ainda precisará validar se o arquivo de faturamento e o arquivo de manifesto estão em conformidade com os formatos solicitados. Caso não encontre nenhum dado em Cloudability após 24 horas, entre em contato com a equipe de suporte do Apptio.

Oferecemos suporte ao AWS Simple Storage Service, Google Cloud Storage e Azure Blob Storage como serviços de armazenamento para abrigar dados alinhados ao FOCUS.

Para adicionar credenciais para dados personalizados em Cloudability, siga as etapas abaixo:

1. Em Cloudability, navegue até Configurações > Credenciais do fornecedor > Adicionar fonte de dados > Outras fontes de dados.
2. Selecione Other Data Sources > Add a Credential > O painel Add other Datasources Account é aberto, clique em **Next**.
3. Clique em Preferred Storage Provider (Provedor de armazenamento preferencial ) e siga as instruções.

AWS Serviço de armazenamento simples

1. Insira o fornecedor para o qual os dados precisam ser ingeridos.
2. Insira **a ID da conta AWS correspondente onde os arquivos estão localizados**.
3. Insira o nome do bucket AWS S3 em Diretório Raiz.
4. Digite os subprefixos opcionais em Subdiretórios.
5. Digite o prefixo do manifesto em Prefixo do manifesto.
6. Clique em Gerar modelo.

Para obter mais informações, consulte o [site Connect Amazon Web Services](aws-credentialing-standard-enterprise-home.html).

Azure Blob Storage 

1. Insira o fornecedor para o qual os dados precisam ser ingeridos.
2. Insira o ID da conta de cobrança dAzure, onde os arquivos estão localizados.
3. Insira a ID do locatário.
4. Digite o ID da assinatura.
5. Digite o nome do Resource Group.
6. Digite o nome da conta de armazenamento.
7. Insira o Blob Container Name em Root Directory.
8. Insira subdiretórios opcionais em Subdiretórios.
9. Digite o prefixo do manifesto em Prefixo do manifesto.
10. Clique em Gerar modelo.

Para obter mais informações, consulte o [site Connect Microsoft Azure](azure-cm-setup.html).

Google Cloud Storage Serviço de armazenamento simples

1. Insira o fornecedor para o qual os dados precisam ser ingeridos.
2. Insira o ID da conta **de cobrança d**GCP, onde os arquivos estão localizados.
3. Insira o nome do bucket GCS GCP em Diretório raiz.
4. Digite os subprefixos opcionais em Subdiretórios.
5. Digite o prefixo do manifesto em Prefixo do manifesto.
6. Clique em Gerar modelo.

Para obter mais informações, consulte o [site Connect Google Cloud](connect-google-cloud.html).

**Perguntas frequentes** :

- **Posso usar o formato FOCUS para trazer dados CSP para AWS, Azure, GCP, OCI?**Não recomendamos o uso do FOCUS para dados de CSP, pois o conjunto de dados de custo atual que o site Cloudability obtém nativamente (exportações CUR/ Azure etc.) é muito mais granular do que o conjunto de dados FOCUS. Usando o FOCUS, obtemos apenas dados de custo; as integrações atuais do CSP também trazem dados de utilização que são usados em vários casos de uso de otimização.

- **Quais são os casos de uso do FOCUS para os dados da CSP?**O FOCUS pode ser usado para conjuntos de dados de CSP para regiões ou fornecedores que não são suportados nativamente em Cloudability. E.g.
  - AWS China
  - Nuvem Ali
  - Qualquer outra nuvem pública à qual o Cloudability não ofereça suporte nativo
- **Se eu trouxer dados de outras regiões ou de outros fornecedores, quais são os pré-requisitos?**
  - Os dados do FOCUS devem ser hospedados em um bucket fora da região à qual o Cloudability não oferece suporte, por exemplo, não na China, mas nos EUA, na UE ou na UA.
  - Certifique-se de que, durante o credenciamento, forneça os **detalhes da conta onde os arquivos de exportação de custos estão hospedados.**
  - Os arquivos de parquet só devem ser compactados enquanto estiverem sendo gerados (usando técnicas de compactação padrão do hadoop e do avro) e não explicitamente compactados.
  - O arquivo FOCUS manifest.JSON deve ter as "chaves de relatório" corretas que especificam os arquivos de relatório exatos a serem recuperados, incluindo as extensões de arquivo corretas.
