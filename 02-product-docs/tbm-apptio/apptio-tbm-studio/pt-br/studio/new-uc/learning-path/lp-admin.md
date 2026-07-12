---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Cursos de formação para administradores"
breadcrumb:
  - "TBM Studio"
  - "Percursos de aprendizagem (baseados em funções)"
source_path: "studio/new-uc/learning-path/lp-admin.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Cursos de formação para administradores

**Objetivo:** Configurar, proteger, otimizar e manter o TBM Studio para sua organização

**A quem se destina:** administradores do TBM Studio, gerentes de plataforma e qualquer pessoa responsável pela configuração do sistema, gestão de usuários e suporte à produção

## Fundamentos (1 hora)

**O que você** aprenderá: Responsabilidades do administrador e conceitos básicos da plataforma

**Objetivos de aprendizagem:**

- Compreender as funções e responsabilidades do administrador
- Conheça o modelo de funções e permissões do usuário
- Compreender o ciclo de vida do desenvolvimento (Dev → Stage → Prod)
- Navegar pelas interfaces administrativas
- Reconhecer os principais conceitos da plataforma

**Tópicos a serem concluídos:**

1. **Visão geral das responsabilidades do administrador** (15 min) *→ Seção 6.1*
2. **Funções e permissões do usuário** (15 min) *→ Seção 6.2*
3. **Ciclo de vida do desenvolvimento** (20 min) *→ Seção 4.5*
4. **Arquitetura da plataforma** (10 min) *→ Seção 4.2, 4.3*

**Pré-requisitos:** Conhecimentos básicos do TBM Studio (recomenda-se concluir o tutorial de Início Rápido)

## Competências essenciais (4 horas)

**O que você** aprenderá: Tarefas administrativas do dia a dia, incluindo gerenciamento de usuários, permissões, compilações e segurança

**Objetivos de aprendizagem:**

- Criar e gerenciar usuários e funções
- Configurar as definições do projeto
- Executar processos de check-in e compilação
- Gerenciar o fluxo de trabalho do desenvolvimento à produção
- Implementar segurança no nível da linha (RLS)
- Monitorar e solucionar problemas nas compilações

**Tópicos a serem concluídos:**

1. [Gerenciar usuários e funções (45 min)](../howtoguides/manage-users-permission/manage-up-intro.html)
2. **Configurar projetos** (30 min) *→ Seção 6.1*
3. **Fluxo de trabalho do check-in principal** (45 min) *→ Seção 4.5*
4. **Processo de compilação e promoção** (60 min) *→ Seção 4.5*
5. [Implementar segurança no nível da linha](../howtoguides/manage-users-permission/implement-rls.html) (45 min)
6. **Monitorar o estado do sistema** (15 min) *→ Seção 6.4*

**Pré-requisitos:** Conclusão do curso básico, acesso de administrador a um projeto

**Tempo estimado para a prática:** Acrescente 2 a 3 horas de prática no ambiente de desenvolvimento

## Avançado (6 horas)

**O que você** aprenderá: Ajuste de desempenho, cenários complexos de segurança, recuperação de desastres e otimização de plataforma

**Objetivos de aprendizagem:**

- Otimize o desempenho da compilação e os tempos de cálculo
- Gerenciar componentes e dependências
- Resolver problemas complexos de compilação
- Gerenciar a recuperação de desastres e a reversão
- Configurar atualização avançada de dados e automação
- Implementar estratégias de ramificação
- Ajuste a plataforma para obter o melhor desempenho

**Tópicos a serem concluídos:**

1. **Otimização de desempenho** (90 min) *→ Seção 6.4*
2. **Gerenciamento de componentes** (45 min) *→ Seção 6.1*
3. **Solução avançada de problemas de compilação** (60 min) *→ Seção 7.1, 7.3*
4. **Recuperação de desastres e reversão** (45 min) *→ Seção 4.5*
5. **Atualização avançada de dados** (30 min) *→ Seção 6.4*
6. **Estratégias de ramificação** (45 min) *→ Seção 4.5*
7. **Reforço de segurança** (45 min) *→ Seção 6.3*

**Pré-requisitos:** Conclusão do curso de Competências Essenciais, experiência prática em suporte à produção

**Desafios comuns:**

- **Compilações lentas:** use o Calc Explorer, simplifique os modelos, analise a complexidade das transformações
- **O RLS não está funcionando:** verifique a precisão da tabela de mapeamento e as atribuições de funções
- **Falhas na promoção:** Valide cuidadosamente no ambiente de teste e verifique se há diferenças entre os ambientes
- **Reclamações dos usuários sobre o acesso:** analise as permissões de forma sistemática e utilize a função de representação para verificar
