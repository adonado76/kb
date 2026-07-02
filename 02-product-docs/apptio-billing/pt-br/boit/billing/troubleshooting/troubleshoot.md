---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Resolução de problemas"
breadcrumb:
  - "Billing"
  - "Resolução de problemas"
source_path: "boit/billing/troubleshooting/troubleshoot.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Resolução de problemas

Este apêndice é um guia prático sobre “o que deu errado e o que verificar primeiro”. Use-o quando os números parecerem errados, os relatórios estiverem vazios ou os diários não estiverem reconciliados.

## Como usar este apêndice

Cada subseção está organizada por:

- **Sintoma** : O que você vê.
- **Causas prováveis** : os suspeitos habituais.
- **O que verificar** : verificações concretas nos dados, na configuração ou no processo.
- **Quem atua** : Normalmente, o administrador/analista, com outros envolvidos conforme necessário.

## As contas parecem obviamente erradas ou vazias

**Sintoma: As contas estão quase ou totalmente vazias**

**Causas prováveis**

- Não há dados de consumo carregados para o período.
- Serviços não marcados como faturáveis.
- Taxas ausentes ou inválidas para o período.
- Período errado selecionado nos relatórios.

**O que verificar**

1. **Tabela de consumo** para o período:
   - Existem linhas para serviços e consumidores esperados?
   - As unidades são diferentes de zero onde você espera que haja uso?
2. **Tabela de serviços/ofertas** :
   - Os serviços principais estão marcados como Ativos e Faturáveis?
   - Algum código ou chave foi alterado recentemente?
3. **Tabela de taxas** :
   - Existem taxas para todos os serviços faturáveis para esse período?
   - As datas de vigência estão corretas (sem problemas de desvio de um mês)?
4. **Filtros do relatório** :
   - Confirme se o relatório está filtrado para o período e os consumidores pretendidos.

**Sintoma: Os encargos totais de faturamento estão muito abaixo ou acima do esperado.**

**Causas prováveis**

- Alimentos consumidos parcialmente ou tardiamente.
- Alterações no modelo de cálculo de custos não consideradas nas premissas de faturamento.
- Taxas mal configuradas (decimal incorreto, moeda errada, unidade errada).
- Grandes mudanças estruturais (migração, aposentadoria) não comunicadas.

**O que verificar**

1. Compare **o total de unidades** por serviço em comparação com o período anterior:
   - Procure por grandes variações percentuais.
2. Compare **os valores das taxas** com o período anterior:
   - Procure taxas que tenham subitamente duplicado, reduzido pela metade ou caído para zero.
3. Verifique **os resultados do cálculo de custos** :
   - O custo total dos principais serviços ou domínios mudou de forma semelhante?
4. Pergunte aos proprietários de domínios:
   - Algum evento tecnológico importante neste período (migração, grande implementação, desativação)?

Se nada explicar a alteração, trate isso como um defeito e rastreie os dados, mapeamentos e taxas.

## Consumidores/serviços ausentes ou inesperados

**Sintoma: uma unidade de negócios, projeto ou produto conhecido está faltando nas faturas.**

**Causas prováveis**

- Consumidor não presente no mestre de consumidores.
- Consumidor presente, mas sem consumo mapeado para ele.
- Consumidor mapeado incorretamente (por exemplo, usando o ID ou a hierarquia errados).

**O que verificar**

1. **Mestre do consumidor** :
   - Pesquise a entidade ausente por ID e nome.
   - Confirme se está marcado como ativo e atribuído à hierarquia correta.
2. **Tabelas de mapeamento** (se utilizadas):
   - Para IDs ou tags externas, verifique os mapeamentos para o consumidor esperado.
   - Verifique se há erros ortográficos, IDs desativados ou linhas de mapeamento duplicadas.
3. **Tabela de consumo** :
   - Existem linhas para o consumidor ausente neste período?
   - Caso contrário, o sistema upstream está fornecendo dados para isso?

**Sintoma: aparecem serviços que deveriam estar desativados ou ser apenas internos.**

**Causas prováveis**

- Serviço não sinalizado como descontinuado ou não faturável.
- Códigos de serviço antigos ainda referenciados por feeds de consumo.
- Serviços internos de “encanamento” acidentalmente marcados como faturáveis.

**O que verificar**

1. **Tabela de serviços/ofertas** :
   - Confirme o status do ciclo de vida (Ativo/Aposentado).
   - Confirmar Faturável = Não para serviços apenas internos.
2. **Tabela de consumo** :
   - Verifique as linhas de uso em relação aos serviços desativados.
   - Confirme se os sistemas upstream pararam de enviar esses IDs.
