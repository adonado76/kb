---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Perguntas frequentes sobre usuários e grupos de usuários"
breadcrumb:
  - "Cloudability Premium"
  - "Administração"
  - "Gerenciar usuários e grupos de usuários"
source_path: "admin/users-and-user-groups-faqs.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Perguntas frequentes sobre usuários e grupos de usuários

## Entra ID e IDP são sinônimos?

O Entra ID é um dos provedores de identidade (IDP) mais utilizados. Há muitas outras IDPs, como Okta, PingIdentify. No momento, estamos oferecendo suporte apenas ao Microsoft Entra ID (também conhecido como Azure AD).

## Qual função em Cloudability pode acessar os recursos?

O recurso pode ser acessado com a permissão existente " UserManagementFeatureFullAccess". Portanto, se um usuário tiver acesso ao recurso 'Gerenciamento de usuários' anteriormente, ele também terá acesso aos recursos Grupos de usuários e Grupos de ID Entra.

## Quantos grupos de usuários ou grupos de IDs Entra podem ser criados em Cloudability?

Não há limite para o número de grupos de usuários ou grupos de IDs Entra que podem ser criados.

## Há um limite para o tamanho do nome de um grupo de usuários?

Sim, os nomes de grupos em Cloudability podem ter até 63 caracteres. Esse limite está alinhado com o limite de caracteres para grupos de IDs Entra no Microsoft Entra ID.

## Quanto tempo leva para as alterações entrarem em vigor ao atribuir visualizações a grupos?

As mudanças seriam quase imediatas. Os usuários que obtiverem acesso ao View via Groups poderão ver as visualizações quase imediatamente.

## As alterações feitas no Entra ID serão refletidas automaticamente no site Cloudability?

As alterações feitas no Entra ID não serão transferidas automaticamente para o site Cloudability. Cloudability Os administradores precisariam sincronizar manualmente usando o botão "Sync Entra ID Groups".

## Quanto tempo é necessário para sincronizar os grupos Entra ID?

Isso pode levar de alguns milissegundos a alguns minutos, dependendo do número de grupos que estão sendo sincronizados e do número de usuários em cada grupo. Se o processo de sincronização estiver demorando mais, será necessário aguardar. Você sempre pode voltar e verificar o campo "Last Synced" Date (Data da última sincronização) para saber se a sincronização foi concluída.

## O que acontece se um usuário que é membro do Entra ID Group não existir em Cloudability?

Durante a sincronização, o site Cloudability verifica se os usuários do grupo Entra ID existem ou não no Cloudabilty. Se um usuário não existir em Cloudability, ele não será importado. Portanto, se você tiver 10 usuários em um Entra ID Group e apenas 8 existirem em Cloudability, somente 8 usuários serão importados.

Observação: Trazer usuários que não sejam da nuvem não é útil, pois eles não podem fazer login em Cloudability de qualquer forma.

## Ao sincronizar os grupos de IDs do Entra, por que alguns usuários não estão sendo importados para o site Cloudability?

Isso geralmente acontece quando os usuários no Entra ID ( Azure AD) não têm um endereço de e-mail válido configurado **ou** se o e-mail configurado não corresponde ao e-mail do usuário em Cloudability. Mesmo que o usuário exista no grupo, o Cloudability só importará usuários cujos endereços de e-mail estejam presentes e coincidam com os do Cloudability. Verifique se o ID de e-mail do usuário não está ausente, vazio ou mal configurado no Entra ID.

## Um usuário pode fazer parte de vários grupos de usuários?

Sim, os usuários podem fazer parte de vários grupos, tanto nos grupos Entra ID quanto nos grupos de usuários manuais.

## Podemos usar esses grupos com HVs (visualizações hierárquicas)?

Sim. Os grupos de usuários e os grupos de ID Entra também estarão disponíveis com HVs.

## Qual é o roteiro para apoiar Grupos de Usuários e Grupos Entra ID para compartilhar Relatórios, Painéis, Alertas, etc.?

O suporte para **grupos de usuários** e **grupos de identificação de armadilhas** está planejado, mas ainda não está disponível em todos os recursos. Atualmente, esses grupos não podem ser usados para compartilhamento ou alertas nas áreas listadas abaixo:

1. Compartilhamento de relatórios e painéis: atualmente, só há a opção de compartilhar com toda a organização ou com usuários.
2. Compartilhamento de painéis de contêineres: atualmente, só há a opção de compartilhar com toda a organização ou com usuários
3. Criando alertas para detecção de anomalias
4. Compartilhamento de planos de carga de trabalho
5. Criando alertas para o plano CFP

Os recursos acima estão no roteiro e estamos trabalhando ativamente para expandir o compartilhamento e os alertas baseados em grupos nessas funcionalidades. As atualizações serão comunicadas assim que a funcionalidade estiver disponível.

## Esses grupos são compatíveis com o site Apptio BI?

Não, não há suporte para User Groups e Entrap ID Groups no site Apptio BI. Sem mencionar que os relatórios e painéis do Cloudability respeitarão o acesso às visualizações com base nesses grupos.

**Tópico pai:** [Gerenciar usuários e grupos de usuários](../admin/manage-users-and-user-groups.html)
