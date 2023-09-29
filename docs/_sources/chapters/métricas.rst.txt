.. Coloque dois pontos antes de uma frase para comentá-la

.. _métricas:

Métricas
========

As funções **DAX** (*Data Analysis Expressions*) permitem criar fórmulas e expressões no Power BI. Elas incluem funções, operadores e valores para realizar cálculos avançados e consultas em dados nas tabelas e colunas relacionadas nos modelos de dados tabulares.

**Cinco funções DAX muito úteis no Power BI.**

**1 - Função** `FILTER <https://learn.microsoft.com/pt-br/dax/filter-function-dax>`_

Esta função é utilizada para retornar um subconjunto de uma tabela ou expressão.

Esta fórmula tem a seguinte estrutura: FILTER (<tabela>, <filtro>)


**2 - Função** `ALL <https://learn.microsoft.com/pt-br/dax/all-function-dax>`_

Esta função é utilizada para retornar todas as linhas de uma tabela ou valores em uma coluna, ignorando qualquer filtro que tenha sido aplicado.

Esta fórmula tem a seguinte estrutura: ALL (<tabela> ou <coluna>)

Assim como a função FILTER, esta função não pode ser usada sozinha, sempre estará com outra função em conjunto. 

Essa função pode ser utilizada tanto numa tabela quanto numa coluna, limpando qualquer filtro colocado nas visualizações.


**3 - Função** `RELATED <https://learn.microsoft.com/pt-br/dax/related-function-dax>`_

A função RELATED retorna um valor relacionado de outra tabela.

Esta fórmula tem a seguinte estrutura: RELATED (<coluna>)

As funções DAX podem ser usadas agregadas com outras funções.

**Exemplo:**

Qtde Vendas SP = COUNTROWS(FILTER(ALL(Vendas);RELATED(Local[Cidade])=”São Paulo”))


**4 - Funções** `TOTALYTD <https://learn.microsoft.com/pt-br/dax/totalytd-function-dax>`_ / `TOTALQTD <https://learn.microsoft.com/pt-br/dax/totalqtd-function-dax>`_ / `TOTALMTD <https://learn.microsoft.com/pt-br/dax/totalmtd-function-dax>`_

Estas funções são de inteligência de tempo e são uma das grandes vantagens da linguagem DAX. Através delas se consegue mais inteligência na análise de dados que envolvem o tempo como variável.

Com estas funções é possível manipular dados de período de tempo, tais como, dias, meses, trimestres e anos. Com elas se cria comparativos entre os períodos. 

Esta fórmula tem a seguinte estrutura: TOTALYTD (<expressão>;<datas>;<filtro>;<data fim ano>)

**Exemplo:**

Total Vendas Ano = TOTALYTD(SUM(Vendas[Valor]);Calendario[Datas])


**5 - Função** `CALCULATE <https://learn.microsoft.com/pt-br/dax/calculate-function-dax>`_

Esta função avalia uma expressão em um contexto que pode ser mudado por filtros específicos. 

Esta provavelmente será uma das que você mais utilizará!

A Função CALCULATE tem a seguinte estrutura: CALCULATE(<expressão>;<filtro1>;<filtro2>;…)

**Exemplo:**

Vendas Todas Cidades = CALCULATE(SUM(Vendas[Valor]);ALL(Local[Cidade]))

O primeiro parâmetro “SUM(Vendas[Valor])” traz a coluna que terá seus valores agregados. O segundo parâmetro “ALL(Local[Cidade])”, como utiliza a função ALL desconsidera qualquer filtro feito e ao mesmo tempo faz com que o cálculo seja aplicado em relação às cidades. 

A função CALCULATE é uma das mais úteis e poderosas funções DAX, é como se fosse um “SE” superpoderoso que junta vários SES em uma única expressão.

Esta função tem algumas regras, veja:

**a)** Os parâmetros de filtros **não** podem se referenciar à medidas

**b)** As expressões **não** podem usar funções que procuram ou retornam tabelas inteiras


Nas documentações listadas a seguir você encontra informações detalhadas sobre sintaxe, parâmetros, valores retornados e exemplos para cada uma das mais de 250 funções usadas em fórmulas DAX, que incluem:

`Funções de agregação <https://learn.microsoft.com/pt-br/dax/aggregation-functions-dax>`_:  calculam um valor (escalar) de uma contagem, soma, média, mínimo ou máximo para todas as linhas de uma coluna ou tabela.

`Funções de data e hora <https://learn.microsoft.com/pt-br/dax/date-and-time-functions-dax>`_: essas funções do DAX são semelhantes às funções de data e hora do Microsoft Excel. No entanto, as funções DAX são baseadas nos tipos de dados datetime usados pelo Microsoft SQL Server.

`Funções de filtro <https://learn.microsoft.com/pt-br/dax/filter-functions-dax>`_: retornam tipos de dados específicos, valores em tabelas relacionadas e dados filtrados por valores relacionados. Funcionam usando tabelas e relações entre elas. As funções de filtragem permitem que se manipule o contexto de dados para criar cálculos dinâmicos.

`Funções financeiras <https://learn.microsoft.com/pt-br/dax/financial-functions-dax>`_: essas funções são usadas em fórmulas que fazem cálculos financeiros, como o valor líquido atual e a taxa de retorno, entre outros..

`Funções de informações <https://learn.microsoft.com/pt-br/dax/information-functions-dax>`_: examinam uma tabela ou uma coluna fornecida como argumento para outra função e retornam se o valor corresponde ao tipo esperado. Por exemplo, a função ISERROR retornará TRUE se o valor referenciado contiver um erro.

`Funções lógicas <https://learn.microsoft.com/pt-br/dax/logical-functions-dax>`_: ss funções lógicas agem sobre uma expressão para retornar informações sobre os valores ou conjuntos dela. Por exemplo, você pode usar a função IF para verificar o resultado de uma expressão e criar resultados condicionais.

`Funções matemáticas e trigonométricas <https://learn.microsoft.com/pt-br/dax/math-and-trig-functions-dax>`_: as funções matemáticas do DAX são semelhantes às funções matemáticas e trigonométricas do Excel. No entanto, há algumas diferenças nos tipos de dados numéricos usados pelas funções DAX.

`Funções pai e filho <https://learn.microsoft.com/pt-br/dax/parent-and-child-functions-dax>`_: ajudam os usuários a gerenciar os dados que são apresentados como uma hierarquia pai/filho nos modelos de dados. Mais informações sobre as funções pai/filho `aqui <https://learn.microsoft.com/pt-br/dax/understanding-functions-for-parent-child-hierarchies-in-dax>`_.

`Funções de relação <https://learn.microsoft.com/pt-br/dax/relationship-functions-dax>`_: essas funções são para gerenciar e utilizar relações entre tabelas. Por exemplo, você pode definir uma relação específica a ser usada em um cálculo.

`Funções estatísticas <https://learn.microsoft.com/pt-br/dax/statistical-functions-dax>`_: calculam valores relacionados a probabilidade e a distribuições estatísticas, como desvio padrão e número de permutações.

`Funções de manipulação de tabela <https://learn.microsoft.com/pt-br/dax/table-manipulation-functions-dax>`_: essas funções retornam uma tabela ou manipulam tabelas existentes.

`Funções de texto <https://learn.microsoft.com/pt-br/dax/text-functions-dax>`_: com essas funções, você pode retornar parte de uma cadeia de caracteres, pesquisar um texto em uma cadeia de caracteres ou concatenar valores de cadeia de caracteres. Funções adicionais destinam-se a controlar os formatos de datas, horas e números.

`Funções de inteligência de dados temporais <https://learn.microsoft.com/pt-br/dax/time-intelligence-functions-dax>`_: essas funções permitem criar cálculos com dados de calendários e datas. Elas permitem manipular dados usando períodos de tempo como dias, meses, trimestres e anos, além de criar e comparar cálculos referentes a esses períodos. Intervalos de data e hora podem ser usados em combinação com funções de agregação ou cálculos para criar comparações significativas entre períodos de tempo.

`Outras funções <https://learn.microsoft.com/pt-br/dax/other-functions-dax>`_: essas funções executam ações exclusivas que não se enquadram nas anteriores.