3. Se necessário, crie uma **regra de tratamento de exceções** :
   - Por exemplo, encaminhe os códigos de serviço aposentados para um serviço dedicado de “Exceção” por um período limitado, enquanto os feeds são limpos.

## Unidades, taxas e anomalias nas taxas unitárias

**Sintoma: Pico ou queda na taxa unitária para um único período**

(A receita detalhada está na Seção 15; esta é a versão resumida.)

**Causas prováveis**

- Custos fixos distribuídos por menos ou mais unidades.
- Alteração na alocação de custos.
- Alteração da taxa que não foi compreendida ou comunicada.
- Volume ou custo ausente para parte do período.

**O que verificar**

1. **Relatório da taxa unitária** para esse serviço em vários períodos:
   - Compare unidades, cobrança, taxa unitária e custo por unidade, quando disponível.
2. **Tabela de taxas** :
   - Confirme se a taxa configurada para esse período não foi alterada acidentalmente.
3. **Resultados do cálculo de custos** :
   - O custo total desse serviço mudou significativamente?
   - Algum dos fatores de alocação foi atualizado?
4. **Dados de consumo** :
   - Verifique se o volume não está truncado (por exemplo, cobertura parcial do mês).

**Sintoma: Cargas zero ou negativas onde não deveriam existir**

**Causas prováveis**

- Zero unidades ou taxas zero para um serviço que deveria ser cobrado.
- Ajustes negativos carregados nas tabelas de consumo ou custos.
- Convenções de sinalização incorretas na lógica do modelo.

**O que verificar**

1. **Relatório de controle de qualidade/exceção** para valores zero ou negativos:
   - Identifique quais serviços e consumidores são afetados.
2. **Tabela de taxas** :
   - Confirme se as taxas são diferentes de zero e estão corretamente assinadas.
3. **Tabela de consumo** :
   - Verifique se foram carregados volumes negativos ou nulos.
4. **Lógica de ajuste** :
   - Se forem utilizados ajustes negativos intencionalmente, confirme que eles são aplicados apenas a cenários de correção específicos.

## Questões relacionadas ao ambiente, construção e promoção

**Sintoma: As alterações testadas em Desenvolvimento não aparecem em Preparação.**

**Causas prováveis**

- Documentos retirados, mas não devolvidos.
- Build não criado ou não promovido de Em desenvolvimento para Staging.
- Analisando a compilação incorreta no Staging.

**O que verificar**

1. Em desenvolvimento:
   - Verifique se há algum documento relacionado ao faturamento ainda em circulação.
   - Certifique-se de que eles sejam verificados após o teste.
2. Visualização das compilações:
   - Confirme que uma nova compilação foi criada após o check-in.
   - Confirme que a compilação é a mesma que o Staging está usando.
3. Em preparação:
   - Verifique qual compilação está ativa e se ela contém as alterações esperadas.

**Sintoma: O estágio parece correto, mas a produção não**

**Causas prováveis**

- A compilação de teste nunca foi promovida para produção.
- Promoção concluída, mas a Produção ainda está usando dados antigos para o período.
- Os usuários estão visualizando relatórios armazenados em cache ou marcados como favoritos de uma versão anterior.

**O que verificar**

1. **Histórico de promoções** :
   - Confirme se a compilação de preparação pretendida foi promovida e bem-sucedida.
2. **ID da compilação de produção** :
   - Verifique se a compilação de produção ativa corresponde à compilação de teste validada.
3. **Relatórios** :
   - Confirme se os usuários estão abrindo relatórios do endpoint e da coleção corretos.
   - Atualize os filtros e, se necessário, os favoritos.

## Relatar problemas

**Sintoma: Os relatórios expiram ou são extremamente lentos**

**Causas prováveis**

- Intervalos de tempo muito amplos (vários anos).
- Relatórios pesados com muitas dimensões não filtradas.
- Consultas ao modelo ou conjunto de dados subjacentes não otimizadas.

**O que verificar**

1. Incentive os usuários a **filtrar** por:
   - Um único período ou intervalo de datas curto.
   - Consumidores ou serviços específicos.
2. Identifique relatórios com problemas de desempenho consistentes:
   - Considere redesenhá-los:
     - Agregando mais.
     - Removendo colunas raramente utilizadas.
3. Para questões persistentes, considere criar **relatórios resumidos** para grandes públicos e reserve relatórios detalhados para analistas.

**Sintoma: Colunas ou filtros alterados “inesperadamente”**

**Causas prováveis**

- Definição do relatório atualizada em Em desenvolvimento e promovida.
- Um relatório local clonado parece semelhante, mas não é o mesmo.
- Visualizações salvas ou filtros pessoais que substituem os padrões.

