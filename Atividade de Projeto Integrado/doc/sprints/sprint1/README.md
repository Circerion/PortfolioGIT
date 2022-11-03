# Sprint 1 - MVP
<p align="center">
      <img src="/doc/frontend/logo-BuzzTech.png" alt="logo da Buzz Tech" width="200">
      <h2 align="center"> Buzz Tech</h2>





<hr>
<br>
<p align="center">
  <a href ="#backlog"> Backlog da Sprint </a>  | 
  <a href ="#tarefas"> Tarefas </a>  |
  <a href ="#evolução"> Evolução do Backlog </a>  |
  <a href ="#hitoria"> Histórias de Usuários </a>  |
  <a href ="#apresentação"> Apresentação </a>
</p>



</p>



<br>

<h4 align="center">
 <a href="https://docs.python.org/3/"><img src = "https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54"/></a>
 <a href="https://www.w3schools.com/tags/tag_doctype.asp"><img src = "https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white"/></a>
 <a href="https://www.w3schools.com/css/"><img src = "https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white"/></a>
 <a href="https://getbootstrap.com/docs/4.1/getting-started/introduction/"><img src = "https://img.shields.io/badge/bootstrap-%23563D7C.svg?style=for-the-badge&logo=bootstrap&logoColor=white"/></a>
 <a href="https://flask.palletsprojects.com/en/2.2.x/"><img src = "https://img.shields.io/badge/flask-%23000.svg?style=for-the-badge&logo=flask&logoColor=white"/></a>
 <a href="https://docs.github.com/pt"><img src = "https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white"/></a>
</h4>


<br>

> Status da Sprint: Concluída :heavy_check_mark:

<br>

As escolhas de tarefa dessa primeira Sprint reflete a definição do MVP, ou seja, versão sintética, porém funcional, de um sistema web para Controle de Ordens de Serviços. Nele o usuário poderá abrir um chamado para alertar um equipamento com mau funcionamento, no qual conterá as seguintes informações:

- Identificação do Laboratório
- Identificação do Computador
- Problema de Hardware ou Software
- Descrição do Problema

Este chamado será automaticamente gerado e organizado em uma tabela na qual o técnico terá acesso às informações fornecidas pelo usuário, bem como um número de identificação da Ordem de Serviço (OS) e dois botões:

- Um para apagar a OS;
- Outro para atualizar a OS.



<br>

##  :date: Backlog da Sprint<a id="backlog"></a>



|                            Tarefa                            |                          Descrição                           |               Histórias de Usuários                | Prioridade | Sprint | Estimativa de Esforço |       Status       |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :------------------------------------------------: | :--------: | :----: | :-------------------: | :----------------: |
| <a href='#identificação'>Identificação dos computadores</a>  | Levantamento de quantos computadores existem nos laboratórios da Fatec e como eles estão distribuídos por laboratório | <a href='#us01'>US01</a>, <a href='#us02'>US02</a> |   Média    |   1    |          4h           | :white_check_mark: |
| <a href='#abertura'>Página de abertura de chamados em HTML</a> | Prototipagem e  criação da página de abertura de chamados funcional e testável para possíveis problemas em HTML. Tópicos da página: Número do laboratório;  Número do computador; Hardware ou Software. |              <a href='#us03'>US03</a>              |    Alta    |   1    |          16h          | :white_check_mark: |
| <a href='#visualização'>Página de visualização dos chamados em HTML</a> | Prototipagem e criação da página de visualização de chamados em HTML. Tópicos da página: Chamados abertos; Data dos chamados; Botão de conclusão dos chamados |              <a href='#us04'>US04</a>              |    Alta    |   1    |          20h          | :white_check_mark: |
|     <a href='#conexão'>Conexão  das páginas no Flask</a>     | Conectar a página de abertura de chamado e de visualização de chamados utilizando o framework Flask. |              <a href='#us05'>US05</a>              |    Alta    |   1    |          10h          | :white_check_mark: |
| <a href='wireframe'>Criação, aprovação e entrega do Wireframe</a> | Criação do protótipo das páginas de abertura de chamado e visualização de chamado com base na identidade visual do cliente. |              <a href='#us06'>US06</a>              |   Média    |   1    |          3h           | :white_check_mark: |



## :checkered_flag: Tarefas <a id="tarefas"></a>

