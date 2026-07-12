---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Ramos e correções"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Ciclo de vida de compilação e implantação"
source_path: "studio/new-uc/concepts-architecture/branch-hotfix.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Ramos e correções

A ramificação permite criar uma cópia completa de um projeto, fazer alterações em paralelo e, em seguida, mesclar essas alterações de volta. Esse recurso avançado oferece suporte a fluxos de trabalho complexos nos quais os processos normais de check-in não são suficientes.

**Ramos x Espaços de trabalho**

**Uma área de trabalho** é um ambiente específico do usuário onde as alterações feitas nos documentos retirados ficam armazenadas até o momento do retorno. Quando você faz o check-out de um documento, você obtém um bloqueio exclusivo sobre ele.

**Um branch** é uma cópia completa do projeto no momento em que foi criado. As alterações feitas em um branch são independentes do trunk principal até que sejam mescladas. Seu espaço de trabalho em um ramo é independente do seu espaço de trabalho no tronco.

**Quando usar ramificações**

Os ramos oferecem suporte a três casos de uso principais:

**1. Alterações de configuração de longo prazo**

Quando as alterações de configuração demorarem semanas ou meses para serem concluídas, crie um branch para trabalhar em paralelo enquanto o carregamento de dados operacionais continua no trunk. Exemplo: uma grande reestruturação do modelo que exige testes extensivos.

**2. Correção de emergência na produção**

Quando o ambiente de produção apresentar um problema, mas o de desenvolvimento contiver alterações que ainda não estão prontas para implantação, crie um ramo de correção. Corrija o problema específico no branch, promova-o para a produção e, em seguida, faça a fusão da correção de volta ao trunk. As ramificações de hotfix são processadas em paralelo com outras compilações, contornando a fila normal.

**3. Auditar ou arquivar o estado anterior**

Quando precisar visualizar um estado anterior do projeto — como um exercício fiscal encerrado —, crie um branch a partir desse momento. Isso permite que você veja os números exatos como eram, mesmo que o modelo atual tenha mudado.

**Limites de ramificação e considerações sobre desempenho**

- **Limite de ramificações:** máximo de 5 ramificações por ambiente (em todos os projetos)
- **Uso de recursos:** Cada ramificação utiliza os mesmos recursos que o projeto original. A criação de um branch efetivamente dobra o consumo de recursos.
- **Fila de cálculos:** os cálculos das ramificações (exceto hotfixes) são colocados na fila junto com os cálculos do tronco. Se o tronco leva 3 horas para ser calculado, o ramo também levará.
- **Ajuste o intervalo de tempo:** Limite o intervalo de tempo na sua ramificação (Configurações do projeto > Configurações de tempo) para minimizar o tempo de cálculo. Use apenas os períodos necessários para os testes.

Atenção:

**Impacto no desempenho:** Antes de criar uma ramificação, considere o impacto nos tempos de cálculo. Se o cálculo do seu projeto no trunk levar 3 horas, a criação de um branch acionará imediatamente um cálculo de mais de 3 horas, podendo ficar na fila atrás ou à frente dos cálculos do trunk.

**Criação de um ramo de correção**

Quando a Produção precisa de uma correção urgente, mas o Ambiente de Teste ainda não está pronto para ser promovido:

1. Acesse o documento na versão de produção.
2. Dê uma olhada no documento. Quando solicitado, selecione “Hotfix” (não “Desenvolvimento”).
3. Faça suas alterações e envie o código. A linha de hotfixes é compilada em paralelo com outras compilações.
4. Bloqueie o ramo da correção no Stage e selecione Promover agora.
5. Incorpore as alterações ao branch principal para que não se percam.
6. Promova a compilação do trunk que inclui a correção incorporada.
7. Feche o ramo de correções para economizar recursos.

**Mesclagem de ramos**

Antes de realizar a fusão, certifique-se de que:

- Nenhum dos documentos a serem mesclados está em checkout no trunk
- Você não tem nenhum documento retirado do repositório
- Todos os documentos da filial foram registrados

Para mesclar: No “Histórico de check-ins” do ramo, selecione os check-ins a serem mesclados (Ctrl+clique para selecionar vários), clique com o botão direito do mouse e selecione “Mesclar alterações no ramo”. Resolva quaisquer conflitos caso o mesmo documento tenha sido modificado tanto no branch quanto no trunk. Após a fusão, faça o check-in dos documentos fusionados no trunk.

Nota:

**Prática recomendada:** Limite os check-ins de ramificação a aproximadamente 30 documentos por vez. Se você tiver 100 documentos retirados, devolva-os em lotes de 30. Isso resolve uma limitação ao mesclar um grande número de check-ins.
