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

Instalar versão mais antiga de um pacote
```
Exemplo 
install.packages("fixest", version='0.8.4')
```

Atualizar pacotes
```
old.packages() 
update.packages()
update.packages(checkBuilt=TRUE, ask=FALSE)
```

Carregar pacotes
```
#library(package)
#require(pacote)
```

Descarregar packages
```
detach('package:pacote', unload =TRUE)
```

Verificar versão do pacote
```
packageDescription("pacote")
```

Package ``pacman`` para instalar e carregar pacotes
> O pacman verifica se os pacotes estão instalados, se não estão, ele instala e carrega automaticamente.
```
install.packages('pacman')
library(pacman)

# Exemplos de aplicação
p_load(ggplot2, dplyr, stringr)    # Install & load packages
p_unload(ggplot2, dplyr, stringr)  # Unload packages
p_update(update = FALSE)           # Check for outdated packages
p_update()                         # Update all packages
```

Instalando e carregando pacotes automaticamente
```
if(!require(pacman)){install.packages("pacman")}
p_load(ggplot2, dplyr, stringr) 
```

Limpar console e objetos
```
rm(list=ls())
```

Definir pasta/diretório de trabalho
```
setwd ("D:/")
```

Abrir diretório de trabalho
```
Abrir_Diretorio <- function(directory = getwd()){
  system(sprintf('open %s', shQuote(directory)))
}
opendir("D:/")
```

Utilizar uma função específica de um pacote sem carrega-lo
```
(pacote)::função()
```

Acessar documentação
> Obs: é possível acessar o help de uma função, pacote selecionando a função com mouse + F1
```
help('pacote')
help(package='pacote')
```

Help função 
> Também é possível fazer, selecionando a função, package etc + F1
```
?comando
help('comando')
help('comando', package='pacote')
```

## Configurações de Memória e Processador.

Expandir memória
> Obs: também é possível selecionar a quantidade memória desejada substituindo os valores em mb no lugar do 9....
```
memory.limit (9999999999) 
```

Checar quantidade de memória selecionada
```
memory.size()
```

Limpar memória (itens ocultos mas não apaga os objetos) 
```
gc() 
```

Escolhendo quantos threads do CPU serão utilizadas
> Obs: esse comando é do pacote `data.table`
```
setDTthreads(20) 
```

## Visualização de Dataframes

Visualizar todo o dataframe
```
View(df)
```

Visualizar 100 linhas do dataframe
```
View(head(df, n=100))
```

Visualizar algumas colunas do dataframe
```
view(df[,c("var_1", "var_2", "var_3")])
```

Visualizar 100 linhas de algumas colunas
```
view(head(df[,c("var_1", "var_2", "var_3")], n=100))
```

Visualizar algumas colunas com data.table
```
view(df[,.(var_1, var_2, var_3)])
```

Visualizar nome das colunas do df
```
names(df)
colnames(df)
```

Visualizar nome de colunas a partir do número da coluna
```
names(df)[c(1:4,9,20)]
```

Visualizar número atribuido a cada coluna a partir do nome
```
Col_number <- which(names(df) %in% c("var1","var2","var3","var4"))
```

Visualizar prévia do df
```
df
```

Visualizar as primeiras linhas do df
```
head(df) 
head(df, n==10) # Visualizar as primeiras 5 linhas
```

Visualizar as últimaslinhas do df
```
tail(df) 
tail(df, n==5) # Visualizar as últimas 5 linhas
```

Visualizar  dimensões do dataframe (colunas e linhas)
```
dim(df)
```

Visualizar detalhes das variáveis do df
```
str(df)
```

Visualizar classes das colunas e outras informações
```
glimpse(df)
```

Visualizar classe de uma coluna no df (numérico, string, etc.)
```
class(df$var1)
```

Visualizar classe de um objeto (numeric, matrix, data.frame, etc,)
```
class(df)
```

Visualizar classe de todas colunas
```
lapply(df,class)
```

Listar objetos
```
ls(df)
```

Visualizar e plotar colunas do df rapidamente    
Ver mais em: https://livebook.datascienceheroes.com/appendix.html#funmodeling-quick-start

```
# Instalar package 
if(!require(funModeling)){install.packages("funModeling")}

# Ver quantidades de zeros missings etc.
df_status(df)

# Plotar todas variáveis númericas do df
plot_num(df, path_out = ".")

# Plotar todas variáveis categóricas do df (devem estar em fator)
freq(df)
```


## Manipulando Dataframes

Ordenando alfabeticamente as colunas do df
```
df <- df %>% dplyr::select(order(colnames(df)))
```

Ordenando df com as colunas desejadas
> Nota: isso é um subset, portando, se não colocar o nome da coluna ela será excluida do df
```
df <- df %>% dplyr::select(c("var_3", "var_1", "var_2")) 
```

Ordenar coluna do df
```
# Ordenar de forma crescente
df <- df [order(df$var1),]

# Ordenar de forma decrescente
df <- df [order(df$var1),decreasing = (TRUE),] 
```

Ordenar colunas do df
```
df <- df %>%  dplyr::select(sort(current_vars()))
```
Escolher qual será a primeira coluna do df
```
df <- df %>% dplyr::relocate(var)
```

Gerar amostra com o comando `subset`
```
# Gerar amostra apenas com as colunas var1 var2 var3
df_novo <- subset(df, select = c(var1, var2, var3)) 

# Gerar amostra sem as colunas var1 var2 var3
df_novo <- subset(df, select = -c(var1, var2, var3)) 

# Utilizando nomes com espaços
df_novo <- subset(df, select = -c(`var 1`, `var 1`, `var 1`)) 
```

Dropar colunas contendo determinada expressão
```
df_novo <- subset(df, select = c(!grepl("^Expressão",names(df))))
```

Gerar amostra  com package `data.table`
> Obs: só funciona se o objeto for um data.table
```
# Gerar amostra apenas com as colunas var1 var2 var3
df_novo <- df[,.(var1, var2, var3)]

# Remover colunas var1 var2 var3
df_novo <- df[, c("var1", "var2", "var3") := NULL]

# Remover ids que aparecem apenas uma vez no painel de dados (data.table)
setDT(df)[, if(.N>1) .SD, by = id]

# Outros Subsets com data.table
df <- df[!(df$var=="var1"),]
df <- df[(df$Ano>=2009 & df$Ano==2017),]

# Subset com muitas condições (deixar se var_1 contem as linhas A até J 
df2 <- df[(df$var_1 %in% c("A", "B", "C", "D", "E", "F", "G", "H", "I", "J")),]
```			     
			     
Gerar amostra com período delimitado
```
df_novo <- subset(df, Ano>=2009)
df_novo <- subset(df, Ano>=2009 & Ano<=2018)
```

Gerar amostra com as primeiras 1000 linhas do df
```
df_novo  <- head(df, n=1000)
```

Reshape de long para wide (painel)
```
df_wide = reshape(data = df_long, idvar = "id", 
v.names= c("var1","var2","var3"), sep = "_", 
timevar = "Ano", times = c(2000,2001,2002,2003), 
direction = "wide")
```

Reshape de wide para long (painel) (data.table)
```
df_long <- melt(setDT(df), id.vars = c("Código"), variable.name = "year")
```

Reshape de wide para long (painel) com varias colunas (data.table)
```
df_long  <- melt(setDT(df), id.vars = c("id"),
                            variable.name = "year",
                            measure = patterns("^Nome_1", 
                                               "^Nome_2", 
                                               "^Nome_3"), 
                            value.name = c("Nome_1", 
                                           "Nome_2", 
                                           "Nome_3"))
```

Clonar coluna do df com package `dplyr`
```
df <- df %>% dplyr::mutate(var_clone1 = var1) %>%   
             dplyr::mutate(var_clone2 = var2)
```

Clonar coluna do df
```
df$var_clone1 <- df$var1
```