1. ### Identificação dos computadores<a id='identificação'></a>

   Para fazer o levantamento de quantos computadores existem nos laboratórios da Fatec e como eles estão distribuídos, o time buscou informações junto ao responsável técnico que atende os chamados sobre problemas com os computadores. Segundo informado, a Fatec São José dos Campos conta com um total de **14 laboratório**, sendo que estes estão divididos em **4 layouts distintos**, como apresentado nas imagens a seguir:

   

   | ![Laboratório com 32 computadores](img/idLabs/32comp.png)    | ![Laboratório com 24 computadores](img/idLabs/24comp.png)    |
   | ------------------------------------------------------------ | ------------------------------------------------------------ |
   | ![Laboratório médio com 18 computadores](img/idLabs/18comp_medio.png) | ![Laboratório menor com 18 computadores](img/idLabs/18comp_menores.png) |

   | Laboratório | Quantidade | Somatório de Computadores |
   | ----------- | ---------- | ------------------------- |
   | Grandes     | 4          | 104                       |
   | Méidios     | 8          | 144                       |
   | Pequenos    | 2          | 36                        |

   | Total de computadores |
   | :-------------------- |
   | 284                   |

   

   | Quantidades de Laboratórios.                                 |
   | ------------------------------------------------------------ |
   | 14 laboratórios no total                                     |
   | 4 laboratórios *maiores* nas salas 402 (32 Comp + 1 professor) e 401, 301, 302 (24 comp + 1  professor). |
   | 8 laboratórios *médios* nas salas 403, 405, 406, 407, 408, 409, 411 e 412 (18 computadores + 1  professor) . |
   | 2 laboratórios *menores* nas salas 404 e 303 (18 computadores + 1 professor), que utilizam a posição horizontal de fileiras. |

   | Identificação de controle das máquinas                       |
   | ------------------------------------------------------------ |
   | Númeração  Sequencial. As portas são os pontos de partida, e cada sala conta com 2 bancadas por  fileria. |
   | Controle  somente pelo número de sala do laboratório e da localização da bancada. Exemplo: Laboratório 401, máquina 01 ficaria 401-01. |
   | Concetração  de máquinas semelhantes na mesma sala, porém não há uma padronização. |
   | Não há  movimentação de máquinas entre as salas, somente quando um computador quebra,  assim um novo é colocado no lugar. |

   | Controle  hardware                                           |
   | ------------------------------------------------------------ |
   | A nível de componentes internos, não há um pradrão estabelecido por laboratório, pois as máquinas novas  substituem as quebradas. |
   | O mesmo  se dá quanto aos periféricos. Há dificuldade de compra de elemento para  realizar a manutenção devido a burocracias de licitação. |

   | Dicas fornecidas pelo técnico                                |
   | ------------------------------------------------------------ |
   | Fornecer o status das máquinas. Exemplo: Demonstrar para o usuário no layout quais máquinas estão em manutenção. |
   | Controlar  máquinas apenas por identificação das salas e posição das bancadas, como anteriormente descrito. |
   | Deixar o controle de ID o mais simples possive, pois há pouca mão de obra  pra atualizar e abastecer o sistema. |

   <br>

2. ### Página de abertura de chamados em HTML<a id='abertura'></a>

   Prototipagem e  criação da página de abertura de chamados em HTML. Como parte do MVP, esta tarefa terá como objetivo entregar uma página funcional e testável para possíveis problemas. Sendo a págna que em que os usuários identificararão o problema das máquinas, outro objetivo é criar um sistema simples para os usuários, mas que ao mesmo tempo tenha todas as informações necessárias para que o técnico identifique tanto o problema, quanto a máquina em questão. Os campos de preenchimento do formulário desta página serão:

   - Número do laboratório;  
   - Número do computador; 
   - Se é problema de Hardware ou Software;
   - Descrição do problema.

   Para visualizar a página HTML de *abertura de chamados*, acesse o <a href=''>link :link:</a>.

   <br>

3. ### Página de visualização dos chamados em HTML<a id='visualização'></a>

   Prototipagem e criação da página de visualização de chamados em HTML. Como parte do MVP, esta tarefa terá como objetivo entregar uma página funcional e testável para possíveis problemas. Os usuários que fazer abertura de chamado não terão acesso à essa pagina. Por motivos gerenciais, apenas os técnicos terão acesso o link. Nela, além dos itens preenchidos pelos usuários na página de <a href='abertura'>abertura de chamados</a>, a tabela também contará com os seguintes itens para controle das OS:

   - Data dos chamados;
   - ID dos chamados;
   - Botão de apagar o chamado;
   - Botão para atualizar o chamado.

   Para visualizar a página HTML de *visualização de chamados*, acesse o <a href=''>link :link:</a>.

   <br>

