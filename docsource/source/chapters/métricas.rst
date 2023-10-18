.. Coloque dois pontos antes de uma frase para comentá-la

.. _métricas:

Métricas
========

Quando manipulamos tabelas no Power BI, pode ser que queremos inserir uma informação que não está contida nos dados,
como por exemplo um cálculo feito sobre duas outras colunas. Talvez este cálculo não possa ser inserido na etapa de
transformação, pois os dados são alimentados de maneira dinâmica no Power BI (por exemplo, a partir de um banco de
dados). Para estas situações, existem as **métricas**.

Uma métrica é parecida com uma função do Microsoft Excel, e é diferente de inserir uma **coluna** na tabela. Para
calcular os valores que serão inseridos nas células da coluna de métrica, utilizamos a linguagem de programação
**DAX** (*Data Analysis Expressions*).

Apesar de não ser estritamente necessário ter conhecimentos prévios de programação para usar o Power BI, se você já
tiver uma formação em áreas de Tecnologia da Informação, sua prática no Power BI será facilitada. Do contrário, você
aprenderá os conceitos da linguagem DAX enquanto cria relatórios no Power BI.

.. list-table:: Diferença entre colunas e métricas de uma tabela no Power BI
   :widths: 30 30 30
   :header-rows: 1

   * - Característica
     - Coluna
     - Métrica
   * - Uso de memória
     - 🔺
     - 🔽
   * - Uso de processamento
     - 🔽
     - 🔺

.. note::

    Você pode praticar seus conhecimentos na linguagem DAX no site `dax.do <https://dax.do/>`_.

Funções comuns do DAX
---------------------

Existe um conjunto de funções do DAX que são mais frequentemente usadas do que outras. Consulte a
`documentação oficial <https://learn.microsoft.com/pt-br/dax/dax-function-reference>`_ da Microsoft para uma lista
completa de todas as funções.

`FILTER <https://learn.microsoft.com/pt-br/dax/filter-function-dax>`_
*********************************************************************

Utilizada para retornar um subconjunto de uma tabela ou expressão.

.. code-block:: dax

    FILTER (<tabela>, <filtro>)

`ALL <https://learn.microsoft.com/pt-br/dax/all-function-dax>`_
***************************************************************

Utilizada para retornar todas as linhas de uma tabela ou valores em uma coluna, ignorando qualquer filtro que tenha sido aplicado.

.. code-block:: dax

    ALL (<tabela> ou <coluna>)

Assim como a função FILTER, esta função não é utilizada por si só, sempre estando acompanhada de outra função.

`RELATED <https://learn.microsoft.com/pt-br/dax/related-function-dax>`_
***********************************************************************

Retorna um valor relacionado de outra tabela.

.. code-block:: dax

    Qtde Vendas SP = COUNTROWS(
        FILTER(
            ALL(Vendas);
            RELATED(Local[Cidade]) = "São Paulo"
        )
    )


`TOTALYTD <https://learn.microsoft.com/pt-br/dax/totalytd-function-dax>`_ / `TOTALQTD <https://learn.microsoft.com/pt-br/dax/totalqtd-function-dax>`_ / `TOTALMTD <https://learn.microsoft.com/pt-br/dax/totalmtd-function-dax>`_
*********************************************************************************************************************************************************************************************************************************

Com estas funções, é possível utilizar dados temporais para retornar dados, como coletar o dia, mês, trimestre, ano, etc
de uma coluna com data. Também é possível comparar períodos.

.. code-block:: dax

    Total Vendas Ano = TOTALYTD(
        SUM(Vendas[Valor]);
        Calendario[Datas]
    )


`CALCULATE <https://learn.microsoft.com/pt-br/dax/calculate-function-dax>`_
***************************************************************************

Avalia uma expressão em um contexto que pode ser mudado por filtros específicos.

.. code-block:: dax

    Vendas Todas Cidades = CALCULATE(
        SUM(Vendas[Valor]);
        ALL(Local[Cidade])
    )

O primeiro parâmetro ``SUM(Vendas[Valor])`` traz a coluna que terá seus valores agregados. O segundo parâmetro
``ALL(Local[Cidade])``, como utiliza a função ALL desconsidera qualquer filtro feito e ao mesmo tempo faz com que o
cálculo seja aplicado em relação às cidades.

Esta função possui algumas regras:

* Os parâmetros de filtros **não** podem se referenciar à medidas;
* As expressões **não** podem usar funções que procuram ou retornam tabelas inteiras.

Tipos de funções
----------------

