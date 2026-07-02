---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Gerenciar dados de referência no TBM Studio"
breadcrumb: []
source_path: "it-planning/planning/manage-itfmf-reference.html"
images:
  - "resources/planning_images/studio_check-out_upload.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Gerenciar dados de referência no TBM Studio

aplica-se a: Planning

As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.

As dimensões são as categorias de dados essenciais nos itens de linha do orçamento. Muitas dimensões incorporadas têm dependências em outras dimensões. Consulte [Dependências de atributos e dimensões de dados de referência](manage-reference-data.html) para obter informações. Nos aplicativos Apptio Planning , você pode trabalhar com dados TBM Studio no Microsoft Excel, trabalhar com conjuntos de dados mestre e atualizar dados de referência.

## Substituir os dados de referência do site TBM Studio

Você pode modificar os dados de referência do site TBM Studio em Data Studio. Faça o download dos dados de referência existentes em TBM Studio, modifique-os no Excel e, em seguida, substitua os dados em TBM Studio usando as etapas a seguir:

1. Em **TBM Studio**, selecione a visualização do ambiente Em desenvolvimento.
2. No Project Explorer, abra e edite as informações da tabela conforme necessário e, em seguida, clique em Exportar.
3. Abra e modifique os dados de referência no Excel e, em seguida, salve o arquivo como um arquivo.csv.
4. No Project Explorer, selecione a tabela e clique em Check Out. O nome da tabela muda para laranja para indicar que o check-out foi feito.
5. No painel Etapas, clique em Upload.

   ![imagem](../../../../../03-media/apptio-planning/resources/planning_images/studio_check-out_upload.png)
6. Clique com o botão direito do mouse em Initial Upload e selecione Overwrite.
7. Navegue até o arquivo.csv salvo e selecione-o.
8. No painel Etapas, clique em Tabela para inspecionar os dados e confirmar suas alterações.
9. Repita esse processo conforme necessário.

## Confirmar dados mestre

Confirme os dados nos conjuntos de dados mestre integrados e promova os dados para a produção usando as etapas a seguir. Observe que os conjuntos de dados mestre integrados são agrupados.

1. No Project Explorer, abra o ITP Account Master e inspecione os dados. Se os novos dados contiverem um nome de coluna diferente do nome da coluna inicial, os dados não poderão ser abertos. Nesse caso, verifique o conjunto de dados mestre e execute novamente a etapa Append para corrigir esse problema.
2. Clique em Check In.
3. Clique na guia Project (Projeto ) e, em seguida, clique em Calculation Queue (Fila de cálculo ) para visualizar o status do check-in mais recente. Quando o cálculo de preparação estiver concluído, o status será exibido como Concluído, indicando que você pode promover as alterações para Produção.
4. Altere a visualização do ambiente de In Development para Staging.
5. Clique em Lock (Bloquear ) para impedir check-ins.
6. Clique em Promotion Options (Opções de promoção ).
7. Clique em Promote Now (Promover agora ) para promover seu cálculo de Staging para Production (Produção).
8. Clique em Unlock (Desbloquear ).

## Atualizar dimensões e atributos

A tabela a seguir fornece informações sobre onde atualizar as dimensões (dados que o Planning extrai para as colunas) e os atributos de configuração (cálculos que o Planning usa para calcular o preço ou o custo).

| Módulo associado | Obrigatório ou opcional | Atualize em TBM Studio e envie para Planning | Atualize em Planning e envie para TBM Studio |
| --- | --- | --- | --- |
| Planning | Necessário | Conta | Permissões de objeto de custo |
| Planning | Necessário | Centro de custos | Regras de alocação de mão de obra |
| Planning | Necessário | Departamento |  |
| Planning | Necessário | Taxas trabalhistas |  |
| Planning | Necessário | Função |  |
| Planning | Opcional | Local |  |
| Planning | Opcional | Fornecedor |  |
| Planning | Opcional | Tipo de contrato |  |
| Planning | Opcional | Classe de ativos |  |
| Múltiplas moedas | Necessário | Taxa de câmbio real |  |
| Múltiplas moedas | Necessário | Taxa de câmbio planejada |  |
| Project Financial Planning | Necessário | Projeto |  |
| Project Financial Planning | Necessário | Grupo de projetos |  |
| Project Financial Planning | Necessário | Pool de mão de obra externa |  |
| Project Financial Planning | Necessário | Pool de mão de obra interna |  |

Observação: As permissões de objetos de custo e as regras de alocação de mão de obra são processos manuais opcionais para exportar para o Excel e fazer o upload para o site TBM Studio.

A tabela a seguir mostra onde atualizar os dados do plano, da previsão e dos resultados reais:

| Módulo associado | Obrigatório ou opcional | Atualize em TBM Studio e envie para Planning | Atualizar em Planning  e empurre para TBM Studio |
| --- | --- | --- | --- |
| Planning | Necessário | Dados reais | Dados planejados |
| Planning | Necessário |  | Dados de previsão |

VEJA TAMBÉM :

- [Gerenciar os dados de referência do centro de custos](manage-cost-center.html)
- [Atualizar a hierarquia do departamento](update-department-hierarchy.html)
- [Forçar um plano para usar dados de referência atualizados](force-plan-use.html)
