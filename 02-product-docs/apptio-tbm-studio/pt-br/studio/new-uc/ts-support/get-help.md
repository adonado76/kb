---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Como obter ajuda"
breadcrumb:
  - "TBM Studio"
  - "Solução de problemas e suporte"
source_path: "studio/new-uc/ts-support/get-help.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Como obter ajuda

Caso a solução de problemas por conta própria não resolva o seu problema, utilize estes recursos para obter assistência adicional.

## Recursos internos

Antes de entrar em contato com o suporte, verifique o painel de Recomendações para obter sugestões automáticas. Muitos problemas podem ser resolvidos automaticamente com os assistentes de solução de problemas. Use o recurso de pesquisa de relatórios para localizar métricas, rótulos, dimensões ou componentes em todo o projeto.

## Como entrar em contato com o suporte

**Quando entrar em contato com o suporte:**

- A solução de problemas por conta própria não resolveu o problema
- Você precisa recuperar as configurações antigas
- Suspeita-se que haja problemas no nível do sistema
- Você precisa de ajuda com operações de reversão ou recuperação complexas

**Preparação para entrar em contato com o suporte - Reúna estas informações:**

- Texto exato de quaisquer mensagens de erro
- Passos para reproduzir o problema
- Ambiente (Desenvolvimento, Teste ou Produção)
- Quando a edição foi publicada pela primeira vez
- Quaisquer alterações recentes na configuração ou nos dados
- Dados do Calc Explorer (se estiverem relacionados ao desempenho)
- Capturas de tela que mostram o problema

## Cadeia de escalonamento

|  |  |
| --- | --- |
| **Nível** | **Ações** |
| **Nível 1: Autoatendimento** | Use o painel de recomendações, analise o painel de erros, verifique o Calc Explorer, consulte a documentação |
| **Nível 2: Equipe** | Coordenar com outros usuários do TBM Studio, consultar o administrador interno e verificar se há problemas conhecidos |
| **Nível 3: Suporte** | Envie um ticket de suporte com informações detalhadas, incluindo os dados de diagnóstico do Calc Explorer |
| **Nível 4: CSM** | Para questões complexas ou recorrentes, orientação estratégica sobre otimização de modelos e solicitações de funcionalidades |

## 7.4.4 Reverter uma configuração

Quando algo der errado e você precisar restaurar uma configuração anterior, use o recurso de reversão. Considere reverter as alterações quando algo que foi integrado estiver causando problemas de desempenho, algo tiver sido implantado prematuramente ou alterações na configuração tiverem prejudicado o funcionamento do sistema.

Atenção: **Considerações importantes antes de reverter as alterações**

- Quaisquer cálculos em andamento serão interrompidos
- Todos os check-ins realizados após o ponto de reversão serão descartados
- Será necessário executar um cálculo de fase completa
- Se houver outros cálculos do projeto em execução, a reversão poderá ficar na fila

**Procedimento de reversão:**

- Selecione o documento no Explorador de Projetos
- Na guia "Build", selecione "Histórico de check-in"
- Clique com o botão direito do mouse no check-in para o qual deseja reverter e selecione “Reverter para”
- Insira um motivo descritivo para a reversão
- Clique em “Reversão do check-in” e monitore o status da compilação
- Quando terminar, atualize as áreas de trabalho em Página inicial > Atualizar área de trabalho
