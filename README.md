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

Com os avanços e facilidades do momento decidimos inovar e introduzir nosso restaurante ao novo mundo 4.0. Aqui, acreditamos que a experiência gastronômica deve ser mais do que apenas sabores excepcionais, deve ser uma fusão de criatividade, comodidade e interatividade. Ao adotar o cardápio QR Code, proporcionamos aos nossos clientes uma maneira rápida, fácil e segura de explorar nossas opções gastronômicas, ao mesmo tempo em que oferecemos uma experiência aprimorada que atende às necessidades dos tempos atuais, onde o sistema de QR Code foi cuidadosamente implementado com o objetivo inicial de aprimorar o atendimento a pedidos e otimizar a organização das tarefas na cozinha.
 

### 3 ) Minimundo do sistema proposto

O restaurante possuirá nome e  código de identificação. Este terá duas classes de usuário - o Admin, que possui login e senha e o Cliente, que possui nome, email e telefone - , além de outras duas entidades que servirão de ferramenta para as operações. O Cardápio é feito apartir da composição de itens que possuem nome, descrição e preço, e categoria que possuem o nome da categoria. Os QR codes de cada mesa e elas apenas possuem seu código de identificação. A Tela de Login não será a mesma para as duas classes de usuário, através do código de QR Code o usuário é direcionado ao cardápio e o link direto redireciona a tela de login do ADMIN. Haverá apenas um Admin por restaurante. Este poderá criar ou destruir QR codes, assim como alterar a mesa que é associada a cada um dos QR codes. O Admin também poderá modificar o cardápio, alterando, removendo ou adicionando itens e categorias.  A Cozinha será apenas uma por restaurante, esta possuirá um computador que recebe pedidos e os entrega às respectivas mesas.  Existem vários clientes para cada restaurante, e para cada 1 QR Code. Este QR Code analisa o cardápio e retorna várias opções para o cliente fazer o pedido. Após o pagamento, o QR Code anexa ao pedido o número da mesa e envia o pedido para a cozinha.

### 4.PROTOTIPAÇÃO, PERGUNTAS A SEREM RESPONDIDAS E TABELA DE DADOS<br>
#### 4.1 RASCUNHOS BÁSICOS DA INTERFACE (MOCKUPS)


