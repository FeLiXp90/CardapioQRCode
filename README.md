# Sumário

# TRABALHO 01:  CARDÁPIO QR CODE
Trabalho desenvolvido durante a disciplina de BD1

### 1. COMPONENTES<br>
Integrantes do grupo<br>
João Victor Ferrareis Ribeiro: joaovito2002@hotmail.com<br>
Renzo Fraga Loureiro Marinho: renzofraga49@gmail.com<br>
Perseu Fernandes Machado de Oliveira: perseu.fmo@gmail.com<br>
Felipe Becalli Trindade: felipebecallitrindade@gmail.com<br>


### 2.INTRODUÇÃO E MOTIVAÇÃO<br>

Com os avanços e facilidades do momento decidimos inovar e introduzir nosso restaurante ao novo mundo 4.0. Ao introduzir um sistema de QR CODE, nosso objetivo inicial seria melhorar o atendimento a pedidos e organização a prioridades nas tarefas da cozinha. Esperamos sempre nos qualificar e dar um upgrade para sempre encher sua barriga com felicidade.
 

### 3 ) Minimundo do sistema proposto

O restaurante possuirá nome e  código de identificação. Este terá duas classes de usuário - o Admin e o Cliente - , além de outras duas entidades que servirão de ferramenta para as operações. O Cardápio(Itens e Categorias) e os QR codes de cada mesa. A Tela de Login será a mesma para todas as duas classes de usuário, mas dependendo do seu login e senha porém serão direcionadas baseado nas credenciais e o aplicativo identificará a classe dirigindo o usuário para telas diferentes.  Haverá apenas um Admin por restaurante. Este poderá criar ou destruir QR codes, assim como alterar a mesa que é associada a cada um dos QR codes. O Admin também poderá modificar o cardápio, alterando, removendo ou adicionando pratos e categorias.  A Cozinha será apenas uma por restaurante. Esta possuirá um computador que recebe pedidos e os entrega às respectivas mesas.  Existem vários clientes para cada restaurante, e para cada 1 QR Code. Este QR Code analisa o cardápio e retorna várias opções para o cliente fazer o pedido. Após o pagamento, o QR Code anexa ao pedido o número da mesa e envia o pedido para a cozinha.

### 4.PROTOTIPAÇÃO, PERGUNTAS A SEREM RESPONDIDAS E TABELA DE DADOS<br>
#### 4.1 RASCUNHOS BÁSICOS DA INTERFACE (MOCKUPS)


[https://github.com/FeLiXp90/CardapioQRCode/blob/master/imagens/balsamiq.png](https://github.com/FeLiXp90/CardapioQRCode/blob/master/imagens/balsamiq.png)/<br>

![Alt text](https://github.com/FeLiXp90/CardapioQRCode/blob/master/imagens/balsamiq.png "Página ADMIN")

![PROTOTIPAÇÃO - SISTEMA DE CARDÁPIO QR CODE.pdf](https://github.com/FeLiXp90/CardapioQRCode/blob/master/arquivos/PrototipacaoCardapioQRCode.pdf)
#### 4.2 QUAIS PERGUNTAS PODEM SER RESPONDIDAS COM O SISTEMA PROPOSTO?
    a) O sistema proposto poderá fornecer quais tipos de relatórios e informaçes? 
    b) Crie uma lista com os 5 principais relatórios que poderão ser obtidos por meio do sistema proposto!
    
> A Empresa DevCom precisa inicialmente dos seguintes relatórios:
* Relatório que mostre o nome de cada supervisor(a) e a quantidade de empregados supervisionados.
* Relatório relativo aos os supervisores e supervisionados. O resultado deve conter o nome do supervisor e nome do supervisionado além da quantidade total de horas que cada supervisionado tem alocada aos projetos existentes na empresa.
* Relatorio que mostre para cada linha obtida o nome do departamento, o valor individual de cada salario existente no  departamento e a média geral de salarios dentre todos os empregados. Os resultados devem ser apresentados ordenados por departamento.
* Relatório que mostre as informações relacionadas a todos empregados de empresa (sem excluir ninguém). As linhas resultantes devem conter informações sobre: rg, nome, salario do empregado, data de início do salario atual, nomes dos projetos que participa, quantidade de horas e localização nos referidos projetos, numero e nome dos departamentos aos quais está alocado, informações do historico de salário como inicio, fim, e valores de salarios antigos que foram inclusos na referida tabela (caso possuam informações na mesma), além de todas informações relativas aos dependentes. 
>> ##### Observações: <br> a) perceba que este relatório pode conter linhas com alguns dados repetidos (mas não todos). <br>  b) para os empregados que não possuirem alguma destas informações o valor no registro deve aparecer sem informação/nulo. 
* Relatório que obtenha a frequencia absoluta e frequencia relativa da quantidade de cpfs únicos no relatório anterior. Apresente os resultados ordenados de forma decrescente pela frequencia relativa.

 
 
#### 4.3 TABELA DE DADOS DO SISTEMA:
    a) Esta tabela deve conter todos os atributos do sistema e um mínimo de 10 linhas/registros de dados.
    b) Esta tabela tem a intenção de simular um relatório com todos os dados que serão armazenados 
    
