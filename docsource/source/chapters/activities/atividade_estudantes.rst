.. Coloque dois pontos antes de uma frase para comentá-la

.. _atividade-estudantes:

Estudantes
==========

Faça download da tabela `iestudantes.csv
<https://coplin-ufsm.github.io/powerbi/data/Pessoal/Base%20de%20Dados/iestudantes.csv>`_ no seu computador, e abrindo-a
No Power BI, faça um relatório com os seguintes itens:

.. |uncheck| raw:: html

    <input type="checkbox">

#. Número de alunos...

   * |uncheck| total, como um número
   * |uncheck| Por gênero, como um gráfico de rosca
   * |uncheck| Por etnia, como um gráfico de barras horizontais
   * |uncheck| Por modalidade (EAD ou Presencial), como um gráfico de barras verticais
   * |uncheck| Por nível de ensino, como um gráfico de barras horizontais
   * |uncheck| Por turno, como um gráfico de barras horizontais
   * |uncheck| Por grau acadêmico, como um gráfico de barras horizontais
   * |uncheck| Por centro, como um gráfico de barras horizontais
   * |uncheck| Um filtro para selecionar estudantes nacionais ou estrangeiros

.. |details| raw:: html

    <details>
    <summary><b>Medida</b></summary>

        <code>
            Alunos = SUM(iestudantes[NUM_ALUNOS])
        </code>

    </details>


Solução
-------

#. Carregar dados
#. Colocar primeira linha como cabeçalho
#. Converter colunas numéricas para números inteiros
#. Criar medida que soma o número de alunos |details|
#. Criar gráficos
#. Criar seletor
