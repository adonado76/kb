---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Autenticação e identidade"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
source_path: "studio/new-uc/concepts-architecture/security-model/authentication-identity.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Autenticação e identidade

A autenticação é a primeira camada de segurança. Isso verifica se o usuário é quem afirma ser antes de conceder qualquer acesso ao TBM Studio.

## Métodos de autenticação

O TBM Studio oferece suporte a vários métodos de autenticação, gerenciados por meio da plataforma Enhanced Access Administration (EAA).

**Nome de usuário e senha**

O método de autenticação mais básico. Os usuários fazem login com um endereço de e-mail e uma senha. Os administradores de domínio configuram as políticas de senha por meio da caixa de diálogo Segurança do domínio, incluindo:

- Tempo mínimo e máximo de validade da senha (o valor “ -1 ” significa ilimitado)
- Requisitos de complexidade da senha
- Políticas de bloqueio de contas

Nota: **Configuração da política de senhas**

Um valor de “ -1 ” nos campos “Idade mínima da senha” e “Idade máxima da senha” significa “ilimitado” Deixe o campo “Intervalo mínimo entre alterações de senha” definido como “ -1 ”, a menos que sua organização exija um intervalo mínimo entre as alterações de senha.

**Autenticação única (SSO)**

Para organizações que utilizam provedores de identidade corporativos, o TBM Studio oferece suporte à integração de SSO. Quando o SSO está ativado, os usuários se autenticam por meio do provedor de identidade corporativo, em vez de digitar uma senha separada do TBM Studio. O SSO é configurado no nível do usuário — definir a senha de um usuário como “SSO” (em qualquer formato) faz com que o usuário seja autenticado por meio do provedor de SSO.

**Autenticação por chave de API**

Para acesso programático (envios e downloads de dados, além de integrações), o TBM Studio oferece suporte à autenticação por chave de API por meio da Administração de Acesso Avançada. As chaves de API consistem em uma chave pública e uma chave secreta. Elas são o método de autenticação preferido para acesso à API, pois oferecem maior segurança do que os pares de nome de usuário/senha e podem ser limitadas a permissões específicas.

Nota:

**Melhores práticas: autenticação de API**

Use chaves de API em vez de nome de usuário/senha para todas as integrações automatizadas. É possível conceder permissões mínimas às chaves de API (como acesso apenas para upload), seguindo o princípio do privilégio mínimo. Consulte a seção 5.5 (Referência da API) para obter informações detalhadas sobre a configuração da chave da API.

## Identidade do usuário no TBM Studio

Quando um usuário se autentica, o TBM Studio cria uma sessão que rastreia sua identidade durante toda a sua interação com o sistema. Os principais conceitos da sessão incluem:

- **Tokens de sessão:** Após a autenticação, o sistema emite um token (como o Apptio -opentoken) que é utilizado nas solicitações subsequentes sem a necessidade de repetir a autenticação.
- **Tempo limite da sessão:** as sessões expiram após um período de inatividade, configurado no nível do domínio. Quando uma sessão expira, o usuário precisa se autenticar novamente.
- **Representação:** Os administradores podem assumir a identidade de outro usuário para verificar suas permissões e resolver problemas de acesso. Esta é uma ferramenta de teste valiosa para validar configurações de segurança.

Importante: **Falsificação de identidade**

A representação é uma ferramenta administrativa poderosa. Use-o apenas para fins de teste e resolução de problemas. Ao assumir a identidade de um usuário, você vê exatamente o que esse usuário veria, incluindo suas restrições de RLS e permissões de relatório.
