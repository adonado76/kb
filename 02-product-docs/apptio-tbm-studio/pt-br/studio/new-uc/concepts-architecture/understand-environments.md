---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Compreendendo os três ambientes"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Ciclo de vida de compilação e implantação"
source_path: "studio/new-uc/concepts-architecture/understand-environments.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Compreendendo os três ambientes

O TBM Studio organiza o trabalho em três ambientes distintos, cada um com uma finalidade específica no fluxo de trabalho que vai do desenvolvimento à produção. É possível acessar os três ambientes a partir de um único URL, pelo menu “Ambiente” na barra de ferramentas.

**Ambiente de desenvolvimento**

O ambiente de desenvolvimento é o seu espaço de trabalho pessoal para fazer alterações. Ao fazer o check-out de um documento e começar a editá-lo, você entra automaticamente no ambiente de desenvolvimento. As principais características incluem:

- **Isolamento:** Suas edições são locais, restritas ao seu espaço de trabalho. Os outros usuários não poderão ver suas alterações até que você as envie.
- **Cálculo em tempo real:** ao salvar as alterações, o TBM Studio calcula as transformações e as métricas para que você possa validar seu trabalho imediatamente.
- **Vários espaços de trabalho:** se outros usuários tiverem documentos retirados, seus ambientes de desenvolvimento aparecerão no menu Ambiente. Com as permissões adequadas, você pode visualizar ou até mesmo editar documentos no espaço de trabalho de outro usuário.
- **Mudança automática:** quando você não tiver nenhum documento retirado, o TBM Studio muda automaticamente para o ambiente de teste.

**Ambiente de teste**

O ambiente de preparação reúne todas as alterações registradas de todos os usuários. Funciona como camada de integração e validação antes da produção. As principais características incluem:

- **Estado compartilhado:** todas as edições de todos os usuários são combinadas aqui após o check-in.
- **Cálculo completo:** Após cada registro, o Stage realiza um cálculo completo, incluindo exercícios e relatórios.
- **Gateway de validação:** os administradores validam as alterações no ambiente de teste antes de promovê-las para o ambiente de produção.
- **Recurso de bloqueio:** A fase de preparação pode ser bloqueada para impedir novos check-ins durante o processo de promoção.

Nota:

Os nós de cálculo de estágios são provisionados sob demanda, o que pode levar até 15 minutos. O cálculo em si é executado após a conclusão do provisionamento.

**Ambiente de Produção**

O ambiente de produção contém a versão validada e aprovada do seu projeto, que é utilizada pelos usuários finais. As principais características incluem:

- **Somente leitura para a maioria dos usuários:** os usuários com permissão apenas de visualização sempre veem o ambiente de produção. Eles não conseguem ver os ambientes de teste ou de desenvolvimento.
- **Atualizações controladas:** Somente administradores podem transferir conteúdo do ambiente de teste para o de produção.
- **Promoção quase instantânea:** No TBM Studio 12.x, a promoção para a fase de produção é quase instantânea.
- **A visibilidade depende da promoção:** a produção só aparece no menu Ambiente depois que o Stage tiver sido promovido pelo menos uma vez.

**Comparação de ambientes**

|  |  |  |  |
| --- | --- | --- | --- |
| **Aspecto** | **Desenvolvimento** | **Preparação** | **Produção** |
| Propósito | Edição individual | Integração e validação | Consumo do usuário final |
| Visibilidade | Específico do usuário | Todos os editores | Todos os usuários |
| Calcula | Transformações, Métricas | Transformações, métricas, análises detalhadas, relatórios | Recebe compilações promovidas |
| Quem pode editar | Usuários avançados, administradores | N/A (aceita check-ins) | N/A (recebe promoções) |
