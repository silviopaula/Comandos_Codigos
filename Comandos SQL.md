# Comandos para SQL


![img0 ](https://i.ibb.co/FgykSn9/img0.png "img0")

***Autor:*** Silvio da Rosa Paula        
     
Essas notas são baseadas no Curso de SQL Completo oferecido gratuitamente com certificação de 18 horas  pela [Softblue](https://www.softblue.com.br/site/curso/id/3/CURSO+SQL+COMPLETO+BASICO+AO+AVANCADO+ON+LINE+BD03)

## **DICIONÁRIO PARA UM DBA SQL Jr.**

Fonte: [Dicionário para um DBA SQL Jr (dbaonboarding.com.br)](https://www.dbaonboarding.com.br/post/dicionario-para-um-dba-sql-jr)

Aqui são descritos alguns termos e traduções dos comandos mais utilizados.

**1) Instância ou Servidor:** É a *Engine*, ou seja, o ambiente que armazena os bancos de dados de aplicações, quando você instala o SQL Server, é a Instância que é instalada e configurada. Em alguns casos pode ser chamada de servidor.

**2) String de conexão:** É o caminho utilizado para conectar na instância e posteriormente no banco de dados da aplicação. Ela é formada pelo IP (ou nome da máquina onde a instância está instalada), barra invertida, nome da instância vírgula e a porta que foi configurada, por exemplo: 170.0.0.2\SQLPRD,1851. Cada modelo de conexão (dependendo da linguagem de programação utilizada) vai complementar essa string com o nome da base de dados, o usuário e a senha para conexão.

**3) BD, base, banco, database:** Todos esses nomes são usados para tratar de fato do banco de dados que armazena os dados, um banco de dados é formado por um conjunto de tabelas (formadas por linhas e colunas) que armazenam dados de uma aplicação.

**4) Backup, faz uma cópia do banco, clonar o banco:** Esses termos se referem a criar uma imagem do banco de dados em um determinado momento (backup), possibilitando que ele seja restaurado com todos seus dados e objetos com o estado atual do momento em que foi gerado.

**5) Startar ou iniciar o banco, parar ou Stopar o banco, baixar a instância subir a instância:** Se referem a ações com o serviço da instância do SQL Server. Para determinadas ações pode ser necessário parar o serviço, ou seja, deixar o ambiente completamente inacessível, seja para uma manutenção, migração, ou qualquer ação que necessite que ninguém acesse. Baixar a instância é o mesmo que parar o serviço, subir a instância é o mesmo que iniciar o serviço.

**6) Subir o banco, restaurar a base:** Ambos estão relacionados a restaurar um backup do banco de dados.

**7) Base de desenvolvimento:** Banco de dados igual ao de produção porém disponibilizado em um outro ambiente para uso exclusivo da equipe de desenvolvimento do sistema para validações e novos desenvolvimentos de rotinas no sistema.

**8) Base de testes:** banco de dados igual ao de produção porém disponibilizado em outro ambiente para validação de novos desenvolvimentos, testes de rotinas com erro, input de dados de validação, realização de treinamentos de cadastros (por exemplo). Todos os dados gerados nesse banco de dados são descartados.

**9) Atualizar a base de homologação/teste:** Pegar o backup mais recente do banco de dados oficial e sobrescrever a base de testes com esse backup deixando a base de testes mais próxima do ambiente oficial, com dados atualizados.

**10) Replicar o banco:** Dependendo do contexto pode ter 2 significados, o primeiro é criar uma cópia para a base de testes ("replica o banco na base de testes por favor") e o segundo é de fato criar uma replicação, ou seja, ter um segundo ambiente espelhando o banco de dados oficial para alta disponibilidade ou até uso para projetos de BI.

**11) HA**: Alta disponibilidade, garantir que o banco esteja sempre online, pra isso você usa algumas técnicas e funcionalidades do SQL Server, montando uma arquitetura que permite o banco estar sempre disponível.

**12) Disaster Recovery**: Recuperação de desastres, conseguir recriar um ambiente que foi perdido, seja por um problema físico ou a nível logico (problemas com o windows), por exemplo, invasão com sequestro de dados onde perdeu o ambiente precisa recriar ele exatamente igual estava.

**13) Dados:** São valores atribuídos a alguma coisa ou a alguma pessoa, é a forma bruta.

**14) Informação:** É quando você estrutura os dados de maneira que eles possam ser interpretados e fazem sentido. Os dados são valores que por si só podem não dizer nada enquanto a informação é a junção e ordenação dos dados dando um sentido a eles te dando a possibilidade de tomar decisão.

**15) Datawarehouse:** É um grande banco de dados, um grande repositório de dados focado em oferecer base para trabalhos com BI, ele centraliza informações de diversas fontes para que os analistas possam extrair relatórios e tomar decisões em cima disso.

**16) OLAP:** O OLAP, do inglês "On-line Analytical Processing", é o tipo de banco de dados focado em análise de dados, o datawarehouse é OLAP.

**17) OLTP:** O OLTP, do inglês "On-line Transaction Processing", é o tipo de banco de dados transacional, os bancos dos sistemas que recebem transações, ou seja, insert, update e delete o tempo todo. OLAP tem foco no nível estratégico e organizacional enquanto o OLTP foca no nível operacional. A principal diferença é que o OLAP é otimizado para leitura e geração de análises enquanto o OTLP tem alta velocidade na manipulação de dados operacionais.

**18) Truncar:** Executar o comando "truncate table" que limpa uma tabela por inteiro de uma só vez. ("Vou truncar aquela tabela"). **"Termo abrasileirado".**

**19) Dropar:** Executar o comando "drop..." que exclui um objeto do banco de dados, pode ser uma tabela, view, procedure... ("Vou dropar aquela tabela"). **"Termo abrasileirado"**

**20) Scriptar:** Gerar o script de uma tabela, view, procedure, trigger.... **"Termo abrasileirado"**


### Glossário  SQL:

| **Abreviação/Comando** | **Tradução/Descrição**|
|---------|------------------------------------------------------------------------------------------|
|SQL 	  | Structured Query Language, ou Linguagem de Consulta Estruturada.|
|SGBD	  | Sistema de gerenciamento de banco de dados (EX: PostgreSQL, MySQL, Oracle, MongoDB, etc).|
|DML 	  | Data Manipulation Language, ou Linguagem de Manipulação de Dados.|
|DDL 	  | Data Definition Language, ou Linguagem de Definição de Dados.|
|DCL      | Data Control Language, ou Linguagem de Controle de Dados.|
|DBA      | Database administrator, ou Administrador de banco de dados.|
|TCL      | Transactional Control Languag, ou Linguagem de Controle de Transações.|
|QUERY    | Tradução: consulta.|
|`SELECT`   | ***Selecionar*** (utilizado para Selecionar linhas, colunas, tabelas).|
|`FROM`     | ***A partir de*** (indica a tabela de dados que será pesquisada).|
|`WHERE`    | ***Onde*** (consiste em uma expressão envolvendo uma condição).|
|`BETWEEN`  | ***Entre*** (utilizado para consultar valores entre um range.|
|`DISTINCT` | ***Distinto*** (utilizado para consultar valores distintos.|
|TB         | Abreviação de Tabela.|
|Var        | Por vezes uma coluna também é chamada de variável|
|ROWS       | Tradução: ***linhas***.|
|`SCHERMAS` | Representa o ***Esquema*** da tabela (esquema de segurança, acesso, estrutura etc).|
|`FETCH`    | Tradução: ***Buscar***.|
|`*`        | Utilizamos ***Asterisco*** para selecionar tudo, ex: todas as colunas do banco de dados.|
|`%`        | Caracter ***%*** coringa utilizado para indicar a posição (no início, em qualquer posição ou no final) que um conteúdo será procurado no valor string do campo especificado.|
|`_`        | Indica o número de caracteres envolvidos na pesquisa.|
|`NULL`     | ***Nulo*** ou ***Missing*** representado por [null].|
|`UPDATE`   | ***Atualizar*** ou substituir.|
|`COMMIT`   | Para salvar o que foi feito, tradução cometer, praticar, enviar etc.|
|`TRUNCATE` | Truncar, na pratica excluir todas as linhas da tabela e manter o cabeçalho.|
|`PRIMARY KEY, PK`  | ***Chave Primária*** (Identificador "id" de um conjunto de dados.|
|`FOREING KEY, FK`  | ***Chave Estrangeira*** É a coluna em outras tabelas que fazem referencia a uma PK.|
|`COMPOSITE KEY`    | Existem ***Chaves Compostas*** com duas ou mais colunas.|

**Fonte:** [Funções SQL)](https://www.concepcaoweb.com.br/site/glossario-de-funcoes-sql/)

### Funções Estatísticas:
|**Função** | **Descrição** |
|--------------------|------------------------------------------------------------------------------------|
|`AVG()`             | Retorna o valor médio de uma coluna específica.|
|`BINARY_CHECKSUM()` | O valor do BINARY_CHECKSUM computado sobre uma linha ou uma tabela ou sobre uma lista de expressões. BINARY CHECKSUM é usada para detectar alterações em uma linha ou uma tabela.|
|`CHECKSUM()`        | O valor de CHECKSUM computado sobre uma linha ou uma tabela, ou sobre uma lista de expressões. CHECKSUM é usada para construir índices de hash.|
|`CHECKSUM_AGG()`    | O valor de CHECKSUM de um grupo. Valores nulos são ignorados.|
|`COUNT()`           | Retorna o número de linhas.|
|`COUNT_BIG()`       | Igual ao COUNT mas o COUNT_BIG sempre retorna um tipo de dados bigint.|
|`MAX()`             | Retorna o valor máximo de uma coluna específica.|
|`MIN()`             | Retorna o valor mínimo de uma coluna específica.|
|`SUM()`             | Retorna a soma de uma coluna específica.|
|`STDEV()`           | Desvio padrão de todos os valores.|
|`STDEVP()`          | Desvio padrão da população.|
|`VAR()`             | Variância estatística de todos os valores.|
|`VARP()`            | Variância estatística de todos os valores da população.|

**Fonte:** [Funções SQL)](https://www.concepcaoweb.com.br/site/glossario-de-funcoes-sql/)


### Funções para manipulação de strings:
|**Função**  | **Descrição**  |
|--------------------|------------------------------------------------------------------------------------|
|`ASCII(string)` | Pega o valor em ASCII da string.|
|`CHAR(integer)` | Troca inteiro do ASCII em um caracter.|
|`LEN(string)`   | Identifica o comprimento de uma expressão em caracteres.|
|`LOWER(string)` | Converte uma string uppercase para lowercase.|
|`LTRIM(string)` | Retorna os espaços em branco.|
|`PATINDEX (posição, expressão)`  |Retorna a posição de uma string dentro de um texto. Se não encontrar, retorna zero.|
|`REPLICATE (string, integer)`  | Repete N vezes um caractere especificado.|
|`REVERSE(string)`  | Retorna o inverso de uma expressão.|
|`RTRIM (string)`  | Remove os espaços em branco à direita de uma string.|
|`SPACE(integer)`  | Retorna o número de espaços em branco informados no parâmetro.|
|`STUFF(string texto, X, Y, string texto_a_inserir)`  | Apaga da string “texto” os y caracteres a partir da posição x e os substitui por “texto à inserir”.|
|`SUBSTRING (string texto, posição_inicial, tamanho)` | Retorna uma string com o comprimento definido em “tamanho” extraída da string “texto”, a partir da “posição inicial”.|
|`UPPER(string)`  | Retorna string em maiúsculas .|

**Fonte:** [Funções SQL)](https://www.concepcaoweb.com.br/site/glossario-de-funcoes-sql/)


### Funções de manipulação de data/hora:
|**Função**  | **Descrição**  |
|-------------------------------------------|-------------------------------------------------------------|
|`Year`       							    | yy, yyyy.|
|`Month`      							    | mm, m.|
|`Dayofyear`   							    | dy, y.|
|`Day`         							    | dd, d.|
|`Week`        							    | wk, ww.|
|`Hour`									    | hh.|
|`Minute`	     							| mi, n.|
|`Second`     								| ss, s.|
|`Millisecond`								| ms.|
|`DATEADD (parte, número, data)` 	        | Adiciona um valor a parte de uma data.|
|`DATEDIFF (parte, data inicial, data final)` | Subtrai a data inicial da data final, indicando o resultado na unidade definida em “parte".|
|`GETDATE()` 							    | Retorna a data atual do sistema.|
|`DATENAME (parte, data)`                   | Retorna o nome da parte de uma data.|
|`DATEPART(parte, data)`                    | Retorna a parte de uma data.|

**Fonte:** [Funções SQL)](https://www.concepcaoweb.com.br/site/glossario-de-funcoes-sql/)


### Funções de Sistema:
|**Função**  | **Descrição**  |
|-------------------------------------------|-------------------------------------------------------------|
|`CAST(expressão as datatype`) | Converte uma expressão no datatype informado.|
|`COL_LENGTH(nome_da_tabela, nome_da_coluna)` | Retorna o tamanho da coluna.|
|`COL_NAME(id_da_tabela, id_da_coluna)` | Retorna o nome da coluna.|
|`DATALENGTH(expressao)`       | Retorna o numero de bytes usados para armazenar a expressão.|
|`DB_ID(nome_do_banco)`        | Retorna o ID do banco informado.|
|`DB_NAME(id_do_banco)`        | Retorna o nome do banco.|
|`HOST_ID()` | Retorna a ID da estação que está acessando o SQL Server.|
|`HOST_NAME()` 				 | Retorna o nome da estação que está acessando o SQL Server.|
|`IDENT_INCR(nome_da_tabela_ou_view)` | Retorna o valor incrementado.|
|`IDENT_SEED(tabela_ou_view)`  | Retorna o valor inicial da coluna.|
|`INDEX_COL(nome_da_tabela, indice_id, chave_id)` | Retorna o nome da coluna que participa do índice.|
|`ISNULL(expressão, valor)`    | se a expressão for null, troca pelo valor especificado.|
|`ISNUMERIC(expressão)`        | Retorna 1 se a expressão for numérica e 0 se não for.|
|`NEWID()`                    | Retorna um novo valor do tipo uniqueidentifier.|
|`NULLIF(expressão_1, expressão_2)` | Retorna nulo se as duas expressões forem equivalentes. Se não forem, retorna à primeira expressão.|
|`OBJECT_ID(nome_do_objeto)`   | Retorna o ID de um objeto, a partir do nome fornecido.|
|`OBJECT_NAME(ID_do_objeto)`   | Retorna o nome do objeto, a partir do ID fornecido.|
|`PARSENAME(objeto, parte)`    | Retorna a parte do nome de um objeto, desde que tenha sido qualificado.|
|`STATS_DATE(tabela_id, indice_id)` | Retorna a data em que as estatísticas do índice foram atualizadas.|
|`SUSER_SID(nome_do_usuario)`  | Retorna o ID do usuário informado.|
|`SUSER_NAME(usuario_id)`      | Retorna o id do usuário no servidor. O argumento é opcional.|
|`SUSER_SNAME(id_do_usuario)`  | Retorna o nome do usuário informado. Se nenhum ID de usuário for passado para a função, retorna o nome do usuário logado.|
|`USER_ID(nome_do_usuario)`    | Retorna o ID do usuário informado para o BD em uso.|
|`USER_NAME(id_do_usuario)`    | Retorna o usuário conectado ao BD.|

**Fonte:** [Funções SQL)](https://www.concepcaoweb.com.br/site/glossario-de-funcoes-sql/)


### Funções Matemáticas:
|**Função**  | **Descrição**  |
|-------------------------------------------|-------------------------------------------------------------|
|`ABS(número)` 		 | Retorna o valor absoluto do número.|
|`ACOS(float)` 		 | Retorna o arco-cosseno do número informado.|
|`ASIN(float)` 		 | Retorna o arco-seno do número informado.|
|`ATAN(float)` 		 | Retorna o arco-tangente do número informado.|
|`ATN2 (Float expressao_1, float expressao_2)` | Arco-tangente do valor definido pela divisão da primeira expressão pela segunda.|
|`CEILING(número)`     | Retorna o menor inteiro que seja maior ou igual ao número informado.|
|`COS(float)` 		 | Retorna o cosseno do número informadov
|`COT(float)` 		 | Retorna a cotangente do número informado.|
|`DEGREES(número)`     | Converte radianos para graus.|
|`EXP(float)` 		 | Retorna o exponencial de um número especificado.|
|`FLOOR(número)` 	     | Retorna o maior inteiro que seja menor ou igual ao número informado.|
|`LOG(float)` 		 | Retorna o logaritmo natural do número informado.|
|`LOG10(float)` 		 | Retorna o logaritmo base 10 do número informado.|
|`PI()` 				 | Retorna o valor de PI 3.1415926535897931.|
|`POWER(número, potência)` | Retorna o valor elevado à potência informada.|
|`RADIANS(número)` 	 | Converte graus para radianos.|
|`RAND(expressão)` 	 | Um número aleatório entre 0 e 1. Expressão é opcional e será usada como semente da cadeia pseudoaleatória.|
|`ROUND(número, precisão, arredonda_ou_trancar)` | Arredonda ou tranca o número fornecido de acordo com a precisão informada. Se o terceiro parâmetro não for passado para a função, o número é arredondado. Se quiser que o número seja truncado, deve-se fornecer o valor 1.|
|`SIGN(numero)` 		 | Retorna sinal positivo, negativo ou zero do número.|
|`SIN(float)` 		 | Retorna o seno do ângulo especificado.|
|`SQRT(float)` 	     | Retorna a raiz quadrada de um número.|
|`TAN(float)` 	     | Retorna a tangente de um número informado.|
|`SQUARE(float)` 	     | Retorna o quadrado de um número.|
|`OFFSET 2` 			 | Permite pular os dois primeiros registros de um consulta.|

**Fonte:** [Funções SQL)](https://www.concepcaoweb.com.br/site/glossario-de-funcoes-sql/)

### Dicas:
|**Função**  | **Descrição**  |
|--------------------------------|----------------------------------------------------------|
|`#`                               | Para adicionar um comentário basta utilizar # antes.|
|Começa com `/*` e terminar com `*/` | Para adicionar um texto/comentário no SQL.|
|`;`                               | o ponto e virgula encerra um comando.|



## **Comandos para Consulta SQL.**

Ver todas as colunas e todas as linhas de uma TB

    SELECT * FROM schemas."TB";

Se o banco não possui schemas, chamamos somente a TB

    SELECT * FROM TB;

Ver todas as colunas e todas e somente as 10 primeiras linhas

    SELECT * FROM schemas."TB" limit 10;

ou

    SELECT * FROM schemas."TB" fetch first 10 rows only;

Ver uma coluna de uma TB e mostrar as 10 primeiras linhas

    SELECT var FROM schemas."TB" limit 10;

Filtrar linhas duplicadas 

> Obs: quando temos uma TB com chave primária provavelmente não teremos valores repetidos.

    SELECT DISTINCT * FROM schemas."TB";

Ver os valores únicos de uma coluna especifica

    SELECT DISTINCT var FROM schemas."TB";

Filtrar valores de uma TB ou coluna

    SELECT * FROM schemas."TB" WHERE var >=100;

Contar linhas da TB

    SELECT COUNT(*) FROM schemas."TB";

Filtrar dados com uma condição especifica

SELECT * FROM schemas."TB" WHERE var =10;

    SELECT * FROM schemas."TB" WHERE var ='status';

Filtrar dados com duas condições especificas

AND (&)

    SELECT * FROM schemas."TB" WHERE var =10 AND var2='status';

OR (ou)

    SELECT * FROM schemas."TB" WHERE var =10 OR var2='status';

Filtrar dados com duas condições especifica com a função BETWEEN

> Obs: o between utiliza o inclusive, no exemplo abaixo os valores 10 e 20 serão reportados.

    SELECT * FROM schemas."TB" WHERE var BETWEEN 10 and 20;

Filtrar dados com operador LIKE, retorna somente as linhas com o status

> OBS: o interessante deste operador é que pode buscar por uma parte do status.

    SELECT * FROM schemas."TB" WHERE var LIKE 'status';

Ex status: 'status baixo', 'status alto', 'status muito alto')

> **%alto**  irá mostrar todas as linhas que possua caracteres antes da palavra alto.
> **alto%**  irá mostrar todas as linhas que possua caracteres após a palavra alto.
> (ou seja, nada!)
> **%alto%**  irá mostrar todas as linhas que contenha a palavra alto entre caracteres.
> palavra alto

    SELECT * FROM schemas."TB" WHERE var LIKE '%alto';

Filtrar dados com operador IN

> Equivalente a var=20 OR var=30 OR var=40 OR var=50

    SELECT * FROM schemas."TB" where var IN(20,30,40,50);

Verificar missings na TB ou coluna

    SELECT * FROM schemas."TB" where var is null;

Verificar valores sem missings

    SELECT * FROM schemas."TB" where var is not null;

Ordenar consulta

> De forma Crescente

    SELECT * FROM schemas."TB" order by var1;

ou

    SELECT * FROM schemas."TB" order by var1, var2;

> De forma Decrescente

    SELECT * FROM schemas."TB" order by var1 des;

 ou

    SELECT * FROM schemas."TB" order by var1 des, var2 des;

Valores valores mínimos, máximos, média, contagem e soma

    SELECT min(var) FROM schemas."TB";
    SELECT max(var) FROM schemas."TB";
    SELECT avg(var) FROM schemas."TB";
    SELECT count(*) FROM schemas."TB";
    SELECT sum(*)  FROM schemas."TB";

    SELECT min(var), avg(var), max(var), count(*), sum(*) FROM schemas."TB";

Ver média dos dados agrupados pela coluna 2

    SELECT avg(var1), var2 FROM schemas."TB" group by(var2);

Ver valores  da consulta arredondados arredondados 

    SELECT round(avg(var1)) FROM schemas."TB";

Consultar valores de duas variáveis que estão em TBs diferentes 

> Obs: as TBs devem estar relacionadas pelas chaves.

    SELECT T1.var1, T2.var2
    FROM schemas."TB1" T1, schemas."TB2" T2
    WHERE T1.id = T2.id
    GROUP by T2.var3;

Consultar  qualquer string que inicia com o nome Juca.

    LIKE 'Juca%';

Consultar qualquer string que termina com o nome  Silva.

    LIKE '%Silva';

Consultar qualquer string que contenha Santos em qualquer posição.

    LIKE '%Santos%';

Consultar qualquer String de dois caracteres, que contenha na primeira letra A na primeira posição.

    LIKE 'A_';

Consultar qualquer String de dois caracteres, que contenha a letra A na segunda posição.

    LIKE '_A';

Consultar  qualquer String de três caracteres, onde  a letra seja A apareça na segunda posição.

    LIKE '_A_';

Consultar qualquer string que contenha a letra A na penúltima posição.

    LIKE '%A_';

Ver qualquer string que contenha a letra A na segunda posição.

    LIKE '_A%';

Consultar qualquer string com exatamente três caracteres.

    LIKE '___';

Consultar qualquer string com pelo menos três caracteres.

    LIKE '___%';

Consultar qualquer string que contenha  o  caractere " em qualquer posição.

    LIKE '%''%';

Consultar qualquer string que comece por ab%cd.

    LIKE 'ab\%cd%';

Consultar qualquer string que comece por ab\cd.

    LIKE 'ab\\cd%';

Consultar qualquer string que não iniciem com o nome Juca.

> NOT LIKE é o oposto de LIKE

    LIKE 'Juca%'

Juntar consultar ou pedir duas ou mais consultar ao mesmo tempo

    SELECT * FROM TB WHERE id=5
    UNION
    SELECT * FROM TB WHERE id=6;

Ver período disponível dos dados 

> Exemplo no datalake [Base dos Dados](https://console.cloud.google.com/bigquery?ref=https:%2F%2Fbasedosdados.org%2F&project=astute-quarter-301119&pli=1&ws=!1m0)
> Aqui queremos saber quantos períodos de tempo, ou seja, anos tem disponível na TB br_ibge_pib.municipio

    SELECT DISTINCT ano FROM `basedosdados.br_ibge_pib.municipio`;

Ver quantos ids temos por ano ex:

> Exemplo Base dos  Dados

    SELECT count(id_municipio), ano FROM `basedosdados.br_ibge_pib.municipio` group by(ano);

Consultar utilizando o OFFSET pulando as duas primeiras linhas

    SELECT * FROM TB OFFSET 2;
    
Consultar a média utilizando o comando GROUP BY

    SELECT DB, AVG(var1) FROM TB GROUP BY var2;

Exemplo pedindo a média utilizando o comando GROUP BY com o comando HAVING

    SELECT DEPARTAMENTO, AVG(SALARIO) FROM FUNCIONARIOS GROUP BY DEPARTAMENTO HAVING AVG(SALARIO)>1500;

> Exemplo:
![img3 ](https://i.ibb.co/YfCwcJ5/img3.png "img3 ")
  
**SUBQUERIES:** Realização de consultas baseadas em uma lista o outra consulta, ou seja, uma consulta dentro de uma consulta.
**IN:** Se desejamos que o retorno da primeira consulta esteja presente no retorno da segunda consulta.
**NOT IN:** ou que não esteja no retorno da segunda consulta.

Exemplo utilizando **IN**: Queremos a lista de funcionarios dos departamentos com a média salarial acima de 1500.

    SELECT NOME FROM FUNCIONARIOS WHERE DEPARTAMENTO IN 
    (SELECT DEPARTAMENTO FROM FUNCIONARIOS GROUP BY DEPARTAMENTO HAVING AVG(SALARIO)>1500);

> Exemplo:

![img4 ](https://i.ibb.co/LppyXPC/img4.png "img4 ")


## **Comando para manipulação de dados:**

Fazer replace (substituir) NAs variáveis (colocar nulo onde está NA)
> Obs: o commit é para confirmar o comando

    UPDATE schemas."TB" set var = null where var = 'NA';
    commit;

Deletar todas as linhas de uma TB
> OBS: o cabeçalho com nome das variáveis não será deletado

    TRUNCATE schemas."TB";

Deletar todas as linhas de uma TB e as TBs relacionadas

    TRUNCATE CASCATE schemas."TB";
    commit;

Deletar a TB inteira

    DELETE schemas."TB";

Dropar linhas a partir de uma condição

    DELETE FROM schemas."TB" where var ='status';

Deletar banco de dados inteiro

    DROP DATABASE`banco`;

Inserir dados manualmente na TB 

    INSERT INTO schemas."TB"(var1, var2, var3) VALUES (10, 35, 50);

Converter temporariamente o tipo de uma variável
> Ex: suponha que a var1 é uma string que contém números

    SELECT * FROM schemas."TB" WHERE cast(var1 as integer)=2;

Atualizar uma linha numérica ou fazer replace

    UPDATE TB SET var = var*10 WHERE id=1;

Atualizar todas as linhas de uma coluna
 > Desabilitar o safe update

    SET SQL_SAFE_UPDATES = 0; 
        UPDATE TB SET var = var*10;

> Habilitar o safe update

    SET SQL_SAFE_UPDATES = 1; 

Arredondar valores com duas casas

    UPDATE TB SET var = ROUND(var, 2);

## **União entre Tabelas**

Para facilitar o entendimento, a Figura 1 traz uma representação gráfica, baseada na Teoria dos Conjuntos, muito conhecida na matemática. Nessa imagem, temos a representação de duas TBs (A e B) e o resultado esperado por cada tipo de join (a área em vermelho representa os registros retornados pela consulta).

**Figura 1** – Representação gráfica dos _joins._

![img5 ](https://i.ibb.co/z7s1888/img5.png "img5")
**Fonte** [(SQL JOINS)](https://www.devmedia.com.br/sql-join-entenda-como-funciona-o-retorno-dos-dados/31006)


**INNER JOIN:**

- Também conhecido como o Join padrão;
- Gera o produto cartesiano entre as TBs;
- Combina todas as linhas da primeira TB com todas as linhas da segunda, que satisfaçam as condições das chaves;
> Exemplo:

    SELECT * FROM PESSOAS INNER JOIN VEICULOS ON PESSOAS.CPF = veiculos.CPF;
    
> Ou utilizando apelidos

    SELECT * FROM PESSOAS p INNER JOIN VEICULOS v ON p.CPF = v.CPF;

![img6 ](https://i.ibb.co/wzW73YN/img6.png "img6" )


**EQUI JOIN:**

- Similar ao Inner join, porém, utilizado apenas quando os nomes das chaves nas duas TBs são idênticos.
- Equi Join é uma forma simplificada do Inner join;
> Exemplo:
> 
    SELECT * FROM PESSOAS JOIN VEICULOS USING (CPF);

![img6 ](https://i.ibb.co/wzW73YN/img6.png.png "img6" )

**NON-EQUI JOIN: Juntando tabelas sem um campo em comum**
- Na TB SALARIOS temos a faixa de salários para Analista Jr e Analista Sênior, o comando irá identificar em qual faixa de salário a qual a  PESSOA se encaixa.
> Exemplo:

     SELECT P.NOME, P.SALARIO, S.FAIXA FROM PESSOAS P INNER JOIN SALARIOS S ON P.SALARIO 
     BETWEEN S.INICIO AND S.FIM;

![img8 ](https://i.ibb.co/ZhXpqM4/img8.png "img8" )

**LEFT JOIN: também conhecido como OUTER JOIN ou LEFT OUTER JOIN**
- Une as linhas que não satisfazem a condição de união;
- Left: linhas da primeira TB cujo o campo de condição não satisfaçam a união de TBs;
> Exemplo:

    SELECT * FROM PESSOAS LEFT JOIN VEICULOS ON PESSOAS.CPF = VEICULOS.CPF;

![img9 ](https://i.ibb.co/KLYWB11/img9.png "img9" )

**RIGHT JOIN: também conhecido como OUTER JOIN ou RIGHT OUTER JOIN**

- Une as linhas que não satisfazem a condição de união
- Right: linhas da primeira TB cujo o campo de condição não satisfaçam a união de TBs;
> Exemplo:

    SELECT * FROM PESSOAS RIGHT JOIN VEICULOS ON PESSOAS.CPF = VEICULOS.CPF;
![img10 ](https://i.ibb.co/CVjjBK6/img10.png"img10" )


**FULL JOIN: também conhecido como FULL OUTER JOIN.**
- O Full join é a combinação do Left join e Right join;
- No MY SQL não tem o full join é preciso fazer um UNION
> Exemplo: NO MY SQL

    SELECT * FROM PESSOAS LEFT JOIN VEICULOS ON PESSOAS.CPF = VEICULOS.CPF
    UNION
    SELECT * FROM PESSOAS RIGHT JOIN VEICULOS ON PESSOAS.CPF = VEICULOS.CPF;

![img11 ](https://i.ibb.co/xGH7f8t/img11.png"img11" )

**SELF JOIN:**
- Consiste na união da TB com ela mesma;
- Esse comando da dois apelidos para mesma TB;
> Exemplo:

    SELECT A.NOME, B.NOME AS INDICADO_POR FROM PESSOAS A JOIN PESSOAS B ON A.INDICADO = B.CPF

![img12 ](https://i.ibb.co/M5NQJL2/img12.png"img12" )



## **View**

view ou visões são definidas como uma TB virtual composta por linhas e colunas de dados vindos de TBs relacionadas em uma query (um agrupamento de SELECT’s, por exemplo). As linhas e colunas da view são geradas dinamicamente no momento em que é feita uma referência a ela.

Ao criarmos uma view, podemos filtrar o conteúdo de uma TB a ser exibida, já que a função da view é exatamente essa: filtrar TBs, servindo para agrupá-las, protegendo certas colunas e simplificando o código de programação.

É importante salientar que, mesmo após o servidor do SQL Server ser desligado, a view continua “viva” no sistema, assim como as TBs que criamos normalmente. As views não ocupam espaço no banco de dados.

**Vantagens das Views**

Temos muitos motivos e vantagens para usarmos views em nossos projetos que podem fazer a diferença:

* Economia de espaço em discos para representar as mesmas informações, por exemplo TBs ordenadas por alguma regra;
* Facilidade de manutenção de expressões SQL;
* Reuso: as views são objetos de caráter permanente. Pensando pelo lado produtivo isso é excelente, já que elas podem ser lidas por vários usuários simultaneamente;
* Segurança: as views permitem que ocultemos determinadas colunas de uma TB. Para isso, basta criarmos uma view com as colunas que acharmos necessário que sejam exibidas e as disponibilizarmos para o usuário;
* Simplificação do código: as views nos permitem criar um código de programação muito mais limpo, na medida em que podem conter um SELECT complexo. Assim, criar views para os programadores a fim de poupá-los do trabalho de criar SELECT’s é uma forma de aumentar a produtividade da equipe de desenvolvimento;

**Alguns detalhes**

* Visões não armazenam dados;
* Por não armazenar dados elas não fazem parte do modelo lógico dos bancos;
* Elas podem ser excluídas sem perder informações do banco;

> Exemplo:
> > Visão A: Salário >= 1500;
> Visão B: Salário <= 2500;

![img13 ](https://i.ibb.co/ZfdyxBp/img13.png"img13" )

Criando uma view

    CREATE VIEW salarios_1500 AS SELECT * FROM NOME WHERE SALARIO >=1500;

Chamar uma view

    SELECT * FROM salarios_1500;

Excluir uma view

    DROP VIEW SALARIO _1500;


## **Controle de acesso ao SQL**

Para maior detalhamento:
[Permissões : GRANT / REVOKE : SQL Server : Controle de Acesso aos Dados (webmundi.com)](https://www.webmundi.com/banco-de-dados/principais-comandos-ms-sql-server-parte-4-controle-de-acesso-aos-dados/)

Níveis de segurança configuráveis no SQL
![img14 ](https://i.ibb.co/Zm5nDMn/img14.png"img14" )


**Linguagem de controle de dados:**
| **Função**  |         **Descrição**                     |
|-------------|-------------------------------------------|
|CREATE USER  | Utilizado para criar um usuário.          |
|DROP USER    | Utilizado para excluir um usuário.        |
|GRANT        | Habilita o acesso ao banco, TBs, etc. |
|REVOKE       | Revoga acessos aos dados.                 |


Uma boa prática, é para um mesmo usuário fornecer acesso em diferentes níveis para quando ele está no computador local ou quando ele está acessando ao banco de dados via outros IPs, ou seja, de uma rede externa.

> Exemplo: 
> Podemos criar um usuário com permissão de somente para ler os dados se  ele não tiver utilizando o computador local, se caso alguém roube sua senha senha não conseguirá apagar o banco de dados.

**Gerenciar usuário e acesso:**

Criar um usuário: onde: local = endereço na internet dado pelo ip ex:111.222.333.444

    CREATE USER ‘usuario1’@’111.222.333.444’ IDENTIFIED BY ‘senha’;

Criar um usuário: para usar a partir de uma maquina local

    CREATE USER ‘usuario1’@’localhost’ IDENTIFIED BY ‘senha’;

Criar um usuário: para qualquer endereço ip

    CREATE USER ‘usuario1’@’%’ IDENTIFIED BY ‘senha’;

Fornecendo acesso de adm(ALL)para o banco_de_dados1

    GRANT ALL ON BANCO_DE_DADOS1.* TO ‘usuario1’@’localhost’;

Fornecendo acesso somente ler dados (SELECT) no banco_de_dados1

    GRANT SELECT ON BANCO_DE_DADOS1.* TO ‘usuario1’@’localhost’;

Fornecendo acesso somente ler dados (SELECT) no banco_de_dados1 somente para TB1

    GRANT SELECT ON BANCO_DE_DADOS1.TB1 TO ‘usuario1’@’localhost’;

Fornecendo acesso para inserir dados (INSERT) no banco_de_dados1 somente na TB1

    GRANT INSERT ON BANCO_DE_DADOS1.TB1 TO ‘usuario1’@’localhost’;

Remover acesso de inserir dados na TB1 do banco_de_dados1

    REVOKE INSERT ON BANCO_DE_DADOS1.TB1 FROM ‘usuario1’@’localhost’;

Remover acesso de ver dados na TB1 do banco_de_dados1

    REVOKE SELECT ON BANCO_DE_DADOS1.TB1 FROM ‘usuario1’@’localhost’;

Remover acesso total ao banco_de_dados1

    REVOKE ALL ON BANCO_DE_DADOS1.* FROM ‘usuario1’@’localhost’;

Excluir usuário

    DROP USER ‘usuario1’@’localhost’;

Listar usuários do servidor

    SELECT USER FROM mysql.user;

Ver privilégios de usuários

    SHOW GRANTS FROM ‘usuario1’@’localhost’;


## **Transações ACID**

O que é uma transação?
Uma transação é uma sequência de operações executadas como uma única unidade lógica de trabalho.

**ACID:** é um conceito que se refere às quatro propriedades de transação de um sistema de banco de dados:
||  |
|-------|------------------|
|**A**  |**A**tomicidade   |
|**C**  |**C**onsistência  |
| **I** |**I**solamento    |
| **D** | **D**urabilidade |

**Atomicidade:** Em uma transação envolvendo duas ou mais partes de informações discretas, ou a transação será executada totalmente ou não será executada, garantindo assim que as transações sejam atômicas.

_Ex: transferência de dinheiro de uma conta para outra._

**Consistência:**  A transação cria um estado válido dos dados ou em caso de falha retorna todos os dados ao seu estado antes que a transação foi iniciada.

> Exemplo:  
> suponha uma TB de contas bancárias vinculada a uma TB  de clientes, a consistência diz respeito a cada conta bancária possuir um cliente cadastrado e relacionado com a conta.

**Isolamento:** Uma transação em andamento mas ainda não validada deve permanecer isolada de qualquer outra operação, ou seja, garantimos que a transação não será interferida por nenhuma outra transação concorrente.

**Durabilidade:** Dados validados são registados pelo sistema de tal forma que mesmo no caso de uma falha e/ou reinício do sistema, os dados estão disponíveis em seu estado correto.

* Geralmente as verificações de transações são feitas após a normalização dos dados.

**Linguagem de Transação:**

Iniciar uma transação

    STAR TRANSACTION;

Gravar uma transação

    COMMIT;

Anular uma transação

    ROLLBACK;

> Exemplo: 
> Ver engines

    SHOW ENGINES;

Criar uma TB transasional

> Obs: o engine irá ativar o transaction

    CREATE TABLE contas_bancarias
    (
    id int unsigned not null auto_increment,
    
    titular varchar(45) not null,
    
    saldo double not null,
    
    PRIMARY KEY (id)
    
    ) engine = InnoDB;

Adicionando dados nas TBs

    INSERT INTO contas_bancarias (titular, saldo) VALUES ('André', 1000);
    INSERT INTO contas_bancarias (titular, saldo) VALUES ('Carlos', 2000);

Fazer consulta

    SELECT * FROM contas_bancarias;

Fazer uma modificação e voltar atrás

    start transaction;
    UPDATE contas_bancarias SET saldo = saldo - 100 WHERE id = 1;
    UPDATE contas_bancarias SET saldo = saldo + 100 WHERE id = 2;
    rollback;

Fazer uma modificação e gravar

    start transaction;
    UPDATE contas_bancarias SET saldo = saldo - 100 WHERE id = 1;
    UPDATE contas_bancarias SET saldo = saldo + 100 WHERE id = 2;
    commit;


## **Store Procedures**

**O que é um procedimento armazenado?**

Um procedimento armazenado é um código SQL preparado que você pode salvar, para que o código possa ser reutilizado continuamente.

Portanto, se você tem uma consulta SQL que escreve repetidamente, salve-a como um procedimento armazenado e, em seguida, apenas chame-a para executá-la.

Você também pode passar parâmetros para um procedimento armazenado, de modo que o procedimento armazenado possa agir com base nos valores dos parâmetros que são transmitidos.

Store procedures são um complemento a transações.

**Vantagens**

* Centralização (padronização das consultas);
* Segurança (Restringir a interação dos usuários com o banco de dados);
* Performance e Velocidade;
* Suporte a transações (será garantido que os códigos irão funcionar, ou caso ocorra erros nenhuma ação será salva de forma inconsistente)

**Desvantagens**

* Dependendo do modo que for executado as Store Procedures pode reduzir a performance e a velocidade;


**Gerenciando Stored Procedures:**

Criando uma stored procedure

    CREATE PROCEDURE nome;

Invocando uma Stored Procedure

    CALL nome
    EXECUTE nome;

Excluindo uma stored procedure

    DROP PROCEDURE nome;


## **Triggers (Gatilhos)**

**O que são Triggers?

O termo trigger (gatilho em inglês) define uma estrutura do banco de dados que funciona, como o nome sugere, como uma função que é disparada mediante alguma ação. Geralmente essas ações que disparam os triggers são alterações nas TBs por meio de operações de inserção, exclusão e atualização de dados (insert, delete e update).

Um gatilho está intimamente relacionado a uma TB, sempre que uma dessas ações é efetuada sobre essa TB, é possível dispará-lo para executar alguma tarefa.

Exemplos de aplicações: horários programados para uma determinada tarefa; um produto esgotando no estoque; um valor que foi atingido; verificar se um produto está acabando no estoque; verificações programadas.

**Vantagens**

* Centralização;
* Segurança;
 * Performance e Velocidade;
* Maior autonomia para o banco de dados

**Gerenciando Triggers:**

Criar um Trigger

    CREATE TRIGGER nome tipo ON TB

Excluindo um trigger

    DROP TRIGGER nome

Executar um código ANTES (BEFORE) que um registro seja inserido em uma determinada TB.

    BEFORE INSERT;

Executar um código ANTES (BEFORE) que um determinado registro seja atualizado na TB.

    BEFORE UPDATE;

Executar um código ANTES (BEFORE) que um determinado registro seja deletado da TB.

    BEFORE DELETE;

Executar um código APÓS (AFTER) que um registro seja inserido em uma determinada TB.

    AFTER INSERT;

Executar um código APÓS (AFTER) que um determinado registro seja atualizado na TB.

    AFTER UPDATE;

Executar um código APÓS (AFTER) que um determinado registro seja deletado da TB.

    AFTER DELETE;

**Prática de Stored Procedures & Triggers**

Criar uma TB de exemplo

    CREATE TABLE pedidos
    (
    id int unsigned not null auto_increment,
    descricao varchar(100) not null,
    valor double not null default '0',
    pago varchar(3) not null default 'Não',
    PRIMARY KEY (id)
    );

Inserindo valores na TB

    INSERT INTO pedidos (descricao, valor) VALUES ('TV', 3000);
    INSERT INTO pedidos (descricao, valor) VALUES ('Geladeira', 1400);
    INSERT INTO pedidos (descricao, valor) VALUES ('DVD Player', 300);
Criar Stored Procedures que de tempos em tempos para limpar os pedidos não pagos

> Obs: dá para fazer isso bem fácil via menu

    DELIMITER $$
    CREATE PROCEDURE limpa_pedidos()
    BEGIN
    SET SQL_SAFE_UPDATE =0;
    DELETE FROM pedidos WHERE pago = 'Não';
    END $$
    DELIMITER;

Realizar uma consulta e realizar um call da procedure

    SELECT * FROM pedidos
    CALL limpa_pedidos();

**EXEMPLO 2:** 
Queremos que toda vez que a TB estoque receba um novo produto queremos que nesse momento seja feito uma chamada para limpar os pedidos da TB pedidos

Criar nova TB

    CREATE TABLE estoque
    (
    id int unsigned not null auto_increment,
    descricao varchar(50) not null,
    quantidade int not null,
    PRIMARY KEY (id)
    );

#Criar trigger

    CREATE TRIGGER gatilho_limpa_pedidos
    BEFORE INSERT  # Definir o tipo de trigger
    ON estoque  # Na TB estoque queremos que para cada linha
    FOR EACH ROW  # para cada linha execute o limpa_pedidos
    CALL limpa_pedidos();

Consultar quantos registros temos na TB (nenhum)

    SELECT * FROM pedidos;

Inserir novos registros

    INSERT INTO pedidos (descricao, valor) VALUES ('TV', 3000);
    INSERT INTO pedidos (descricao, valor) VALUES ('Geladeira', 1400);
    INSERT INTO pedidos (descricao, valor) VALUES ('DVD Player', 300);

Consultar quantos registros temos na tabela

    SELECT * FROM pedidos;

Inserindo produtos na TB estoque e consultando (e o gatilho limpa_pedidos foi acionado invocando a triggers limpa pedidos)

    INSERT INTO estoque (descricao, quantidade) VALUES ('Fogão', 5);
    SELECT * FROM pedidos;
    SELECT * FROM estoque;

Fazendo um update em pedidos

    UPDATE pedidos SET pago = 'Sim' WHERE id = 8;
    SELECT * FROM pedidos;

Inserindo novos dados vamos ver que só irá permanecer os pedidos pagos

    INSERT INTO estoque (descricao, quantidade) VALUES ('Forno', 3);
    SELECT * FROM pedidos;
    SELECT * FROM estoque;


## **Resumo**

**Complementos & Especificações**

Diferentes tipos: Categorias de instruções (Transact-SQL)

* Data Manipulation Language (DML) 
* Data Definition Language (DDL)
* Data Control Language (DCL)
* Transactional Control Language (TCL)

**DML (Linguagem de Manipulação de Dados)** É um conjunto de instruções usada nas consultas e modificações dos dados armazenados nas TBs do banco de dados.

`SELECT` Seleção de uma ou várias linhas ou colunas de uma ou várias TBs
`INSERT` Inserir dados a uma ou mais TBs no banco de dados
`UPDATE` Atualizar dados de uma ou mais TBs no banco de dados
`DELETE` Excluir dados de uma ou mais TBs no banco de dados
`MERGE`  Unir TBs
`BULK INSET` Importa um arquivo de dados em uma TB ou exibição do banco de dados em um formato especificado pelo usuário

**DDL (Linguagem de Definição de Dados**) É um conjunto de instruções usado para criar e modificar as estruturas dos objetos armazenados no banco de dados.

`ALTER`  modificar a definição de entidades existentes. Use `ALTER TABLE` para adicionar uma nova coluna a uma TB ou use `ALTER DATABASE` para definir opções do banco de dados.
`CREATE`  Use instruções `CREATE` para definir novas entidades. Use `CREATE TABLE` para adicionar uma nova TB em um banco de dados.
`DROP` Use instruções `DROP` para remover entidades existentes. Use `DROP TABLE` para remover uma TB de um banco de dados.
`DISABLE TRIGGER` Desabilita uma Trigger DML, DDL ou de logon.
`ENABLE TRIGGER` Habilita uma Trigger DML, DDL ou de logon.
`TRUNCATE TABLE` Remove todas as linhas de uma TB sem registrar as exclusões de linhas individuais.
`UPDATE STATISTICS` Atualiza estatísticas de otimização de consulta de uma TB ou view indexada.

**DCL (Linguagem de Controle de Dados)** São usados para controle de acesso e gerenciamento de permissões para usuários em no banco de dados. Com eles, pode facilmente permitir ou negar algumas ações para usuários nas TBs ou registros (segurança de nível de linha).

`GRANT`  Atribui privilégios de acesso do usuário a objetos do banco de dados.
`REVOKE`  Remove os privilégios de acesso aos objetos obtidos com o comando GRANT.
`DENY`  O comando é usado para impedir explicitamente que um usuário receba uma permissão específica.

**TCL (Linguagem de Controle de Transações)** São usados ​​para gerenciar as mudanças feitas por instruções DML. Ele permite que as declarações a serem agrupadas em transações lógicas.

`COMMIT` É usado para salvar permanentemente qualquer transação no banco de dados.
`ROLLBACK` Este comando restaura o banco de dados para o último estado commited.

**Anomalia de inserção:** impede que a inclusão de registros devido à falta de dados (ex: adicionar um novo plano de tv a cabo sendo que nenhum cliente comprou) solução gerar uma TB para os planos.

**Anomalia de exclusão:** impede a exclusão de um registro devido ao relacionamento com outras TBs.

**Normalização de banco de dados:** Normalização é uma ferramenta usada no projeto lógico que serve para reestruturar TBs e atributos, reduzindo assim redundâncias e permitindo o correto crescimento do banco de dados. Por meio dela que bancos com muita movimentação garantem sua integridade após remoção, inserção e alteração dos dados. 
Ver detalhes em [http://spaceprogrammer.com/bd/normalizando-um-banco-de-dados-por-meio-das-3-principais-formas/](http://spaceprogrammer.com/bd/normalizando-um-banco-de-dados-por-meio-das-3-principais-formas/)

**Tipos de dados permitidos em SQL:**

![img15 ](https://i.ibb.co/zfZcsGp/img15.png"img15" )


**Outros tipos de dados permitidos em SQL:**

`BLOB` Permite  armazenamento de informações  binárias, arquivos, imagens.
`TEXT` Permite o armazenamento de grandes informações e strings.
`Redes` Permite o armazenamento de endereços de IP, MAC-ADRESS e outros.
`Monetários` Permite o armazenamento de valores monetários com as formatação cifras etc. (R$).
`Geométricos` Permite o armazenamento de informações de formas geométricas.

**Atributos em SQL:**

`NULL / Not NULL` Permite  ou não valores nulos
`Unsigned / Signed` Permite ou não números negativos
`Auto-increment` Sequência, contadores
`Zerofill` Preenche o valor numérico completando com zeros a esquerda



## **Boas práticas na escolha do tipo de dados e armazenamento em disco.**

O objetivo é dessas práticas é a economia de espaço e melhorar o processamento de dados. 
Segue a lista de boas práticas:

I. Escolher o menor tipo de dados para cada informação.

>  Exemplo: para idade é recomendado escolher um int com no máximo 3
> casas.

II. Quanto menor o tipo de dado, mais rápido é o processamento.

**Maus usos dos tipos de dados**
I. Armazenar dados numéricos em colunas string;
II. Armazenar dados numéricos em campos maiores que o necessário;
III. Criar campos de string maiores que o necessário;

**Nomenclaturas e detalhes de um banco relacional**

* Entidades (TBs) e atributos;
* Registros (Tuplas) [Tuplas no SQL é diferente do Python];
* Chaves (Primária e estrangeira);
* Relacionamento entre entidades (TBs);
* Integridade referencial (relação dos dados das TBs de forma coerente);
* Normalização (é o processo de organização de campos e TBs)
* Uma TB só pode ter uma chave primária que pode ser composta de uma ou mais colunas;
* Uma TB pode ter mais de uma chave estrangeira;

## Referências

* [A Base dos Dados](https://console.cloud.google.com/bigquery?)
* [Curso de SQL Completo Gratuito - Softblue](https://www.softblue.com.br/site/curso/id/3/CURSO+SQL+COMPLETO+BASICO+AO+AVANCADO+ON+LINE+BD03)
* [Dicionário para um DBA SQL Jr (dbaonboarding.com.br)](https://www.dbaonboarding.com.br/post/dicionario-para-um-dba-sql-jr)
*  [https://www.concepcaoweb.com.br/site/glossario-de-funcoes-sql/)](https://www.concepcaoweb.com.br/site/glossario-de-funcoes-sql/)

*  [https://www.devmedia.com.br](https://www.devmedia.com.br/sql-join-entenda-como-funciona-o-retorno-dos-dados/31006)
* [Permissões : GRANT / REVOKE : SQL Server : Controle de Acesso aos Dados (webmundi.com)](https://www.webmundi.com/banco-de-dados/principais-comandos-ms-sql-server-parte-4-controle-de-acesso-aos-dados/)