4. ### Conexão  das páginas no Flask <a id='conexão'></a>

   Como tarefa fundamental para atingir MVP, esta tarefa propõe-se a conectar as páginsa de abertura de chamado e de visualização de chamados utilizando o framework Flask. Feita essa conexão, os chamados abertos pelos usuários serão automaticamente enviados e preenchidos na tabela te visualizão, para que o técnico possa, assim, analisar os problemas e adotar as devidas mediadas para resolvê-lo. Neste sentido, a partir desta tarefa já é possível que o cliente teste o sistema para avaliar e identificar pontos fortes e possíveis mudanças. Em consonância com a metodologia ágil do Scrum, colocar o produto em teste logo no início aumenta as chances de, ao final do tempo de desenvolvimento, a entrega atenda as necessidades e expectativas do cliente.

   

   Nos testes que fizemos da aplicação, o resultado foi o seguinte:

   

   ![Teste do MVP](img/MVP/MVP.gif)

   

   ***Como executar a aplicação:***

   

   1. Execute o Powershell ou Terminal do Windows como <u>ADMINISTRADOR</u> 

   2. Crie uma pasta para você trabalhar sua aplicação

   ```
   mkdir flask
   ```

   3. Acesse a  pasta 

   ```
   cd flask/
   ```

   4. Execute o seguinte comando para verificar se você possui o Python instalado no seu computador. Caso não possua, antes de seguir para o próximo passo, baixe o instalador no site oficial e instale na sua máquina.

   ```
   python --version
   ```

   5. Depois, crie um ambiente virtual para executar sua aplicação

   ```
   py -3 -m venv venv
   ```

   6. Agora, mude a politica de execução do seu windows para conseguir ativar o ambiente virtual

   ```
   Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Scope LocalMachine
   ```

   7. Ative o ambiente virtual com o seguinte comando

   ```
   venv\Scripts\activate
   ```

   8. Coloque os arquivos da API nesse diretorio que você criou e executar o seguinte comando para instalar as bibliotecas

   ```
   pip install -r .\requirements.txt
   ```

   9. Por fim, é so executar a aplicação executando

   ```
   python app.py
   ```

   

   A seguir estão os [***requirements***](src/requirements.txt) para rodar a aplicação:

   

   ```
   click==8.1.3
   Flask==2.2.2
   gunicorn==20.1.0
   importlib-metadata==4.12.0
   itsdangerous==2.1.2
   Jinja2==3.1.2
   MarkupSafe==2.1.1
   tinydb==4.7.0
   Werkzeug==2.2.2
   zipp==3.8.1
   ```

   <br>

5. ### Criação, aprovação e entrega do Wireframe<a id='wireframe'></a>

   Para termos mais clareza de como deve ficar a identidade visual do produto, a criação e aprovação do Wireframe é parte essencial desta primeira Sprint. A partir dele, é possível alinhar as expectativas com o cliente quanto à criação do frontend da página ficará. Além disso, o Wireframe dará a direção para que os desenvolvedores construam páginas que tanto atendam à identidade do cliente, bem como para entender como criar um sistema web que seja intuitivo e atgradável para os usuários e técnicos que o utilizarão.  Foi desenvolvido o Wirefram das seguintes páginas:

   

   |                 Home                  |                     Abertura de Chamado                      |                   Visualização de Chamado                    |
   | :-----------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
   | ![Home](img/wireframe/PáginaHome.png) | ![Abertura de Chamado](img/wireframe/AberturaDeChamados.png) | ![Visualização de Chamado](img/wireframe/VisualizaçãoDeChamados.png) |

   Para visualizar o *Wireframe* em PDF, acesse o [link :link:](img/wireframe/wireframe.pdf).

<br>

## :hatching_chick: Evolução do Backolog<a id='evolução'></a>

Como a metodologia ágil Scrum tem como princípios a adaptabilidade e o processo iteraitvo, mudanças ocorrem para que o produto chegue ao final da Sprint com o maior valor possível. Para isto, foram necessárias alterações de tarefas que geraram 4 atualizações de versão do Backlog do Produto:

