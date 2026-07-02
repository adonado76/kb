---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Funções e permissões do usuário"
breadcrumb:
  - "Benchmarking"
  - "Introdução"
source_path: "it-benchmarking/user-roles.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Funções e permissões do usuário

As funções e permissões dos usuários controlam quem pode visualizar e trabalhar com o Benchmarking. Uma função é um conjunto de permissões atribuídas a um usuário, e ninguém pode acessar um produto IBM Apptio sem ter pelo menos uma função em sua conta, que é gerenciada na Administração de Acesso. Na Administração do Access, os administradores autorizados criam e gerenciam registros de usuários, atribuem ou removem funções e controlam quais funções podem acessar cada endpoint do produto, quais endpoints estão abertos a qualquer função elegível e quais endpoints estão totalmente ocultos. Para obter detalhes sobre como atribuir funções, gerenciar contas de usuário e acessar os produtos IBM Apptio, consulte a documentação sobre [Administração de Acesso](/docs/SSFG2DK/frontdoor/home.html).

**Fun** ções padrão do  
 usuário As seguintes funções padrão têm acesso ao Benchmarking:

- **Administrador**
  - Acesso total a todos os recursos do Benchmarking (incluindo Benchmarking Interativo e Cálculo de Custos).
  - Inclui acesso administrativo à Administração do Access e capacidade de criar funções personalizadas.

**Funções personalizadas**

  

Você pode criar funções personalizadas na Administração de Acesso. As funções personalizadas permitem que você adapte o acesso para atender às necessidades específicas da sua organização.

**Permissões**   
A tabela a seguir lista as permissões disponíveis específicas para o Benchmarking Interativo e suas descrições

Tabela 1.

| Nome da permissão | Descrição |
| --- | --- |
| AccessInteractiveBenchmarkingTestTools | Pode acessar ferramentas para testar Benchmarking Interativo |
| ConfigureInteractiveBenchmarking | É possível configurar perfis de benchmarking interativos, fontes de dados de custos, moeda e seleções. |
| DeleteInteractiveBenchmarkingDataAndProfiles | Pode excluir ou substituir permanentemente os dados de Benchmarking Interativo e/ou perfis de clientes. |
| RetrieveInteractiveBenchmarkingCostData | Pode recuperar dados de custos reais a partir de aplicações de transparência de custos. |
| UseInteractiveBenchmarkingServiceAccount | É possível conectar-se a aplicativos de transparência de custos usando a conta do serviço de benchmarking interativo. [infosvcs@apptio.com](mailto:infosvcs@apptio.com "(Abre em uma nova guia ou janela)") |
| ViewInteractiveBenchmarksAndCostData | É possível visualizar painéis que exibem benchmarks interativos e dados de custos. |
