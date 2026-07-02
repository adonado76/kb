---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Componente CTF Vendors: instalar e configurar"
breadcrumb: []
source_path: "cost-transparency/configuration/ctfvendors.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Componente CTF Vendors: instalar e configurar

Para configurar os fornecedores, instale o componente CTF-Vendors e carregue os dados do arquivo de dados mestre do fornecedor de sua organização. O componente CTF-Vendors não é instalado automaticamente com o projeto padrão Costing Standard . Os dados para preencher a tabela Vendor Master Data (Dados mestre do fornecedor) no aplicativo Costing Standard normalmente são provenientes do arquivo de dados mestre do fornecedor no aplicativo financeiro de sua organização, como Oracle Financials ou SAP ERP Financials.

## Sobre as chaves

As chaves da tabela de dados mestre do fornecedor são todas predefinidas e não devem ser alteradas.

| Chave | Com base em | Lógica |
| --- | --- | --- |
| Chave da fonte de custo\_fornecedor | ID do Fornecedor  Chave da fonte de custos  Metacampo | Anexe o texto CS\_Vendor com o campo ID do fornecedor e o metacampo Chave da fonte de custos. |
| Chave Vendor\_ITRT | Fornecedor CSP KeyIT Recurso TowerIT Subtorre de recursos | SE Chave Vendor\_CSP = Vendor\_CSP\_null THEN Anexar o texto Vendor\_ITRT com IT Resource Tower e IT Resource Sub-tower ELSE Definir o texto como Vendor\_ITRT\_null |
| Chave Vendor\_CSP | A CSP é  Nome do fornecedor | SE É CSP = sim THEN Anexar o texto Vendor\_CSP ao nome do fornecedor ELSE Defina o texto como Vendor\_CSP\_null |

## Instalar o componente

O componente CTF - Vendors não é instalado com o projeto padrão Costing Standard .

Para instalar o componente CTF - Vendors:

1. Abra o projeto Costing Standard .
2. Clique na guia **Projeto**.
3. Clique em **Components (Componentes** ) na faixa de opções.
4. Clique no componente **CTF - Vendors**.
5. Clique em **Install (Instalar** ).

## Fontes de dados típicas

As cifras do fornecedor geralmente são extraídas de um registro geral.

## Uploads

Normalmente, você carrega uma única tabela de fornecedor que é anexada à tabela de dados mestre do fornecedor. O conjunto de dados deve conter campos que possam ser mapeados para os campos apropriados na tabela Dados mestre do fornecedor.

## Preencher o conjunto de dados mestre

Há um conjunto de dados mestre associado ao componente CTF - Fornecedores: Dados mestre do fornecedor

## Campos obrigatórios e recomendados

Os campos obrigatórios e recomendados necessários para iluminar os relatórios padrão do fornecedor estão listados abaixo.

- É CSP (obrigatório)
- Subnível de recursos de TI (obrigatório)
- Torre de recursos de TI (obrigatório)
- Função do fornecedor (obrigatório)
- ID do fornecedor (obrigatório)
- Gerente de fornecedores (recomendado)
- Nome do fornecedor (obrigatório)
- Serviço do fornecedor (recomendado)
- Tipo de fornecedor (obrigatório)

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