Deixar dfs selecionados
```
rm(list=setdiff(ls(), c("df1", "df2", "df3")))

```

Remover df ou outros objetos
```
rm(df)
```

Remover todos os objetos que comtém no nome "df"
```
rm(list = ls()[grepl("df", ls())])
```

Clonar df
```
df_novo <- df_antigo
```

Renomear colunas
```
df <- rename(df, c("nome_novo_1" = "nome_antigo_1",
                   "nome_novo_2" = "nome_antigo_2"))
```

Renomear múltiplas colunas utilizando seu indice (número)
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

Adicionar prefixo ou sufixo nas colunas
```
# Prefixo
colnames(df) <- paste("ln", colnames(df), sep = "_")

# Sufixo para as 10 primeiras colunas
colnames(df)[1:10] <- paste(colnames(df)[1:10], "texto", sep = "_")
```

Dropar (deletar) colunas do df
```
df$var1  <-NULL
df$var2 <- df$var3 <-NULL
```

Gerar nova coluna no df
```
df$var0 = 0
df$var3 = (df$var1 + df$var2)
df$var4 = (df$var1 * df$var2)
df$var5 = (df$var1 / df$var2)
df$var6 = (df$var1)^2 
```

Gerar nova coluna a partir da soma de duas colonas desconsiderando os missings
```
df$var_total<- rowSums(df[,c("var1", "var2")], na.rm=TRUE)
```

Remover missings das colunas 2 a 10
```
df <- df[complete.cases(df[ , 2:10]),]
```

Gerar nova coluna com o logaritmo natural
> Obs: esse comando gera o logaritmo natural
```
df$log_var1 <- log(df$var1)
```

