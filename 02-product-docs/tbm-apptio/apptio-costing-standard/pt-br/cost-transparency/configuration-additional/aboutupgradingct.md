---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Sobre a atualização do padrão de cálculo de custos"
breadcrumb: []
source_path: "cost-transparency/configuration-additional/aboutupgradingct.html"
images:
  - "resources/images/ap_images/ui-tbar-settings.png"
  - "resources/images/ct_images/11151_1.png"
  - "resources/images/ct_images/11151_5.png"
  - "resources/images/ct_images/ct-about-1.png"
  - "resources/images/ct_images/ct-comp-vers.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Sobre a atualização do padrão de cálculo de custos

- Aplica-se a: TBM Studio 12.x e posterior, no modelo v102 e posterior

O processo de upgrade para Costing Standard envolve atualizações nas seguintes camadas.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/11151_1.png)

## Camada de plataforma

A plataforma (ou base de código Apptio ), denominada TBM Studio, é um conjunto de recursos e capacidades que permitem executar tarefas que orientam os aplicativos Apptio, como criar modelos, carregar conjuntos de dados, alocar custos e criar relatórios. TBM Studio também inclui o mecanismo de cálculo Apptio.

A meta é fazer o upgrade de todos os clientes do TBM Studio 12.x para a versão mais recente a cada trimestre. Em um esforço para manter nossos aplicativos atualizados com os recursos e aprimoramentos de desempenho mais recentes, programamos a manutenção obrigatória durante um intervalo de datas específico. Para saber as datas, entre em contato com o gerente de sucesso do cliente ou com a [equipe do CS-Upgrade](https://community.apptio.com/docs/DOC-9207 "(Abre em uma nova guia ou janela)").

**Controle de versão**. R12 é um atalho que se refere à versão atual do produto básico TBM Studio . As versões incrementais de TBM Studio são representadas como 12.1, 12.2, etc. Para fazer upgrade para uma nova versão do TBM Studio, entre em contato com o Customer Success Manager.

Para ver a versão do TBM Studio que está sendo executada, selecione ![](../../../../../03-media/apptio-costing-standard/resources/images/ap_images/ui-tbar-settings.png) > About.

A janela a seguir exibe a versão TBM Studio :

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ct-about-1.png)

## Camada de aplicativos

Os aplicativos são componentes predefinidos que usam os recursos da plataforma para atingir um caso de uso. Os componentes do aplicativo podem conter os seguintes elementos de conteúdo:

- Conjuntos de dados mestre
- Objetos modelo
- Taxonomia
- Métricas
- Perspectivas
- Relatórios

**Controle de versão**. O controle de versão dos aplicativos Apptio é refletido como versões de modelo. O modelo v106, por exemplo, é o número de versão atribuído aos componentes do aplicativo lançados com TBM Studio 12.6. É possível usar versões anteriores do modelo (por exemplo, Modelo v105 em TBM Studio 12.6 ), mas não vice-versa. Por exemplo, você não pode executar o Template v106 em TBM Studio 12.5.

Para ver a versão do modelo que está sendo executada, abra TBM Studio e selecione *Project > Project Settings*.

A caixa de diálogo Editar configurações do projeto é aberta, exibindo a versão do componente.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ct-comp-vers.png)

**Orientação de upgrade**

As atualizações de aplicativos ficam a seu critério:

- Mude para um novo modelo de aplicativo se quiser usar os recursos e aprimoramentos mais recentes introduzidos por esse modelo.
- Você pode optar por fazer upgrade para uma nova versão da plataforma, mas permanecer na versão atual do modelo do aplicativo. Por exemplo, você pode optar por atualizar para TBM Studio 12.6, mas permanecer no Template v104 se não precisar dos recursos mais recentes.
- Você pode ignorar as versões de modelo. Por exemplo, você pode atualizar do modelo de aplicativo v104 para v106, ignorando o modelo v105. No entanto, se você optar por ignorar as versões, deverá atualizar todos os seus componentes para evitar possíveis problemas.

Observação: para acessar um modelo de aplicativo atual, é necessário fazer upgrade para a versão mínima da plataforma compatível com esse modelo. Por exemplo, não é possível acessar o modelo v106 a menos que você esteja em TBM Studio 12.6 e posterior.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/11151_5.png)

Você deve atualizar o site TBM Studio antes de atualizar o modelo de aplicativo.

Para obter instruções passo a passo:

- Faça o upgrade do modelo v103, consulte [Upgrade Costing Standard do modelo v103 para a versão mais recente](../v12.x-on-tbm-studio-12.x/upgrade-guide-v103-to-latest/upgradect.html).
- Faça upgrade dos modelos v104 ou posterior, consulte [Upgrade Costing Standard do modelo v104+ para a versão mais recente](../v12.x-on-tbm-studio-12.x/upgradect-v104.html).

## Camada de taxonomia da TBM

A Taxonomia TBM é uma estrutura para alocar os custos de TI em uma abordagem padrão que permite que os líderes de tecnologia executem e otimizem a TI como um negócio. A atualização de uma versão para outra é uma decisão orientada pelo cliente e não está diretamente relacionada às atualizações da plataforma ou do conteúdo. Os arquivos de referência para cada versão do ATUM estão disponíveis no produto. A mudança de uma versão do site ATUM para outra exige alterações nos dados e nas estratégias de alocação para mapear os custos para as novas categorias. Para obter mais informações, consulte a seção
