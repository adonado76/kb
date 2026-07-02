---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Inventário de recurso"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
source_path: "product/resource-inventory.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Inventário de recurso

O Inventário de Recursos permite criar uma lista de recursos em nuvem provenientes de várias contas, com diversas dimensões e métricas. Ao unificar os dados de faturamento, utilização e metadados descritivos, você consegue obter uma visão mais abrangente do inventário dos seus recursos.

## Principais casos de uso para o inventário de recursos

1. **Mapeamento de dados de custo para utilização**

   **Solução:** Ao combinar o Inventário de Recursos com as tags sintéticas d Cloudability (dimensões de tag, grupos de contas e mapeamentos de negócios), é possível mapear com precisão os custos dos recursos. Por exemplo, é possível verificar a utilização exata da CPU e da memória de uma instância específica do Compute Engine pertencente à “Equipe Alpha” e alocar seu custo de acordo com isso. Isso permite a criação de relatórios de showback robustos para que as equipes compreendam seu consumo, bem como modelos de chargeback fundamentados para o faturamento interno.
2. **Redução de resíduos**

   **Desafio:** Recursos com provisionamento excessivo geram gastos desnecessários com a nuvem. Identificar manualmente instâncias do Compute Engine ou discos gerenciados subutilizados é demorado e propenso a erros.

   **Solução:** Utilize as métricas “Utilização da CPU (média)”, “Utilização da memória (média)” e “Memória utilizada” do inventário. Identifique instâncias com uso médio de CPU ou memória consistentemente baixo. No caso dos discos gerenciados, monitore seu tamanho em relação aos dados efetivamente armazenados para identificar oportunidades de redução do tamanho.
3. **Otimização de desempenho e identificação de gargalos**

   **Desafio:** Recursos com provisionamento insuficiente podem causar gargalos de desempenho, afetando a capacidade de resposta das aplicações e a experiência do usuário. Para identificar a causa raiz, são necessários dados detalhados de utilização.

   **Solução:** Analise a utilização da CPU (máxima), a utilização da memória (máxima) e a utilização da rede (máxima). Picos nessas métricas podem indicar a necessidade de ampliar os recursos. Esses dados ajudam você a otimizar de forma proativa a alocação de recursos para garantir o desempenho ideal das aplicações.
4. **Resolução proativa de problemas**

   **Desafio:** Picos inesperados de custos ou queda no desempenho podem ser difíceis de identificar sem dados detalhados no nível dos recursos.

   **Solução:** Monitore regularmente as métricas de utilização fornecidas pelo Inventário de Recursos. Aumentos repentinos e inexplicáveis na utilização da CPU (mín.) ou na memória utilizada em uma instância que, de resto, está estável podem indicar um processo fora de controle, uma configuração incorreta ou até mesmo um incidente de segurança. Ao configurar alertas com base nessas métricas, você pode detectar anomalias antecipadamente e tomar medidas corretivas antes que elas tenham um impacto significativo nos custos ou nas operações.
5. **Gerenciamento do ciclo de vida e governança de recursos**

   **Desafio:** Acompanhar o ciclo de vida dos recursos em nuvem, desde a ativação até o desativamento, pode ser complexo, levando à existência de recursos “zumbis” que geram custos sem agregar valor.

   **Solução:** A “data de lançamento dos recursos”, combinada com as métricas de utilização, é de valor inestimável. Identifique os recursos que estão em execução há um longo período com baixa utilização persistente. Por exemplo, uma instância do Compute Engine com uma data de ativação muito antiga e com utilização de CPU (média) e utilização de memória (média) consistentemente baixas pode ser um recurso esquecido que pode ser encerrado com segurança. Essa abordagem proativa garante uma melhor gestão dos recursos e evita gastos desnecessários.

Ao oferecer uma visão unificada do seu inventário, acompanhada de métricas detalhadas de utilização e metadados essenciais, o Cloudability permite que você tome decisões baseadas em dados, otimize seus gastos com nuvem e aumente a eficiência de suas operações na nuvem.

- **[AWS Inventário de recursos](../product/aws-resource-inventory.html)**
- **[Azure Inventário de recursos](../product/azure-resource-inventory.html)**
- **[GCP Inventário de recursos](../product/gcp-resource-inventory.html)**
- **[Inventário de Recursos da OCI](../product/oci-resource-inventory.html)**
- **[Perguntas frequentes sobre o inventário de recursos](../product/resource-inventory-faqs.html)**