**O que verificar**

1. Confirme o nome e a localização **do relatório canônico**.
2. Compare o layout atual com o projeto documentado no Apêndice B ou nas especificações internas.
3. Se as alterações forem legítimas, atualize a documentação e as capturas de tela do treinamento.
4. Se as alterações forem acidentais, restaure o layout pretendido em Em desenvolvimento e volte a promover.

## Problemas de integração entre diários e finanças

**Sintoma: O departamento financeiro não consegue carregar o arquivo do diário**

**Causas prováveis**

- O layout do arquivo não corresponde ao formato de importação GL esperado.
- Campos obrigatórios (contas, centros de custo, códigos da empresa) em falta.
- Caracteres especiais ou problemas de codificação.

**O que verificar**

1. Compare a exportação atual com o **modelo acordado** :
   - Ordem das colunas, nomenclatura, tipos de dados.
2. Use relatórios de controle de qualidade ou validações:
   - Procure por segmentos financeiros ausentes ou inválidos.
3. Teste com um **pequeno subconjunto** de linhas:
   - Ajuda a isolar problemas de formatação versus problemas de conteúdo de dados.

**Sintoma: Diários lançados, mas os totais não correspondem aos relatórios de faturamento**

**Causas prováveis**

- Os filtros são aplicados de forma diferente em Faturamento e Finanças.
- Lançamento em períodos diferentes (por exemplo, mês de acumulação versus mês de uso).
- Diferenças de arredondamento ou conversão de moeda.
- Algumas linhas foram rejeitadas durante a publicação.

**O que verificar**

1. Execute novamente **o relatório de exportação do diário** para o período:
   - Confirme o total por conta e consumidor.
2. Em Finanças:
   - Faça um **balancete ou uma lista do diário** para as mesmas contas e o mesmo período.
3. Compare:
   - Se houver alguma diferença, verifique se:
     - Linhas rejeitadas.
     - Ajustes manuais.
     - Códigos de período diferentes.

Se as discrepâncias forem recorrentes, chegue a um acordo sobre **uma visão de reconciliação padrão** e prazos de calendário entre o departamento de Faturamento e o departamento Financeiro.

## Armadilhas específicas da edição

**Armadilhas específicas dos Essentials**

Aviso: Aplica-se apenas ao Billing Essentials.

Problemas comuns:

- Esperando ver visualizações ricas em domínios (nuvem, aplicativos, projetos) que exigem o Padrão de Faturamento.
- Supondo que o acesso ao TBM Studio exista para todas as funções, quando a configuração do Essentials é frequentemente propriedade de um parceiro ou equipe separada.

Mitigações:

- Defina expectativas claras sobre o que o Essentials pode e não pode mostrar.
- Documente como solicitar alterações de configuração à equipe que tem acesso ao Studio.

**Armadilhas específicas das normas**

Aviso: Aplica-se apenas ao padrão de faturamento.

Problemas comuns:

- Implantação excessiva de componentes de domínio sem estabilizar o caminho principal PxQ.
- Desalinhamento das alterações nos custos com as expectativas de faturamento (por exemplo, renomeação de serviços ou alteração de alocações no meio do período).
- Identificação de lacunas de governança que prejudicam as visualizações da nuvem e dos aplicativos.

Mitigações:

- Estabilize o **serviço principal × faturamento do consumidor** antes de adicionar complexidade à nuvem, ao projeto e aos preços de transferência.
- Coordenar as alterações no cálculo de custos com as partes interessadas do departamento de faturamento e finanças.
- Use relatórios de controle de qualidade e exceções específicos do domínio para reforçar a disciplina dos dados.

## Quando escalar

Algumas questões são melhor tratadas por uma equipe especializada ou um parceiro de apoio.

Escalar quando:

- Vários ciclos de faturamento consecutivos não são concluídos ou exigem soluções manuais complexas.
- Os problemas de exportação e lançamento do diário persistem mesmo após verificações locais.
- Suspeita-se que existam defeitos de modelo nos próprios componentes entregues, e não apenas na configuração local.
- Os prazos legais ou regulamentares estão em risco devido a falhas na faturação.

Antes de escalar:

- Captura:
  - Descrição clara dos sintomas.
  - Período(s) afetado(s).
  - Capturas de tela ou trechos de relatórios.
  - Medidas já tomadas e conclusões até o momento.

Uma abordagem disciplinada de resolução de problemas, juntamente com este apêndice, geralmente resolverá a maioria dos problemas localmente. Quando isso não acontecer, uma boa documentação do que você já verificou tornará qualquer escalonamento muito mais eficiente.