![Exemplo de Tabela de dados da Empresa Devcom](https://github.com/discipbd1/trab01/blob/master/arquivos/TabelaEmpresaDevCom_sample.xlsx?raw=true "Tabela - Empresa Devcom")
    
    
### 5.MODELO CONCEITUAL<br>
            
!["Modelo Conceitual"](https://github.com/FeLiXp90/CardapioQRCode/blob/master/imagens/conceitual.png "Modelo Lógico")
    
    
        
    
#### 5.1 Validação do Modelo Conceitual
    [Grupo Richard]: [Micaely]
    Deveria ser feita uma mudança na associação de ADMIN com ITEM e CATEGORIA, onde esses precisariam estar ligado ao RESTAURANTE e não ao ADMIN.
    
    [Grupo 02]: [Integrantes que avaliaram]

#### 5.2 Descrição dos dados 
 
ITEM: É um prato que está associado a uma categoria e faz parte do cardápio do Restaurante.
CATEGORIA: É uma categoria de pratos que está associado a vários itens. _ex: refrigerantes, pizzas, hamburguers, etc._
QR CODE: Está associado a uma mesa e redireciona o cliente ao cardápio.
PEDIDO: É um registro de compra feito pelo cliente ao efetuar o pagamento dos itens selecionados no cardápio.
CLIENTE: É um cliente que fez pagamento no restaurante.
MESA: É uma mesa do restaurante que está associado a um QR Code e aos clientes.
ADMIN: É o dono do restaurante que gerencia o cardápio do seu empreendimento e faz controle das mesas.



### 6	MODELO LÓGICO<br>
![Modelo Lógico](https://github.com/FeLiXp90/CardapioQRCode/blob/master/imagens/ModeloLogicoDoCardapioCorrigdo.png "Modelo Lógico")

### 7	MODELO FÍSICO<br>
CREATE TABLE CLIENTE(<br>
CODIGO     			int,<br>
NOME       			VARCHAR(45),<br>
TELEFONE   			VARCHAR(45),<br>
EMAIL      			VARCHAR(45)<br>
);<br>


CREATE TABLE PEDIDO(<br>
CODIGO     			int,<br>
DATA_HORA  			timestamp,<br>
STATUS     			VARCHAR(45),<br>
FK_CLIENTE_COD		int,<br>
FK_MESA_COD			int<br>
);<br>

CREATE TABLE PEDIDO_ITEM(<br>
FK_PEDIDO_COD		int,<br>
FK_ITEM_COD			int,<br>
QUANTIDADE			int<br>
);<br>

CREATE TABLE ITEM(<br>
CODIGO     			int,<br>
NOME				VARCHAR(45),<br>
DESCRICAO			VARCHAR(45),<br>
PRECO				real<br>
);<br>

CREATE TABLE MESA(<br>
CODIGO				int,<br>
COD_QR_CODE			VARCHAR(45)<br>
);<br>

CREATE TABLE ADMIN(<br>
CODIGO				int,<br>
NOME_RESTAURANTE	VARCHAR(45),<br>
LOGIN				VARCHAR(45),<br>
SENHA				VARCHAR(45)<br>
);<br>

CREATE TABLE CATEGORIA(<br>
CODIGO				int,<br>
NOME				VARCHAR(45)<br>
);<br>

CREATE TABLE ITEM_CATEGORIA(<br>
FK_ITEM_COD			int,<br>
FK_CATEGORIA_COD	int<br>
);<br>
        
       
### 8	INSERT APLICADO NAS TABELAS DO BANCO DE DADOS<br>

DROP TABLE IF EXISTS CLIENTE;<br>
CREATE TABLE CLIENTE(<br>
CODIGO     			int,<br>
NOME       			VARCHAR(45),<br>
TELEFONE   			VARCHAR(45),<br>
EMAIL      			VARCHAR(45)<br>
);<br>


DROP TABLE IF EXISTS PEDIDO;<br>
CREATE TABLE PEDIDO(<br>
CODIGO     			int,<br>
DATA_HORA  			timestamp,<br>
STATUS     			VARCHAR(45),<br>
FK_CLIENTE_COD		int,<br>
FK_MESA_COD			int<br>
);<br>

DROP TABLE IF EXISTS PEDIDO_ITEM;<br>
CREATE TABLE PEDIDO_ITEM(<br>
FK_PEDIDO_COD		int,<br>
FK_ITEM_COD			int,<br>
QUANTIDADE			int<br>
);<br>

DROP TABLE IF EXISTS ITEM;<br>
CREATE TABLE ITEM(<br>
CODIGO     			int,<br>
NOME				VARCHAR(45),<br>
DESCRICAO			VARCHAR(45),<br>
PRECO				real<br>
);<br>

DROP TABLE IF EXISTS MESA;<br>
CREATE TABLE MESA(<br>
CODIGO				int,<br>
COD_QR_CODE			VARCHAR(45)<br>
);<br>

DROP TABLE IF EXISTS ADMIN;<br>
CREATE TABLE ADMIN(<br>
CODIGO				int,<br>
NOME_RESTAURANTE	VARCHAR(45),<br>
LOGIN				VARCHAR(45),<br>
SENHA				VARCHAR(45)<br>
);<br>

DROP TABLE IF EXISTS CATEGORIA;<br>
CREATE TABLE CATEGORIA(<br>
CODIGO				int,<br>
NOME				VARCHAR(45)<br>
);<br>

DROP TABLE IF EXISTS ITEM_CATEGORIA;<br>
CREATE TABLE ITEM_CATEGORIA(<br>
FK_ITEM_COD			int,<br>
FK_CATEGORIA_COD	int<br>
);<br>

INSERT INTO CLIENTE(CODIGO,NOME,TELEFONE,EMAIL) VALUES<br>
(1,'Wagner Moura','98765-4321','wagnermoura@gmail.com'),<br>
(2,'Gabriel Pensador','23456-7800','gabriel@gmail.com'),<br>
(3,'Romeu Banhos','21345-6789','romeu@gmail.com'),<br>
(4,'Eliseu Faria','32145-6789','eliseu@gmail.com'),<br>
(5,'Bartolomeu Bragança','12345-6789','bartolomeu@gmail.com'),<br>
(6,'Carlos Roberto','54312-6789','carlos@gmail.com');<br>

INSERT INTO PEDIDO(CODIGO,DATA_HORA,STATUS,FK_CLIENTE_COD,FK_MESA_COD) VALUES<br>
(1,'11/04/2023 16:03:00 -3:00','Entregue',2,2),<br>
(2,'11/04/2023 16:10:00 -3:00','Entregue',1,3),<br>
(3,'11/04/2023 16:11:00 -3:00','Entregue',5,1),<br>
(4,'11/04/2023 16:15:00 -3:00','Preparando...',4,5),<br>
(5,'11/04/2023 16:20:00 -3:00','Preparando...',6,4),<br>
(6,'11/04/2023 16:23:00 -3:00','Preparando...',3,6);<br>

INSERT INTO PEDIDO_ITEM(FK_PEDIDO_COD,FK_ITEM_COD,QUANTIDADE) VALUES<br>
(1,2,1),<br>
(1,6,2),<br>
(2,3,1),<br>
(3,1,1),<br>
(4,6,2),<br>
(5,5,2),<br>
(6,4,3);<br>

INSERT INTO ITEM(CODIGO,NOME,DESCRICAO,PRECO) VALUES<br>
(1,'Coraçãozinho','200g de coração de galinha',10.00),<br>
(2,'Picanha','200g de picanha',12.00),<br>
(3,'Alcatra','200g de alcatra',11.00),<br>
(4,'Pão de Alho','1 Pão de Alho',8.50),<br>
(5,'Coca 2L','1 Coca cola 2L',12.00),<br>
(6,'Cerveja Brahma','Lata de Brahma',3.00);<br>

INSERT INTO MESA(CODIGO,COD_QR_CODE) VALUES<br>
(1,'/cardapio/mesa=1'),<br>
(2,'/cardapio/mesa=2'),<br>
(3,'/cardapio/mesa=3'),<br>
(4,'/cardapio/mesa=4'),<br>
(5,'/cardapio/mesa=5'),<br>
(6,'/cardapio/mesa=6');<br>

INSERT INTO ADMIN(CODIGO,NOME_RESTAURANTE,LOGIN,SENHA) VALUES<br>
(1,'Rei da Picanha','Admin_Luiz','Flamengo123');<br>

INSERT INTO CATEGORIA(CODIGO,NOME) VALUES<br><br>
(1,'Carnes'),<br>
(2,'Petiscos'),<br>
(3,'Bebidas');<br>

INSERT INTO ITEM_CATEGORIA(FK_ITEM_COD,FK_CATEGORIA_COD) VALUES<br>
(1,1),<br>
(2,1),<br>
(3,1),<br>
(4,2),<br>
(5,3),<br>
(6,3);<br>

# BACKUP: DROP, CREATE e INSERT<br>
Está no Colaboratório no Tópico 9.<br>
![Arquivo Backup](https://github.com/FeLiXp90/CardapioQRCode/blob/master/arquivos/pgpyaahu.2023-05-23T18_51_06%2B00_00.sql.lzo "backup.sql - Cardápio QR Code")

The backups are compressed with lzop, to restore run: lzop -cd "$FILENAME" | psql "$DATABASE_NAME" . Or click "Restore" on any of the backups below.<br>

### 9	TABELAS E PRINCIPAIS CONSULTAS<br>

Link para o colaboratório do trabalho: https://colab.research.google.com/drive/1kYHZTWgSQqFBIL3jeicpZtVbrdSAZ7c_#scrollTo=6QFjfiOLWl1n<br>
    
#### 9.1	CONSULTAS DAS TABELAS COM TODOS OS DADOS INSERIDOS (Todas) <br>

># Marco de Entrega 01: Do item 1 até o item 9.1<br>

#### 9.2	CONSULTAS DAS TABELAS COM FILTROS WHERE (Mínimo 4)<br>
#### 9.3	CONSULTAS QUE USAM OPERADORES LÓGICOS, ARITMÉTICOS E TABELAS OU CAMPOS RENOMEADOS (Mínimo 11)
    a) Criar 5 consultas que envolvam os operadores lógicos AND, OR e Not
    b) Criar no mínimo 3 consultas com operadores aritméticos 
    c) Criar no mínimo 3 consultas com operação de renomear nomes de campos ou tabelas

#### 9.4	CONSULTAS QUE USAM OPERADORES LIKE E DATAS (Mínimo 12) <br>
    a) Criar outras 5 consultas que envolvam like ou ilike
    b) Criar uma consulta para cada tipo de função data apresentada.

