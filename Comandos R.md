# Comandos R
![enter image description here](https://miro.medium.com/max/1400/1*cuOlMPTUQ3cTY7ldb-usKw.png)

**Autores:**              
Silvio da Rosa Paula                             
Dianifer Leal Borges          

## Dicionário de Termos:

|Abreviação  | Descrição |
|------------|-----------|
|     df     | dataframe |
|     TB     | tabela    |
|    Var     | Coluna    |

## Operadores de Comparação:
Os operadores de comparação sempre retornam um valor lógico TRUE ou FALSE.

| Operador |   Significado    |
|----------|------------------|
|     ==   | igual a          |
|     !=   | diferente de	    |
|     >    | maior que        |
|     <    | menor que        |
|     >=   | maior ou igual a |
|     <=   | menor ou igual a |

**Fonte** [Bóson Treinamentos em Ciência e Tecnologia](http://www.bosontreinamentos.com.br/programacao-em-r/operadores-logicos-e-operadores-de-comparacao-em-r/)

##  Operadores Lógicos:
Também conhecidos como operadores booleanos, permitem trabalhar com múltiplas condições relacionais na mesma expressão, e retornam valores lógicos verdadeiro ou falso..

| Operador |   Descrição    |                  Explicação                                   |
|----------|----------------|---------------------------------------------------------------|
|    &     | AND lógico     |Versão vetorizada. Compara dois elementos do tipo vetor e retorna um vetor de TRUEs e FALSEs
|    &&    |  AND lógico	|Versão não-vetorizada. Compara apenas o primeiro valor de cada vetor, retornando um valor lógico.
|    l     | OR lógico      |Versão vetorizada. Compara dois elementos do tipo vetor e retorna um vetor de TRUEs e FALSEs
|    ll    | OR lógico      |Versão não-vetorizada. Compara apenas o primeiro valor de cada vetor, retornando um valor lógico.
|    !     | NOT lógico     |Negação lógica. Retorna um valor lógico único ou um vetor de TRUE / FALSE.
|    xor   | XOR            |Ou Exclusivo. Retorna valor lógico TRUE se ambos os valores de entrada forem diferentes entre si, e retorna FALSE se os valores forem iguais.

**Fonte** [Bóson Treinamentos em Ciência e Tecnologia](http://www.bosontreinamentos.com.br/programacao-em-r/operadores-logicos-e-operadores-de-comparacao-em-r/)

##  Operadores  Aritméticos

| Operador |   Descrição      |
|----------|------------------|
|     +    | adição           |
|     -    | subtração	      |
|     *    | multiplicação    |
|     /    | divisão          |
|    :     | sequência        |
|     ^    |  exponencial     |
|    %%    | módulo           |


## Atalhos

| Operação                      |    Atalho                 |
|-------------------------------|---------------------------|
|Executar                       | Ctrl  + Enter             |
|Salvar script                  | Ctrl + S                  |
|Limpar console                 | Ctrl + L                  |
|Lista  argumentos da função    | Ctrl + espaço  ou Tab     |
|Adicionar pipe(`%>%`)          | Ctrl + shift + M          |
|Cria um chunk no R Markdown    | Ctrl + Alt + I            |
|Restart Rstudio                | Crtl + Shift + F10        |
|Visualizar todos os atalhos    | Alt  + Shift + K          |
|Mais Zoom                      | Crtl  +                   |
|Menos Zoom                     | Crtl  -                   |

## Instalar e Carregar Pacotes

Instalar pacotes
```
install.packages('package')
install.package(c('package1','package2','package3'))
```

Instalar uma versão mais antiga de um pacote
```
packageurl <- "http://cran.r-project.org/src/contrib/Archive/ggplot2/ggplot2_0.9.1.tar.gz"
install.packages(packageurl, repos=NULL, type="source")

# ou
require(remotes)
install_version("package1", version = "0.0.1", repos = "http://cran.us.r-project.org")

# Instalar mais de um pacote 
install.versions(c('package1', 'package2'), c('0.0.1', '1.0.0'))
```

Atualizar pacotes
```
old.packages() 
update.packages()
update.packages(checkBuilt=TRUE, ask=FALSE)
```

Carregar pacotes instalados
```
#library(package)
#require(pacote)
```

Como descarregar pacotes
```
detach('package:pacote', unload =TRUE)
```

Verificar a versão do pacote
```
packageDescription("pacote")
```

Limpar console e base de dados
```
rm(list=ls())
```

Definir pasta de trabalho
```
setwd ("D:/")
```

Utilizar uma função específica de um pacote sem carregar o pacote
```
(pacote)::função()
```

Acessar a documentação
> Obs: é possível acessar o help de uma função ou pacote simplesmente 
> selecionando a função com mouse  e pressionando F1
```
help('pacote')
```

Acessar  a documentação de um pacote
```
help(package='pacote')
```

Para acessar o help de um comando específico
```
?comando
help('comando')
help('comando', package='pacote')
```

## Configurações de Memória e Processador.

Expandir memória
> Obs: também é possível selecionar a quantidade memória desejada
> substituindo os valores em mb no lugar do 9....
```
memory.limit (9999999999) 
```

Checar quantidade de memória selecionada
```
memory.size()
gc()
gc(reset=TRUE) # Limpar memória
```

Escolhendo quantos threads do CPU serão utilizadas
> Obs: esse comando é do pacote `data.table`
```
setDTthreads(20) 
```

## Visualização de Dataframes

Visualizar dataframe no browser
```
View(df)
```

Visualizar o nome das variáveis de um dataframe
```
names(df)
colnames(df)
```

Visualizar nome de colunas utilizando seu número
```
names(df)[c(1:4,9,20)]
```

Visualizar uma prévia do dataframe
```
df
```
Visualizar as primeiras 10 linhas do dataframe
```
head(df) 
head(df, n==5) ## Ver as primeiras 5 linhas
```

Visualizar as últimas 10 linhas do dataframe
```
tail(df) 
tail(df, n==5) ## Ver as últimas 5 linhas
```

Visualizar  dimensões do dataframe (colunas e linhas)
```
dim(df)
```

Visualizar detalhes das variáveis do dataframe
```
str(df)
```

Visualizar o tipo de classe de uma variável (numérico, string, etc.)
```
class(df$var1)
```

Visualizar  a classe de um objeto (numeric, matrix, data.frame, etc,)
```
class(df)
```

Listar objetos no ambiente de trabalho
```
ls(df)
```

## Manipulando Dataframes

Ordenando alfabeticamente as colunas de um dataframe
```
df <- df %>% select(order(colnames(df)))
```

Ordenar uma coluna de um dataframe
```
# Ordenar de forma crescente
df <- df [order(df $var1),]

# Ordenar de forma decrescente
df <- df [order(df $var1),decreasing = (TRUE),] 
```

Ordenar colunas de um dataframe
```
df <- df %>%  select(sort(current_vars()))
```

Gerar uma amostra com o comando `subset`
```
# Gerar uma amostra apenas com as colunas var1 var2 var3
df_novo <- subset(df, select = c(var1,var2,var3)) 

# Gerar uma amostra sem as colunas var1 var2 var3
df_novo <- subset(df, select = -c(var1,var2,var3)) 
```

Gerar uma amostra  com package `data.table`
> Obs: só funciona se o objeto for um data.table
```
# Gerar uma amostra apenas com as colunas var1 var2 var3
df_novo <- df[,.(var1, var2, var3)]

# Gerar uma amostra sem a coluna var1
df <- df[!(df$var=="var1"),]
```

Gerar uma amostra com período delimitado
```
df_novo <- subset(df, Ano>=2009)
df_novo <- subset(df, Ano<2009)
df_novo <- subset(df, Ano>=2009 & Ano<=2018)
```

Gerar uma amostra com as primeiras 1000 linhas de um dataframe
```
df_novo  <- head(df, n=1000)
```

Reshape de long para wide
```
df_wide = reshape(data = df_long, idvar = "id", 
v.names= c("var1","var2","var3"), sep = "_", 
timevar = "Ano", times = c(2000,2001,2002,2003), 
direction = "wide")
```

Clonar uma variável do dataframe com package `dplyr`
```
df <- df %>% mutate(var_clone1 = var1) %>%   
             mutate(var_clone2 = var2)
```

Clonar uma variável
```
df$var_clone1 <- df$var1
```

Deixar somente alguns dos dataframes selecionados
```
rm(list=(ls()[ls()!="df1", "df2"]))
```

Remover  dataframe
```
rm(df)
```

Renomear data.frame
```
df_novo <- df_antigo
rm(df_antigo)
```

Renomear colunas
```
df <- rename(df, c("nome_novo_1" = "nome_antigo_1",
                   "nome_novo_2" = "nome_antigo_2"))
```

Renomear múltiplas colunas de um só vez
```
names(df)[1:4] <- c("var1", "var2","var3" ,"var4")
```

Renomear colunas com pacote `data.table`
> Obs: só funciona se o objeto for do tipo data.table
```
setNames(df, 'nome_antigo', 'nome_novo')
```

Renomear colunas de um data.frame
```
names(df)[names(df) == 'nome_antigo'] <- 'nome_novo'
```

Renomear colunas adicionando um prefixo e sufixo
```
# Prefixo
colnames(df) <- paste("ln", colnames(df), sep = "_")

# Sufixo para as 10 primeiras colunas
colnames(df)[1:10] <- paste(colnames(df)[1:10], "texto", sep = "_")
```

Dropar (deletar) colunas do dataframe
```
df$var1  <-NULL
df$var2 <- df$var3 <-NULL
```

Gerar uma nova coluna dentro em um dataframe
```
df$var0 = 0
df$var3 = (df$var1 + df$var2)
df$var4 = (df$var1 * df$var2)
df$var5 = (df$var1 / df$var2)
df$var6 = (df$var1)^2 
```

Gerar nova coluna por meio da soma de duas colonas desconsiderando os missings
```
df$var_total<- rowSums(df[,c("var1", "var2")], na.rm=TRUE)
```

Gerar uma nova coluna tirando o  logaritmo de uma variável
> Obs: esse comando gera o logaritmo natural
```
df$log_var1 <- log(df$var1)
```

Gerar múltiplas colunas em logaritmo 
> Obs: depois basta renomear as colunas (recomendo adicionar somente o prefixo com:
>  ``colnames(df) <- paste("ln", colnames(df), sep = "_")``
```
# Criar uma função para gerar o logaritmo
logplusone <- function(x) {log(x[1])}

# Gerar log das colunas 1 a 10
df[,1:10] <- as.data.frame(lapply(df[,3:5], FUN = function(x) {sapply(x, FUN = logplusone)}))
```

Adicionar um label com pacote `Hmisc`
> Nota: o label é um descrição, ou seja, um rótulo para a coluna com a sua descrição. Cabe destacar que o label pode gerar problemas posteriormente com algumas transformação, portanto, adicione o label  após realizar todas as transformações nas colunas.
```
label(var[[1]]) <- "var descrição"
```

Converter uma coluna de numérico para string. objeto do tipo `datatable`
```
df <- as.data.table(apply(df, "var", as.character))  
class(df$var)
```
Converter uma coluna de string para numérico. objeto do tipo `datatable`
```
df <- as.data.table(apply(df, "var", as.numeric))  
class(df$var)
```
Converter uma coluna para numérico
```
df$var1 <- as.numeric(df$var1)
```

Converter um conjunto de colunas para numérico com `dplyr`
```
df <- df %>% mutate_at(c(1:10), as.numeric)
```

Converter todo dataframe para numérico
```
df = as.data.frame(sapply(df, as.numeric))
```

Converter uma coluna para fator
```
df$var1 <- factor(df$var1)
```

Converter colunas selecionadas para numérico
```
df <- df %>% mutate_at(c(1:15), as.numeric)
```

Substituir (replace) inf para zero com `dplyr`
    Nota: inf é a abreviação de infinito
```
fortify.zoo(log_ret) %>% mutate_all(function(x) ifelse(is.infinite(x), 0, x))
# ou
df$var[which(!is.finite(df$var))] <- 0
```

Gerar uma variável categórica com `dplyr`
> Exemplo: suponha que temos uma variável categórica com tipos de produtos, e queremos gerar uma nova variável categóricas agregando esses produtos. A saída deste comando resulta e uma variável com 4 categorias, 0,1,2,3,4
```
df <- df %>% mutate(var_cat = ifelse(Var_Produto %in% c(1:24,28,35,99), 1,
                              ifelse(Var_Produto %in% c(26,34), 2 ,
                              ifelse(Var_Produto %in% c(25,32,33), 3, 0))))
```

Arredondando valores de uma coluna ou de varias colunas 
> Nota: o comando arredonda com 2 casas decimais.
```
df %>% mutate_at(vars(var1), funs(round(., 2)))
df %>% mutate_at(vars(var1, var2, va3), funs(round(., 2)))
```

Arredondar valores de todas as colunas exceto a var1
```
df %>% mutate_at(vars(-var1), funs(round(., 2)))
```

Arredondar valores de todas as colunas cujo nome começa por VAR
```
df %>% mutate_at(vars(starts_with("VAR")), funs(round(., 2)))
```

Arredondar valores  apenas colunas numéricas
```
mydf %>% mutate_if(is.numeric, ~round(., 2))
```

Agregar  dados por id com `dplyr`
> Obs: as colunas do agrupamento devem ser fatores
```
df_novo <- df %>% 
           group_by(as.factor(id)) %>%  # 
           summarise(var1 = mean(var1),
                     var2 = mean(var2))
```

Agregar  os dados por id e Ano com `data.table`
```
df <- setDT(df)[, lapply(.SD, sum), by = .(id, ANO)]
```

Agregar  os dados com a soma
```
df_novo <- summarise(df, total_var = sum(var))
```

Replace (substituir) de forma fácil
```
df$var1[df$var2 == 1] <- 1 # fazer replace para 1 em var1 se var2 ==1
[df$var2 == 2] <- 1        # fazer replace para 1 se var2 ==2
```

Replace com ifelse 
> Nota: Fazer replace na variável var1, se var1 for menor que zero então var1 irá receber o valor de 1, caso contrário não irá alterar
```
df$var1 = ifelse(df$var1 <0, 1, df$var1)
```

Remover primeira e última linha
```
df <- df[-1, ]
```


##  Variáveis  do Tipo Data (Date)

Converter uma variável para o tipo date com `lubridate`
> Nota: ymd representa a ordem em que a data está construída, ou seja:
 y=ano, m=mês, d=dia
```
df$Data_var <- ymd(paste(df$Data_var))
```

Extrair apenas o ano de uma coluna do tipo date
```
df$Ano <- format(as.Date(df$Data, format="%d/%m/%Y"),"%Y")
```

Extrair apenas o mês de uma coluna do tipo date
```
df$Ano <- format(as.Date(df$Data, format="%d/%m/%Y"),"%m")
```

Extrair apenas o dia de uma coluna do tipo date
```
df$Ano <- format(as.Date(df$Data, format="%d/%m/%Y"),"%d")
```

Dividir coluna em várias com `splitstackshape`    
``install.packages(‘splitstackshape’) ``  
``library(splitstackshape)``    
```
df<- cSplit(df, "var", "/") # ex: absde/12/asdf/2010
```

## Missings Values

Ver total de missings das colunas de um dataframe
```
summary(df$var)
colSums(is.na(df))

# Criar uma matrix com o total de missings (fica melhor para visualizar)
Missings <- as.matrix(colSums(is.na(Covaridas_mun)))
print(Missings)
```

Remover missings e deixar o dataframe completo sem missings com `dplyr`
```
df <- df[complete.cases(df),]
```

Removendo cédulas vazias (missings) de um dataframe
```
df <- subset(df, var!="")
```

Remover missings baseado em uma variável com `zoo` 
```
df <- df[!is.na(df$Var1),]
```

Imputar dados faltante com interpolação

```
df <- df %>%  group_by(id) %>%  mutate_at(vars(var1, var2, var3, IMPOSTOS_2), 
                                list(inter = ~na.approx(., na.rm = FALSE)))
```

Substituir missings pela média GERAL
```
df$var = ifelse(is.na(df$var), mean(df$var, na.rm=TRUE), df$var)
```

Substituir missings pela mediana GERAL isso evita problemas com outliers
```
df$var = ifelse(is.na(df$var), median(df$var, na.rm=TRUE), df$var)
```

Substituir missings pela média agrupada por id com `dplyr`
```
# Gerar a função para imputar média agrupada
impute.mean <- function(x) replace(x, is.na(x), mean(x, na.rm = TRUE))
df <- df %>% group_by(id) %>% mutate(var1_nova = impute.mean(var1), 
                                     var2_nova = impute.mean(var2)) 
```

Substituir missings pela mediana agrupada por id com `dplyr`
```
impute.median <- function(x) replace(x, is.na(x), median(x, na.rm = TRUE))
df <- df %>% group_by(id) %>% mutate(var1_nova = impute.median(var1), 
                                     var2_nova = impute.median(var2)) 
```

Substituir missings pela média e mediana agrupada por id com `datatable`
```
df <- as.data.table(df)
df <- df[is.na(df$var), "var_nova"] <- mean(na.omit(df$var))
df <- df[is.na(df$var), "var_nova"] <- median(na.omit(df$var))
```

Ver o total de missings de uma coluna
```
lyrsapply(df, function(x) sum(is.na(x))) 
```

Excluir missings das colunas var1 ou var2 ou var3 e gerar um novo dataframe
```
df_novo <- df[!(is.na(df$var1)) | !(is.na(df$var2))| !(is.na(df$var3)),]
```

Substituir de missings de uma coluna por valores de outra coluna
```
df$A <- ifelse(is.na(df$A), df$B, df$A)
```

Atribuindo zero a todos os missings com `imputeTS`     
``install.packages('imputeTS')``    
``library(imputeTS)``    
```
df <- na_replace(df, 0)
```

Atribuindo zero a todos os missings
> Nota: fazer replace para 0 em var1 se var2 ==NA (missings)
```
df$var[is.na(df$var)] <- 0 
```

Remove colunas com mais de 50% NA
```
dat[, which(colMeans(!is.na(dat)) > 0.5)]
```

Remove linhas com mais de 50% NA
```
dat[which(rowMeans(!is.na(dat)) > 0.5), ]
```

Remove colunas e linhas com mais de 50% NA
```
dat[which(rowMeans(!is.na(dat)) > 0.5), which(colMeans(!is.na(dat)) > 0.5)]
```


## Outliers

Para maiores informações consulte:    
https://statsandr.com/blog/outliers-detection-in-r/


Plotar gráfico de dispersão
```
plot(df$var1, df$var2)
```

Grafico de dispersão
```
# grafico de dispersão condicional a variável de  tratamento
xyplot (df$var1 ~ df$var2 | df$tratamento) 
```

Plotar boxplot
```
boxplot(df$var1)
boxplot(df$var1, outline = TRUE)
boxplot.stats(df$var1)$out 
outlier_var1 = base[df$var1< 0, ]
outliers_var1 = base[df$var1> 10000,]
```
Identificando e plotando outliers
```
outliers =c(boxplot.stats(df$var1)$out,
boxplot.stats(df$var2)$out)
data_outliers = data[-c(which(df$var1%in% outliers),
which(df$var2%in% outliers)),]
```
Histograma com `ggplot2`
```
ggplot(dat) + 
aes(x = var1) +
 geom_histogram(bins = 30L, fill = "#0c4c8a") + 
 theme_minimal()
```

Boxplot com `ggplot2`
```
ggplot(dat) + 
aes(x = "", y = var1) + 
geom_boxplot(fill = "#0c4c8a") + 
theme_minimal()
```

Plotar boxplot
```
boxplot(df[, 1:4], main="df")
```

Gráfico de barras rápido
```
counts = table(df$var)
barplot(counts, main="titulo", xlab="titulox")
```

Gráfico de densidade
```
# grafico condicional a variável de  tratamento
densityplot (~ df$var1 | df$tratamento)
```

## Estatísticas 

Ver mais detalhes em: 
https://rpubs.com/melinatarituba/353262
https://anderlerv.netlify.app/tabelas-com-stargazer/10/2018/


Descritivas
```
summary(df)
summary(df$var1, df$var2)
```

Exportar descritivas com `stargazer`             

   ``install.packages(“stargazer”)``                  
   `` library(stargazer)``                   

```
stargazer(df, type = "text", out = "Descritivas.txt")
stargazer(df, type = "html", out = "Descritivas.txt")
stargazer(df, type = "html",title="Descritivas", digits=3, out = "Descritivas.doc")
```

Tabela de estatísticas descritivas com `fields`
``install.package('fields')``
``library(fields)``
```
Tabela_descritivas<- cbind(stats(df$var1), stats(df$var2), stats(df$var3), stats(df$var4))
colnames(Tabela_descritivas)<- c("var1","var2", "var3", "var4")
round(Tabela_descritivas,3) ## Arredondando em 3 casas decimais
```

Outra maneira de obter as estatísticas descritivas com `pastecs`
``install.package('pastecs')``
``library(pastecs)``
```
stat.desc(df) 
stat.desc(df[,c("var1","var2","var3","var4")])
stat.desc(df[,c("var1","var2","var3","var4")], basic=TRUE, desc=TRUE, norm=TRUE, p=0.95)
```

Matriz de correlação
```
correlation.matrix <- cor(df)
round(correlation.matrix, 2)
```

Matriz de correlação
```
cor(df$var1, df$var2) #correlacao padrao é a de pearson
cor(df$var1, df$var2, method = "pearson")  #correlacao de pearson
cor(df$var1, df$var2, method = "kendall")  #correlacao de Kendall
cor(df$var1, df$var2, method = "spearman") #correlacao de spearman
cor(df) ## vai comparar todas as variaveis (obs: todas variaveis devem ser numericas)
cor(df[,c("var1","var2","var3","var4")])
```

Matriz de correlação
```
knitr::kable(cor(df))
```

Plotar matriz de correlação
```
corrplot(cor(df), method = "circle")
corrplot(cor(df), method = "square")
corrplot(cor(df), method = "color")
corrplot(cor(df), method = "number")
corrplot(cor(df), method = "pie")
corrplot(cor(df), method = "shade")
```

Plotar matriz de correlação par a par 
```
pairs(swiss)
```

Exportar matriz de correlação com `stargazer`
```
correlation.matrix <- cor(attitude[,c("var1","var2","var3")]) 
stargazer(correlation.matrix, title="Matriz de Correlação", type = "html")
```

Estatísticas descritivas por grupos
```
tapply(df$var1, df$var_grupos, summary)
```

Para ver proporções (table)
```
prop.table(table(df$var))
```


## Regressões Básicas Econometria 

Pooled ols estimador
``install.packages('plm')``
``library(plm)``
```
pooling <- plm(Y ~ X, data=df, model= "pooling") 
summary(pooling)
```

Between estimador
```
between <- plm(Y ~ X, data=df, model= "between") 
summary(between)
```

First differences estimador
```
firstdiff <- plm(Y ~ X, data=df, model= "fd")
summary(firstdiff)
```

Fixed effects ou within estimador
```
fixed <- plm(Y ~ X, data=df, model= "within")
summary(fixed)
```

Random effects estimador
```
random <- plm(Y ~ X, data=df, model= "random")
summary(random)
```

LM test for random effects versus pooled
```
plmtest(pooling)
```

LM test for fixed effects versus pooled
```
pFtest(fixed, pooling)
```

Hausman test for fixed vs random effects model
```
phtest(random, fixed)
```

## Strings


Substituir caracteres com a função                    
``install.packages('stringr')``               
``library(stringr)``                     
```
df$var <- str_replace(df$var, "-", "")
```

Remover caracteres específicos
> Nota: use “^x” se quiser excluir os que começam com X use “x$” sequiser excluir os que terminam com X
```
df_novo <- df[!grepl("E+", df$var),]  
df_novo <- df[!grepl("^X$", df$var),]
```

Remover linhas que contém  4 caracteres ou mais caracteres
```
df = df[(which(nchar(df$var) >= 4)),]
```

Padronizando strings retirando apenas alguns caracteres `stringr`
```
df$var <- str_replace(df$var, "-", "")
df$var <- str_replace(df$var, "\\[", "")  # Para remover [
df$var <- str_replace(df$var, "\\\\", "") # Para remover \
df$var <- str_replace(df$var, "\\.", "")  # Para remover . 
```

Remove todos caracteres *não-alfanuméricos* 
> Nota: remove caracteres especiais
```
df$var <- gsub("[[:punct:]]", "", df$var)
```

Remove todos caracteres *não-numéricos*
> Nota: remove  letras e caracteres especiais
```
df$var <- gsub("[^0-9]", "", df$var)
```

Remove todos caracteres numéricos
> Nota: remove somente números, (não remove caracteres especiais)
```
df$var <- gsub('[[:digit:]]+', '', df$var)
```

Remove caracteres especiais
> Nota: remove somente caracteres especiais acentos e outros)
```
df$var <- gsub("[^[:alnum:]]", " ", df$vra)
```

Converte letras minusculas para maiusculas com `magrittr`
``install.packages('magrittr')``
``library(magrittr)``
```
df %<>% mutate_if(is.character, toupper)
```

Remover linhas com a expressão exata
```
df <- subset(df, var!="expressao")
```

Remover os espaços iniciais e finais
```
df$var <- str_trim(df$var)                
```

Deixar somente os dois primeiros caracteres
```
df$var <- substr(df$var, 0, 2)
```

Replace (substituir) string
```
df$var <- str_replace(df$var, "mulher", "Homem")
```

Deixar somente alguns dígitos 
```
str_left <- function(string, n){ # Deixar somente os últimos dígitos
  substr(string, 1, n)}
df$var <- substrRight(df$var, 4) # Deixar os ultimos 4 digitos
df$var <- str_left(df$var, 4)    # Deixar os primeiros 4 digitos
df$var <- str_mid(x, 6, 9)       # Deixar os digitos 6 ao 9
```

Dividir coluna em várias com `splitstackshape`
``install.packages(‘splitstackshape’) ``
``library(splitstackshape)``
```
df<- cSplit(df, "var", "/") # ex: absde/12/asdf/2010
```

## Merge, Join, Append

Ver mais informações em: 
https://rpubs.com/CristianaFreitas/311735
[Fulljoin: Tudo sobre Joins (merge) em R](https://www.fulljoin.com.br/posts/2016-05-12-tudo-sobre-joins/)


**Append**
```
df_novo <- data.table::rbindlist(list(df1,df2))
#ou
df_novo <- rbind.data.frame(df1,df2,df3)
#ou
df_novo <- rbind(df1, df2)
```

**Merge**
```
# se os nomes das variaveis são iguais
df_novo <- merge(df1,df2, by=c('var1','var2'), all=TRUE)

# se os nomes das variaveis são diferentes
df_novo <- merge(df1,df2, by.x='var_x', by.y='var_y', all=TRUE) 
```

 **Left_join**
```
# Não é necessário definir as variáveis pois o comando identifica 
DF <- left_join(DF1,DF2) 
```


## Dummy (One Hot Encode)

Gerar dummy com ifelse
> Nota: se var for igual "abc" será atribuído ao valor de 1 caso contrário será 0
```
df$D_var <- ifelse(df$var=="abc",1,0)
df$D_Masculino <- ifelse(df$Sexo = 'M', 1,0)
df$D_Feminino  <- ifelse(df$Sexo = 'F', 1,0)
```

Gerar dummie com diversas condições
> Nota: se var1 for igual c(1,10,28) ou  var2 for igual a c(2,5,23:26) será atribuído ao valor de 1 caso contrário será 0
```
df <- df %>% mutate(D_var = ifelse(var1 %in% c(1,10,28), 1,                   
                            ifelse(var2 %in% c(2,5,23:26), 1,0)))
```

Gera dummies com `fastDummies`                         
``install.packages(‘fastDummies’) ``                                   
``library(fastDummies)``                           
> Nota: com fastaDummies basta selecionar uma variável categórica que ele gera as dummies.
```
df <- dummy_cols(df, select_columns =c("var"))
```

Gerar dummies  com `data.table` e `mltools`
``install.packages(‘mltools’) ``
``library(mltools)``
```
# Transformar em dummies as colunas 1 a 3
df <- one_hot(as.data.table(df[,1:3])) 
```

Codificar variáveis categóricas
```
# codifica as colunas 1,2 e 3 
df <- data.matrix(df[,1:3]) 
```

Gerar dummies a partir de uma variável categórica
```
df2 <- df %>% spread(var_categorica,var) 
```

Transformar colunas em dummies com  `fastDummies`
```
df <- dummy_cols(df, select_columns = "Idade_grp")
```


## Tarefas Prontas

Desabilitar notação científica
```
options(scipen = 999)
```

Apagar um arquivo salvo em uma pasta no computador
```
file.remove("D:/data.R")
file.remove("D:/data.RDS")
file.remove("D:/data.csv")
```

Remover observações duplicadas
```
# Ver quantas observações temo sem duplicados
df$var %>% unique() %>% length()  

# Remover duplicados.       
df2 <- df %>% filter(!duplicated(var))   
```

Remover duplicados baseado em duas variáveis
```
df_novo <- df[!duplicated(df[c('var1', 'var2')]),] 
#ou
df2 <- unique(df, by = "var1")
```

Obter o valor mínimo de duas colunas
```
df <- transform(df, new_Var = pmin(var1, var2))
```

Padronização de  escala das colunas do df
```
df_pad = scale(df[,1:4]) 
```

Normalização de dados (deixar em uma escala entr 0 e 1)
``install.packages("scales")``
``library(scales)``
```
df$var_Norm <- rescale(df$var) 
```

Gerar um lag e lead de uma variável observando os grupos 
```
df <-  df %>% group_by(id) %>% mutate(L1_var = dplyr::lag(var, n = 1, default = NA))
df <-  df %>% group_by(id) %>% mutate(F1_var = dplyr::lead(var, n = 1, default = NA))
```

Gerar (id) identificador a partir de uma ou mais colunas
```
df <- df %>% group_by(var1,var2) %>% mutate(id = cur_group_id())
```

Obter código IBGE das UF  a partir do código de municípios
```
Se o código ibge do municipios for de 7 dígitos 
df$Cod_UF <- substr(df$id7, 1, (nchar(df$id7)-5))

Se o código ibge do municipios for de 6 dígitos 
df$Cod_UF <- substr(df$id7, 1, (nchar(df$id7)-4))
```

Trabalhando com CPF
Nota:  os CPF tem zeros nos primeiros caracteres (zeros a esquerda), se importarmos os dados  como numéricos os zeros serão removidos, portanto uma boa pratica é trabalhar com eles em string

```
# Importar CPF como string
df <- read.csv("D:/dados.csv", colClasses=c(CPF="character"),)
```

Caso o CPF tenha sido convertido em numérico é possível adicionar os zeros a esquerda  convertendo para string

```
df$CPF <- str_pad(df$CPF, width = 11, pad = "0", side = "left")
```

Retirando ponto e traço de CPF
```
df$CPF <- gsub("\\W","",df$CPF)
```

Gerar classes etárias com `fastDummies`
```
df$Idade_grp <- df$Idade
df$Idade_grp <- ifelse((df$Idade>=1  & df$Idade<=10) , 'Idade_01_20',df$Idade_grp)
df$Idade_grp <- ifelse((df$Idade>=10 & df$Idade<=20) , 'Idade_10_20',df$Idade_grp)
df$Idade_grp <- ifelse((df$Idade>=21 & df$Idade<=30) , 'idade_21_30',df$Idade_grp)
df$Idade_grp <- ifelse((df$Idade>=31 & df$Idade<=40) , 'idade_31_40',df$Idade_grp)
df$Idade_grp <- ifelse((df$Idade>=41 & df$Idade<=50) , 'idade_41_50',df$Idade_grp)
df$Idade_grp <- ifelse((df$Idade>=51 & df$Idade<=60) , 'idade_51_60',df$Idade_grp)
df$Idade_grp <- ifelse((df$Idade>=61 & df$Idade<=70) , 'idade_61_70',df$Idade_grp)
df$Idade_grp <- ifelse((df$Idade>=71) , 'idade_71_mais',df$Idade_grp)
df <- dummy_cols(df, select_columns = "Idade_grp")
```

Balanceando classes em modelos de Machine Learning               
``install.packages(“DMwR”) ``       
``library(DMwR``        

```
set.seed(9560)
df_treino_balanceado <- SMOTE(var_desbalanceada ~., data=df_treino)
table(df_treino_balanceado$var_desbalanceada) 
prob.table(table(df_treino_balanceado$var_desbalanceada)
```

## Plotar Gráficos Lado a Lado

Ver mais detalhes de gráficos para R em:
 [https://www.r-graph-gallery.com/](https://www.r-graph-gallery.com/)
Dica: para executar chunk no Rmarkdown utilize o atalho Ctrl+Shift+Enter

```
# Gráfigco lado a lado com plot
split.screen(figs=c(2,2))
screen(1)
comandográfico(plot)
screen(2)
ggplot(VPL_outorga_final, aes(x=VPL_outorga)) + 
comandográfico(plot)
screen(3)
comandográfico(plot)
screen(4)
comandográfico(plot)
close.screen(all=TRUE)
```

```
# Gráfigco lado a lado ggplot
install.packages("egg")
library(egg)
grid.arrange(fig1, fig2, fig3, fig4, ncol=2, nrow=2)
```

## Gerar estações do ano a partir de uma variável do tipo date
```
# Criar função para gerar as estações do ano no hemisfério sul
toSeason <- function(dat) {
     stopifnot(class(dat) == "Date")
     scalarCheck <- function(dat) {
         m <- as.POSIXlt(dat)$mon + 1        
         d <- as.POSIXlt(dat)$mday           
         if ((m == 3 & d >= 23) | (m == 4) | (m == 5) | (m == 6 & d < 21)) {            # outono
             r <- 1
         } else if ((m == 6 & d >= 21) | (m == 7) | (m == 8) | (m == 9 & d < 23)) {     # inverno
             r <- 2
         } else if ((m == 9 & d >= 23) | (m == 10) | (m == 11) | (m == 12 & d < 21)) {  # Primavera
             r <- 3
         } else {
             r <- 4                                                                     # Verão
         }
         r
     }
     res <- sapply(dat, scalarCheck)
     res <- ordered(res, labels=c("Outono", "Inverno", "Primavera", "Verão"))
     invisible(res)
}

# Aplicar função
df <- data.frame(Date=df, Estacoes=toSeason(df$var_date))

# Renomear removendo o prefixo .Date
df <- df %>% rename_all(~stringr::str_replace(.,"Date.",""))
```

## Importar e Exportar Dados

> Nota: No Rstudio é possível importar bases de dados via menu.

Importar arquivo excel com `readxl`
```
df <- read_excel("D:/dados.xlsx", sheet = "Planilha1")
```

Importar base de dados do stata .dta com `haven`
```
read_dta(df, "df.dta")
```

Exportar base de dados do stata  .dta  com `haven`
```
write_dta(df, "df.dta")
```

Importar .csv de forma mais rápida com `data.table`
```
df_amostra <- fread(D:df.csv)
```

Exportar .csv com `data.table`
```
write.table(DT,"test.csv",sep=",")
```

Importar .csv  com read.table padrão
```
system.time(DF1 <- read.csv("test.csv"))        
```

Importar .csv com  `sqldf`                          
``install.packages('sqldf')``               
``require(sqldf)``                    
```
SQL_df <- read.csv.sql("test.csv",dbname=NULL))
```

Importar .csv com  `ff / ffdf`
``install.packages('ff')``
``require(ff)``
```
FF_df <- read.csv.ffdf(file="test.csv",nrows=n))  
```

Função para remover acentos
Fonte: [Retirar acentos de um Data Frame com a Linguagem R](https://www.thomazrossito.com.br/retirar-acentos-de-um-data-frame-com-a-linguagem-r/)
```
rm_accent <- function(str,pattern="all") {
  if(!is.character(str))
    str <- as.character(str)
  pattern <- unique(pattern)
  if(any(pattern=="Ç"))
    pattern[pattern=="Ç"] <- "ç"
  symbols <- c(
    acute = "áéíóúÁÉÍÓÚýÝ",
    grave = "àèìòùÀÈÌÒÙ",
    circunflex = "âêîôûÂÊÎÔÛ",
    tilde = "ãõÃÕñÑ",
    umlaut = "äëïöüÄËÏÖÜÿ",
    cedil = "çÇ"
  )
  nudeSymbols <- c(
    acute = "aeiouAEIOUyY",
    grave = "aeiouAEIOU",
    circunflex = "aeiouAEIOU",
    tilde = "aoAOnN",
    umlaut = "aeiouAEIOUy",
    cedil = "cC"
  )
  accentTypes <- c("´","`","^","~","¨","ç")
  if(any(c("all","al","a","todos","t","to","tod","todo")%in%pattern)) # opcao retirar todos
    return(chartr(paste(symbols, collapse=""), paste(nudeSymbols, collapse=""), str))
  for(i in which(accentTypes%in%pattern))
    str <- chartr(symbols[i],nudeSymbols[i], str)
  return(str)
}

# Aplicando a função
df_teste_sem_acento <- rm_accent(df_teste$Assunto)
```

Deflacionar variáveis monetárias
Fonte: [https://fmeireles.com/blog/rstats/deflacionar-series-no-r-deflatebr/](https://fmeireles.com/blog/rstats/deflacionar-series-no-r-deflatebr/)

> Nota: Primeiro passo é gerar uma variável do tipo date. Neste exemplo  é utilizada a variável Ano para gerar uma data do último dia do Ano.  Essa data será utilizada para a deflacionar.

```
# Gerar variável Data
df$Data <- 0
df$Data <- ifelse (df$Ano  == 2006, "2006-12-31", df$Data)
df$Data <- ifelse (df$Ano  == 2007, "2007-12-31", df$Data)
df$Data <- ifelse (df$Ano  == 2008, "2008-12-31", df$Data)
df$Data <- ifelse (df$Ano  == 2009, "2009-12-31", df$Data)
df$Data <- ifelse (df$Ano  == 2010, "2010-12-31", df$Data)
df$Data <- ifelse (df$Ano  == 2011, "2011-12-31", df$Data)
df$Data <- ifelse (df$Ano  == 2012, "2012-12-31", df$Data)
df$Data <- ifelse (df$Ano  == 2013, "2013-12-31", df$Data)
df$Data <- ifelse (df$Ano  == 2014, "2014-12-31", df$Data)
df$Data <- ifelse (df$Ano  == 2015, "2015-12-31", df$Data)
df$Data <- ifelse (df$Ano  == 2016, "2016-12-31", df$Data)
df$Data <- ifelse (df$Ano  == 2017, "2017-12-31", df$Data)
table(df)

# Converter a variável Data para o formato date com lubridate
df$Data <- as.Date(df$Data)

# Deflacionar com o pacote deflateBR utilizando o IPCA para o ano 2017
install.packages('deflateBR')
library(deflateBR)
df$var_monetaria_def <- ipca(var$var_monetaria_def,var$Data, "12/2017")

# Ver como era e como ficou
summary(df$var_monetaria)
summary(df$var_monetaria_def)
```

Gerar um banco de dados SQL com SQLite

Fonte:  [https://db.rstudio.com/databases/sqlite/](https://db.rstudio.com/databases/sqlite/)

Baixe o SQLiteBrowser para conferir após o procedimento:
[DB Browser for SQLite (sqlitebrowser.org)](https://sqlitebrowser.org/)

```
#Instalando SQLite            
install.packages("RSQLite")               

# install.packages("devtools")                     
devtools::install_github("rstats-db/RSQLite")                

# Carregar pacote            
library(DBI)            

# Definir pasta de trabalo (onde será salvo o arquivo.db)
setwd("D:/")

# Criando uma conexão com RSQLite e especificar o nome do banco de dados
con <- dbConnect(drv=RSQLite::SQLite(), dbname="db_sqlite.db")

# Importar dados de uma tabela excel por exemplo
library(readxl)
TB_Excel <- read_excel("D:/TB_Excel.xlsx")

# Adicionar a tabela ao db_sqlite
dbWriteTable(con, "TB_Excel ",  TB_Excel )

# Listar as tabelas do banco SQLite
dbListTables(con)

# Ver colunas de uma tabela no SQLite
dbListFields(con, "TB_Excel")

# Fazer uma query no SQLite
res <- dbSendQuery(con, "SELECT * FROM TB_Excel")
dbFetch(res)

# Limpar resultados de um consulta
dbClearResult(res)

# Ddesconectar da base
dbDisconnect(con)

# Carregar a tabela TB_Excel do banco de dados para o R
con <- dbConnect(drv=RSQLite::SQLite(), dbname="db_sqlite.db")
TB_Excel <- dbReadTable(con, "TB_Excel")
```

Webscrap por meio de um API do governo

Nota: basicamente o que esses comandos fazem  é pegar os códigos das estações meteorológicas e substituir no comando que acessa o site, baixar  os dados meteorológicos do inmet e salvar em .csv)

```
# Carregar pacotes
library(jsonlite)
library(readr)
library(dplyr)

# Definir pasta de trabalo (onde será salvo os arquivos .csv)
setwd("D:/")

# Definir um vetor com o código das estações meteorológicas 
> Obs: tem aproximadamente 912 estações, consultar no site do imet
x <- c(83512,83659,83704)
Estacao = list()
Tabela_Estacao = list()

for(cod in x) {
  Estacao[[as.character(cod)]] <- fromJSON(paste0("https://apitempo.inmet.gov.br/estacao/2000-01-01/2020-12-31/", cod))
  Tabela_Estacao[[as.character(cod)]]<- as_data_frame(Estacao[[as.character(cod)]])
  write.csv(Estacao[[as.character(cod)]], paste0('Tabela_Estacao_', cod, '.csv'))
}
```

## Referências 
* [Bóson Treinamentos em Ciência e Tecnologia](http://www.bosontreinamentos.com.br/programacao-em-r/operadores-logicos-e-operadores-de-comparacao-em-r/)

* [https://statsandr.com/blog/outliers-detection-in-r/](https://statsandr.com/blog/outliers-detection-in-r/)

* [https://rpubs.com/melinatarituba/353262](https://rpubs.com/melinatarituba/353262)  

* [https://anderlerv.netlify.app/tabelas-com-stargazer/10/2018/](https://anderlerv.netlify.app/tabelas-com-stargazer/10/2018/)

* [https://rpubs.com/CristianaFreitas/311735](https://rpubs.com/CristianaFreitas/311735)  

* [Fulljoin: Tudo sobre Joins (merge) em R](https://www.fulljoin.com.br/posts/2016-05-12-tudo-sobre-joins/)

* [https://www.r-graph-gallery.com/](https://www.r-graph-gallery.com/)

* [Retirar acentos de um Data Frame com a Linguagem R](https://www.thomazrossito.com.br/retirar-acentos-de-um-data-frame-com-a-linguagem-r/)

* [https://fmeireles.com/blog/rstats/deflacionar-series-no-r-deflatebr/](https://fmeireles.com/blog/rstats/deflacionar-series-no-r-deflatebr/)

* [https://db.rstudio.com/databases/sqlite/](https://db.rstudio.com/databases/sqlite/)

* [DB Browser for SQLite (sqlitebrowser.org)](https://sqlitebrowser.org/)

