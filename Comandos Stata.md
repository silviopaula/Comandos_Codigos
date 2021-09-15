


# Comandos STATA

![Stata ](http://www.stata.com/includes/images/stata-fb.jpg "Stata ")

**Autor:** Silvio da Rosa Paula           
  
 Para maiores detalhes consulte:               
[[U] User's Guide (stata.com)](https://www.stata.com/manuals/u.pdf)


## Comandos iniciais

*Limpar o ambiente de variáveis

    clear all

*Definindo a pasta de trabalho

    cd "D:\OneDrive\"

Instalar pacotes

    ssc install pacote
    
Repetir a instalação de um pacote

    ssc install pacote, replace

*Abrir uma base de dados .dta

    use "D:\base.dta", clear

## Fazendo cálculos rápidos no Stata
Para utilizamos o stata como calculadora precisamos utilizar o comando ***display*** antes da operação.

    display 9 + 9
    display 9 - 9
    display 9 * 9
    display 9 / 9
    display 9^2
    display exp(9)
    display log(9)

## Trabalhando coma arquivos .dta

*Abrir somente algumas variáveis de um banco de dados

> Obs: o Clear limpa o ambiente de variáveis

    use var1 var2 using "D:\base.dta", clear

*Salvar uma base de dados no formato.dta 
> Obs: o replace substitui o base.dta se existir na pasta

    save "D:\base.dta", replace

*Zipando bases e arquivos

    zipfile Base.dta, saving(Base)

*Extrair zip (ele só irá extrair e não abrir carregar a base de dados)

    unzipfile myfiles, replace

*Apagar um arquivo de uma pasta diretamente do stata

    capture erase "D:\Base.dta"
    capture erase "D:\Base.csv"


## Manipulando variáveis

*Ver variáveis

    browse
    browse var1 var2

*Gerar uma variável

    gen var

*Excluir uma variável

    drop var

*Clonar uma variável

    clonevar nova_var = var

*Converter todas as variáveis para numérico

    destring, replace

*Converter somente uma variável específica para numérico

    destring var_string, generate(var_numeric)

*Converter todas as variáveis para numérico ignorando a virgula

    destring, replace dpcomma

*Destring e ignorar caracteres especiais

    destring, replace ignore("*")

*Gerar variável em log

    gen ln_var = ln(var)

*Converter ln para (exp) a variável volta para sua condição inicial

    gen var = exp(ln_var)

*Renomear variável

    ren nome_antigo nome_novo

*Gerar uma amostra somente com as variáveis selecionadas

    keep var1 var2

*Adicionar (Label) rótulo nas variáveis

    label var var1 "texto"

*Tabular dados de uma variável

    tab var

*Ordenar variáveis 

> De forma crescente

    sort var
    gsort var

> De forma decrescente
> 
    gsort -var
 

*Filtrar tabela de dados

> Deixar somente se var = status

    keep if var=="status"

> Deixar somente se var = zero

    keep if var==0
    
> Excluir somente se var = status

    drop if var=="status"

> Excluir somente se var = zero

    drop if var==0

*Concatenar duas variáveis e gerar uma terceira

    egen var3 = concat(var1 var2)

  
## Estrutura de Repetição

***Foreach**

> Exemplo: loop para substituir missings por zero de três variáveis

    foreach i in var1 var2 var3 { 
    replace `i'=0 if `i'==.
    } 

***Forvalue**

> Exemplo: gerar var_2000=2000; var_2001=2001 ... 2020

    forvalues i = 2000(1) 2020{
    gen var_`i' = `i'
    }

## Trabalhando com Strings

*Extrair um contexto de uma variável string

> Exemplo:  Suponha uma variável  Ano= "02/09/2000 11:35:42", se  quisermos pegar somente o Ano da string

    forvalues i = 2000(1) 2020{
    replace Ano = "`i'" if strpos(Ano, "`i'")
    }

*Transformar letras minusculas em maiúsculas

    gen var_minuscula = upper(var_maiuscula)

*Transformar letras maiúsculas em minúsculas

    gen var_maiuscula = lower(var_minuscula)


## Trabalhando com variáveis do tipo Date
Para mais informações assista o vídeo: [ALB tutoriais científicos](https://www.youtube.com/channel/UCrrN0ZrTZPr0vEF_W1eqesQ)

A maioria dos softwares armazena datas numericamente ou seja, contando o número de dias a partir de uma data inicial predeterminada "por esse motivo evite de abrir arquivos com dadas históricas no Excel, pois ele vai substituir e você perderá as informações". 
O stata armazena datas como número de dias desde 01/01/1960, e armazena data hora como o número de milissegundos desde  01/01/1960 00:00:00:00.

Exemplos:  se digitarmos na barra de comando diretamente uma data obtemos os valores numéricos das datas 

       display d(1/1/1960) // Teremos um retorno do valor = 0.
       display d(1/1/1961) // Teremos um retorno do valor = 366
       display d(1/1/1959) // Teremos um retorno do valor =-365
       
 Calcular  idade.
   
      display d(18/08/2021) - d(30/1/1984)          // idade em dias.
      display (d(18/08/2021) - d(30/1/1984))/365.25 // idade em anos
           
    
    
**Convertendo dadas para um padrão**
Dependendo a fonte de dados, as informações de data podem vir de diferentes formas por exemplo a data de 18 de Janeiro de 1960:

|18/01/1960|   18/1/1960    |    01.18.1960   |   18/1/60 |  jan/18/1960   |   18/jan/1960 09:42  |   18/01/1960 09:42  | 

##

**Exemplo 1:** Suponha que nossa variável de data tenha os seguinte layouts (todas tem os 4 dígitos do Ano)
       |18/01/1960  | 01.18.1960 | jan/18/1960  | 18/1/1960  | 
       
 Gerando uma variável de data do tipo (Numérica) a partir de outra variável com data

        gen Data2 = date(Data, "DMY") // onde DMY = Dia; Mês; Ano 
        
   Convertendo a nova variável data numérica para um formato mais legível
 
        format %dtDD/NN/CCYY Data2

##
    
**Exemplo 2:** Suponha que nossa variável de data tenha os seguinte layouts  (Nem todas tem os 4 dígitos do Ano)
       |18/01/60  | 01.18.1960 |   
       
  

  Não podemos simplesmente utilizar o comando anterior pois no caso onde temos apenas 2 dígitos no ano,
     ele irá gerar missings, para contornar esse problema utilizaremos o comando split para separar os componentes da data.
   
   Com split ele irá quebrar a variável cada vez que encontrar a contra barra 
   
       split Data, p(/)

   Convertendo variáveis geradas em numéricas 
    
        destring Data1 Data2 Data3, replace
    
   Agora podemos substituir a Data3 que contem o ano com apenas dois dígitos por 4 dígitos 
    
        replace Data3=2018 if Data3=18
        replace Data3=1993 if Data3=9

Agora podemos unir as 3 variáveis data e formatar para o padrão brasileiro dmy
    
        gen Data_ok = mdy(Data2 , Data1 , Data3)
        format %dtDD/NN/CCYY Data_ok 

Os mesmos comandos podem ser utilizados para resolver outros problemas.


## Estatísticas

*Obter as estatísticas descritivas de todas variáveis

    summarize 
    *ou 
    sum
    
*Exportar descritivas para um arquivo word

> Obs: Esse pacote pode ser utilizados para extrair outros resultados

    ssc install asdoc
    asdoc sum, replace title(Descritivas) save(D:\Descritivas.rtf) fs(10) dec(3) tzok , replace

> Onde:    fs(10) = tamanho da fonte;  
> .rtf é o formato que será salvo o arquivo, pode ser substituído por .doc
>  dec(3) = 3 decimais;   
>  tzok  =
>  replace = substitui a tabela se existir, pode ser substituído por **append** ou seja, adicionar a uma tabela já existente
> sempre mostrar a mesma quantidade de decimais e não  elimina os zeros
> à direita   Ver mais detalhes em:

Para mais detalhes veja:          
 [asdoc : options and examples )](https://fintechprofessor.com/2018/03/22/asdoc-options-examples/)

*Estatísticas descritivas de apenas uma variável

    sum var1

*Matriz de correlação de todas variáveis

    correlate
    *ou
    corr

*Matriz de correlação de apenas uma variável

    corr var1

  
## Missings values

  A presença de observações ausentes (missing values) tem o potencial de  incorrer em  endogeneidade, ocasionando vieses nos estimadores de máxima verossimilhança, por essa razão muitos modelos de econometria espacial não permitem missings.

**O que fazer na presença de missings?**
Não existe uma resposta definitiva para essa pergunta, portanto, podemos adotar algumas medidas:

i- Substituir missings por zero: alguns pacotes no permitem substituir os valores ausentes por zero
     incluindo o comando "zero" no final da regressão.

ii- Interpolação: podemos interpolar e extrapolar os valores ausentes porém esse método
     resolve o problema de indivíduos que não possuem nenhuma observação no painel de dados.
	 
iii- Imputação: podemos imputar dados diretamente no stata. A imputação nada mais é que uma previsão 
	 de dados. Isso pode ser feito por  diferentes métodos e modelos de regressão como OLS, LOGIT etc..
	 é importante saber se os dados são estacionários ou raiz unitária para ter uma boa imputação de dados.

iv- Excluir: podemos excluir aqueles indivíduos que não temos nenhuma observação, porém é importante
     lembrar que é preciso excluir de todos os anos e também excluir da matriz de contiguidade se tiver 
     trabalhando com dados espaciais. Ademais, é possível imputar dados por meio de métodos de Machine learning.
     
*O melhor package para visualizar missings é o  **mdesc**

    ssc install mdesc

*Visualizar missings de todas variáveis

    mdesc

*Visualizar missings de apenas uma variável

    mdesc var1

*Replace valores missings para zero

    replace var=0 if var==.

*Recode valores missings para zero

    recode var . = 0

*Replace valores missings para a média

> Obs: também é possível usar o sum para obter a média e substituir deforma semelhante a feita para zero

    egen mean_var = mean(var), by(id) 
    replace var=mean_var  if var==.

*Replace valores missings para a mediana
 
    egen median_var = median(var), by(id) 
    replace var=median_var if var==.

*Replace valores missings de  um grupo de variáveis para a média

     foreach var  in var1 var2 var3{ 
       egen mean_var = mean(`var'), by(id) 
       replace`var'=mean_var if `var'==.
       drop mean_var 
    }

*Replace valores missings com interpolação e extrapolação

> Obs: como escolher as variáveis para interpolação? geralmente é utilizada unidade  de tempo, contudo se a correlação for baixa os valores imputados não serão bons, então neste caso é possível utilizar uma variável com maior correlação com a variável que apresenta missings. Para exemplo utilizaremos a variável Ano para imputar dados em var_1

    *Interpolar e Extrapolar
    by id, sort : ipolate var_1 Ano, generate(var_1_int) epolate 
   

> Onde:    
> id é o identificador da tabela    
> `ipolate` é o comando de
> interpolação    
>  `epolate` é o comando de extrapolação

   
## Variáveis Dummy (One-Hot Encoding)

*Gerar dummies a partir de uma variável categórica numérica ou string

    tabulate var, generate (Dummie_var)


*Gerar dummies a partir de uma variável categórica numérica com replace e if

    gen D_var = 0
    replace D_var =1 if var_cat==1

*Gerar dummies a partir de uma variável categórica strings com replace e if

    gen D_var = 0
    replace D_var =1 if var=="palavra"

 
*Gerar uma variável dummy a partir de uma expressão dentro de variável do tipo string

> Exemplo: suponha uma variável com descrição da altura de pessoas, e nós estamos interessados em gerar uma dummies para pessoas altas e  baixas

    gen D_Alto = "0"
    replace D_Alto = "1" if strpos(Var_altura_pessoa, "Homem Alto")
    destring D_Alto, generate(D_Alto_numeric)

    gen D_Baixo = "0"
    replace D_Baixo = "1" if strpos(Var_altura_pessoa, "Homem Baixo")
    destring D_Baixo, generate(D_Baixo_numeric)

  
*Gerar uma dummy a partir de uma variável de data

    gen D_4_novembro_2018 = 0
    replace D_ datax _1 = 1 if DATA == date("04nov2018", "DMY")

  

## Merge e Append 

Para mais informações consulte
[Stata: Merge, Append, Join](http://stataproject.blogspot.com/2007/12/combine-multiple-datasets-into-one.html)

A união de tabela de dados no stata não foge a regra dos demais softwares, R, Python, SQL. Podemos unir tabelas da verticalmente, por exemplo, quando temos vários períodos de tempo em tabelas diferentes (cabe destacar que os nomes das colunas devem ser os mesmos) e queremos empilhar, para tanto utilizamos o comando `append` e a união horizontal quando utilizamos os comandos `merge` ou `joinby`.

| União            | Representação no Stata |
|------------------|------------------------|
|um-para-um        | (1:1)                  |
|um-para-muitos    | (1:m)                  |
|muitos-para-um    | (m:1)                  |
|muitos-para-muitos| (m:m)                  |
 
### **Combinando vários conjuntos de dados em um**

  **Append (união vertical)**
  
> Obs: a base de dados que será feito o append deve ser preparada de antemão com os mesmos nomes das colunas e salva em .dta

    append using "D:\base.dta"

![append](http://3.bp.blogspot.com/_iuN8kqdF7_g/R1Qx5w-x8AI/AAAAAAAAAcs/re82FmvonSA/s400/Slide1.GIF "append")


**Merge  um-para-um:**        
se a variável de identificação que aparece nos arquivos for única em ambos os arquivos, então é uma correspondência um a um. Único significa que para cada valor dessa variável, há apenas uma observação que a contém. Na figura abaixo, o país é a variável identificadora. Em ambos os conjuntos de dados, cada país tem apenas uma observação.

    merge 1:1 id Ano using "D:\Base_2.dta"
    
![Merge 1:1](http://4.bp.blogspot.com/_iuN8kqdF7_g/R1Qx6A-x8BI/AAAAAAAAAc0/JmKXbgAGDuk/s400/Slide2.GIF "Merge 1:1")

**Merge  um-para-muitos:**             
se a variável de identificação for única em um arquivo, mas não única no outro, então é uma correspondência um-para-muitos. Isso é muito comum quando você tem grupos de observações em um arquivo (o arquivo com a variável de identificação que não é única) e informações sobre cada grupo em outro arquivo (o outro arquivo). A figura a seguir o deixará mais claro:

    merge 1:m id Ano using "D:\Base_2.dta"


**Merge  muitos-para-muitos:**             
isso é muito raro. Isso também é problemático, uma vez que não existe uma regra inequívoca para a atribuição de valores de observações em um arquivo para observações no outro arquivo. Não vou elaborar muito sobre essa correspondência.

    merge m:m id Ano using "D:\Base_2.dta"
    
**Diferenças entre Merge  muitos-para-muitos e Joinby**
A questão é como combinar os valores de um conjunto de dados com o outro. Acho que a melhor maneira de explicar a diferença entre os comandos é graficamente:

![Merge Joinby](http://2.bp.blogspot.com/_iuN8kqdF7_g/R1VdfQ-x8DI/AAAAAAAAAdE/uhqsCF_HAFU/s400/Slide4.gif  "Merge Joinby")


Agora você pode entender o significado da frase que descreve o comando joinby na referência de ajuda: "Forme todas as combinações de pares dentro de grupos".


## Collase (agregação)

Às vezes, temos dados que precisam ser collapsados na média, total, min, max, etc, para serem úteis. Por exemplo, você pode  pode ter dados semanais, mas deseja dados mensais, ou ter dados por municípios mas queremos dados por estados etc. Nestes casos recorremos ao comando collapse.

> Obs: se o objetivo é a contagem de dados, lembre-se que zero também serão contados como observações. Portando, para o exemplo abaixo a variável dummy de faltas (D_faltas) o zero foi substituído por missings com seguinte comando:
> `replace D_faltas=. if D_faltas==0`. Cabe destacar que o objetivo aqui é agregar microdados em dados em nível municipais por ano.

    collapse                           ///
    (mean) Media_idade = idade         ///
    (count) Qtd_faltas = D_faltas      ///
    (sum) Total_inscritos = Inscritos  ///
    (percent) Per_homens = D_homens    ///
    ,by(id Ano)

## Trabalhando com painel de dados
Quando desejamos trabalhar com painel de dados, devemos declara para o stata nossa intenção

Exemplo: declarar que estamos trabalhando com um painel de dados por ano

    xtset id Ano, yearly

*Se nosso painel de dados tem alguns ids faltantes ou períodos faltantes e queremos completa-los com missings utilizamos

    tsfill, full


## Globais

Global é um objeto semelhante a uma lista de variáveis. Normalmente utilizamos globais quando queremos chamar um conjunto de variáveis para executar uma tarefa. Exemplo: suponha que você tenha 30 variáveis explicativas em uma regressão, para não ter que colocar o nome das 30 variáveis dentro do comando basta criar uma global e chamar a global no lugar das variáveis explicativas 

    global var_global var1 var2 var3 var4 var5... var30

Exemplo de regressão com global:

     reg y $var_global

  
## Análise Exploratória de Dados

**Gráficos para explorar variáveis ​​contínuas**

Histogramas, diagramas de densidade e boxplots, criados por **histograma** , **kdensity** e **boxplot** respectivamente, ilustram a distribuição das variáveis.

**Histograma** 

       histogram var1, normal
       histogram var1, normal start(30) width(5) 

**Gráfico de densidade**
    
      kdensity var1, normal
      kdensity var1, normal width(5) 
    
**boxplot**

      graph box var1
      graph box write, over(grupo)

**Gráfico de dispersão**

      twoway (scatter var1 var2)
    

**Gráficos para explorar variáveis ​​contínuas por grupos**
    
   O comando `tabstat` pode calcular estatísticas descritivas dentro de grupos.
  
      tabstat var, by (id) stat (n meam sd)  
      tabstat var, by(prgtype) stat(n mean sd p25 p50 p75)

  Veja mais exemplos de gráficos e seus respectivos comandos                    
 [Visual overview for creating graphs (stata.com)](https://www.stata.com/support/faqs/graphics/gph/stata-graphs/)
[Graphics | Stata](https://www.stata.com/features/publication-quality-graphics/)

Veja mais detalhes da AED
 [Stata Guide: Exploratory Data Analysis (mwn.de)](https://wlm.userweb.mwn.de/Stata/wstatexp.htm)
[Stata Class Notes: Exploring Data (ucla.edu)](https://stats.idre.ucla.edu/stata/seminars/notes/stata-class-notesexploring-data/)

## Tarefas Prontas

### *Gerar id (identificador)

    egen id = group(var)
    
### *Gerar uma variável aleatória

    set seed 123
    gen newaleat =runiform()


### Ordenar a tabela de forma aleatória

    set seed 123
    gen newaleat =runiform()
    sort newaleat

  
### Gerar variável com Soma, Média, Minímo, Máximo, Contagem e etc, a partir de outras variáveis

    sort id Ano
    by id Ano: var_sum = sum(var)     // Soma
    by id Ano: var_min = min(var)     // Minímo
    by id Ano: var_mean = mean(var)   // Média
    by id Ano: var_max = max(var)     // Máximo
    by id Ano: var_count = count(var) // Contagem

### Gerar dummy das estações do ano no hemisfério sul

Exemplo: Suponha que você possui uma variável com essa estrutura **data_hora ="02/09/2000**" e queremos gerar dummies e uma variável categórica de estações do ano.

Datas de inicio e fim das estações do ano
- Primavera: 1 setembro até 30 novembro (9 - 11)
- Verão: 1 dezembro até 28 fevereiro (12 - 2)
- Outono: 1 março até 31 maio (3 - 5)
- Inverno: 1 junho até 31 agosto (6 - 8)

**Gerar dummy de Primavera**

    clonevar Primavera = data_hora
    replace Primavera = "1" if strpos(Primavera, "/09/")
    replace Primavera = "1" if strpos(Primavera, "/10/")
    replace Primavera = "1" if strpos(Primavera, "/11/")
    replace Primavera = "0" if strpos(Primavera, ":")
    destring Primavera, generate(d_primavera)
    drop Primavera

 **Gerar dummy de Verão**

    clonevar Verão = data_hora
    replace Verão = "1" if strpos(Verão, "/12/")
    replace Verão = "1" if strpos(Verão, "/01/")
    replace Verão = "1" if strpos(Verão, "/02/")
    replace Verão = "0" if strpos(Verão, ":")
    destring Verão, generate(d_verão)
    drop Verão

 **Gerar dummy de Outono**

    clonevar Outono = data_hora
    replace Outono = "1" if strpos(Outono, "/03/")
    replace Outono = "1" if strpos(Outono, "/04/")
    replace Outono = "1" if strpos(Outono, "/05/")
    replace Outono = "0" if strpos(Outono, ":")
    destring Outono, generate(d_outono)
    drop Outono

  **Gerar dummy de Inverno**

    clonevar Inverno = data_hora
    replace Inverno = "1" if strpos(Inverno, "/06/")
    replace Inverno = "1" if strpos(Inverno, "/07/")
    replace Inverno = "1" if strpos(Inverno, "/08/")
    replace Inverno = "0" if strpos(Inverno, ":")
    destring Inverno, generate(d_inverno)
    drop Inverno

**Verificar sobreposição**

    tab d_primavera if (d_verão==1     | d_outono==1 | d_inverno==1)
    tab d_verão     if (d_primavera==1 | d_outono==1 | d_inverno==1)
    tab d_outono    if (d_primavera==1 | d_verão==1  | d_inverno==1)
    tab d_inverno   if (d_primavera==1 | d_verão==1  | d_outono==1)

  **Gerar variável categórica de estações**
  
      gen  Estacoes = ""
      replace Estacoes = "Verao"     if  d_verão ==1  
      replace Estacoes = "Outono"    if  d_outono ==1  
      replace Estacoes = "Inverno"   if  d_inverno ==1  
      replace Estacoes = "Primavera" if  d_primavera ==1  


### *Gerar dummy de turnos do dia

Exemplo: Suponha que você possui uma variável com essa estrutura **data_hora ="02/09/2000 11:35:42**"

Turnos do dia
- Matutino ou Manhã: 6:00 às 11:59
- Vespertino ou Tarde: 12:00 às 17:59
- Noturno ou Noite: 18:00 às 23:59* Madrugada: 00:00 às 05:59
- Primeiro deixar somente as horas


**Manhã**

    clonevar turno_manhã = horas
    replace turno_manhã = "1" if strpos(data_hora, "06")
    replace turno_manhã = "1" if strpos(data_hora, "07")
    replace turno_manhã = "1" if strpos(data_hora, "08")
    replace turno_manhã = "1" if strpos(data_hora, "09")
    replace turno_manhã = "1" if strpos(hodata_horaras, "10")
    replace turno_manhã = "1" if strpos(data_hora, "11")
    replace turno_manhã = "0" if turno_manhã != "1"
    destring turno_manhã, generate(d_manhã)
    drop turno_manhã

  
**Tarde**

    clonevar turno_tarde = horas
    replace turno_tarde = "1" if strpos(data_hora, "12")
    replace turno_tarde = "1" if strpos(data_hora, "13")
    replace turno_tarde = "1" if strpos(data_hora, "14")
    replace turno_tarde = "1" if strpos(data_hora, "15")
    replace turno_tarde = "1" if strpos(data_hora, "16")
    replace turno_tarde = "1" if strpos(data_hora, "17")
    replace turno_tarde = "0" if turno_tarde != "1"
    destring turno_tarde, generate(d_tarde)
    drop turno_tarde

  
**Noite**

    clonevar turno_Noite = horas
    replace turno_Noite = "1" if strpos(data_hora, "18")
    replace turno_Noite = "1" if strpos(data_hora, "19")
    replace turno_Noite = "1" if strpos(data_hora, "20")
    replace turno_Noite = "1" if strpos(data_hora, "21")
    replace turno_Noite = "1" if strpos(data_hora, "22")
    replace turno_Noite = "1" if strpos(data_hora, "23")
    replace turno_Noite = "0" if turno_Noite != "1"
    destring turno_Noite, generate(d_noite)
    drop turno_Noite


**Madrugada**

    clonevar turno_madrugada = horas
    replace turno_madrugada = "1" if strpos(data_hora, "00")
    replace turno_madrugada = "1" if strpos(data_hora, "01")
    replace turno_madrugada = "1" if strpos(data_hora, "02")
    replace turno_madrugada = "1" if strpos(data_hora, "03")
    replace turno_madrugada = "1" if strpos(data_hora, "04")
    replace turno_madrugada = "1" if strpos(data_hora, "05")
    replace turno_madrugada = "0" if turno_madrugada != "1"
    destring turno_madrugada, generate(d_madrugada)
    drop turno_madrugada

 
**Verificar sobreposição**

    tab d_manhã if (d_tarde==1 | d_noite==1 | d_madrugada==1)
    tab d_tarde if (d_manhã==1 | d_noite==1 | d_madrugada==1)
    tab d_noite if (d_tarde==1 | d_manhã==1 | d_madrugada==1)
    tab d_madrugada if (d_tarde==1 | d_noite==1 | d_manhã==1)
    destring data_hora, generate(Horas)
    drop horas


### Identificar e remover observações duplicadas

    sort id Ano
    quietly by id Ano: gen dup = cond(_N==1,0,_n)
    tab dup

> Onde: 
> dup = 0 gravação é única 
> dup = 1 gravação é duplicada, primeira ocorrência 
> dup = 2 gravação é duplicada, segunda ocorrência 
> dup = 3 gravação é duplicada, terceira ocorrência 
> etc...
> Excluindo os repetidos 

    keep if dup==0


### Verificando quantos id existem por período

    gen obs=_n
    bysort obs: egen contagem=count(id)
    tab contagem Ano


### Excluir linhas de uma variável de forma aleatória

    set seed 123
    bys coortes : gen rnd = uniform()
    bys coortes (rnd) : keep if _n == 1

### Fazer teste de diferença de médias (t-test) com e sem pesos e exportar para word

    ssc install psmatch2

**Sem pesos***

    asdoc pstest var1 var2 var3, raw treat(D_Tratamento), replace title(T-test sem pesos') ///
    save(Balanço_covariadas.rtf) fs(10) dec(3) tzok

**Com pesos**

    asdoc pstest var1 var2 var3, treat(D_Tratamento) mw(Pesos), append title(T-test com pesos') ///
    save(Balanço_covariadas.rtf) fs(10) dec(3) tzok


## Referências

[ User's Guide (stata.com)](https://www.stata.com/manuals/u.pdf)                               
[ALB tutoriais científicos](https://www.youtube.com/channel/UCrrN0ZrTZPr0vEF_W1eqesQ)                      
[asdoc : options and examples )](https://fintechprofessor.com/2018/03/22/asdoc-options-examples/)                            
[Stata: Merge, Append, Join](http://stataproject.blogspot.com/2007/12/combine-multiple-datasets-into-one.html)                        
 [Visual overview for creating graphs (stata.com)](https://www.stata.com/support/faqs/graphics/gph/stata-graphs/)                       
[Graphics | Stata](https://www.stata.com/features/publication-quality-graphics/)                           
 [Stata Guide: Exploratory Data Analysis (mwn.de)](https://wlm.userweb.mwn.de/Stata/wstatexp.htm)                             
[Stata Class Notes: Exploring Data (ucla.edu)](https://stats.idre.ucla.edu/stata/seminars/notes/stata-class-notesexploring-data/)                          