As funções DAX podem ser agrupadas por tipos: o tipo de dado de entrada e o processamento realizado sobre estes dados.
Uma lista não-extensiva dos tipos de funções seria:

* `Funções de agregação <https://learn.microsoft.com/pt-br/dax/aggregation-functions-dax>`_:  calculam um valor (escalar) de uma contagem, soma, média, mínimo ou máximo para todas as linhas de uma coluna ou tabela.
* `Funções de data e hora <https://learn.microsoft.com/pt-br/dax/date-and-time-functions-dax>`_: essas funções do DAX são semelhantes às funções de data e hora do Microsoft Excel. No entanto, as funções DAX são baseadas nos tipos de dados datetime usados pelo Microsoft SQL Server.
* `Funções de filtro <https://learn.microsoft.com/pt-br/dax/filter-functions-dax>`_: retornam tipos de dados específicos, valores em tabelas relacionadas e dados filtrados por valores relacionados. Funcionam usando tabelas e relações entre elas. As funções de filtragem permitem que se manipule o contexto de dados para criar cálculos dinâmicos.
* `Funções financeiras <https://learn.microsoft.com/pt-br/dax/financial-functions-dax>`_: essas funções são usadas em fórmulas que fazem cálculos financeiros, como o valor líquido atual e a taxa de retorno, entre outros..
* `Funções de informações <https://learn.microsoft.com/pt-br/dax/information-functions-dax>`_: examinam uma tabela ou uma coluna fornecida como argumento para outra função e retornam se o valor corresponde ao tipo esperado. Por exemplo, a função ISERROR retornará TRUE se o valor referenciado contiver um erro.
* `Funções lógicas <https://learn.microsoft.com/pt-br/dax/logical-functions-dax>`_: ss funções lógicas agem sobre uma expressão para retornar informações sobre os valores ou conjuntos dela. Por exemplo, você pode usar a função IF para verificar o resultado de uma expressão e criar resultados condicionais.
* `Funções matemáticas e trigonométricas <https://learn.microsoft.com/pt-br/dax/math-and-trig-functions-dax>`_: as funções matemáticas do DAX são semelhantes às funções matemáticas e trigonométricas do Excel. No entanto, há algumas diferenças nos tipos de dados numéricos usados pelas funções DAX.
* `Funções pai e filho <https://learn.microsoft.com/pt-br/dax/parent-and-child-functions-dax>`_: ajudam os usuários a gerenciar os dados que são apresentados como uma hierarquia pai/filho nos modelos de dados. Mais informações sobre as funções pai/filho `aqui <https://learn.microsoft.com/pt-br/dax/understanding-functions-for-parent-child-hierarchies-in-dax>`_.
* `Funções de relação <https://learn.microsoft.com/pt-br/dax/relationship-functions-dax>`_: essas funções são para gerenciar e utilizar relações entre tabelas. Por exemplo, você pode definir uma relação específica a ser usada em um cálculo.
* `Funções estatísticas <https://learn.microsoft.com/pt-br/dax/statistical-functions-dax>`_: calculam valores relacionados a probabilidade e a distribuições estatísticas, como desvio padrão e número de permutações.
* `Funções de manipulação de tabela <https://learn.microsoft.com/pt-br/dax/table-manipulation-functions-dax>`_: essas funções retornam uma tabela ou manipulam tabelas existentes.
* `Funções de texto <https://learn.microsoft.com/pt-br/dax/text-functions-dax>`_: com essas funções, você pode retornar parte de uma cadeia de caracteres, pesquisar um texto em uma cadeia de caracteres ou concatenar valores de cadeia de caracteres. Funções adicionais destinam-se a controlar os formatos de datas, horas e números.
* `Funções de inteligência de dados temporais <https://learn.microsoft.com/pt-br/dax/time-intelligence-functions-dax>`_: essas funções permitem criar cálculos com dados de calendários e datas. Elas permitem manipular dados usando períodos de tempo como dias, meses, trimestres e anos, além de criar e comparar cálculos referentes a esses períodos. Intervalos de data e hora podem ser usados em combinação com funções de agregação ou cálculos para criar comparações significativas entre períodos de tempo.
* `Outras funções <https://learn.microsoft.com/pt-br/dax/other-functions-dax>`_: essas funções executam ações exclusivas que não se enquadram nas anteriores.

Bibliografia
------------

* `dax.do <https://dax.do/>`_
* `Documentação das funções DAX <https://learn.microsoft.com/pt-br/dax/dax-function-reference>`_