#### 9.5	INSTRUÇÕES APLICANDO ATUALIZAÇÃO E EXCLUSÃO DE DADOS (Mínimo 6)<br>
    a) Criar minimo 3 de exclusão
    b) Criar minimo 3 de atualização

#### 9.6	CONSULTAS COM INNER JOIN E ORDER BY (Mínimo 6)<br>
    a) Uma junção que envolva todas as tabelas possuindo no mínimo 2 registros no resultado
    b) Outras junções que o grupo considere como sendo as de principal importância para o trabalho

#### 9.7	CONSULTAS COM GROUP BY E FUNÇÕES DE AGRUPAMENTO (Mínimo 6)<br>
    a) Criar minimo 2 envolvendo algum tipo de junção

#### 9.8	CONSULTAS COM LEFT, RIGHT E FULL JOIN (Mínimo 4)<br>
    a) Criar minimo 1 de cada tipo

#### 9.9	CONSULTAS COM SELF JOIN E VIEW (Mínimo 6)<br>
        a) Uma junção que envolva Self Join (caso não ocorra na base justificar e substituir por uma view)
        b) Outras junções com views que o grupo considere como sendo de relevante importância para o trabalho

#### 9.10	SUBCONSULTAS (Mínimo 4)<br>
     a) Criar minimo 1 envolvendo GROUP BY
     b) Criar minimo 1 envolvendo algum tipo de junção

