---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Testes e validação de segurança"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
  - "Melhores práticas de segurança"
source_path: "studio/new-uc/concepts-architecture/security-model/security-testing.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Testes e validação de segurança

Validar sua configuração de segurança é tão importante quanto configurá-la inicialmente. Use essas técnicas para garantir que sua segurança funcione conforme o esperado.

**Técnicas de teste**

1. **Filtro de visualização:** Na etapa do pipeline RLS, use o filtro de visualização para inserir o e-mail de um usuário e ver exatamente quais linhas ele veria em uma tabela específica.
2. **Representação de usuário:** Os administradores podem assumir a identidade de qualquer usuário para visualizar relatórios e tabelas da perspectiva desse usuário. Isso testa toda a pilha: funções, permissões de relatórios e RLS em conjunto.
3. **Troca de funções:** Se você tiver várias funções disponíveis, alterne entre elas para verificar se a visibilidade dos relatórios e o acesso aos componentes mudam conforme o esperado. Lembre-se de atualizar o navegador após a mudança.
4. **Validação entre relatórios:** Após configurar o RLS, abra todos os relatórios que utilizam os dados protegidos para verificar se a filtragem funciona corretamente — incluindo os destinos de detalhamento.

**Erros comuns de configuração de segurança**

|  |  |  |
| --- | --- | --- |
| **Configuração incorreta** | **Risco** | **Prevenção** |
| O RLS foi aplicado às tabelas de resumo, mas não às tabelas detalhadas | Os usuários veem resumos filtrados, mas os dados não filtrados ao aprofundar a análise | Aplique o RLS a todas as tabelas acessíveis por meio da navegação detalhada |
| Utilização do RLS para usuários administradores | Os usuários administradores podem ignorar o RLS através do modo Studio | Utilize a função de administrador apenas para usuários que realmente precisem de acesso total ao sistema |
| Falta o RLS em uma etapa do modelo | Dados visíveis em um nível, mas não em outros, criando visualizações inconsistentes | Adicione uma etapa RLS a cada etapa do modelo no pipeline que exija filtragem |
| A tabela de mapeamento não foi atualizada após alterações na organização | Os novos funcionários ou os funcionários transferidos veem dados incorretos | Estabelecer um processo para atualizar as tabelas de mapeamento sempre que ocorrerem mudanças organizacionais |
| Contas de API com permissões excessivas | Os processos automatizados têm acesso mais amplo do que o necessário | Crie funções personalizadas específicas para contas de API com permissões mínimas |

**Tópico principal:** [Melhores práticas de segurança](../../../../studio/new-uc/concepts-architecture/security-model/security-best-practices.html)
