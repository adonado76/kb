---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Segurança e conformidade"
breadcrumb:
  - "TBM Studio"
  - "Administração"
source_path: "studio/new-uc/admin/sec-comp.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Segurança e conformidade

**Tipo de conteúdo:** Conceitual / Guia prático

**Público-alvo:** Administradores, responsáveis pela segurança

**Pré-requisitos:** Função de administrador, conhecimento dos requisitos de segurança de dados

A TBM Studio oferece várias camadas de segurança para proteger dados financeiros confidenciais e garantir a conformidade com as políticas da organização. Esta seção aborda as configurações de segurança de domínios, a segurança em nível de linha e as práticas de governança de dados.

## Configurações de segurança do domínio

As configurações de segurança do domínio controlam as políticas de autenticação, os requisitos de senha e o gerenciamento de sessões para todos os usuários no seu ambiente do Apptio.

**Para acessar as configurações de segurança do domínio:**

1. Vá até a guia **Projeto**.
2. Clique **em "Segurança do domínio** ".
3. Configure políticas de senha, configurações de sessão e opções de autenticação.

**Configurações da política de senhas**

|  |  |
| --- | --- |
| **Configuração** | **Descrição** |
| Comprimento mínimo da senha | Número mínimo de caracteres exigido para senhas |
| Idade mínima da senha | Quantos dias antes é possível alterar uma senha. O valor de “ -1 ” significa “ilimitado”. |
| Tempo máximo de validade da senha | Dias até que a senha expire e precise ser alterada. O valor de “ -1 ” significa “ilimitado”. |
| Histórico de senhas | Número de senhas anteriores que não podem ser reutilizadas |

## Segurança em nível de linha (RLS)

A segurança no nível da linha garante que os usuários vejam apenas os dados aos quais têm permissão de acesso. O RLS filtra os dados no nível da linha com base nos atributos do usuário, permitindo que o mesmo relatório exiba dados diferentes para usuários diferentes.

**Nos casos em que a RLS se aplica:**

- **Tabelas de transformação** - Filtram as linhas visíveis antes que os dados sejam inseridos nos relatórios
- **Tabelas editáveis** - Restringe os dados que os usuários podem visualizar e modificar
- **Relatórios** - As agregações refletem apenas a visualização filtrada para cada usuário

**Observação:** *Ao publicar tabelas editáveis com o RLS ativado, as linhas que o usuário não consegue visualizar são preservadas, e não substituídas. Isso evita a perda de dados quando os usuários publicam suas alterações.*

## Práticas de governança de dados

Uma governança de dados eficaz garante a qualidade, a segurança e a conformidade dos dados. O TBM Studio oferece diversos recursos para apoiar os fluxos de trabalho de governança.

## Períodos de encerramento

Os períodos encerrados impedem a modificação de dados, mas permitem a geração de relatórios. Utilize períodos encerrados para os exercícios fiscais concluídos, a fim de manter a integridade dos dados.

## Regras de atualização de dados

As regras de atualização de dados monitoram quando as tabelas são atualizadas e enviam notificações caso os dados fiquem desatualizados. Isso ajuda a garantir que os dados sejam carregados em tempo hábil e evita a geração de relatórios com informações desatualizadas.

**Para criar uma regra de atualização de dados:**

1. Acesse **Projeto > Regras de atualização de dados**.
2. Clique em **“Criar regra”** e especifique a frequência de atualização desejada.
3. Configure notificações por e-mail para atualizações perdidas.
4. Associe as regras a uma ou mais tabelas.

## Linhagem de dados

A linhagem de dados rastreia o fluxo de dados ao longo do seu projeto no TBM Studio, mostrando de onde os dados se originaram, como foram transformados e onde são utilizados. O histórico é essencial para a análise de impacto e a resolução de problemas.

**Casos de uso do Lineage:**

- **Análise de impacto** - Compreender o que seria afetado pela alteração ou remoção de uma coluna ou tabela
- **Limpeza** - Identificar tabelas órfãs ou métricas calculadas não utilizadas
- **Privacidade de dados** - Identifique onde os dados confidenciais estão localizados e expostos

**Para acessar a linhagem:**

- Clique com o botão direito do mouse em qualquer entidade no Explorador de Projetos e selecione **“Rastrear Linhagem” para este documento**
- Clique com o botão direito do mouse na guia do documento, na parte inferior da área de trabalho, e selecione **“Rastrear linhagem”**
