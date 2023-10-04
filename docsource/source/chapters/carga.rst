.. Coloque dois pontos antes de uma frase para comentá-la

.. _carga:

Carga de dados
==============

Após a extração e a transformação, a carga de dados consiste em carregá-los propriamente para o Power BI. Após a carga,
entende-se que os dados estão prontos para serem consumidos da maneira como se apresentam.

Ao carregar os dados, estes passam a fazer parte de um *dataset*. Este *dataset* pode ser consumido por diversos
*relatórios*, ou então apenas por um, a depender dos casos de uso.

.. note::
    A carga que nos referimos aqui é do modelo ETL (*extraction - transformation - load*), e não necessariamente a
    carga feita no Power BI.

Pode ser que, após fazer a carga, você perceba que faltou realizar algum pré-processamento (transformação) nos dados.
É possível então realizar esta etapa utilizando o editor Power Query, interno ao Power BI. As modificações feitas serão
imediatamente aplicadas e os dados serão recarregados automaticamente.

Na documentação
`Fontes de dados no Power BI Desktop <https://learn.microsoft.com/pt-br/power-bi/connect-data/desktop-data-sources>`_
são listadas as diversas fontes disponíveis para carregar dados para o Power BI.