[https://github.com/FeLiXp90/CardapioQRCode/blob/master/imagens/balsamiq.png](https://github.com/FeLiXp90/CardapioQRCode/blob/master/imagens/balsamiq.png)/<br>

![Alt text](https://github.com/FeLiXp90/CardapioQRCode/blob/master/imagens/balsamiq.png "Página ADMIN")

![PROTOTIPAÇÃO - SISTEMA DE CARDÁPIO QR CODE.pdf](https://github.com/FeLiXp90/CardapioQRCode/blob/master/arquivos/PrototipacaoCardapioQRCode.pdf)<br>

#### 4.2 QUAIS PERGUNTAS PODEM SER RESPONDIDAS COM O SISTEMA PROPOSTO?

 > Cardápio QR Code precisa inicialmente dos seguintes relatórios:

   * Relatório que mostre a data de todas as compras durante um periodo. Serve para fazer um balanço, saber quais dias e horário tem muito movimento.<br>
   * Relatório da moda dos itens vendidos, que serve para verificar quais produtos estão saindo mais e quais não estão sendo vendidos.<br>
   * Relatório do cardápio geral, com o nome dos itens e preço, ordenado pela categoria. Usado para criação do cardápio.<br>
   * Relatório de clientes com contagem associada a quantidade de compras mensalmente efetuada. Usada para identificar fidelidade e gerar descontos.<br>
   * Relatório de cliente com nome do cliente relacionando com o codigo do pedido e a mesa, e ordenada os item_pedidos com o status em "aguardando" ou "entregue. Serve para fazer verificação dos itens que ainda estão aguardando para serem feitos e entregues pela cozinha.
 
 
 #### 4.3 TABELAS DE DADOS DO SISTEMA:
    
 ![Tabela Modelo Logico](https://github.com/FeLiXp90/CardapioQRCode/blob/master/arquivos/Tabelas%20Exemplo%20Modelo%20L%C3%B3gico%20(2).xlsx) "Tabela - Cardápio QR Code")<br>
 Link: https://docs.google.com/spreadsheets/d/1n-Mo7cHK3E_brFU1ScfYX4t0fWqM9vOJ039CIgLGFXo/edit#gid=0
 
    
### 5.MODELO CONCEITUAL<br>
            
!["Modelo Conceitual"](https://github.com/FeLiXp90/CardapioQRCode/blob/master/imagens/conceitual.png "Modelo Lógico")
    
    
        
    
#### 5.1 Validação do Modelo Conceitual<br>
   
   [Grupo Richard] : [Micaely] <br>
   Deveria ser feita uma mudança na associação de ADMIN com ITEM e CATEGORIA, onde esses precisariam estar ligado ao RESTAURANTE e não ao ADMIN.<br>
   A gente não fez a mudança porque não há restrição de existência (drop em cascata) se a chave estrangeira do admin fosse salva ali. Isso não faz tanto sentido e nem diferença quando vai para o modelo lógico.<br>
    
   [Grupo Fernanda] : [Fernanda Jaimara]<br>
    Sugeriu mudanças visuais no modelo, tais como: Restaurante deveria estar acima ou no mesmo nível que mesa, restaurante deve estar acima ou no mesmo nível que admin, Admin deve estar no mesmo nível ou superior a item.<br> 
    Também sugeriu a mudança: QR code vira atributo de mesa.<br>
    A mudança do QR Code virar atributo não achamos válida, pois o QR pode estar instanciado a várias mesas. Quanto à questão visual e de leitura, não achamos que faça real diferença, especialmente porque o que dará entendimento do sistema é a descrição do mini-mundo.<br>

#### 5.2 Descrição dos dados 
 
ITEM: É um prato que está associado a uma categoria e faz parte do cardápio do Restaurante.<br>
CATEGORIA: É uma categoria de pratos que está associado a vários itens. _ex: refrigerantes, pizzas, hamburguers, etc._<br>
QR CODE: Está associado a uma mesa e redireciona o cliente ao cardápio.<br>
PEDIDO: É um registro de compra feito pelo cliente ao efetuar o pagamento dos itens selecionados no cardápio.<br>
CLIENTE: É um cliente que fez pagamento no restaurante.<br>
MESA: É uma mesa do restaurante que está associado a um QR Code e aos clientes.<br>
ADMIN: É o dono do restaurante que gerencia o cardápio do seu empreendimento e faz controle das mesas.<br>



### 6	MODELO LÓGICO<br>
![Modelo Lógico](https://github.com/FeLiXp90/CardapioQRCode/blob/master/imagens/ModeloLogicoDoCardapioCorrigdo.png "Modelo Lógico")

### 7	MODELO FÍSICO<br>

Tabela cliente:<br>
CREATE TABLE CLIENTE(<br>
CODIGO     			int,<br>
NOME       			VARCHAR(45),<br>
TELEFONE   			VARCHAR(45),<br>
EMAIL      			VARCHAR(45)<br>
);<br>

Tabela pedido:<br>
CREATE TABLE PEDIDO(<br>
CODIGO     			int,<br>
DATA_HORA  			timestamp,<br>
STATUS     			VARCHAR(45),<br>
FK_CLIENTE_COD		int,<br>
FK_MESA_COD			int<br>
);<br>

Tabela pedido_item:
CREATE TABLE PEDIDO_ITEM(<br>
FK_PEDIDO_COD		int,<br>
FK_ITEM_COD			int,<br>
QUANTIDADE			int<br>
);<br>

Tabela item:<br>
CREATE TABLE ITEM(<br>
CODIGO     			int,<br>
NOME				VARCHAR(45),<br>
DESCRICAO			VARCHAR(45),<br>
PRECO				real<br>
);<br>

Tabela mesa:<br>
CREATE TABLE MESA(<br>
CODIGO				int,<br>
COD_QR_CODE			VARCHAR(45)<br>
);<br>

Tabela admin:<br>
CREATE TABLE ADMIN(<br>
CODIGO				int,<br>
NOME_RESTAURANTE	VARCHAR(45),<br>
LOGIN				VARCHAR(45),<br>
SENHA				VARCHAR(45)<br>
);<br>

Tabela categoria:<br>
CREATE TABLE CATEGORIA(<br>
CODIGO				int,<br>
NOME				VARCHAR(45)<br>
);<br>

Tabela item_categoria:<br>
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
(6,'Carlos Roberto','54312-6789','carlos@gmail.com'),<br>
(7,'João Luiz','13258-1234','joaoluiz@gmail.com'),<br>
(8,'Hannah Montanna','40028-9220','hannymtn@gmail.com'),<br>
(9,'Perseu Fraga','98760-1234','perseufmofraga@gmail.com'),<br>
(10,'Felipe Ferrareis','13114-1234','ferrareisfbt@gmail.com');<br>

INSERT INTO PEDIDO(CODIGO,DATA_HORA,STATUS,FK_CLIENTE_COD,FK_MESA_COD) VALUES<br>
(1,'11/04/2023 16:03:00 -3:00','Entregue',2,2),<br>
(2,'11/04/2023 16:10:00 -3:00','Entregue',1,3),<br>
(3,'11/04/2023 16:11:00 -3:00','Entregue',5,1),<br>
(4,'11/04/2023 16:15:00 -3:00','Preparando...',4,5),<br>
(5,'11/04/2023 16:20:00 -3:00','Preparando...',6,4),<br>
(6,'11/04/2023 16:23:00 -3:00','Preparando...',3,6),<br>
(7,'12/04/2023 16:20:00 -3:00','Preparando...',7,4),<br>
(8,'12/05/2023 16:23:00 -3:00','Entregue',8,6),<br>
(9,'12/06/2023 16:20:00 -3:00','Preparando...',10,4),<br>
(10,'12/07/2023 16:23:00 -3:00','Entregue',9,6);<br>


INSERT INTO PEDIDO_ITEM(FK_PEDIDO_COD,FK_ITEM_COD,QUANTIDADE) VALUES<br>
(1,2,1),<br>
(1,6,2),<br>
(2,3,1),<br>
(3,1,1),<br>
(4,6,2),<br>
(5,5,2),<br>
(6,4,3),<br>
(7,5,2),<br>
(8,4,3),<br>
(9,5,2),<br>
(10,4,3);<br>

INSERT INTO ITEM(CODIGO,NOME,DESCRICAO,PRECO) VALUES<br>
(1,'Coraçãozinho','200g de coração de galinha',10.00),<br>
(2,'Picanha','200g de picanha',12.00),<br>
(3,'Alcatra','200g de alcatra',11.00),<br>
(4,'Pão de Alho','1 Pão de Alho',8.50),<br>
(5,'Coca 2L','1 Coca cola 2L',12.00),<br>
(6,'Cerveja Brahma','Lata de Brahma',3.00),<br>
(7,'Dollynho','1 Dollynho 1L',4.00),<br>
(8,'Cerveja Heineken','Garrafa de Heineken 600ml',12.00),<br>
(9,'Pepsi','1 Pepsi 2L',8.00),<br>
(10,'Cerveja Skol','Lata de Skol',5.00);<br>

INSERT INTO MESA(CODIGO,COD_QR_CODE) VALUES<br>
(1,'/cardapio/mesa=1'),<br>
(2,'/cardapio/mesa=2'),<br>
(3,'/cardapio/mesa=3'),<br>
(4,'/cardapio/mesa=4'),<br>
(5,'/cardapio/mesa=5'),<br>
(6,'/cardapio/mesa=6'),<br>
(7,'/cardapio/mesa=7'),<br>
(8,'/cardapio/mesa=8'),<br>
(9,'/cardapio/mesa=9'),<br>
(10,'/cardapio/mesa=10'),<br>
(11,'/cardapio/mesa=11');<br>

INSERT INTO ADMIN(CODIGO,NOME_RESTAURANTE,LOGIN,SENHA) VALUES<br>
(1,'Rei da Picanha','Admin_Luiz','Flamengo123');<br>

INSERT INTO CATEGORIA(CODIGO,NOME) VALUES<br><br>
(1,'Carnes'),<br>
(2,'Petiscos'),<br>
(3,'Bebidas'),<br>
(4,'Sanduiches'),<br>
(5,'Massas'),<br>
(6,'Doces'),<br>
(7,'Sorvetes'),<br>
(8,'Mexicana'),<br>
(9,'Vegana'),<br>
(10,'Gourmet');<br>

INSERT INTO ITEM_CATEGORIA(FK_ITEM_COD,FK_CATEGORIA_COD) VALUES<br>
(1,1),<br>
(2,1),<br>
(3,1),<br>
(4,2),<br>
(5,3),<br>
(6,3),<br>
(7,3),<br>
(8,3),<br>
(9,3),<br>
(10,3);<br>

# BACKUP: DROP, CREATE e INSERT<br>
Está no Colaboratório no Tópico 9.<br>
![Arquivo Backup](https://github.com/FeLiXp90/CardapioQRCode/blob/master/arquivos/pgpyaahu.2023-05-23T18_51_06%2B00_00.sql.lzo "backup.sql - Cardápio QR Code")

The backups are compressed with lzop, to restore run: lzop -cd "$FILENAME" | psql "$DATABASE_NAME" .<br>

### 9	TABELAS E PRINCIPAIS CONSULTAS<br>
    
#### 9.1	CONSULTAS DAS TABELAS COM TODOS OS DADOS INSERIDOS (Todas) <br>

Link para o colaboratório do trabalho: https://colab.research.google.com/drive/1kYHZTWgSQqFBIL3jeicpZtVbrdSAZ7c_#scrollTo=6QFjfiOLWl1n<br>

Todas as seguintes consultas apresentadas estão no colab apresentado.

># Marco de Entrega 01: Do item 1 até o item 9.1<br>

#### 9.2	CONSULTAS DAS TABELAS COM FILTROS WHERE (Mínimo 4)<br>

    SELECT * FROM PEDIDO WHERE status = 'Preparando...';
    
    SELECT * FROM pedido where fk_mesa_cod=1;
    
    SELECT cliente.nome as nome_cliente,pedido.status,item.nome
    FROM CLIENTE cliente
    JOIN PEDIDO pedido
    ON cliente.codigo=pedido.fk_cliente_cod
    JOIN PEDIDO_ITEM pedido_item
    ON pedido.fk_cliente_cod=pedido_item.fk_pedido_cod
    JOIN ITEM item
    ON pedido_item.fk_ITEM_cod=item.codigo
    where cliente.nome='Wagner Moura';
    
    SELECT * FROM CATEGORIA
    JOIN Item_categoria
    on categoria.codigo=fk_CATEGORIA_cod
    JOIN item
    on item.codigo=fk_CATEGORIA_cod
    WHERE categoria.NOME='Carnes';

#### 9.3	CONSULTAS QUE USAM OPERADORES LÓGICOS, ARITMÉTICOS E TABELAS OU CAMPOS RENOMEADOS (Mínimo 11)
    a) Criar 5 consultas que envolvam os operadores lógicos AND, OR e Not
    
    SELECT * FROM PEDIDO WHERE status = 'Preparando...' AND fk_mesa_cod = '4';
    
    SELECT QUANTIDADE FROM PEDIDO_ITEM WHERE fk_item_cod = '5' AND fk_pedido_cod = '5';
    
    SELECT * FROM CATEGORIA
    JOIN Item_categoria
    on categoria.codigo=fk_CATEGORIA_cod
    JOIN item
    on item.codigo=fk_CATEGORIA_cod
    WHERE categoria.NOME='Carnes' AND NOT fk_item_cod = '1';
    
    SELECT cliente.nome as nome_cliente,pedido.status,item.nome
    FROM CLIENTE cliente
    JOIN PEDIDO pedido
    ON cliente.codigo=pedido.fk_cliente_cod
    JOIN PEDIDO_ITEM pedido_item
    ON pedido.fk_cliente_cod=pedido_item.fk_pedido_cod
    JOIN ITEM item
    ON pedido_item.fk_ITEM_cod=item.codigo
    WHERE cliente.nome='Hugo Chavez' AND item.nome = 'Picanha';
    
    SELECT * FROM PEDIDO WHERE data_hora > '2023-12-01' OR STATUS = 'Preparando...';
    
     b) Criar no mínimo 3 consultas com operadores aritméticos 
    
    SELECT * FROM ITEM WHERE preco * 1.2 > 10;
    
    SELECT NOME
    FROM ITEM
    INNER JOIN PEDIDO_ITEM ON ITEM.codigo = PEDIDO_ITEM.fk_item_cod
    WHERE quantidade * preco > 12
    GROUP BY ITEM.nome;
    
    SELECT NOME,SUM(preco)
    FROM ITEM
    INNER JOIN PEDIDO_ITEM ON ITEM.codigo = PEDIDO_ITEM.fk_item_cod
    WHERE (quantidade * preco) / 2 < 10
    GROUP BY ITEM.nome;
    
    
    c) Criar no mínimo 3 consultas com operação de renomear nomes de campos ou tabelas
    
    SELECT C.NOME AS ALCUNHA FROM CLIENTE AS C WHERE C.NOME LIKE 'F%';
    SELECT I.NOME AS PRODUTO, I.PRECO AS CUSTA 
    FROM ITEM AS I 
    WHERE I.PRECO IS NOT NULL AND I.PRECO <> 0 
    ORDER BY CUSTA ASC;

    SELECT DATA_HORA AS DATE FROM PEDIDO ORDER BY DATE DESC;

#### 9.4	CONSULTAS QUE USAM OPERADORES LIKE E DATAS (Mínimo 12) <br>
    SELECT * FROM CLIENTE AS C WHERE C.NOME LIKE 'J%';
    
    SELECT * FROM ITEM AS I WHERE I.NOME LIKE 'C%';
    
    SELECT * FROM CATEGORIA AS C WHERE C.NOME LIKE '%es';
    
    SELECT C.NOME, C.TELEFONE FROM CLIENTE AS C WHERE C.NOME ILIKE '%b%';
    
    SELECT * FROM CATEGORIA AS C WHERE C.NOME ILIKE '%c%';
    
    SELECT CURRENT_DATE, DATA_HORA ,STATUS FROM PEDIDO AS P;
    
    SELECT CURRENT_TIME,DATA_HORA,STATUS FROM PEDIDO AS P;
    
    SELECT NOW(),DATA_HORA,STATUS FROM PEDIDO AS P;
    
    SELECT AGE(CURRENT_DATE,DATA_HORA) AS "Tempo do pedido",STATUS FROM PEDIDO AS P;
    
    SELECT DATE_PART('MONTH',AGE(CURRENT_DATE,DATA_HORA)),STATUS FROM PEDIDO AS P;
    
    SELECT DATE_PART('YEAR',AGE(CURRENT_DATE,DATA_HORA)),STATUS FROM PEDIDO AS P;
    
    SELECT EXTRACT('MONTH' FROM DATA_HORA),STATUS FROM PEDIDO AS P;
    
    SELECT C.NOME, EXTRACT('MONTH' FROM DATA_HORA) AS "Ano do pedido", STATUS<br> 
    FROM PEDIDO AS P <br>
    INNER JOIN CLIENTE AS C ON (C.CODIGO = P.FK_CLIENTE_COD)<br>
    WHERE P.STATUS LIKE '%Entrege%';<br>

#### 9.5	INSTRUÇÕES APLICANDO ATUALIZAÇÃO E EXCLUSÃO DE DADOS (Mínimo 6)<br>
    b) Criar minimo 3 de atualização
    
    UPDATE CLIENTE
    SET NOME = 'Hugo Chavez'
    WHERE CODIGO = 1;
    
    UPDATE ADMIN
    SET SENHA = 'PALMEIRASNAOTEMMUNDIAL'
    WHERE CODIGO = 1;

    UPDATE ITEM
    SET DESCRICAO = '150g de coracao de galinha'
    WHERE CODIGO = 1;
    
    a) Criar minimo 3 de exclusão
    
    DELETE FROM CLIENTE WHERE NOME = 'Hugo Chavez';
    
    DELETE FROM ITEM WHERE NOME = 'Picanha';
    
    DELETE FROM MESA WHERE CODIGO=1;
    

#### 9.6	CONSULTAS COM INNER JOIN E ORDER BY (Mínimo 6)<br>
    a) Uma junção que envolva todas as tabelas possuindo no mínimo 2 registros no resultado
    
    SELECT * 
    FROM cliente INNER JOIN pedido 
    ON pedido.fk_cliente_cod = cliente.codigo
    INNER JOIN pedido_item
    ON pedido.codigo=pedido_item.fk_pedido_cod
    INNER JOIN item
    ON pedido_item.fk_item_cod=item.codigo
    INNER JOIN item_categoria
    ON item_categoria.fk_item_cod=item.codigo
    INNER JOIN categoria
    ON categoria.codigo=fk_categoria_cod
    INNER JOIN admin
    ON admin.codigo=categoria.codigo
    INNER JOIN mesa
    ON pedido.fk_mesa_cod=mesa.codigo
    ORDER BY cliente.telefone DESC;
    
    b) Outras junções que o grupo considere como sendo as de principal importância para o trabalho

    SELECT cliente.nome,data_hora,status,fk_mesa_cod as mesa,quantidade,item.nome as item
    FROM CLIENTE cliente
    JOIN PEDIDO pedido
    ON cliente.codigo=pedido.fk_cliente_cod

    JOIN MESA mesa
    ON pedido.fk_mesa_cod=mesa.codigo

    JOIN PEDIDO_ITEM pedido_item
    ON pedido_item.fk_pedido_cod=pedido.codigo

    JOIN ITEM item
    ON item.codigo=pedido_item.fk_item_cod

    ORDER BY CASE
        WHEN status = 'Preparando...' THEN 0
        WHEN status = 'Entregue' THEN 1
        ELSE 2
    END;

