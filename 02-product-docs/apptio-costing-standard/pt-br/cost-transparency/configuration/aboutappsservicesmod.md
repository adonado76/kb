---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Sobre a configuração do módulo de aplicativos e serviços"
breadcrumb: []
source_path: "cost-transparency/configuration/aboutappsservicesmod.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Sobre a configuração do módulo de aplicativos e serviços

O Módulo de Aplicativos e Serviços é usado para alocar os custos de Torres de Recursos de TI na infraestrutura associada e, por fim, na tabela de Aplicativos e Serviços. Os relatórios resultantes podem ser usados para obter insights sobre as despesas do portfólio de aplicativos e serviços. O módulo Aplicativos e serviços é um pré-requisito para o módulo Unidades de negócios. Para configurar o módulo de aplicativos e serviços, instale os componentes do CT Apps.

Aplica-se a: Costing Standard em TBM Studio 12.0 e posterior

## Customizado

Ao contrário do módulo Costing Standard Foundation, o módulo Applications and Services geralmente é personalizado para corresponder aos dados disponíveis em uma organização. As descrições dos dados e da configuração do módulo Aplicativos e Serviços devem ser consideradas como uma maneira de configurar os componentes. A forma como você acaba configurando os componentes pode ser diferente.

## Requisitos de configuração para o módulo de aplicativos e serviços

O Módulo Costing Standard Foundation (CTF) é um pré-requisito para o Módulo de Aplicativos e Serviços. Depois que a instalação do módulo CTF estiver concluída e validada, você poderá optar por começar a usar o módulo Applications and Services simplesmente alocando partes das despesas da Torre de recursos de TI diretamente na tabela Applications Master Data com base em regras básicas. No entanto, à medida que você obtiver mais dados de infraestrutura e tiver relações disponíveis para alocar defensivamente os gastos da infraestrutura para os aplicativos de suporte, provavelmente optará por começar a trazer os dados para o aplicativo e, aos poucos, fornecer um modelo de custos mais defensável.

## Componentes do módulo

Os componentes Applications and Services não são instalados automaticamente quando você cria um projeto Costing Standard . Você deve instalar cada componente separadamente. Você pode instalar qualquer combinação dos componentes. Eles não dependem um do outro.

O CT Applications and Services Module inclui os seguintes componentes:

- CT Apps - Aplicativos
- Aplicativos CT - Comunicação
- Aplicativos CT - Centros de Data
- Aplicativos de TC - Dispositivos do usuário final
- Aplicativos CT - Mainframes
- Aplicativos CT - Rede
- Aplicativos CT - Servidores
- CT Apps - Componente de serviços
- CT Apps - componente Service Desk
- Aplicativos CT - Componente de armazenamento

| Se você modificou esse arquivo não mestre: | Você deve anexar os dados a esse arquivo mestre: |
| --- | --- |
| Lista de torres de recursos de TI | Dados mestre da torre de recursos de TI |
| Metas de utilização dos servidores | Servidores Dados mestre |
| Metas de utilização de armazenamento | Dados mestre de armazenamento |
| Dispositivos de armazenamento que utilizam metas de utilização | Dispositivos de armazenamento Dados mestre |

## Instalar os componentes

Você instala os componentes do módulo Applications and Services seguindo as mesmas etapas usadas para instalar os componentes do módulo CTF. A ordem em que você instala os componentes não é importante.

1. Clique na guia Projeto.
2. Clique em Components (Componentes) na faixa de opções.
3. Clique em um dos componentes do CT.
4. Clique em Instalar.
5. Clique em View All Components (Exibir todos os componentes).
6. Repita as etapas 4 a 6 para os componentes restantes do TC.

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
