---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Validação e rastreamento de modelos"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Arquitetura do modelo"
source_path: "studio/new-uc/concepts-architecture/model-architecture/model-validation.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Validação e rastreamento de modelos

Depois que seu modelo estiver configurado e tiver sido calculado, o próximo passo fundamental é verificar se os custos são alocados corretamente e se os resultados da alocação são razoáveis e auditáveis.

## Validação de modelo

A validação é o processo de verificar se o seu modelo produz resultados precisos, completos e equilibrados. Existem três tipos de verificações de validação a serem realizadas.

**Verificação de saldo**

A verificação mais básica: os totais da origem correspondem aos totais do destino? Se você começou com US$ 5 milhões na fonte de custo, a soma de todos os objetos de destino finais também deve ser de US$ 5 milhões (deduzidos quaisquer valores não alocados intencionalmente).

- **O que verificar:** a soma dos valores do objeto de origem deve ser igual à soma dos valores finais do objeto de destino, acrescida de quaisquer valores não alocados
- **Se os valores não baterem:** verifique se há alocações excessivas (o tipo de valor “Padrão” pode causar alocações excessivas), fórmulas mal configuradas ou problemas de qualidade dos dados

**Verificações de integridade**

Verifique se todos os dados esperados passaram pelo modelo. Isso significa verificar se todas as linhas de origem foram processadas, se todos os objetos do modelo receberam entradas e se nenhuma alocação foi ignorada silenciosamente devido a problemas de configuração.

- Analise os valores dos custos não alocados em cada nível (não apenas no primeiro)
- Verifique se os objetos intermediários têm valores diferentes de zero
- Verifique se todos os períodos esperados estão presentes nos resultados

**Verificações de plausibilidade**

Mesmo quando um modelo está equilibrado e completo, os resultados podem não ser razoáveis. Compare os resultados atuais com os de períodos anteriores, orçamentos ou referências externas para identificar anomalias.

- Houve alguma unidade de negócios cujos custos tenham variado mais de 20% em relação ao mês anterior sem uma causa conhecida?
- Os custos unitários (custo por servidor, custo por aplicativo) estão dentro dos intervalos esperados?
- As proporções relativas entre as unidades de negócios correspondem às expectativas?

## Rastreamento de custos

O rastreamento de custos é a capacidade de acompanhar um custo específico desde sua origem até seu destino final (rastreamento prospectivo) ou a partir de um valor final até suas origens (rastreamento retrospectivo). Isso é essencial para auditorias, perguntas das partes interessadas e resolução de problemas.

**Rastreamento de custos: para onde foi esse custo?**

Partindo de uma fonte conhecida (por exemplo, uma fatura específica de um fornecedor), rastreie seu percurso pelo modelo para verificar quais unidades de negócios acabaram por receber parcelas desse custo. Tanto a visualização em diagrama do TBM Studio quanto o Single Object Modeler oferecem suporte à navegação progressiva pela cadeia de alocação.

**Rastreamento retrospectivo: de onde veio esse custo?**

Partindo de um valor final em um relatório (por exemplo, a alocação de " $1.8M " da área de Engenharia), rastreie o modelo para entender quais custos de origem contribuíram para esse valor. Esta é a pergunta que as partes interessadas fazem com mais frequência: “Por que os custos de TI do meu departamento são assim?”

Nota:

**Identificando as melhores práticas**

Documente a lógica de alocação do seu modelo em linguagem simples, juntamente com a configuração técnica. Quando um diretor financeiro pergunta: “Por que meus custos aumentaram?”, Ter uma explicação narrativa pronta (“Seu departamento adicionou 15 servidores em março, aumentando sua parcela nos custos do data center”) é muito mais eficaz do que explicar detalhadamente o modelo técnico.

## Relatórios de modelos (diagramas de Sankey)

A TBM Studio oferece Relatórios de Modelagem, que utilizam visualizações no estilo Sankey para apresentar os fluxos de custos de forma intuitiva e visual. Esses relatórios diferem dos relatórios padrão do Report Studio e foram criados especificamente para a validação de modelos e a comunicação com as partes interessadas.

**Características do diagrama de Sankey:**

- Exibe os custos que transitam pelas camadas definidas (por exemplo, Finanças → Centros de custo → Infraestrutura → Serviços)
- A largura da linha é proporcional ao valor do custo, tornando os grandes fluxos imediatamente visíveis
- Clique em qualquer linha do fluxo para acessar os detalhes subjacentes no nível da transação
- Alternar entre a visualização de Sankey e a exibição de dados em tabela
- Suporta várias colunas por camada para uma análise detalhada

**Quando usar os relatórios modelo:**

- **Validação:** Verifique se os custos são distribuídos conforme o esperado por cada nível
- **Comunicação:** Mostre às partes interessadas como seus custos são calculados, utilizando um formato visual intuitivo
- **Auditoria:** Analisar detalhadamente fluxos específicos para rastrear itens de custo individuais
- **Integração:** Ajude os novos membros da equipe a compreender rapidamente a estrutura do modelo