#### 9.7	CONSULTAS COM GROUP BY E FUNÇÕES DE AGRUPAMENTO (Mínimo 6)<br>
    SELECT FK_ITEM_COD FROM PEDIDO_ITEM GROUP BY FK_ITEM_COD;
 
    SELECT FK_PEDIDO_COD FROM PEDIDO_ITEM GROUP BY FK_PEDIDO_COD; 

    SELECT FK_ITEM_COD,COUNT(FK_ITEM_COD) AS QTD FROM PEDIDO_ITEM GROUP BY FK_ITEM_COD;
 
    SELECT FK_PEDIDO_COD,COUNT(FK_PEDIDO_COD) AS QTD FROM PEDIDO_ITEM GROUP BY FK_PEDIDO_COD; 

#### 9.8	CONSULTAS COM LEFT, RIGHT E FULL JOIN (Mínimo 4)<br>
    a) Criar minimo 1 de cada tipo
    
    SELECT * 
    FROM cliente LEFT JOIN pedido 
    ON pedido.fk_cliente_cod = cliente.codigo;

    SELECT * 
    FROM pedido RIGHT JOIN cliente
    ON pedido.fk_cliente_cod = cliente.codigo;

    SELECT * 
    FROM pedido FULL JOIN cliente
    ON pedido.fk_cliente_cod = cliente.codigo;

    SELECT * 
    FROM mesa FULL JOIN pedido
    ON pedido.fk_mesa_cod = mesa.codigo;