># Marco de Entrega 02: Do item 9.2 até o ítem 9.10<br>

### 10 RELATÓRIOS E GRÁFICOS

#### a) análises e resultados provenientes do banco de dados desenvolvido (usar modelo disponível)
#### b) link com exemplo de relatórios será disponiblizado pelo professor no AVA
#### OBS: Esta é uma atividade de grande relevância no contexto do trabalho. Mantenha o foco nos 5 principais relatórios/resultados visando obter o melhor resultado possível.

    

### 11	AJUSTES DA DOCUMENTAÇÃO, CRIAÇÃO DOS SLIDES E VÍDEO PARA APRESENTAÇAO FINAL <br>

#### a) Modelo (pecha kucha)<br>
#### b) Tempo de apresentação 6:40 

># Marco de Entrega 03: Itens 10 e 11<br>
<br>
<br>




### 12 FORMATACAO NO GIT:<br> 
https://help.github.com/articles/basic-writing-and-formatting-syntax/
<comentario no git>
    
##### About Formatting
    https://help.github.com/articles/about-writing-and-formatting-on-github/
    
##### Basic Formatting in Git
    
    https://help.github.com/articles/basic-writing-and-formatting-syntax/#referencing-issues-and-pull-requests
    
    
##### Working with advanced formatting
    https://help.github.com/articles/working-with-advanced-formatting/
#### Mastering Markdown
    https://guides.github.com/features/mastering-markdown/

    
### OBSERVAÇÕES IMPORTANTES

#### Todos os arquivos que fazem parte do projeto (Imagens, pdfs, arquivos fonte, etc..), devem estar presentes no GIT. Os arquivos do projeto vigente não devem ser armazenados em quaisquer outras plataformas.
1. <strong>Caso existam arquivos com conteúdos sigilosos<strong>, comunicar o professor que definirá em conjunto com o grupo a melhor forma de armazenamento do arquivo.

#### Todos os grupos deverão fazer Fork deste repositório e dar permissões administrativas ao usuário do git "profmoisesomena", para acompanhamento do trabalho.

#### Os usuários criados no GIT devem possuir o nome de identificação do aluno (não serão aceitos nomes como Eu123, meuprojeto, pro456, etc). Em caso de dúvida comunicar o professor.


Link para BrModelo:<br>
http://www.sis4.com/brModelo/download.html
<br>


Link para curso de GIT<br>
![https://www.youtube.com/curso_git](https://www.youtube.com/playlist?list=PLo7sFyCeiGUdIyEmHdfbuD2eR4XPDqnN2?raw=true "Title")


