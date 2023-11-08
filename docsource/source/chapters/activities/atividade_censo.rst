.. Coloque dois pontos antes de uma frase para comentá-la

.. _atividade-censo:

Censo
=====

O seguinte exercício faz uso de um conjunto de dados extraído do site UCI Machine Learning Repository, chamado
`adult <https://archive.ics.uci.edu/dataset/2/adult>`_. O objetivo principal deste conjunto de dados é predizer, com
base em informações como sexo, etnia, profissão, nacionalidade, etc, qual o salário bruto anual das pessoas. Cada linha
é um indivíduo, e a última coluna é o atributo "classe" (o atributo que deseja-se adivinhar).

Faça download da tabela `adult <https://coplin-ufsm.github.io/powerbi/data/censo/Base%20de%20Dados/adult.csv>`_, que já
passou por um pré-processamento. Após, abra-a no Power BI e faça as seguintes tarefas:

.. |uncheck| raw:: html

    <input type="checkbox">

* |uncheck| Substituir valores faltantes usando um média (para colunas numéricas) ou moda (para colunas categóricas)
* |uncheck| Remover colunas que não serão utilizadas na visualização (e.g. fnlwgt)
* |uncheck| Substituir nomes de valores por descrição mais legível (e.g. State-gov)