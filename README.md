# Power BI

Este repositório consiste em um conjunto de boas práticas para trabalhar no Power Bi. A ideia é criar um **guia** para 
nortear o desenvolvimento de relatórios e padronizar o *layout* das páginas.

## Documentação

Estas instruções aplicam exclusivamente para a geração da documentação que está em 
https://coplin-ufsm.github.io/powerbi. Se você não deseja gerar as páginas HTML novamente, desconsidere esta seção.

### Instalação (apenas uma vez)

1. Instale o [Python Anaconda](https://www.anaconda.com/download) no seu computador e adicione-o ao PATH do sistema
   * Para verificar se o Python está no PATH, abra a linha de comando e digite `python --version`. Se a mensagem for um
     número, então o Python foi instalado corretamente
2. Com a linha de comando aberta, execute os seguintes comandos:
   
   ```bash
   conda create --name powerbi pip --yes
   conda activate powerbi
   conda install --file requirements.txt --yes
   ```

### Geração (várias vezes)

A cada vez que você modificar os arquivos da documentação, será necessário gerar os arquivos HTML novamente. Siga o 
passo a passo a seguir:

1. Com a linha de comando aberta, execute o seguinte comando:

   ```bash
   conda activate powerbi
   cd docsource
   ```

2. Para gerar novamente as páginas HTML, digite o comando 

   ```bash
   make github
   ```

   Isto criará páginas HTML na pasta [docs](docs). Você pode ver o index da documentação no arquivo 
   [docs/index.html](docs/index.html).

3. As regras dos arquivos RestructText estão disponíveis 
   [aqui](https://github.com/ralsina/rst-cheatsheet/blob/master/rst-cheatsheet.rst).