|          **Backlog 1.0** <br>30% ███▒▒▒▒▒▒▒           |
| :---------------------------------------------------: |
|                 Abertura de chamados                  |
|                       Hardware                        |
|                       Software                        |
|                         Rede                          |
|                Layout dos camputadores                |
|                       Legendas                        |
| Possibilidades de mudar características do computador |

|                Backlog 2.0<br>50% █████▒▒▒▒▒                 |
| :----------------------------------------------------------: |
|                Identificação dos computadores                |
|        Início da página de abertura de chamados HTML         |
|    Início da página de visualização dos chamados em HTML     |
|          Levantamento e listagem dos tipos de danos          |
|             Início da criação do banco de dados              |
|                      Página do Técnico                       |
|               Linkar banco de dados as páginas               |
|                   Criar layout das páginas                   |
| Aprimorar possibilidade de mudanças das configurações das máquinas |
|              Criação de  identificações visuais              |
|                      Testes e correções                      |

|                Backlog 2.1<br>75% ███████▒▒▒                 |
| :----------------------------------------------------------: |
|                Identificação dos computadores                |
|             Página de abertura de chamados HTML              |
|         Página de visualização dos chamados em HTML          |
|          Levantamento e listagem dos tipos de danos          |
|             Início da criação do banco de dados              |
| Criação da área do Técnico /Diferenciar a interface dependendo de |
| Linkar Banco de Dados com área do técnico e abertura de chamados |
|      Botão de conclusão de chamados na área do técnico       |
|             Confirmação de 'solicitação enviada'             |
|          Layout visual da localização das máquinas           |
|       Aprimoramento da identificação dos computadores        |
|              Criação de identificações visuais               |
|       Criação de uma página home e página de contatos        |
|         Aprimoramento da Identidade Visual da Página         |

|               Backlog 3.0 <br>99% ██████████]                |
| :----------------------------------------------------------: |
|                Identificação dos computadores                |
|            Página de abertura de chamados em HTML            |
|         Página de visualização dos chamados em HTML          |
|          Criação, aprovação e entrega do Wireframe           |
|                 Conexão das páginas no Flask                 |
|          Levantamento e listagem dos tipos de danos          |
|      Criação da Modelagem Conceitual do Banco de Dados       |
|                Criação da imagem Esquema SQL                 |
|             Início da Criação do Banco de Dados              |
| Criação da área do Técnico /Diferenciar a interface dependendo de |
| Linkar Banco de Dados com área do técnico e abertura de chamados |
|      Botão de conclusão de chamados na área do técnico       |
|             Confirmação de 'solicitação enviada'             |
|          Layout visual da localização das máquinas           |
| Ligação do Layout da localização das Máquinas do laboratorio ao Banco de Dados |
|       Aprimoramento da identificação dos computadores        |
|              Criação de identificações visuais               |
|       Criação de uma página home e página de contatos        |
|    Aprimoramento da Identidade e Unidade Visual da Página    |



## :key: Histórias de Usuário<a id="historia"></a>



|          ID           |                     História de Usuário                      |
| :-------------------: | :----------------------------------------------------------: |
| US01<a id='us01'></a> | Natália, aluna e Andréa, professora, precisam de uma forma de identificação nominal dos computadores. |
| US02<a id='us02'></a> | Pedro, técnico, precisa de uma identificação para diferenciar os diversos computadores semelhantes dentro da Fatec. |
| US03<a id='us03'></a> | Como  estudante e professora, Natália e Andreia, respectivamente, deveriam ser  capazes de pedir ajuda ao técnico quando o computador não estivesse  funcionando como esperado. |
| US04<a id='us04'></a> | Como  técnico responsável pelo bom funcionamento dos computadores, Pedro deveria  ter um acesso rápido aos relatos dos problemas técnicos dos computadores. |
| US05<a id='us05'></a> | Pedro  precisa de um ambiente com sistema integrado para que ele receber automaticamente os chamados abertos pelos usuários. |
| US06<a id='us06'></a> | Como usuárias, Natália e Andréa precisam de uma interface *clean* e intuitiva que seja fácil de usar e, ao mesmo tempo, não falte as informações as necessária para que Pedro identifique o problema. |

<br>

## :mega: Apresentação da Sprint<a id='#apresentação'></a>

Para visualizar a *Apresentação da Sprint 1* em PDF, acesse o <a href='/doc/sprints/sprint1/img/Sprint1.pdf'>link :link:</a>.
