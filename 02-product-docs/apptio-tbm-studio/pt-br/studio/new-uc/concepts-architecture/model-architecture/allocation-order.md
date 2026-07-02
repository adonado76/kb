---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Ordem de alocação e processamento"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Arquitetura do modelo"
source_path: "studio/new-uc/concepts-architecture/model-architecture/allocation-order.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Ordem de alocação e processamento

## Por que a ordem é importante

Em um modelo de custos em vários níveis, as alocações não são todas executadas simultaneamente. A ordem em que as alocações são processadas determina os resultados finais, pois as alocações posteriores dependem do resultado das anteriores.

Considere uma cadeia simples: a fonte de custo faz a alocação para os fornecedores, e os fornecedores fazem a alocação para as unidades de negócios. A alocação dos fornecedores deve ser concluída antes que as unidades de negócios possam receber sua parcela — caso contrário, não haveria custos a serem distribuídos pelos fornecedores.

## Sequenciamento baseado em dependências

O TBM Studio determina automaticamente a ordem de alocação com base no gráfico de dependências do modelo. O sistema analisa quais objetos alimentam quais outros objetos e estabelece uma sequência de processamento que respeita essas dependências.

**As regras são:**

- As alocações de um objeto só são executadas depois que todas as alocações recebidas para esse objeto tiverem sido concluídas
- Os objetos sem dependências a montante (objetos de origem) são processados primeiro
- Objetos no mesmo nível, sem dependências entre si, podem ser processados em paralelo
- A sequência de processamento é determinística — o mesmo modelo produz sempre a mesma ordem de execução

## Alocações em vários níveis

Na maioria dos modelos do mundo real, os custos passam por várias camadas intermediárias antes de chegarem ao seu destino final. Isso é chamado de alocação em várias camadas ou com vários saltos.

**Como funcionam os fluxos em várias camadas**

Vamos analisar um custo de US$ 1.000 por meio de um modelo de cinco níveis:

|  |  |  |  |
| --- | --- | --- | --- |
| **Camada** | **Objeto** | **O que acontece** | **Resultado** |
| 1 | Origem do custo | $1.000 são lançados no Razão como despesa do centro de dados | Valor de origem de US$ 1.000 |
| 2 | Fornecedores | Correspondência com a Dell com base no ID do fornecedor; US$ 1.000 são transferidos para a Dell | A Dell recebe US$ 1.000 |
| 3 | Serviços de Tecnologia | Alocado para computação (70%) e armazenamento (30%) com base no uso | Computação: US$ 700, Armazenamento: US$ 300 |
| 4 | Soluções | Os US$ 700 da Compute são distribuídos entre ERP (US$ 400) e CRM (US$ 300) de acordo com o volume de transações | ERP: US$ 400, CRM: US$ 300 |
| 5 | Unidades de negócios | Os US$ 400 do ERP são divididos entre Vendas (US$ 240) e Engenharia (US$ 160) com base no número de usuários | Vendas: US$ 240, Eng: US$ 160 |

Em cada nível, o mecanismo de alocação aplica as regras definidas para esse objeto de modelo. A saída de uma etapa passa a ser a entrada da seguinte. É por isso que uma sequência adequada é essencial — e por que o diagrama do modelo é indispensável para compreender o fluxo de custos.

## Dependências circulares

Uma dependência circular ocorre quando o Objeto A é referenciado pelo Objeto B e o Objeto B é referenciado de volta pelo Objeto A (seja diretamente ou por meio de uma cadeia de objetos intermediários). Isso cria um loop infinito que não pode ser resolvido por meio do processamento sequencial normal.

**A abordagem do TBM Studio:**

- **Prevenção:** O gráfico do modelo não deve conter ciclos. O TBM Studio valida o gráfico de dependências e impede que você crie configurações de alocação que resultariam em fluxos circulares.
- **A recursão como exceção:** a alocação por recursão (Seção 4.3.4 ) é o único mecanismo compatível para lidar com dependências mútuas. Ele utiliza um processamento iterativo com limites de precisão e de iterações para convergir para um resultado.
- **Detecção:** Se uma dependência circular for criada inadvertidamente (normalmente devido a configurações complexas envolvendo vários objetos), o processo de compilação reporta um erro em vez de entrar em um loop infinito.

Nota:

**Como evitar dependências circulares**

Projete sua hierarquia de modelos de forma que o fluxo seja unidirecional — das fontes de custo, na base, até os consumidores de negócios, no topo. Se você precisar de uma alocação retroativa, avalie se uma alocação recursiva ou uma hierarquia de modelos reestruturada seria mais adequada.
