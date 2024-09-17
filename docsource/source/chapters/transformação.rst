.. Coloque dois pontos antes de uma frase para comentá-la

.. _transformação:

Transformação
=============

A **transformação** é a etapa em que os dados extraídos seu formato prévio são convertidos para um formato que facilita
o trabalho. Posto de outra forma, o objetivo desta etapa é **"limpá-los"** de maneira que a qualidade dos dados seja
melhorada.

É possível transformar os dados em duas etapas: antes do seu carregamento no Power BI, utilizando editores de planilhas
como o Microsoft Excel, Libreoffice Calc, ou uma linguagem de programação com Python; ou então no próprio Power BI,
através do editor Power Query.

Independente da ferramenta utilizada, a transformação de dados consiste em:

- Adicionar ou remover linhas e colunas;
- Substituir valores faltantes;
- Categorizar dados (e.g. de números para intervalo de valores, como por exemplo faixas etárias);
- Alterar o tipo dos dados (e.g. de texto para uma data, ou de texto para um número);
- Adicionar uma coluna que é o cálculo de outras colunas, utilizando funções;
- Remover dados duplicados;
- Identificar e remover valores fora de um intervalo, como oriundos de erros de digitação;
- Dividir uma planilha em outras menores;
- Dentre outras tarefas.

A documentação
`Visão geral de Consulta no Power BI Desktop <https://learn.microsoft.com/pt-br/power-bi/transform-model/desktop-query-overview>`_
e o tutorial `Formatar e combinar dados no Power BI Desktop <https://learn.microsoft.com/pt-br/power-bi/connect-data/desktop-shape-and-combine-data>`_
fornecem instruções passo-a-passo do processo de transformação dos dados diretamente no Editor Power Query.

.. É importante mencionar que aqui a fonte de dados original não é afetada.

.. note::
    Se você optar por transformar os dados no Power Query, as modificações feitas não serão refletidas nas fontes de
    dados. Em outras palavras, se você deletar uma coluna no Power Query, por exemplo, esta coluna ainda estará presente
    na planilha do Excel da qual os dados foram extraídos.

Tarefa
------

Considerando a tabela `iestudantes.csv
<https://coplin-ufsm.github.io/powerbi/data/pessoal/Base%20de%20Dados/iestudantes.csv>`_, e utilizando o Power Query,
transforme a coluna **Nacionalidade** de gentílico (e.g. brasileiro, peruano, etc) para o nome do país (e.g. Brasil,
Peru, etc).


Bibliografia
------------

A Microsoft apresenta um roteiro de aprendizagem para transformação de dados em seus
`Roteiros de Aprendizagem <https://learn.microsoft.com/pt-br/training/paths/prepare-data-power-bi/>`_.