Gerar múltiplas colunas com logaritmo natural
> Obs: depois basta renomear as colunas (recomendo adicionar somente o prefixo com:
>  ``colnames(df) <- paste("ln", colnames(df), sep = "_")``
```
# Criar uma função para gerar o logaritmo natural
log_natural <- function(x) {log(x)}

# Aplicar função log_natural nas colunas 1 a 10
df[,1:10] <- as.data.frame(lapply(df[,1:10], FUN = function(x) {sapply(x, FUN = log_natural)}))

# Aplicar função log_natural nas colunas 1 a 10 e 12 ao 20
df[,c(1:10, 12:20)] <- as.data.frame(lapply(df[,c(1:10, 12:20)], FUN = function(x) {sapply(x, FUN = log_natural)}))

# Criar função para gerar o logaritmo natural + 1 (para quando temos zeros na coluna)
log_mais_um <- function(x) {log(x + 1)}

# Aplicar função log_mais_um nas colunas 1 a 10
df[,1:10] <- as.data.frame(lapply(df[,1:10], FUN = function(x) {sapply(x, FUN = log_mais_um)}))

# Aplicar função log_mais_um nas colunas 1 a 10 e 12 ao 20
df[,c(1:10, 12:20)] <- as.data.frame(lapply(df[,c(1:10, 12:20)], FUN = function(x) {sapply(x, FUN = log_mais_um)}))
```

Adicionar label a uma coluna com pacote `Hmisc`
```
# Instalar package 
if(!require(Hmisc)){install.packages("Hmisc")}
```

```
label(var[[1]]) <- "var descrição"
```

Converter coluna numérica para string. objeto do tipo `datatable`
```
df <- as.data.table(apply(df, "var", as.character))  
class(df$var)
```

Converter coluna string para numérico. objeto do tipo `datatable`
```
df <- as.data.table(apply(df, "var", as.numeric))  
class(df$var)
```

Converter varias colunas em fator umerico ou  string etc.
```
col_names <- c("var_1", "var_2", "var_3", "var_4")
df[,col_names] <- lapply(df[,col_names], factor)
```

Converta strings BRL (valores com Cifrão) para númerico
```
reais()
```

Converter coluna para numérico (cuidado se a coluna for factor irá gerar problemas)
```
df$var1 <- as.numeric(df$var1)
```

Converter coluna factor para numérico (primeiro converter para character após para numérico)
```
df$var1 <- as.character(df$var1) 
df$var1 <- as.numeric(df$var1)
```

Converter conjunto de colunas para numérico com `dplyr`
```
df <- df %>% dplyr::mutate_at(c(1:10), as.numeric)
```

Converter conjunto de colunas para factor com `dplyr`
```
df <- df %>% dplyr::mutate_at(c(1:10), as.factor)
```

Converter todo df para numérico
```
df = as.data.frame(sapply(df, as.numeric))
```

Converter coluna para factor
```
df$var1 <- factor(df$var1)
```

Converter varias colunas para factor
```
col_names <- c("var_1", "var_2", "var_3") # definindo 3 colunas
col_names_all <- colnames(df) # obter todos os nomes das colunas
df[,col_names] <- lapply(df[,col_names], factor)
```

Converter colunas para numérico, utilizando o indice(número)
```
df <- df %>% dplyr::mutate_at(c(1:15), as.numeric)
```

Substituir (replace) inf para zero com `dplyr`
    Nota: inf é a abreviação de infinito
```
fortify.zoo(log_ret) %>% dplyr::mutate_all(function(x) ifelse(is.infinite(x), 0, x))
# ou
df$var[which(!is.finite(df$var))] <- 0
```

Substituir inf e -inf por NA com data.table
```
invisible(lapply(names(df),function(.name) set(df, which(is.infinite(df[[.name]])), j = .name,value =NA)))

# Substituir inf de todas as colunas
is.na(df) <- sapply(df, is.infinite)
```

Gerar coluna categórica com `dplyr`
> Exemplo: suponha que temos uma coluna categórica com difentes tipos de produtos e queremos gerar uma nova coluna categóricas agregando esses produtos. A saída deste comando resulta e uma variável com 4 categorias, 0,1,2,3,4
```
df <- df %>% dplyr::mutate(var_cat = ifelse(Var_Produto %in% c(1:24,28,35,99), 1,
                                     ifelse(Var_Produto %in% c(26,34), 2 ,
                                     ifelse(Var_Produto %in% c(25,32,33), 3, 0))))
```

Arredondando valores de uma ou varias colunas 
> Nota: o comando arredonda com 2 casas decimais.
```
df %>% dplyr::mutate_at(vars(var1), funs(round(., 2)))
df %>% dplyr::mutate_at(vars(var1, var2, va3), funs(round(., 2)))
```

Arredondar valores de todas as colunas exceto a var1
```
df %>% dplyr::mutate_at(vars(-var1), funs(round(., 2)))
```

Arredondar valores de todas as colunas cujo nome começa por VAR
```
df %>% dplyr::mutate_at(vars(starts_with("VAR")), funs(round(., 2)))
```

Arredondar valores apenas das colunas numéricas
```
mydf %>% dplyr::mutate_if(is.numeric, ~round(., 2))
```

Agregar dados por id com `dplyr`
> Obs: as colunas do agrupamento devem ser fatores
```
df_novo <- df %>% dplyr::group_by(as.factor(id, Ano)) %>%  
                  dplyr::summarise(Max_var   = max(var),
                                   Media_var = mean(var),
                                   Total_var = sum(var),
                                   Min_var = min(var),
				   Contagem_distinta = n_distinct(var))
```

Adicionar coluna com valores agregados por id com `dplyr`
```
df <- df %>% dplyr::group_by(id) %>%  
             dplyr::mutate(Total = sum(var1, na.rm=TRUE),
                           Contagem = n_distinct(var2))
```

Agregar dados por id e Ano com `data.table`
```
df_novo <- setDT(df)[ , .(Max_var   = max(var, na.rm=TRUE),
                          Media_var = mean(var, na.rm=TRUE),
                          Min_var   = min(var, na.rm=TRUE),
                          Total_var = sum(var, na.rm=TRUE)), 
                          by =c("id", "Ano")]
```

Agregar dados por id e Ano com `data.table` e gerar novas colunas
```
setDT(df)[ , .(Max_var   := max(var, na.rm=TRUE),
               Media_var := mean(var, na.rm=TRUE),
               Min_var   := min(var, na.rm=TRUE),
               Total_var := sum(var, na.rm=TRUE)), 
               by =c("id", "Ano")]
```

Adicionar coluna com valores agregados por id com `data.table`
```
df <- df[, ":="(Total = sum(var1, na.rm=TRUE), 
                        Contagem = uniqueN(var2)), 
                        by =c("id")]
```		
		
Contar valores únicos de uma coluna agrupando por id
```
df_novo <- df %>% dplyr::group_by(id) %>% dplyr::summarize(Total = n_distinct(var), Count = n())
```

Contar linhas sem missings por id 
```
df2 <- df1 %>% dplyr::group_by(id) %>% dplyr::mutate(contagem = sum(!is.na(var)))
```

Contar o número de caracteres de uma coluna
```
df$Length <- str_count(df$var)
table(df$Length)
```

Agregar dados utilizando a soma
```
df_novo <- summarise(df, total_var = sum(var))
```

Replace missings com valores de outras colunas `dplyr`
```
df <- df %>% dplyr::mutate(var_1 = coalesce(var_1, var_2, var_3, var_4, var_5))
```

Replace com ifelse 
> Nota: Fazer replace na variável var1, se var1 <0, então var1 receberá o valor 1, caso contrário permanecerá inalterada
```
df$var1 = ifelse(df$var1 <0, 1, df$var1)
```

Replace (substituir)
```
df$var1[df$var2 == 1] <- 1   # Replace para 1 em var1 se var2 ==1
df$var1[df$var1 == 0] <- NA  # Replace de 0 para NA
[df$var2 == 2] <- 1          # Replace para 1 se var2 ==2

# Substiuir infinitos por missings
df$var[is.infinite(df$var)] <- NA 

# Substiuir missings por zero
df$var[is.na(df$var)] <- 0 

# Replace Para muitas colunas
df[,  1:10][ df[,  1:10] == 0 ] <- NA # fazer replace de 0 para NA
```

Imputar missings utilizando `imputeTS`  
ver mais:
https://cran.rstudio.com/web/packages/imputeTS/vignettes/Cheat_Sheet_imputeTS.pdf
https://cran.r-project.org/web/packages/imputeTS/readme/README.html

```
# Instalar package 
if(!require(imputeTS)){install.packages("imputeTS")}  
```

```
# Atribuir zeros para todo os missings do df
df <- na_replace(df, 0)

# Atribuir zeros para todo os missings de uma coluna
df$var <- na_replace(df$var, 0)

# Atribuir zeros para todo os missings de vetor de colunas
df[, 1:20] <- na_replace(df[, 1:20], 0)

cols <- c("var1", "var2", "var3", "var4")
Col_number <- which(names(df) %in% cols)

# Imputar a mediana por id e Ano
df <- df %>% group_by(id, Ano) %>%  na_mean(df[, Col_number], option = "median")

# Imputar a media por id e Ano
df <- df %>% group_by(id, Ano) %>%  na_mean(df[, Col_number])

# Imputar a moda por id e Ano
df <- df %>% group_by(id, Ano) %>%  na_mode(df[, Col_number])

# Imputar com interpolação por id e Ano
df <- df %>% group_by(id, Ano) %>%  na_interpolation(df[, Col_number], option = "spline")

# Imputar com valores aleatórios por id e Ano
df <- df %>% group_by(id, Ano) %>%  na_random(df[, Col_number])

# Imputar zeros por id e Ano
df <- df %>% group_by(id, Ano) %>%  na_replace(df[, Col_number], 0)

# Remover missings por id e Ano
df <- df %>% group_by(id, Ano) %>%  na_remove(df[, Col_number])

# Outras funções
ggplot_na_distribution, ggplot_na_intervals, ggplot_na_gapsize, ggplot_na_imputations
Também é possível adicionar sazonalidade e etc
```

Replace de todas colunas com 'nan' para 'NA'
```
invisible(lapply(names(df),function(.name) set(df, which(is.nan(df[[.name]])), j = .name,value =NA)))
```

Replace virgula e ponto
```
# Replace virgula para ponto
df$var <- gsub(",", "\\.", df$var)

# Replace ponto para virgula
df$var <- gsub("\\.", ",", df$var)
```

Replace virgula para ponto (outra forma)
```
df <- format(df, decimal.mark=",") %>% as.data.frame()
df = as.data.frame(sapply(df, as.numeric))
```

Replace valores de uma coluna, se outra coluna contém a expressão.
> Exemplo: suponha que a coluna Municipio contém o nome do municipio underline e a Sigla do UF, bastaria criar uma Coluna UF e preender os valores desta forma
```
# Municípios que terminam com RS
df$UF[which(grepl("RS$", df$Municipio))] <- "RS"

# Municípios  que iniciam com RS
df$UF[which(grepl("^RS", df$Municipio))] <- "RS" 
```

Remover primeira e última linha
```
df <- df[-1, ]
```

Gerar categorias a partir de uma variável númericas  
```
# Instalar package 
if(!require(funModeling)){install.packages("funModeling")} 
```
          
```
# Gerar 5 categorias
df$var_5cat = equal_freq(df$var, n_bins = 5)
```

Transpor linha para colunas
```
df <- as.data.frame(t(df))
```
##  Colunas do Tipo Data (Date)

Converter coluna para date com `lubridate`
> Nota: ymd representa a ordem em que a data deve estar, ou seja:
 y=ano, m=mês, d=dia
```
df$Data_var <- ymd(paste(df$Data_var))
```

Extrair o ano da coluna date
```
df$Ano <- format(as.Date(df$Data, format="%d/%m/%Y"),"%Y")
```

Extrair o mês da coluna date
```
df$Ano <- format(as.Date(df$Data, format="%d/%m/%Y"),"%m")
```

Extrair apenas o dia de uma coluna do tipo date
```
df$Ano <- format(as.Date(df$Data, format="%d/%m/%Y"),"%d")
```

Dividir coluna em várias com `splitstackshape`   
```
# Instalar package 
if(!require(splitstackshape)){install.packages("splitstackshape")}
```
 
```
df<- cSplit(df, "var", "/") # ex: absde/12/asdf/2010
```

## Missings Values

Ver total de missings das colunas de um dataframe
```
summary(df$var)
colSums(is.na(df))
```

Criar uma matrix com o total de missings (fica melhor para visualizar)
```
Missings <- as.matrix(colSums(is.na(df)))
print(Missings)
```

Visualizar linhas com missings
```
View(subset(df, select=c("id", "Ano", "var_missing"), is.na(var_missing)))
```

Criar uma matrix com o total de celulas vazias
```
empty <- as.matrix(colSums(df==""))
print(empty)
```

Fazer resumo de missings e zeros   
                       
```
if(!require(funModeling)){install.packages("funModeling")} 
df_status(df)
```

Gerar tabela resumo de missings, zeros e vazios
```
resumo <- df_status(df)
resumo$vazias <- apply(df, 2, function(x) length(which(x == '')))
resumo$OBS_Total <- nrow(df)
resumo$perc_vazias = df$vazias / df$OBS_Total
```

Ver total de células vazias 
```
# Ver células vazias de uma coluna string
vazias <- length(which(df$var == ''))
vazias

# Ver células vazias de todas colunas
vazias <- apply(df, 2, function(x) length(which(x == '')))
vazias 
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
df <- df %>%  dplyr::group_by(id) %>%  dplyr::mutate_at(vars(var1, var2, var3), 
                                                   list(inter = ~na.approx(., na.rm = FALSE)))
```

Preencher susbstituir missings com valores anterior ou posterior                 
ver mais em https://tidyr.tidyverse.org/reference/fill.html
```
df <- df %>% dplyr::group_by(id) %>%  dplyr::fill(c(VAR_1, VAR_2), .direction = "downup")
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
df <- df %>% dplyr::group_by(id) %>% dplyr::mutate(var1_nova = impute.mean(var1), 
                                                  var2_nova = impute.mean(var2)) 
```

Substituir missings pela mediana agrupada por id com `dplyr`
```
impute.median <- function(x) replace(x, is.na(x), median(x, na.rm = TRUE))
df <- df %>% dplyr::group_by(id) %>% dplyr::mutate(var1_nova = impute.median(var1), 
                                                   var2_nova = impute.median(var2)) 
```

Substituir missings pela média e mediana agrupada por id com `datatable`
```
df <- as.data.table(df)
df <- df[is.na(df$var), "var_nova"] <- mean(na.omit(df$var))
df <- df[is.na(df$var), "var_nova"] <- median(na.omit(df$var))
```
Substituir missings pela média e mediana agrupada por id com `datatable` para muitas colunas
```
cols <- c("var_1", "var_2", "var_3", "var_4")

df_novo <- df[, (cols) := lapply(.SD, function(x) nafill(x, type = "const", fill = median(x, na.rm = TRUE)))
                   , by = var_grupo
                   , .SDcols = cols][]
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
df$Var_1 <- ifelse(is.na(df$Var_1), df$Var_2, df$Var_1)
```

Atribuindo zero a todos os missings com `imputeTS`  
    
```
# Instalar package
if(!require(imputeTS)){install.packages("imputeTS")}  

# Atribuir zeros para todo os missings do dataframe
df <- na_replace(df, 0)

# Atribuir zeros para todo os missings de uma coluna
df$var <- na_replace(df$var, 0)

# Atribuir zeros para todo os missings de vetor de colunas
df[, 1:20] <- na_replace(df[, 1:20], 0)
```

Atribuindo zero a todos os missings
> Nota: fazer replace para 0 em var1 se var2 ==NA (missings)
```
df$var[is.na(df$var)] <- 0 
```

Remove colunas com mais de 50% NA
```
df[, which(colMeans(!is.na(df)) > 0.5)]
```

Remove linhas com mais de 50% NA
```
df[which(rowMeans(!is.na(df)) > 0.5), ]
```

Remove colunas e linhas com mais de 50% NA
```
df[which(rowMeans(!is.na(df)) > 0.5), which(colMeans(!is.na(df)) > 0.5)]
```

Remover linhas que apresentam apenas missings com base em varias colunas
```
df_novo <- df[!(is.na(df$var1)) | !(is.na(df$var2)) | !(is.na(df$var3)),]
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
# grafico de dispersão condicional a variável de var_tratamento
xyplot (df$var1 ~ df$var2 | df$var_tratamento) 
```

Plotar boxplot
```
boxplot(df$var1)
boxplot(df$var1, outline = TRUE)
boxplot.stats(df$var1)$out 
outlier_var1 = df[df$var1< 0, ]
outliers_var1 = df[df$var1> 10000,]
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

Histograma de todas as colunas
```
for(i in c(2,4:ncol(df))){
  hist(df[,i], main = paste('Histogram of', colnames(df)[i]), xlab = colnames(df)[i])
}
```

Boxplot com `ggplot2`

```
# Instalar package
if(!require(ggplot2)){install.packages("ggplot2")}  

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

Identificar outliers                                  
``library(funModeling)``      
Ver mais em: http://pablo14.github.io/funModeling/articles/funModeling_quickstart.html   
    
Método **HAMPEL**                         
Detalhes:                     
O limite inferior é median_value - 3*mad_value. Todos os valores abaixo são considerados outliers.            
O limite superior é median_value + 3*mad_value. Todos os valores acima são considerados outliers.          
O parâmetro chamado k_mad_value e seu valor padrão é 3. O valor k_mad_value pode ser modificado.            
Quanto mais alto o valor k_mad_value, mais altos são os limites.               

Podemos acessar a função interna usada prep_outlierspara calcular o limite de Hampel:
	
```
hampel_outlier(df$var)
hampel_outlier(df$var, k_mad_value = 6) 
```

Método de **TURKEY**         
Detalhes:          
Este método marca outliers usando os quartis, Q1, Q2 e Q3, onde Q1 é indescritível no 25º percentil,
 Q2 no 50º percentil (também conhecido como mediana) e Q3 é o 75º percentil.

O intervalo interquartil (IQR) é calculado fazendo Q3 - Q1.

O limite inferior é: Q1 - 1,5 * IQR. Todos os valores abaixo são considerados outliers.
O limite superior é: Q1 + 1,5 * IQR. Todos os valores acima são considerados outliers.

O valor 3 é para detectar o limite “extremo”. Este método vem do gráfico de caixa, 
onde o multiplicador é 1,5. Isso faz com que muitos mais valores sejam marcados como outliers.

```
tukey_outlier(df$var)
```


## Estatísticas 

Ver mais detalhes em: 
https://rpubs.com/melinatarituba/353262
https://anderlerv.netlify.app/tabelas-com-stargazer/10/2018/

Estatisticas Descritivas com  funModeling

```
# Instalar package
if(!require(funModeling)){install.packages("funModeling")} 

# Estatisticas descritivas de todo o data.frame
profiling_num(df)

# Estatisticas descritivas de apenas uma coluna
profiling_num(df$var)

# Estatisticas descritivas (arredondando para 3 casas decimais)
profiling_num(df) %>% dplyr::mutate_if(is.numeric, ~round(., 3))
```

Estatisticas Descritivas com funções básicas do R
```
# descritivas basicas
summary(df)
summary(df$var1, df$var2)

# Gerar dataframe de descritivas
descritivas <- data.frame(unclass(summary(df)), check.names = FALSE, stringsAsFactors = FALSE)
view(descritivas)

# Descritivas por grupos
tapply(df$var1, df$var_grupos, summary)
```

Estatisticas Descritivas com `stargazer`                        
```
# Instalar package
if(!require(stargazer)){install.packages("stargazer")} 

stargazer(df, type = "text", out = "Descritivas.txt")
stargazer(df, type = "html", out = "Descritivas.txt")
stargazer(df, type = "html",title="Descritivas", digits=3, out = "Descritivas.doc")
```

Estatisticas Descritivas com `fields`
```
# Instalar package
if(!require(fields)){install.packages("fields")} 

Tabela_descritivas<- cbind(stats(df$var1), stats(df$var2), stats(df$var3), stats(df$var4))
colnames(Tabela_descritivas)<- c("var1","var2", "var3", "var4")
round(Tabela_descritivas,3) ## Arredondando em 3 casas decimais
```


Estatisticas Descritivas com `pastecs`
```
# Instalar package
if(!require(pastecs)){install.packages("pastecs")} 

stat.desc(df) 
stat.desc(df[,c("var1","var2","var3","var4")])
stat.desc(df[,c("var1","var2","var3","var4")], basic=TRUE, desc=TRUE, norm=TRUE, p=0.95)

# Descritivas com arredondamento
Descritivas <- as.data.frame(t(stat.desc(df) %>% dplyr::mutate_if(is.numeric, ~round(., 3))))

# Exportando Descritivas com `openxlsx`
# Instalar package
if(!require(openxlsx)){install.packages("openxlsx")} 

Descritivas <- as.data.frame(t(stat.desc(df) %>% dplyr::mutate_if(is.numeric, ~round(., 3))))
write.xlsx(Descritivas, "D:/Descritivas.xlsx", row.names = TRUE)

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

Gerar correlalograma 
                     
```
# Instalar package
if(!require(DescTools)){install.packages("DescTools")} 
if(!require(corrplot)){install.packages("corrplot")}   

corelacao <- DescTools::PairApply(df, DescTools::CramerV)
corrplot::corrplot(corelacao)
```
Para ver proporções (table)
```
prop.table(table(df$var))
```

tabular coluna binária
```
# para uma coluna
table(df$var)

# loop com varias colunas
apply(df[,1:10],2,function(x) table(x))

# loop com varias colunasa pedindo por ano
apply(df[,1:10],2,function(x) table(x, df$Ano))
```

Tabular dados e gerar gráfico    
           
```
# Instalar package
if(!require(funModeling)){install.packages("funModeling")}     

# Tabular dados de uma variável binária     
freq(df, "D_var")                     

# Tabular dados de uma variável categórica, pedindo apenas as primeiras 5 categorias
head(freq(df, "ano"), 5) 
```

Ver correlação de todas colunas em relação a uma especifica  `funModeling`                
```
correlation_table(df, "var")
```

## Strings

Concatenar Unir colunas com data.table (exemplo)
```
df <- df[,Periodo:=paste0(mês, "/", ano, "-", mês, "/", ano)]
```

Concatenar, unir duas colunas strings
```
df$var <- paste(df$var1, df$var2, sep = "")
```

Substituir caracteres com a função
             
```
# Instalar package
if(!require(stringr)){install.packages("stringr")}   

df$var <- str_replace(df$var, "-", "")
```

Remover caracteres específicos
> Nota: use “^x” se quiser excluir os que começam com X; use “x$” sequiser excluir os que terminam com X
```
df_novo <- df[!grepl("^X", df$var),]  # Começa com X
df_novo <- df[!grepl("^X$", df$var),] # Termina com X
```

Remover linhas que contém  4 caracteres ou mais caracteres
```
df = df[(which(nchar(df$var) >= 4)),]
```

Replace strings com `stringr`
```
df$var <- str_replace(df$var, "-", "")
df$var <- str_replace(df$var, "\\[", "")  # Para remover [
df$var <- str_replace(df$var, "\\\\", "") # Para remover \
df$var <- str_replace(df$var, "\\.", "")  # Para remover . 
df$var <- str_replace_all(df$var, c("\\(" = "", "\\)" = "")) # Para remover ( e ) por nada
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

Remova caracteres não numéricos de uma string
```
clean_cnj()
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

Encodificar colunas para latin
```
Encoding(df$var) <- 'latin1'
```

Substitua caracteres latinos estendidos por Unicode
```
escape_unicode()
```

Converter letras minusculas para maiusculas com `magrittr`
if(!require(magrittr)){install.packages("magrittr")}      

```
df %<>% mutate_if(is.character, toupper)
```

Converter letras minusculas para maiuscula 
```
df$var <- toupper(df$var)
```

Deixar primeira letra maiuscula
```
df$var <- str_to_title(df$var)
```

Remover linhas com a expressão exata
```
df <- subset(df, var!="expressao")
```

Remover espaços iniciais e finais
```
df$var <- str_trim(df$var) 
#ou
df$var <- gsub("[[:space:]]", "", df$var)
```

Deixar somente os dois primeiros caracteres
```
df$var <- substr(df$var, 0, 2)
```

Remover 3 caracteres iniciais
```
df$var_nova = substr(df$var, 4,14) # Onde 4 será o caracter de inicio e 14 de fim
```

Replace (substituir) string
```
df$var <- str_replace(df$var, "mulher", "Homem")
```

Contar quantos caracteres tem cada celula de uma coluna
```
df$count <- str_count(df$var)
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

Comparar duas strings e gerar probabilidades baseado na semelhança               
``install.packages('RecordLinkage')``                          
``library(RecordLinkage)``                            
```
df$Prob_1 <- levenshteinSim(df$var_1, df$var_2)
df$Prob_2 <- jarowinkler(df$var_1, df$var_2)
df$Prob_3 <- jarowinkler(df$var_1, df$var_2)
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

 **Left_join para muitos dataframes**
```
joined <- list(df1, df2, df3, df4, df5, df6, %>% 
               reduce(left_join, by = c("id", "year"), fill=TRUE)
```	    

**Left_join** 
```
# Join com nomes diferentes das colunas
df3 <- left_join(df1, df2, by = c("code_ibge" = "id_ibge"))
```

**Left_join** 
```
# left join adicionando sufixo as colunas com mesmo nome
df_3 <- left_join(df_1, df_2, by = "id", suffix = c(".df_1", ".df_2"))
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
df <- df %>% dplyr::mutate(D_var = ifelse(var1 %in% c(1,10,28), 1,                   
                            ifelse(var2 %in% c(2,5,23:26), 1,0)))
```

Gera dummies com `fastDummies`  
if(!require(fastDummies)){install.packages("fastDummies")}                             
> Nota: com fastaDummies basta selecionar uma variável categórica que ele gera as dummies.
```
df <- dummy_cols(df, select_columns =c("var"))
```

Gerar dummies  com `data.table` e `mltools`
if(!require(mltools)){install.packages("mltools")} 
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

Gerar dummy a partir de uma expressão contida em uma string
```
# Gerar dummy
df$Dummie_nova <- as.integer(str_detect(df$var_str,"expressão_1"))

# Fazer replace para outras condições
df$Dummie_nova[as.integer(str_detect(df$var,"expressão_2")) == 1] <- 1
```

Gerar dummy a partir de varias expressões contida em uma string
```
Palavras = c("Palavra_1|Palavra_2|Palavra_3|frase com espaços")

df$Dummie_nova_1 <- as.integer(str_detect(df$var_str,   Palavras))
```

Outras aplicações do str_detect
```
fruit <- c("apple", "banana", "pear", "pinapple")
str_detect(fruit, "a")  # que contenha "a" em qualquer lugar
str_detect(fruit, "^a") # que contenha "a" no inicio da palavra
str_detect(fruit, "a$") # que contenha "a" no final da palavra
str_detect(fruit, "[aeiou]")  # que contenha "aeiou" em qualquer lugar
```

## Tarefas Prontas

**Desabilitar notação científica**
```
options(scipen = 999)
```

**Apagar um arquivo salvo em uma pasta no computador**
```
file.remove("D:/data.R")
file.remove("D:/data.RDS")
file.remove("D:/data.csv")
```

** Remover duplicados de grande volume de dados** `data.table`
```
df2 <- df[, if(.N==1) .SD, .(va1, var2, var3, var4)]
```

**Remover observações duplicadas**
```
**Remover duplicados**       
df2 <- df %>% dplyr::filter(!duplicated(var))   
```

**Visualizar duplicados e gerar coluna de número de ocorrências**
```
df_novo <- data.frame(table(df$var1, df$var2))
```

** Ver quantas observações temo sem duplicados **
```
df$var %>% unique() %>% length() 
```

**Remover duplicados com data.table (ideal para grandes conjuntos de dados**
```
df_novo <- unique(df, by =c("var1", "var2"))

#ou

df_novo <- df %>% unique(by =c("var1", "var2"))
```

**Obter o valor mínimo de duas colunas**
```
df <- transform(df, new_Var = pmin(var1, var2))
```

**Padronização de  escala das colunas do df**
```
# Padronizar e gerar novo dataframe
df_pad = scale(df[,1:4]) 

# Padronizar algumas colunas sem gerar novo dataframe
df[,1:4] = scale(df[,1:4]) 
```

**Normalização de dados (deixar em uma escala entr 0 e 1)**  
if(!require(scales)){install.packages("scales")} 
```
# Normalizar uma coluna
df$var_Norm <- rescale(df$var) 

# Normalizar varias colunas
df <- df %>% dplyr::mutate_at(c(1:10), funs(c(scale(.))))
```

**Gerar um lag e lead de uma variável observando os grupos** 
```
df <-  df %>% dplyr::group_by(id) %>% dplyr::mutate(L1_var = dplyr::lag(var, n = 1, default = NA))
df <-  df %>% dplyr::group_by(id) %>% dplyr::mutate(F1_var = dplyr::lead(var, n = 1, default = NA))
```

**Gerar (id) identificador a partir de uma ou mais colunas**
```
df <- df %>% dplyr::group_by(var1,var2) %>% dplyr::mutate(id = cur_group_id())
```

**Obter código dos municípios de 6 dígitos (id6) a partir do id7**
```
df$id6 <- substr(df$id7, 1, (nchar(df$id7)-1))
```

**Obter código IBGE das UF  a partir do código de municípios**
```
Se o código ibge do municipios for de 7 dígitos 
df$Cod_UF <- substr(df$id7, 1, (nchar(df$id7)-5))

Se o código ibge do municipios for de 6 dígitos 
df$Cod_UF <- substr(df$id7, 1, (nchar(df$id7)-4))
```

**Atribuir nome aos códigos IBGE das UFs e regiões**
```
df<- mutate(df, 
            Nome_UF = factor(Cod_UF,
            levels = c(11, 12, 13, 14, 15, 16, 17, 21, 22, 23, 24, 25, 26, 
                       27, 28, 29, 31, 32, 33, 35, 41, 42, 43, 50, 51, 52, 53),
            labels = c("Rondônia", "Acre", "Amazonas", "Roraima", "Pará", "Amapá", "Tocantins", "Maranhão", 
                       "Piauí", "Ceará", "Rio Grande do Norte", "Paraíba", "Pernambuco", "Alagoas", 
                       "Sergipe", "Bahia", "Minas Gerais", "Espírito Santo", "Rio de Janeiro", "São Paulo",
                       "Paraná", "Santa Catarina", "Rio Grande do Sul", "Mato Grosso do Sul",  "Mato Grosso", 
                       "Goiás", "Distrito Federal")),
            Sigla_UF = factor(Cod_UF,
            levels = c(11, 12, 13, 14, 15, 16, 17, 21, 22, 23, 24, 25, 26, 
                       27, 28, 29, 31, 32, 33, 35, 41, 42, 43, 50, 51, 52, 53),
            labels = c("RO", "AC", "AM", "RR", "PA", "AP", "TO", "MA", "PI", "CE", "RN", "PB", "PE", 
                       "AL", "SE", "BA", "MG", "ES", "RJ", "SP", "PR", "SC", "RS", "MS", "MT", "GO", "DF")),
            Região = factor(Cod_UF,
            levels = c(11, 12, 13, 14, 15, 16, 17, 21, 22, 23, 24, 25, 26, 
                       27, 28, 29, 31, 32, 33, 35, 41, 42, 43, 50, 51, 52, 53),
            labels = c("Norte", "Norte", "Norte", "Norte", "Norte", "Norte", "Norte", "Nordeste", "Nordeste", 
                       "Nordeste", "Nordeste", "Nordeste", "Nordeste", "Nordeste", "Nordeste", "Nordeste", 
                       "Sudeste", "Sudeste", "Sudeste", "Sudeste", "Sul", "Sul", "Sul", "Centro-Oeste", 
                       "Centro-Oeste", "Centro-Oeste", "Centro-Oeste")))				   
```

Gerar Cod_UF a partir das Siglas
```
df <- mutate(df, Cod_UF = recode(Sigla_UF,
             'RO' = 11, 'AC' = 12, 'AM' = 13, 'RR' = 14, 'PA' = 15, 'AP' = 16, 'TO' = 17,
             'MA' = 21, 'PI' = 22, 'CE' = 23, 'RN' = 24, 'PB' = 25, 'PE' = 26, 'AL' = 27, 
             'SE' = 28, 'BA' = 29, 'MG' = 31, 'ES' = 32, 'RJ' = 33, 'SP' = 35, 'PR' = 41, 
             'SC' = 42, 'RS' = 43, 'MS' = 50, 'MT' = 51, 'GO' = 52, 'DF' = 53))
```

**Trabalhando com CPF**    
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

**Gerar classes etárias com `fastDummies`**  
if(!require(fastDummies)){install.packages("fastDummies")} 
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

**Balanceando classes em modelos de Machine Learning**   
if(!require(DMwR)){install.packages("DMwR")}
              
```
set.seed(9560)
df_treino_balanceado <- SMOTE(var_desbalanceada ~., data=df_treino)
table(df_treino_balanceado$var_desbalanceada) 
prob.table(table(df_treino_balanceado$var_desbalanceada)
```

**Remover acentos com package** `abjutils`                    
https://github.com/abjur/abjutils                            
if(!require(abjutils)){install.packages("abjutils")}

# Remover acentos
df$var_nova <- rm_accent(df$var)

**Remover acentos**
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
df$var_nova <- rm_accent(df$var)
```

**Deflacionar variáveis monetárias**                                 
Fonte: [https://fmeireles.com/blog/rstats/deflacionar-series-no-r-deflatebr/](https://fmeireles.com/blog/rstats/deflacionar-series-no-r-deflatebr/)

> Nota: Primeiro passo é gerar uma variável do tipo date. Neste exemplo  é utilizada a variável Ano para gerar uma data do último dia do Ano.  Essa data será utilizada para a deflacionar.

```
# Gerar variável Data
df <- df %>% mutate(Data = ifelse(Ano %in% c(2002), "2002-12-31",
                           ifelse(Ano %in% c(2003), "2003-12-31",
                           ifelse(Ano %in% c(2004), "2004-12-31",
                           ifelse(Ano %in% c(2005), "2005-12-31",
                           ifelse(Ano %in% c(2006), "2006-12-31",
                           ifelse(Ano %in% c(2007), "2007-12-31",
                           ifelse(Ano %in% c(2008), "2008-12-31",
                           ifelse(Ano %in% c(2009), "2009-12-31",
                           ifelse(Ano %in% c(2010), "2010-12-31",
                           ifelse(Ano %in% c(2011), "2011-12-31",
                           ifelse(Ano %in% c(2012), "2012-12-31",
                           ifelse(Ano %in% c(2013), "2013-12-31",
                           ifelse(Ano %in% c(2014), "2014-12-31",
                           ifelse(Ano %in% c(2015), "2015-12-31",
                           ifelse(Ano %in% c(2016), "2016-12-31",
                           ifelse(Ano %in% c(2017), "2017-12-31",
                           ifelse(Ano %in% c(2018), "2018-12-31", 
                                             NA))))))))))))))))))

# Converter a variável Data para o formato date com `lubridate`
df$Data <- as.Date(df$Data)

# Selecionar colunas que serão deflacionadas
Cols_Deflate <- c("var_1", "var_2", "var_3", "var_4")

# Deflacionar com o pacote `deflateBR` utilizando o IPCA para o ano 2018
if(!require(deflateBR)){install.packages("deflateBR")}

# Deflacioanr uma coluna
df$var_monetaria_def <- ipca(df$var_monetaria, df$Data, "12/2018")

# Deflacioanr muitas colunas
for(i in 1:length(Cols_Deflate)) {
  df[ , i] <- ipca(df[ , i], df$Data, "12/2018")
}

# Ver como era e como ficou
summary(df$var_monetaria)
summary(df$var_monetaria_def)
```
**Plotar Gráficos Lado a Lado**

Ver mais detalhes de gráficos para R em:
 [https://www.r-graph-gallery.com/](https://www.r-graph-gallery.com/)
Dica: para executar chunk no Rmarkdown utilize o atalho Ctrl+Shift+Enter

```
# Gráfico lado a lado com plot
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
# Gráfico lado a lado ggplot
install.packages("egg")
library(egg)
grid.arrange(fig1, fig2, fig3, fig4, ncol=2, nrow=2)
```

**Gerar estações do ano a partir de uma variável do tipo date**
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

**Preparar colunas para os novos estimadores de diff (Callaway and Sant'anna; Sun and Abrahan; Gardner e outros)** 
> Suponha que o tratamento do programa XXX, começou em 2006 para alguns municípios do Brasil
```
# Clonar dummy de tratamento e substituindo zeros por missings
df$D_XXX_2 = df$D_XXX
df$D_XXX_2[df$D_XXX_2 == 0] <- NA
table(df$D_XXX_2)

# Gerar variável com o ano de tratamento
df$AT_XXX = (df$D_XXX_2 * df$ANO)
table(df$AT_XXX)

# Gerar indicador do ano de entrada no tratamento
setDT(df)[, Entrada_XXX := min(AT_XXX, na.rm=TRUE), by = "id"]
table(df$Entrada_XXX)

# Substituir infinito por missings
is.na(df$Entrada_XXX) <- sapply(df$Entrada_XXX, is.infinite)

# Gerar dummie onde o municipio tratado sempre recebe o valor 1, em todos periodos que aparece na amostra
df$Todos_Trat_XXX <- df$Entrada_XXX
df$Todos_Trat_XXX[is.na(df$Todos_Trat_XXX)] <- 0
df$Todos_Trat_XXX[df$Todos_Trat_XXX >0] <- 1
table(df$Todos_Trat_XXX, df$ANO) 

# Gerar First_treat_XXX que na prática é igual a variável Entrada_XXX
df$First_treat_XXX <- df$Entrada_XXX
df$First_treat_XXX[is.na(df$First_treat_XXX)] <- 0
table(df$First_treat_XXX)

# Gerar First_treat_XXX_2 (Nesta vamos impedir a reversão do tratamento)
df$First_treat_XXX_2 <- df$First_treat_XXX
df$First_treat_XXX_2[df$ANO > df$Entrada_XXX & df$D_XXX ==0] <- NA
table(df$First_treat_XXX_2)

# Gerar D_XXX_2 (nessa vamos impedir a reversão do tratamento)
df$D_XXX_2 <- df$D_XXX
df$D_XXX_2[is.na(df$First_treat_XXX_2)] <- NA

# Gerar amostra para verificação
Amostra <- df[,.(ANO, id, D_XXX, AT_XXX, Entrada_XXX, Todos_Trat_XXX, First_treat_XXX, First_treat_XXX_2, D_XXX_2)]

# Remover colunas desnecessárias
df <- df[, c("AT_XXX") := NULL]
```


**Imputar missings com XGboost**
ver mais em: https://github.com/agnesdeng/mixgb

Por padrão, escolherá aleatoriamente uma variável incompleta como a resposta e construirá um modelo XGBoost 
com outras variáveis usando os casos completos do conjunto de dados. Portanto, cada corrida é provável que 
retorne resultados diferentes. Os usuários também podem especificar a resposta e covariáveis no argumento e, 
respectivamente.mixgb_cv()mixgb_cv()responseselect_features

```
# Carregar pacotes
if(!require(pacman)){install.packages("pacman")}
p_load(tidyverse, data.table, funModeling, mixgb) 

# Semente
set.seed(2022)

# Preparar 
df_original <- df_original %>% dplyr::mutate_at(c(1:10), as.numeric) # converter as colunas 1 a 10 para numérico

# Visualizar resumo de missings zeros e vazios
resumo <- df_status(df_original)
resumo$vazias <- apply(df_original, 2, function(x) length(which(x == '')))
resumo$OBS_Total <- nrow(df_original)
resumo$perc_vazias = df_original$vazias / df_original$OBS_Total

# Clonar df
df <- df_original

## Imputar missings com XGboost
# É altamente recomendável limpar e verificar seus dados antes da imputação. Aqui estão algumas questões comuns:
# 1- Os dados devem ser um quadro de dados.
# 2- O ID deve ser removido
# 3- Os valores perdidos devem ser codificados como NA não NaN
# 4- Inf ou -Inf não são permitidos
# 5- Células vazias devem ser codificadas como ou valores NA
# 6- Variáveis do tipo "caractere" devem ser convertidas em "fator" 
# 7- Variáveis do tipo "fator" devem ter pelo menos dois níveis

# Selecionar colunas que serão imputadas (colunas com missings)
col_missing <- c("var1", "var2", "var")

# obter o nome das colunas que contém missings
col_missing <- names(which(colSums(is.na(df))>0)) 

# Parâmetros do XGboost - Ver mais em: https://xgboost.readthedocs.io/en/stable/parameter.html
params <- list(max_depth = 2, gamma = 0.1, eta = 0.3, min_child_weight = 1, subsample = 1, 
               colsample_bytree = 1, colsample_bylevel = 1, colsample_bynode = 1, nthread = 25,
               tree_method = "auto",gpu_id = 1, predictor = "auto")

imputed.data <- mixgb(data = cov[col_missing], m = 5, maxit = 1, ordinalAsInteger = TRUE, bootstrap = TRUE, pmm.type = "auto", 
                      pmm.k = 5, pmm.link = "prob", initial.num = "normal", initial.int = "mode", initial.fac = "mode",
                      save.models = FALSE, save.vars = NULL, xgb.params = params, nrounds = 150, print_every_n = 10L,
                      early_stopping_rounds = 20, verbose = 0)

imputed_data_1 <- as.data.frame(imputed.data[[1]])
imputed_data_1 <- cbind(imputed_data_1, df$Ano)

imputed_data_2 <- as.data.frame(imputed.data[[2]])
imputed_data_2 <- cbind(imputed_data_2, df$Ano)

imputed_data_3 <- as.data.frame(imputed.data[[3]])
imputed_data_3 <- cbind(imputed_data_3, df$Ano)

imputed_data_4 <- as.data.frame(imputed.data[[4]])
imputed_data_4 <- cbind(imputed_data_4, df$Ano)

imputed_data_5 <- as.data.frame(imputed.data[[5]])
imputed_data_5 <- cbind(imputed_data_5, df$Ano)

# Pegar a média dos 5 modelos
Mean_df_inputed <- rbindlist(list(imputed_data_1, imputed_data_2, imputed_data_3, imputed_data_4, imputed_data_5))[,lapply(.SD,mean), by= c("df$Ano")]
Mean_df_inputed <- rename(Mean_df_inputed, c("Ano" = "df$Ano"))

# Remover as colunas do df_original que foram imputadas 
df_original <- subset(df_original, select = -c(var1, var2, var3))

# Unir com as colunas imputadas
df2 <- left_join(df_original, Mean_df_inputed, by = c("Ano"))

# Remover dfs que não preciso mais
rm(`imputed.data`, imputed_data_1, imputed_data_2, imputed_data_3, imputed_data_4, imputed_data_5, Mean_df_inputed, col_missing)
```

**Imputar missings com mice**

```
# Carregar pacotes
if(!require(pacman)){install.packages("pacman")}
p_load(tidyverse, data.table, funModeling, mice) 

df_imputed <- mice(df, m=5 ,maxit=5, meth = c("rf"), seed=500)
```

## Importar e Exportar Dados

**Formatos de arquivo suportados**
https://cran.r-project.org/web/packages/rio/vignettes/rio.html

| Format                              | Typical Extension       | Import Package                                              | Export Package                                              | Installed by Default |
| ----------------------------------- | ----------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- | -------------------- |
| Comma-separated data                | .csv                    | [data.table](https://cran.r-project.org/package=data.table) | [data.table](https://cran.r-project.org/package=data.table) | Yes                  |
| Pipe-separated data                 | .psv                    | [data.table](https://cran.r-project.org/package=data.table) | [data.table](https://cran.r-project.org/package=data.table) | Yes                  |
| Tab-separated data                  | .tsv                    | [data.table](https://cran.r-project.org/package=data.table) | [data.table](https://cran.r-project.org/package=data.table) | Yes                  |
| CSVY (CSV + YAML metadata header)   | .csvy                   | [data.table](https://cran.r-project.org/package=data.table) | [data.table](https://cran.r-project.org/package=data.table) | Yes                  |
| SAS                                 | .sas7bdat               | [haven](https://cran.r-project.org/package=haven)           | [haven](https://cran.r-project.org/package=haven)           | Yes                  |
| SPSS                                | .sav                    | [haven](https://cran.r-project.org/package=haven)           | [haven](https://cran.r-project.org/package=haven)           | Yes                  |
| SPSS (compressed)                   | .zsav                   | [haven](https://cran.r-project.org/package=haven)           | [haven](https://cran.r-project.org/package=haven)           | Yes                  |
| Stata                               | .dta                    | [haven](https://cran.r-project.org/package=haven)           | [haven](https://cran.r-project.org/package=haven)           | Yes                  |
| SAS XPORT                           | .xpt                    | [haven](https://cran.r-project.org/package=haven)           | [haven](https://cran.r-project.org/package=haven)           | Yes                  |
| SPSS Portable                       | .por                    | [haven](https://cran.r-project.org/package=haven)           |                                                             | Yes                  |
| Excel                               | .xls                    | [readxl](https://cran.r-project.org/package=readxl)         |                                                             | Yes                  |
| Excel                               | .xlsx                   | [readxl](https://cran.r-project.org/package=readxl)         | [openxlsx](https://cran.r-project.org/package=openxlsx)     | Yes                  |
| R syntax                            | .R                      | base                                                        | base                                                        | Yes                  |
| Saved R objects                     | .RData, .rda            | base                                                        | base                                                        | Yes                  |
| Serialized R objects                | .rds                    | base                                                        | base                                                        | Yes                  |
| Epiinfo                             | .rec                    | [foreign](https://cran.r-project.org/package=foreign)       |                                                             | Yes                  |
| Minitab                             | .mtp                    | [foreign](https://cran.r-project.org/package=foreign)       |                                                             | Yes                  |
| Systat                              | .syd                    | [foreign](https://cran.r-project.org/package=foreign)       |                                                             | Yes                  |
| “XBASE” database files              | .dbf                    | [foreign](https://cran.r-project.org/package=foreign)       | [foreign](https://cran.r-project.org/package=foreign)       | Yes                  |
| Weka Attribute-Relation File Format | .arff                   | [foreign](https://cran.r-project.org/package=foreign)       | [foreign](https://cran.r-project.org/package=foreign)       | Yes                  |
| Data Interchange Format             | .dif                    | utils                                                       |                                                             | Yes                  |
| Fortran data                        | no recognized extension | utils                                                       |                                                             | Yes                  |
| Fixed-width format data             | .fwf                    | utils                                                       | utils                                                       | Yes                  |
| gzip comma-separated data           | .csv.gz                 | utils                                                       | utils                                                       | Yes                  |
| Apache Arrow (Parquet)              | .parquet                | [arrow](https://cran.r-project.org/package=arrow)           | [arrow](https://cran.r-project.org/package=arrow)           | No                   |
| EViews                              | .wf1                    | [hexView](https://cran.r-project.org/package=hexView)       |                                                             | No                   |
| Feather R/Python interchange format | .feather                | [feather](https://cran.r-project.org/package=feather)       | [feather](https://cran.r-project.org/package=feather)       | No                   |
| Fast Storage                        | .fst                    | [fst](https://cran.r-project.org/package=fst)               | [fst](https://cran.r-project.org/package=fst)               | No                   |
| JSON                                | .json                   | [jsonlite](https://cran.r-project.org/package=jsonlite)     | [jsonlite](https://cran.r-project.org/package=jsonlite)     | No                   |
| Matlab                              | .mat                    | [rmatio](https://cran.r-project.org/package=rmatio)         | [rmatio](https://cran.r-project.org/package=rmatio)         | No                   |
| OpenDocument Spreadsheet            | .ods                    | [readODS](https://cran.r-project.org/package=readODS)       | [readODS](https://cran.r-project.org/package=readODS)       | No                   |
| HTML Tables                         | .html                   | [xml2](https://cran.r-project.org/package=xml2)             | [xml2](https://cran.r-project.org/package=xml2)             | No                   |
| Shallow XML documents               | .xml                    | [xml2](https://cran.r-project.org/package=xml2)             | [xml2](https://cran.r-project.org/package=xml2)             | No                   |
| YAML                                | .yml                    | [yaml](https://cran.r-project.org/package=yaml)             | [yaml](https://cran.r-project.org/package=yaml)             | No                   |
| Clipboard                           | default is tsv          | [clipr](https://cran.r-project.org/package=clipr)           | [clipr](https://cran.r-project.org/package=clipr)           | No                   |




> Nota: No Rstudio é possível importar bases de dados via menu.

Importar arquivo excel com `readxl`
```
df <- read_excel("D:/dados.xlsx", sheet = "Planilha1")
```

Importar arquivo excel com `openxlsx`
```
df <- read.xlsx('D:\Arquivo.xlsx')
```

Exportar arquivo excel com `openxlsx`
```
write.xlsx(df, "D:\Arquivo.xlsx")
```

Exportar arquivo excel com `xlsx`
```
write.xlsx(df, "D:\Arquivo.xlsx", sheetName = "Sheet1", col.names = TRUE, row.names = TRUE, append = FALSE)
)
```

Importar base de dados do stata .dta com `haven`
```
read_dta(C:/Pasta/"df.dta")
```

Importar base de dados do stata .dta com `haven` e remover label, formato e outras informações vindas do stata
ver mais em: https://rdrr.io/cran/haven/man/zap_labels.html
zap_empty(), zap_formats(), zap_label(), zap_widths()
```
read_dta(C:/Pasta/"df.dta") %>% zap_label() %>% zap_formats()
```
 
Exportar base de dados do stata  .dta  com `haven`
```
write_dta(df, "df.dta")
```

Abrindo vários arquivos .csv
```
list_data <- list.files(path = "D:/OneDrive/PROJETO IPEA/volume_trafego", pattern = ".csv", full.names = TRUE)

read_data = function(list_data){
  read.csv2(list_data, encoding = "UTF-8", stringsAsFactors=FALSE)
}
myfiles = lapply(X = list_data, FUN = read_data)

#Obtendo um único dataframe
data_demand = data.table::rbindlist(myfiles)
```

Importar .csv de forma mais rápida com `data.table`
* https://www.rdocumentation.org/packages/data.table/versions/1.14.2/topics/fread

```
# Importar csv com fread data.table
df <- read.table("test.csv", header=TRUE, sep=",", quote="", stringsAsFactors=FALSE, comment.char="", nrows=n)
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

Importar varios arquivos .csv fazer append e gerar uma coluna com nome dos arquivos
> Nota: é necessário que os arquivos tenham o mesmo nome nas colunas
```
file_names <- list.files(path = "D:/ARQUIVOS", pattern = "*.csv", full.names = T)
file_list <- lapply(file_names, function(x){
                    ret <- read_csv2(x, skip = 0,locale = default_locale(),trim_ws = TRUE, col_select = NULL,)
                    ret$origin <- x
                    return(ret)})
df <- rbindlist(file_list)
```

Importar varios arquivos .csv fazer append
> Nota: é necessário que os arquivos tenham o mesmo nome nas colunas
```
file_names <- ldply(list.files(path = "D:/ARQUIVOS", pattern = "*.csv", full.names = T), 
                           read.csv, header=TRUE, sep = ";", skip = 0, dec = ",", fill = TRUE)
```

Importar varios arquivos .csv e usar o endereço e nome do arquivo como nome da tabela 
> Nota: é necessário que os arquivos tenham o mesmo nome nas colunas
```
files<- list.files(path = "ARQUIVOS", pattern="*.csv", full.names=T)
for (i in files){
    iname=sub("*.csv","",i)
    f=read.csv(i, header=TRUE, sep = ";", skip = 0, dec = ",", fill = TRUE)
    rownames(f)=paste(rownames(f),iname,sep = "_")
    assign(paste0(iname),f)
}
```

## Gerar um banco de dados SQL com SQLite

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
if(!require(pacman)){install.packages("pacman")}
p_load(data.table, tidyverse, fst, readr, jsonlite)

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


# Bibliometria com bibliometrix

```
if(!require(remotes)){install.packages("remotes")}
install.packages("igraph", type="binary")
remotes::install_github("massimoaria/bibliometrix")
library(bibliometrix)
biblioshiny()
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

