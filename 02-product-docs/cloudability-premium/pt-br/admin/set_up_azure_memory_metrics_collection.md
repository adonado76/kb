---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Configurar a coleta de métricas de memória d Azure"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
  - "Conectar Microsoft Azure"
source_path: "admin/set_up_azure_memory_metrics_collection.html"
images:
  - "images/azure_monitoring.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Configurar a coleta de métricas de memória d Azure

Azure O Monitor Agent coleta dados de monitoramento de máquinas virtuais d Azure e os envia para o Monitor d Azure.

## Sobre esta tarefa

Existem dois tipos de métricas disponíveis no Monitor d Azure :

- **Métricas padrão** : porcentagem de uso da CPU, leituras/gravações em disco, taxa de transferência de rede
- **Métricas do sistema operacional convidado** : Utilização de memória

Para obter mais informações sobre as métricas do Monitor do Azure, consulte “[Métricas compatíveis com o Monitor d Azure](https://learn.microsoft.com/en-us/azure/azure-monitor/reference/metrics-index "(Abre em uma nova guia ou janela)") ”.

## Procedimento

1. Instalar o Agente de Monitor Azure
   1. Linux Instalação

      **Utilizando Azure PowerShell:**

      ```
      Set-AzVMExtension -Name AzureMonitorLinuxAgent -ExtensionType AzureMonitorLinuxAgent -Publisher Microsoft.Azure.Monitor -ResourceGroupName <resource-group-name> -VMName <virtual-machine-name> -Location <location> -TypeHandlerVersion <version-number> -EnableAutomaticUpgrade $true
      ```

      **Usando a CLI do Azure :**

      ```
      az vm extension set --name AzureMonitorLinuxAgent --publisher Microsoft.Azure.Monitor --ids <vm-resource-id> --enable-auto-upgrade true
      ```

      Para obter mais detalhes, consulte “ [Azure](https://learn.microsoft.com/en-us/azure/azure-monitor/agents/azure-monitor-agent-manage?tabs=azure-portal "(Abre em uma nova guia ou janela)") : Gerenciamento do Monitor Agent”.
   2. Instalação do Windows

      **Utilizando Azure PowerShell:**

      ```
      Set-AzVMExtension -Name AzureMonitorWindowsAgent -ExtensionType AzureMonitorWindowsAgent -Publisher Microsoft.Azure.Monitor -ResourceGroupName <resource-group-name> -VMName <virtual-machine-name> -Location <location> -TypeHandlerVersion <version-number> -EnableAutomaticUpgrade $true
      ```

      **Usando a CLI do Azure :**

      ```
      az vm extension set --name AzureMonitorWindowsAgent --publisher Microsoft.Azure.Monitor --ids <vm-resource-id> --enable-auto-upgrade true
      ```

      Observação: Para confirmar se a instalação do agente foi bem-sucedida, verifique a seção de extensões da sua máquina virtual.

      ![Azure Extensão do Agente de Monitoramento](../../../../03-media/cloudability-premium/images/azure_monitoring.jpg)
2. Enviar métricas do sistema operacional convidado com o agente de monitoramento d Azure

   Azure O Monitor Agent permite enviar métricas do sistema operacional convidado diretamente para o Monitor d Azure. Siga as etapas abaixo para configurar a coleta de dados.

   **Referência:** [Regras de coleta de dados para o agente de monitor Azure](https://learn.microsoft.com/en-us/azure/azure-monitor/agents/data-collection-rule-azure-monitor-agent?tabs=portal "(Abre em uma nova guia ou janela)")

   1. Criar regra de coleta de dados

      1. No menu **Monitor**, selecione “**Regras de coleta de dados** ”.
      2. Selecione **“Criar”** para criar uma nova regra de coleta de dados e associações.
      3. Digite um **nome para a regra** e especifique uma **assinatura**, **um grupo de recursos**, **uma região** e **um tipo de plataforma**.
      4. Na guia “**Recursos** ”:
         - Selecione **+ Adicionar recursos** e associe os recursos à regra de coleta de dados. Os recursos podem ser máquinas virtuais, conjuntos de máquinas virtuais em escala (Virtual Machine Scale Sets) e o Arc da Azure para servidores. O portal Azure instala o Agente de Monitoramento do Azure nos recursos que ainda não o tenham instalado.
         - Selecione “**Ativar pontos de coleta de dados** ”.
         - Selecione um ponto de coleta de dados para cada um dos recursos associados à regra de coleta de dados.
      5. Na guia “**Coletar e entregar** ”, selecione **“Adicionar fonte de dados”** para adicionar uma fonte de dados e definir um destino.
      6. Selecione um **tipo de fonte de dados**.
      7. Selecione quais dados você deseja coletar. Para os contadores de desempenho, é possível selecionar entre um conjunto predefinido de objetos e sua taxa de amostragem. Para eventos, você pode selecionar entre um conjunto de registros e níveis de gravidade.

         Importante: O Cloudability leva em consideração apenas as seguintes métricas para a utilização da memória:
         - **Windows:** Bytes de memória disponível + Bytes de memória alocada
         - **Linux :** mem/disponível + mem/ocupada
      8. Na guia **“Destino”**, adicione um ou mais destinos para a fonte de dados. Você pode selecionar vários destinos do mesmo tipo ou de tipos diferentes. Por exemplo, você pode selecionar vários espaços de trabalho do Log Analytics, o que também é conhecido como multihoming.
      9. Selecione **“Adicionar fonte de dados”** e, em seguida, selecione **“Revisar + criar”** para revisar os detalhes da regra de coleta de dados e a associação com o conjunto de máquinas virtuais.
      10. Selecione **“Criar”** para criar a regra de coleta de dados.

          Observação: pode levar até 5 minutos para que os dados sejam enviados aos destinos após a criação da regra de coleta de dados.

**Tópico principal:** [Conectar-se Microsoft Azure](../admin/azure-cm-setup-premium.html)
