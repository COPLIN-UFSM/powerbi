# Power BI

Este repositório consiste em um conjunto de boas práticas para trabalhar no Power Bi. A ideia é criar um **guia** para 
nortear o desenvolvimento de relatórios e padronizar o *layout* das páginas.

## Documentação

Estas instruções aplicam exclusivamente para a geração da documentação que está em 
https://coplin-ufsm.github.io/powerbi. Se você não deseja gerar as páginas HTML novamente, desconsidere esta seção.

### Instalação

Para gerar a documentação, siga o seguinte passo a passo:

1. Abra a linha de comando do seu computador
2. Com o [Python Anaconda](https://www.anaconda.com/download) instalado e adicionado ao PATH do sistema, execute os 
   seguintes comandos na linha de comando:
   
   ```bash
   conda create --name powerbi pip --yes
   conda activate powerbi
   conda install --file requirements.txt --yes
   ```
   
3. Entre na pasta `docsource` e digite o seguinte comando:

   ```bash
   make github
   ```

   Isto criará páginas HTML na pasta [docs](docs). Você pode ver o index da documentação no arquivo 
   [docs/index.html](docs/index.html).

4. As regras dos arquivos RestructText estão disponíveis 
   [aqui](https://github.com/ralsina/rst-cheatsheet/blob/master/rst-cheatsheet.rst).