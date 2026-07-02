---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Configurações do calendário fiscal"
breadcrumb:
  - "Planning"
  - "Configuração e administração"
source_path: "it-planning/planning/custom-calendars.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configurações do calendário fiscal

As configurações do Calendário Fiscal definem como o tempo é estruturado e exibido no Apptio Planning. Um ano fiscal representa uma estrutura temporal recorrente utilizada para o planejamento financeiro, orçamentação e elaboração de relatórios. Ao contrário do calendário gregoriano tradicional, um ano fiscal não precisa começar em 1º de janeiro nem terminar em 31 de dezembro. Em vez disso, as organizações definem datas fiscais que melhor se alinham com seus ciclos de negócios e práticas do setor.

Observação: é necessário ter a função de administrador para gerenciar as configurações do Calendário Fiscal.

Dependendo do tipo de calendário, um ano fiscal pode ser organizado da seguinte forma:

- 12 meses consecutivos (calendário gregoriano),
- Períodos semanais, como variantes 4-4-5, ou
- 13 períodos iguais, normalmente concebidos de forma a que cada período contenha o mesmo número de dias.

Em todos os casos, os calendários fiscais são projetados para se alinharem com o calendário gregoriano subjacente ao longo do tempo, levando em consideração a duração padrão dos anos e os anos bissextos, quando aplicável. Essas configurações se aplicam a todo o ambiente e determinam como as despesas, previsões e resumos são organizados e exibidos em todos os planos.

## Tipos de calendário suportados

Apptio O planejamento suporta os seguintes tipos de calendário fiscal:

**Calendário gregoriano**

O calendário gregoriano é a estrutura fiscal mais comum e consiste em 12 meses consecutivos.

**Recursos:**

- Suporta anos fiscais tradicionais e não tradicionais
  - **Tradicional:** O ano fiscal começa em janeiro e termina em dezembro
  - **Não tradicional:** o ano fiscal começa em qualquer mês selecionado pelo usuário
- Para inícios que não sejam em janeiro, escolha se o ano fiscal é:
  - **Definido pelo período inicial** (por exemplo, FY2025 é julho de 2025 a junho de 2026) ou
  - **Definido pelo período final** (por exemplo, FY2025 julho 2024-June2025 )
- Os rótulos de período podem ser exibidos como:
  - **Meses** (janeiro, fevereiro, março) ou
  - **Pontos** ( P1, P2, P3 )

Para **saber mais**, consulte [*Configurar o calendário fiscal gregoriano.*](https://www.ibm.com/docs/en/apptio-platform/fcs/saas?topic=calendar-configure-gregorian "(Abre em uma nova guia ou janela)")

**4-4-5 (4-5-4 / 5-4-4) Variante do calendário**

Os calendários com variação 4-4-5 são normalmente utilizados por organizações de varejo e manufatura que exigem relatórios semanais consistentes.

**Principais características:**

- O ano fiscal é dividido em semanas, em vez de meses
- Os períodos sempre começam e terminam no mesmo dia da semana
- Organizado em quartos com:
  - Dois períodos de 4 semanas e um período de 5 semanas
- Estruturas suportadas:
  - **4-4-5**
  - **4-5-4**
  - **5-4-4**

Para **saber mais**, consulte [*Configurar o calendário fiscal variante 4-4-5.*](https://www.ibm.com/docs/en/apptio-platform/fcs/saas?topic=calendar-configure-445-variant "(Abre em uma nova guia ou janela)")

**Calendário de 13 períodos**

O calendário de 13 períodos divide o ano fiscal em **13 períodos iguais**, normalmente com quatro semanas cada.

**Por que os clientes utilizam este calendário:**

- Garante que cada período tenha o mesmo número de dias
- Simplifica as comparações operacionais e a análise de tendências
- Comum em organizações com grande volume de produção, logística e operações

Para **saber mais**, consulte [*Configurar calendário fiscal de 13 períodos.*](https://www.ibm.com/docs/en/apptio-platform/fcs/saas?topic=calendar-configure-13-period "(Abre em uma nova guia ou janela)")

## Configurar calendário fiscal

Você pode selecionar um calendário fiscal quando seu ambiente Apptio de planejamento for criado. O tipo de calendário selecionado se aplica a todos os planos criados no ambiente e não pode ser alterado pelos usuários diretamente na interface do usuário.

Para acessar a configuração do seu calendário fiscal, vá para **Configurações (ícone de engrenagem) →** **Configuração do calendário fiscal.**

**Alteração do calendário fiscal**

A alteração do calendário fiscal requer assistência do Apptio Suporte.

**Considerações importantes:**

- Os planos históricos continuam a utilizar o calendário fiscal original
- **Os novos planos** criados após a alteração utilizam o **novo calendário.**
- **Não** é possível comparar planos em diferentes estruturas de calendário

Se você precisar comparar novos planos com planos históricos, será necessário **recriar os planos históricos** usando a nova configuração do calendário fiscal

Para solicitar uma alteração - Envie uma **solicitação de suporte** através IBM do Suporte ou entre em contato com seu Gerente de Sucesso do Cliente