#### 9.9	CONSULTAS COM SELF JOIN E VIEW (Mínimo 6)<br>
     a) Uma junção que envolva Self Join (caso não ocorra na base justificar e substituir por uma view)
     
     Self Joins são bons para associar duas linhas de uma mesma tabela onde uma faz alusão a outra. (Por exemplo, em uma Tabela Pessoas, onde tem Pais e filhos, usaria-se um Self Join para agrupar os pais e os filhos em uma mesma linha, como no nosso trabalho não tem nenhuma tabela com esse tipo de relação onde uma linha faz referencia a outra da mesma tabela, a junção self join então será substituida por uma View.
        
    CREATE VIEW View1 AS
    SELECT cliente.nome as nome_cliente,pedido.status,item.nome
    FROM CLIENTE cliente
    JOIN PEDIDO pedido
    ON cliente.codigo=pedido.fk_cliente_cod
    JOIN PEDIDO_ITEM pedido_item
    ON pedido.fk_cliente_cod=pedido_item.fk_pedido_cod
    JOIN ITEM item
    ON pedido_item.fk_ITEM_cod=item.codigo
    where cliente.nome='Wagner Moura';
    
    CREATE VIEW View2 AS
    SELECT * FROM CATEGORIA
    JOIN Item_categoria
    on categoria.codigo=fk_CATEGORIA_cod
    JOIN item
    on item.codigo=fk_CATEGORIA_cod
    WHERE categoria.NOME='Carnes';
    
    CREATE VIEW View3 AS
    SELECT cliente.nome,data_hora,status,fk_mesa_cod as mesa,quantidade,item.nome as item
    FROM CLIENTE cliente
    JOIN PEDIDO pedido
    ON cliente.codigo=pedido.fk_cliente_cod
    
    JOIN MESA mesa
    ON pedido.fk_mesa_cod=mesa.codigo

    JOIN PEDIDO_ITEM pedido_item
    ON pedido_item.fk_pedido_cod=pedido.codigo

    JOIN ITEM item
    ON item.codigo=pedido_item.fk_item_cod

    ORDER BY CASE
        WHEN status = 'Preparando...' THEN 0
        WHEN status = 'Entregue' THEN 1
        ELSE 2
    END;
        
    b) Outras junções com views que o grupo considere como sendo de relevante importância para o trabalho
        
    Create View View4 AS
    SELECT * FROM cliente
    SELECT * FROM pedido
    SELECT * FROM mesa
    SELECT * FROM admin
    SELECT * FROM categoria
    SELECT * FROM item_categoria
    SELECT * FROM item
    SELECT * FROM pedido_item

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


