---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Adicionar dados à tabela Biblioteca de serviços"
breadcrumb: []
source_path: "boit/service-library-table.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Adicionar dados à tabela Biblioteca de serviços

A tabela Biblioteca de serviços inclui informações sobre os serviços oferecidos por sua organização. Você pode adicionar dados à tabela fazendo upload dos dados de outra fonte, como uma planilha do Excel. Carregue os dados em uma tabela separada e, em seguida, anexe a tabela à tabela da Biblioteca de serviços. Consulte [Carregar um arquivo de dados](../studio/data_studio/upload-data-file.html "Aplica-se a: TBM Studio 12.0 e posterior. O TBM Studio aceita dados de arquivos simples nos formatos separados por vírgula, tabulação, pipe, til, dois pontos e ponto e vírgula. Antes de fazer upload de dados, você deve criar uma tabela na qual os dados serão carregados, se ela ainda não existir.") para obter mais informações.

Se os dados originais da biblioteca de serviços foram anexados à tabela All Business Services, anexe o mesmo arquivo de dados brutos à tabela Service Library. Não anexe o All Business Services diretamente à Biblioteca de serviços; em vez disso, anexe apenas o arquivo bruto. Consulte [Anexar dados](../studio/data_studio/append-data.html "Aplica-se a: TBM Studio 12.0 e posterior") para obter mais informações.

Dados necessários da biblioteca de serviços

- **Preço** - O preço interno definido para o serviço comercial. Usado em Billing Standard ao usar cálculos de Preço x Quantidade.
- **Metodologia de precificação** - A abordagem usada para calcular os valores de Billing Standard showback ou chargeback.
- **Published (Publicado** ) - Indica se um item de linha deve ser incluído nas faturas de estorno. Valores: Sim, Não.
- **Categoria de serviço** - Representa o segundo nível na taxonomia (hierarquia) de serviços. Valores recomendados: Desenvolvimento, Operações, Segurança e Conformidade, Estratégia e Planejamento
- **ID do serviço** - Um identificador exclusivo para o serviço.
- **Nome do serviço** - O nome do serviço. Isso representa o terceiro nível na taxonomia (hierarquia) de serviços.
- **Oferta de serviço** - A opção de serviço representada por esse item. Isso representa o quarto nível na taxonomia (hierarquia) de serviços. As opções de serviço oferecem uma escolha para os consumidores da unidade de negócios em um serviço. Por exemplo, as ofertas de laptops podem incluir: Laptop ultraportátil, Laptop para estação de trabalho e Laptop padrão. As ofertas de e-mail podem incluir: Ouro, Prata e Bronze.
- **Tipo de serviço** - Representa o primeiro nível na taxonomia (hierarquia) de serviços. Valores recomendados: Serviços de aplicativos de negócios, Serviços de entrega, Serviços de infraestrutura, Serviços de usuário final e Serviços de plataforma.
- **Unidade de medida** - A unidade usada para rastrear e distribuir o custo de um serviço comercial para uma ou mais unidades de negócios. As unidades de negócios consomem unidades de um serviço. Por exemplo: caixas de e-mail, usuários de aplicativos, armazenamento alocado, etc.

Serviço recomendado Dados da biblioteca

- **Descrição** - Uma descrição amigável do serviço para o consumidor. Se o campo Long Description for preenchido, essa descrição será usada no lugar dessa descrição.
- **Estágio do ciclo de vida** - O status atual de um serviço. Os valores típicos são: Em serviço, Fora de serviço, Pôr do sol, Integração
- **Descrição longa** - Uma descrição mais detalhada do serviço. Se esse campo for preenchido, o texto será usado em vez do texto no campo Descrição.

Dados opcionais da biblioteca de serviços

- **Gerente de serviços** - A principal pessoa de TI responsável pelo provisionamento e operação do serviço comercial.
- **Proprietário do serviço** - A pessoa de TI responsável pela entrega geral do serviço comercial. As responsabilidades incluem a estratégia, a definição, a seleção e o desempenho financeiro do serviço.

**Hierarquia de serviços recomendada**

A hierarquia de serviços recomendada pelo TBM Council pode ser acessada aqui: [Taxonomia da TBM v2.0](../atum/tbm-taxonomy-v2-definition/intro-taxonomy.html)
