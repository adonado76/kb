---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Configurar um projeto em um idioma diferente do inglês"
breadcrumb: []
source_path: "cost-transparency/configuration/configproject.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Configurar um projeto em um idioma diferente do inglês

Para versões traduzidas do Costing Standard e do Planning, a configuração das versões traduzidas é basicamente a mesma das versões em inglês, exceto pelo fato de que os dados aparecem no idioma fornecido pelos dados de origem. No entanto, algumas colunas exigem inglês para exibir o conteúdo adequadamente.

Aplica-se a: Costing Standard e IT Financial Management em TBM Studio 12.8.2 e posteriores, usando o Template v107 e posteriores

## Configuração de nomes de colunas que não estejam em inglês

As informações a seguir listam os nomes das colunas que precisam permanecer em inglês durante a configuração. Verifique esta lista regularmente, pois outros produtos são traduzidos pelo site Apptio.

### Procedimento

1. Crie seus próprios drivers ou edite os drivers existentes para oferecer suporte ao idioma desejado.
2. Configure suas alocações usando colunas precisas em relacionamentos de dados em vez de usar colunas-chave (isso também é válido para projetos em inglês).
3. Certifique-se de que as configurações do projeto para tamanho de papel e local estejam definidas adequadamente para o idioma desejado.
4. A localidade de classificação é mantida separadamente da localidade da moeda. Escolha uma localidade de classificação que melhor corresponda ao idioma do usuário ou deixe a localidade como inglês se o idioma de destino não precisar de classificação especial.
5. Mantenha as seguintes colunas em inglês, independentemente do idioma do usuário:

   Para PTI:

   - Dados mestre da fonte de custos
   - Tipo de Despesas
   - Tipo de plano
   - Dados mestre de mão de obra
   - É interno

   Para CT:

   - Nenhum.
