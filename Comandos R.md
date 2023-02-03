# Comandos linguagem R v2.0
![enter image description here](https://miro.medium.com/max/1400/1*cuOlMPTUQ3cTY7ldb-usKw.png)

**Autores:**              
Silvio da Rosa Paula                             
Dianifer Leal Borges   

## Operadores de Comparação:
Os operadores de comparação sempre retornam um valor lógico TRUE ou FALSE.

| Operador |   Significado    |
|----------|------------------|
|     ==   | igual a          |
|     !=   | diferente de     |
|     >    | maior que        |
|     <    | menor que        |
|     >=   | maior ou igual a |
|     <=   | menor ou igual a |

**Fonte** [Bóson Treinamentos em Ciência e Tecnologia](http://www.bosontreinamentos.com.br/programacao-em-r/operadores-logicos-e-operadores-de-comparacao-em-r/)

##  Operadores Lógicos:
Também conhecidos como operadores booleanos, permitem trabalhar com múltiplas condições relacionais na mesma expressão, e retornam valores lógicos verdadeiro ou falso..

| Operador |   Descrição    |                  Explicação                                   |
|----------|----------------|---------------------------------------------------------------|
|    &     | AND      |Versão vetorizada. Compara dois elementos do tipo vetor e retorna um vetor de TRUEs e FALSEs
|    &&    |  AND 	|Versão não-vetorizada. Compara apenas o primeiro valor de cada vetor, retornando um valor lógico.
|    l     | OR      |Versão vetorizada. Compara dois elementos do tipo vetor e retorna um vetor de TRUEs e FALSEs
|    ll    | OR     |Versão não-vetorizada. Compara apenas o primeiro valor de cada vetor, retornando um valor lógico.
|    !     | NOT    |Negação lógica. Retorna um valor lógico único ou um vetor de TRUE / FALSE.
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

### Instalar pacotes
```
# Instalar um pacote
install.packages('package')

# Instalar mais de um pacote
install.package(c('package1','package2','package3'))
```

### Instalar versão específica de um pacote
```
install.packages("fixest", version='0.8.4')
```

### Atualizar pacotes
```
old.packages() 
update.packages()
update.packages(checkBuilt=TRUE, ask=FALSE)
```

### Carregar pacotes
```
# Método 1: library
#library(package)

# Método 2: require
#require(pacote)
```

### Utilizar uma função específica de um pacote sem carrega-lo
```
(pacote)::função()
```

###  Acessar documentação
> Obs: é possível acessar o help de uma função, pacote selecionando a função com mouse + F1
```
help('pacote')
help(package='pacote')
```

### Help função 
> Também é possível fazer, selecionando a função, package etc + F1
```
?comando
help('comando')
help('comando', package='pacote')
```

### Descarregar pacote
```
detach('package:pacote', unload =TRUE)
```

### Versão do pacote
```
packageDescription("pacote")
```

### Instalar e carregar pacotes automaticamente 
> O código verifica se o package `dplyr` está instalado, se não estão, ele instala e carrega automaticamente. 
```
if(!require(dplyr)){install.packages("dplyr")}
```

### Instalar e carregar pacotes automáticamente com `pacman` 
> O Package  Pacman verifica se os pacotes estão instalados, se não estão, ele instala e carrega automaticamente.
```
# Intalar e carregar automaticamente o package pacman 
if(!require(pacman )){install.packages("pacman ")}

# Install & load packages
p_load(ggplot2, dplyr, stringr) 

# Unload packages
p_unload(ggplot2, dplyr, stringr)  

# Check for outdated packages
p_update(update = FALSE)   

# Update all packages   
p_update()                         
```

### Desabilitar notação científica
```
options(scipen = 999)
```

### Visualizar todos objetos em memória
```
ls()
```

### Remover todos os objetos em memória
```
rm(list=ls())
```

### Deixar apenas os dfs selecionados
```
rm(list=setdiff(ls(), c("df_1", "df_2", "df_3")))
```

###  Remover dfs ou outros objetos
```
rm(df_1)
```

###  Remover todos os objetos que comtenham no nome "df"
```
rm(list = ls()[grepl("df", ls())])
```

###  Clonar df
```
df_novo <- df
```

### Definir pasta / diretório de trabalho
```
setwd ("D:/")
```

### Abrir diretório de trabalho diretamente do Rstudio
```
Abrir_Diretorio <- function(directory = getwd()){
  system(sprintf('open %s', shQuote(directory)))
  }
opendir("D:/")
```

## Configurações de Memória e Processador.

### Expandir memória
>Obs: também é possível selecionar a quantidade memória desejada substituindo os valores em mb no lugar do 9999999999
```
memory.limit (9999999999) 
```

### Checar quantidade de memória selecionada
```
memory.size()
```

### Liberar memória sem apagar os objetos 
```
gc()
```

### Escolher quantos threads do CPU serão utilizadas com `data.table`
```
setDTthreads(20) 
```

## Visualização e Manipular Dataframes

###  Visualizar  dataframe
```
# Método 1: View
View(df)

# Método 2: 
df
```

###  Visualizar as primeiras  e últimas 10 linhas do dataframe
```
# Visualizar primeiras linhas
head(df, n=10)

# Visualizar primeiras linhas em outra janela
View(head(df, n=10))

# Visualizar últimas linhas
tail(df, n=10)

# Visualizar últimas linhas  em outra janela
View(tail(df, n=10))
```

###  Visualizar 10 linhas de  colunas específicas do dataframe
```
# Visualizar primeiras linhas
View(head(df[,c("Coluna_1", "Coluna_2", "Coluna_3")], n=10))

# Visualizar últimas linhas
View(tail(df[,c("Coluna_1", "Coluna_2", "Coluna_3")], n=10))
```

###   Visualizar colunas específicas do dataframe
```
View(df[,c("Coluna_1", "Coluna_2", "Coluna_3")])
```

###  Visualizar colunas específicas do dataframe com `data.table`
```
View(df[,.("Coluna_1", "Coluna_2", "Coluna_3")])
```

###  Visualizar nome das colunas do df
```
names(df)
colnames(df)
```

###  Visualizar nome das colunas a partir do índice
```
names(df)[c(1:4,9,20)]
```

###  Visualizar índice atribuido as colunas a partir dos nomes
```
Col_number <- which(names(df) %in% c("Coluna_1","Coluna_2","Coluna_3"))
```

###  Visualizar  dimensões do dataframe (linhas e colunas)
```
dim(df)
```

###   Visualizar detalhes das colunas do df
```
str(df)
```

###   Visualizar classes das colunas e outras informações
```
glimpse(df)
```

###   Visualizar classe das colunas do df (numérico, string, etc.)
```
# Visualizar classe de uma coluna específica
class(df$Coluna_1)

# Visualizar classe de todas colunas
lapply(df,class)
```

###   Visualizar classe / tipo de um objeto
```
class(df)
```

###   Ordenar alfabeticamente os nomes das colunas do df
```
df <- df %>% dplyr::select(order(colnames(df)))
```

###  Ordenar coluna do df
```
# Ordenar de forma crescente
df <- df [order(df$Coluna_1),]

# Ordenar de forma decrescente
df <- df [order(df$Coluna_1),decreasing = (TRUE),] 
```

###  Ordenar colunas do df com `dplyr` 
```
# Ordenar
df <- df %>%  dplyr::select(sort(current_vars()))

# Definir qual será as primeiras colunas do df
df <- df %>% dplyr::relocate(Coluna_1)
```

###  Gerar amostra - subset  com `dplyr` 
```
# Gerar amostra apenas com as colunas Coluna_1, Coluna_2, Coluna_3
df_novo <- subset(df, select = c("Coluna_1", "Coluna_2", "Coluna_3")) 

# Gerar amostra sem as colunas Coluna_1, Coluna_2, Coluna_3
df_novo <- subset(df, select = -c("Coluna_1", "Coluna_2", "Coluna_3")) 

# Gerar amostra sem as colunas `Coluna 1`, Coluna 2`, `Coluna 3` (colunas com espaço no nome)
df_novo <- subset(df, select = -c(`Coluna 1`, Coluna 2`, `Coluna 3`)) 

# Gerar amostra apenas com os anos >= 2000
df_novo <- subset(df, Ano>=2000)

# Gerar amostra apenas com os anos >= 2000 e <= 2010
df_novo <- subset(df, Ano>=2000 & Ano<=2010)

# Gerar amostra dropando colunas que comtém determinada expressão no nome
df_novo <- subset(df, select = c(!grepl("^Expressão",names(df)))
```

###  Gerar amostra - subset  utilizando `data.table`
> Obs: só funciona se o objeto for um data.table
```
 # Converter dataframe para datatable
 df <- as.data.table(df)
    
 # Gerar amostra apenas com as colunas Coluna_1, Coluna_2, Coluna_3
 df_novo<- df[,.(Coluna_1, Coluna_2, Coluna_3)]
    
 # Gerar amostra sem as colunas Coluna_1, Coluna_2, Coluna_3
df_novo <- df[, c("Coluna_1", "Coluna_2", "Coluna_3") := NULL]

 # Gerar amostra apenas com os anos >= 2000
 df_novo <- df[(df$Ano>=2000),]

 # Gerar amostra apenas com os anos >= 2000 e <= 2010
df_novo <- df[(df$Ano>=2000 & df$Ano<=2010),]
```	

###  Remover ids duplicados com `data.table`
```	
setDT(df)[, if(.N>1) .SD, by = id]
```	

###  Gerar amostra - subset com muitas condições com `magrittr`
```
df_novo <- df[(df$Coluna_1%in% c("A", "B", "C", "D", "E")),]
```	     
			   
### Remover linhas e colunas do df
```
# Remover a primeira linha do df
df <- df[-1, ]

# Remover a última linha do df
df <- df[-nrow(df), ]

# Remover a primeira coluna do df
df <- df[ , -1]

# Remover a última coluna do df
df <- df[ , -ncol(df)]

# Remover a primeira linha e coluna do df
df <- df[-1 , -1]
```

###  Transpor linha para colunas
```
df <- as.data.frame(t(df))
```
  
###  Gerar amostra - subset com as primeiras 1000 linhas do df
```
df_novo  <- head(df, n=1000)
```

### Clonar coluna do df 
```
# Método 1: com package `dplyr`
df <- df %>% dplyr::mutate(Coluna_1_clone = Coluna_1) %>%   
             dplyr::mutate(Coluna_2_clone = Coluna_2)
             
# Método 2: sem pacote
df$Coluna_1_clone <- df$Coluna_1
```

###  Remover colunas do df (drop)
```
# Método 1: dropar uma coluna
df$Coluna_1 <- NULL

# Método 2: Dropar duas colunas 
df$Coluna_1 <- df$Coluna_2 <- NULL
```

###  Renomear colunas
```
# Método 1: Renomear utilizando o nome
df <- rename(df, c("nome_novo_1" = "nome_antigo_1",
                   "nome_novo_2" = "nome_antigo_2"))

# Método 2: Renomear múltiplas colunas utilizando o indice (número)
names(df)[1:3] <-  c("Coluna_1",  "Coluna_2",  "Coluna_3" )

# Método 3: Renomear colunas de um data.frame
names(df)[names(df) == 'nome_novo_1'] <- 'nome_antigo_1'

# Método 4: Renomear colunas com `data.table` (o objeto deve ser DT)
setNames(df, 'nome_antigo', 'nome_novo')
```

###  Adicionar prefixo ou sufixo ao nome das colunas
```
# PREFIXO

## Método 1: adicionar prefixo ao nome de todas colunas com com dplyr
df %>% rename_all(~ paste0("pre_", .))

## Método 2: adicionar prefixo ao nome de todas colunas
colnames(df) <- paste("ln", colnames(df), sep = "_")

## Método 3: Adicionar prefixo ao nome de uma lista de colunas
cols_to_modify <- c("Coluna_1", "Coluna_2", "Coluna_3")
colnames(df)[colnames(df) %in% cols_to_modify] <- paste("pre_", colnames(df)[colnames(df) %in% cols_to_modify], sep = "")

# SUFIXO

## Método 1: adicionar sufixo ao nome de todas colunas com com dplyr
df %>% rename_all(~ paste0(., "_suf"))

## Método 2: adicionar sufixo ao nome das 10 primeiras colunas
colnames(df)[1:10] <- paste(colnames(df)[1:10], "texto", sep = "_")

## Método 3: Adicionar sufixo ao nome de uma lista de colunas
cols_to_modify <- c("Coluna_1", "Coluna_2", "Coluna_3")
colnames(df)[colnames(df) %in% cols_to_modify] <- paste(colnames(df)[colnames(df) %in% cols_to_modify], "_suf", sep = "")
```

###   Obter o logaritmo natural (ln) de uma coluna
```
df$ln_Coluna_1 <- log(df$Coluna_1)
```

###   Obter o logaritmo natural de múltiplas colunas
> Obs: após gerar as colunas log adicionar prefixo ln_ ao nome 
>  `colnames(df) <- paste("ln", colnames(df), sep = "_")`
```
# Método 1: Para colunas com valores >=1

## Gerar uma função para gerar o logaritmo natural
log_natural <- function(x) {log(x)}

## Aplicar função log_natural as colunas 1 a 10
df[,1:10] <- as.data.frame(lapply(df[,1:10], FUN = function(x) {sapply(x, FUN = log_natural)}))

## Aplicar função log_natural as colunas 1 a 10 e 12 ao 20
df[,c(1:10, 12:20)] <- as.data.frame(lapply(df[,c(1:10, 12:20)], FUN = function(x) {sapply(x, FUN = log_natural)}))


# Método 2: Para colunas que contém Zeros

## Gerar função para gerar o logaritmo natural + 1 
log_mais_um <- function(x) {log(x + 1)}

## Aplicar função log_mais_um nas colunas 1 a 10
df[,1:10] <- as.data.frame(lapply(df[,1:10], FUN = function(x) {sapply(x, FUN = log_mais_um)}))

## Aplicar função log_mais_um nas colunas 1 a 10 e 12 ao 20
df[,c(1:10, 12:20)] <- as.data.frame(lapply(df[,c(1:10, 12:20)], FUN = function(x) {sapply(x, FUN = log_mais_um)}))
```

###  Gerar novas coluna utilizando operações aritiméticas 
```
# Gerar nova coluna com uma constante zero
df$Coluna_1 = 0

# Gerar nova coluna a partir da soma de duas colunas
df$Coluna_3 = (df$Coluna_1 + df$Coluna_2)

# Gerar nova coluna a partir da soma de duas colunas desconsiderando os missings
df$Coluna_3 <- rowSums(df[,c("Coluna_1", "Coluna_2")], na.rm=TRUE)

# Gerar nova coluna a partir da multiplicação de duas colunas
df$Coluna_3 = (df$Coluna_1 * df$Coluna_2)

# Gerar nova coluna a partir da divisão de duas colunas
df$Coluna_3 = (df$Coluna_1 / df$Coluna_2)

# Gerar nova coluna a partir do valor ao quadrado da coluna
df$Coluna_2 = (df$Coluna_1 )^2 
```

### Converter colunas para `character`  (string)
```
# Método 1: 
df$Coluna_1<- as.character(df$Coluna_1)

# Método 2:  com  `datatable`
df <- as.data.table(apply(df, "Coluna_1", as.character))  
class(df$Coluna_1)

# Método 3: Converter lista de colunas 
col_names <- c("Coluna_1", "Coluna_2", "Coluna_3", "Coluna_4")
df[,col_names] <- lapply(df[,col_names], character)
```

###  Converter colunas para numérico `numeric`

> Não é possível converter diretamente  uma coluna `factor` para `numeric` gera valores errados, é necessário primeiro converter para `character` e após para `numeric`
```
# Método 1: a partir de uma coluna `character`
df$Coluna_1<- as.numeric(df$Coluna_1)

# Método 2: a partir de uma coluna `factor`
df$Coluna_1<- as.character(df$Coluna_1) 
df$Coluna_1<- as.numeric(df$Coluna_1)

# Método 3:  com  `datatable`
df <- as.data.table(apply(df, "Coluna_1", as.numeric))  
class(df$Coluna_1)

# Método 4: Converter lista de colunas 
col_names <- c("Coluna_1", "Coluna_2", "Coluna_3", "Coluna_4")
df[,col_names] <- lapply(df[,col_names], numeric)

# Método 5: Converter conjunto de colunas para numérico com `dplyr` utilizando os índices
df <- df %>% dplyr::mutate_at(c(1:10), as.numeric)

# Método 6: Converter todas colunas do df para numérico
df = as.data.frame(sapply(df, as.numeric))
```

###  Converter colunas para fator`factor`
```
# Método 1: 
df$Coluna_1 <- as.numeric(df$Coluna_1)

# Método 2: com  `datatable`
df <- as.data.table(apply(df, "Coluna_1", as.factor))  
class(df$Coluna_1)

# Método 3: Converter lista de colunas 
col_names <- c("Coluna_1", "Coluna_2", "Coluna_3", "Coluna_4")
df[,col_names] <- lapply(df[,col_names], factor)

# Método 4: Converter conjunto de colunas para fator com `dplyr` utilizando os índices
df <- df %>% dplyr::mutate_at(c(1:10), as.factor)
```

###  Converter  coluna  strings com valores em reiais BRL (R$) para númerico
```
# Extraindo apenas o valor numérico
valores_numericos <- as.numeric(gsub("R\\$ | BRL", "", valores))
```

###  Arredondar valores das colunas 
```
# Arredondar valores (2 digítos) de um coluna com `dplyr`
df <- df %>% dplyr::mutate_at(vars(Coluna_1), funs(round(., 2)))

# Arredondar valores (3 digítos) de varias colunas com `dplyr`
df <-df %>% dplyr::mutate_at(vars(Coluna_1, Coluna_2, Coluna_3), funs(round(., 3)))

# Arredondar valores (4 digítos) de todas as colunas exceto a Coluna_1 com `dplyr`
df <-df %>% dplyr::mutate_at(vars(-var1), funs(round(., 4)))

# Arredondar valores (2 digítos) de todas as colunas com nome que começa por "col" com `dplyr`
df <-df %>% dplyr::mutate_at(vars(starts_with("col")), funs(round(., 2)))

# Arredondar valores (2 digítos) apenas das colunas numéricas com `dplyr`
df <- df %>% dplyr::mutate_if(is.numeric, ~round(., 2))
```

### Reshape de long (data panel) para wide com `reshape`
> - A forma de organização da tabela wide, temos os anos nas linhas e os ids nas colunas
> - A forma de organização da tabela wide

> **Explicação dos parâmetros usados na função `reshape`

-   `data`: especifica o dataframe que você deseja converter.
-   `idvar`: especifica a coluna que será usada como identificador único para cada observação.
-   `v.names`: especifica as colunas que serão convertidas para colunas long.
-   `sep`: especifica o separador usado na criação dos nomes das colunas long.
-   `timevar`: especifica a coluna que contém as informações de tempo.
-   `times`: especifica os valores de tempo que serão considerados na conversão.
-   `direction`: especifica a direção da conversão, neste caso, "wide".
```
# Criar um dataframe long
df_long <- data.frame(id = c(1,2,3,4,5),
                      Ano = c(2000,2000,2000,2001,2001),
                      Coluna_1 = c(10,20,30,40,50),
                      Coluna_2 = c(100,200,300,400,500),
                      Coluna_3 = c(1000,2000,3000,4000,5000))
print(df_long)

# Converter o dataframe long para wide
df_wide <- reshape(data = df_long, 
                   idvar = "id", 
                   v.names = c("Coluna_1", "Coluna_2", "Coluna_3"), 
                   sep = "_", 
                   timevar = "Ano", 
                   times = c(2000,2001), 
                   direction = "wide")
print(df_wide )
```

### Reshape de long (data panel) para wide com `data.table`
```
# Criar um dataframe long
df_long <- data.frame(id = c(1,2,3,4,5),
                      Ano = c(2000,2000,2000,2001,2001),
                      Coluna_1 = c(10,20,30,40,50),
                      Coluna_2 = c(100,200,300,400,500),
                      Coluna_3 = c(1000,2000,3000,4000,5000))
print(df_long)

# Converter o dataframe (df) para um data.table (dt)
dt_long <- as.data.table(df_long) 

# Converter o dt long para dt wide 
dt_wide <- dcast(data = dt_long, 
				 id ~ Ano, 
				 value.var = c("Coluna_1", "Coluna_2", "Coluna_3"))
```

###  Reshape dt wide para long com `data.table`
> Neste exemplo, as colunas Código e Município são especificadas como colunas que devem ser mantidas como colunas fixas, enquanto as outras colunas são identificadas como sendo variáveis a serem medidas usando a expressão regular "^[0-9]{4}$". Em seguida, as colunas variable e value geradas pela função melt são renomeadas para Anoe e Valor, respectivamente.
```
df_long <- melt(setDT(df_wide), 
                id.vars = c("id", "Município"), 
                measure.vars = patterns("^[0-9]{4}$"))
setnames(df_long, c("Ano", "Valor"))
```

### Replace com ifelse 
> Fazer replace na variável var1, se var1 <0, então var1 receberá o valor 1, caso contrário permanecerá inalterada
```
df$Coluna_1= ifelse(df$Coluna_1 < 0, 1, df$Coluna_1)
```

###   Replace (substituir)
```
# Substituir os valores na Coluna_1 para (1), se houver linhas na Coluna_2 com o valor (1)
df$Coluna_1[df$Coluna_2== 1] <- 1   

# Substituir os valores (0) da Coluna_1 para (NA) misings
df$Coluna_1[df$Coluna_1== 0] <- NA  

# Substituir os valores (NA) misings da Coluna_1 para (0) 
df$Coluna_1[is.na(df$Coluna_1)] <- 0 

# Substituir os valores na Coluna_2 para (1), se houver linhas na Coluna_2 com o valor (2)
[df$Coluna_2 == 2] <- 1         

# Substiuir valores infinitos (inf) por (NA) missings
df$Coluna_1[is.infinite(df$Coluna_1)] <- NA 

# Substituir valores infinitos (inf) por (NA) missings com `zoo` 
fortify.zoo(log_ret) %>% dplyr::mutate_all(function(x) ifelse(is.infinite(x), 0, x))

# Substituir valores infinitos (inf) por (NA) missings
df$Coluna_1[which(!is.finite(df$Coluna_1))] <- 0

# Substituir valores infinitos (inf) por (NA) missings com `data.table`
invisible(lapply(names(df),function(.name) set(df, which(is.infinite(df[[.name]])), j = .name,value =NA)))

# Substiuir (NA) missings por zero
df$Coluna_1[is.na(df$Coluna_1)] <- 0 

# Substituir os valores (0) das 1 a 10 para (NA) misings
df[, 1:10][ df[, 1:10] == 0 ] <- NA 
```

### Replace decimal virgula por ponto
```
# Substituir decimal por virgula em todoas colunas numéricas
df <- format(df, decimal.mark=",") %>% as.data.frame()
df = as.data.frame(sapply(df, as.numeric))

# Substituir decimal virgula por ponto
df$Coluna_1 <- gsub(",", "\\.", df$Coluna_1)

# Substituir decimal por pornto em todoas colunas numéricas
df <- format(df, decimal.mark=".") %>% as.data.frame()
df = as.data.frame(sapply(df, as.numeric))

# # Substituir decimal ponto por virgula
df$Coluna_1<- gsub("\\.", ",", df$Coluna_1)
```

### Gerar colunas categoricas 
> - Método 2: Suponha que temos uma coluna categórica com difentes tipos de produtos e queremos gerar uma nova coluna categórica agregando esses produtos. A saída deste comando resulta e uma variável com 4 categorias, 0, 1, 2 e 3
```
# Método 1: Com pacote `funModeling` para gerar coluna com 5 categorias
if(!require(funModeling)){install.packages("funModeling")} 
df$Coluna_cat = equal_freq(df$Coluna_1 , n_bins = 5)

# Método 2: Com pacote `dplyr` a partir de determinandas condições
df <- df %>% dplyr::mutate(Coluna_cat_2 = ifelse(Coluna_cat_1 %in% c(1:5,8,9), 1,
                                          ifelse(Coluna_cat_2 %in% c(11, 15:18), 2 ,
                                          ifelse(Coluna_cat_3 %in% c(25, 27, 29), 3, 0))))
```

### Gerar colunas categoricas utilizando quebras estruturais (REFAZER CÓDIGO)
> 1- (quebras estruturais)
> 2 - (Quantil)  
> 3 - (Jenkins)  
```
# 1 - Quebras estruturais
# 2 - Quantil
# 3 - Jenkins
```

###  Adicionar label a uma coluna com pacote `Hmisc`
> `if(!require(Hmisc)){install.packages("Hmisc")}` 
```
# Utilizando nome da coluna
label(df$valores) <- "Coluna_1 valores"

# Utilizando índice da coluna
label(df[[1]]) <- "Coluna_1 descrição"
```

###  Agregar dados por id e Ano com `dplyr`
```
# Agregar dados desconsideraando os missings
df_novo<- df %>% dplyr::group_by(id, Ano) %>%  
  dplyr::summarise(Max_Coluna_1 = max(Coluna_1, na.rm = TRUE),
                   Media_Coluna_1 = mean(Coluna_1, na.rm = TRUE),
                   Total_Coluna_1 = sum(Coluna_1, na.rm = TRUE),
                   Min_Coluna_1 = min(Coluna_1, na.rm = TRUE),
                   Contagem_distinta = n_distinct(Coluna_1, na.rm = TRUE))
```

###  Agregar dados por id e Ano com `data.table`
```
# Agregar dados desconsideraando os missings
df_novo5 <- setDT(df)[,.(Max_Coluna_1   = max(Coluna_1, na.rm=TRUE),
                         Media_Coluna_1 = mean(Coluna_1, na.rm=TRUE),
                         Min_Coluna_1   = min(Coluna_1, na.rm=TRUE),
                         Total_Coluna_1 = sum(Coluna_1, na.rm=TRUE),
                         Contagem_distinta = uniqueN(Coluna_1, na.rm=TRUE)), 
                        by =c("id", "Ano")]
```

### Visualizar informações duplicadas
```
# Gerar tabela com os totais de informações duplicadas
Dup <- data.frame(table(df$Coluna_1, df$Coluna_2))

# Visualizar total de informações repetidas em uma coluna
df$Coluna_1 %>% unique() %>% length() 
```

### Remover  informações duplicadas com `data.table`
```
# Método 1: 
df_novo<- df[, if(.N==1) .SD, .(Coluna_1, Coluna_2, Coluna_3, Coluna_4)]

# Método 2:
df_novo <- unique(df, by =c("Coluna_1", "Coluna_2"))

# Método 3: data.table + dplyr
df_novo <- df %>% unique(by =c("Coluna_1", "Coluna_2"))
```

### Remover  informações duplicadas com `dplyr`
```
df2 <- df %>% dplyr::filter(!duplicated(Coluna_1)) 
```

### Obter o valor mínimo de entre duas colunas
```
df <- transform(df, Min_col_12 = pmin(Coluna_1, Coluna_2))
```

### Gerar coluna com lag e lead de uma coluna agrupado por id 
```
# Gerar lags agrupados por id
df <- df %>% dplyr::group_by(id) %>% 
			  dplyr::mutate(L1_var = dplyr::lag(var, n = 1, default = NA))

# Gerar leads agrupados por id
df <- df %>% dplyr::group_by(id) %>% 
			 dplyr::mutate(F1_var = dplyr::lead(var, n = 1, default = NA))
```

## Strings

### Remover espaços em branco no início e no final da coluna
```
# Método 1: com str_trim
df$Coluna_1 <- str_trim(df$Coluna_1) 

# Método 1: com gsub
df$Coluna_1 <- gsub("[[:space:]]", "", df$Coluna_1)
```

### Contar quantos caracteres tem cada linha da coluna
```
# Contar quantos caracteres tem a Coluna_1
df$Length_Coluna_1 <- str_count(df$Coluna_1)
```

###  Contar  total de celulas vazias
```
# Gerar matrix com o total de linhas vazias de todas colunas
Vazias <- as.matrix(colSums(df==""))

# Contar linhas vazias da Coluna_1
Vazias <- length(which(df$Coluna_1== ''))

# Contar células vazias de todas colunas
Vazias <- apply(df, 2, function(x) length(which(x == '')))
```

### Converter letras minúsculas e maiúsculas
> A função `toupper` converte todas as letras para maiúsculas, enquanto a função `tolower` converte todas as letras para minúsculas.
> 
> `if(!require(stringr)){install.packages("stringr")}`
> `if(!require(magrittr)){install.packages("magrittr")}`
```
# Converter letras para maiúsculas
df$Coluna_1<- toupper(df$Coluna_1)

# Converter letras para maiúsculas com `magrittr`
df %<>% mutate_if(is.character, toupper)

# Converter letras para minúsculas 
df$Coluna_1<- tolower(df$Coluna_1)

# Converter letras para minúsculas com `magrittr`
df %<>% mutate_if(is.character, tolower)

# Converter a primeira letra para maiúsculas com stringr
df$Coluna_1 <- stringr::str_to_title(df$Coluna_1)  
```

### Replace - substituir caracteres com o pacote `stringr`    
>  `if(!require(stringr)){install.packages("stringr")}`    
```
# Replace "-" por "" na Coluna_1
df$Coluna_1<- str_replace(df$Coluna_1, "-", "")

# Replace "[" por "" na Coluna_1
df$Coluna_1 <- str_replace(df$Coluna_1, "\\[", "")

# Replace "\" por "" na Coluna_1
df$Coluna_1 <- str_replace(df$Coluna_1 , "\\\\", "")

# Replace "." por "" na Coluna_1
df$Coluna_1 <- str_replace(df$Coluna_1 , "\\.", "")

# Replace "(" e ")" por "" na Coluna_1
df$Coluna_1 <- str_replace_all(df$Coluna_1 , c("\\(" = "", "\\)" = "")) 

# Replace "mulher" por "homem"
df$Coluna_1 <- str_replace(df$Coluna_1, "mulher", "homem")
```

### Replace - substituir  valores de uma coluna, se outra coluna contém a expressão.
> Exemplo: suponha que a coluna Municipio contém o nome do municipio underline e a Sigla do UF,  para criar uma  coluna UF com a sigla use o código a baixo.
```
# Municípios que terminam com RS
df$Col_UF[which(grepl("RS$", df$Col_Municipio))] <- "RS"

# Municípios  que iniciam com RS
df$Col_UF[which(grepl("^RS", df$Col_Municipio))] <- "RS" 
```

### Remover caracteres específicos
> Nota: use “^x” se quiser excluir os que começam com X; use “x$” sequiser excluir os que terminam com X
```
# Remover as linhas da Coluna_1 que iniciam com a letra X
df_novo <- df[!grepl("^X", df$Coluna_1),]

# Remover as linhas da Coluna_1 que terminan com a letra X
df_novo <- df[!grepl("^X$", df$Coluna_1),]
```

###  Concatenar (Unir) colunas com data.table
```
# Gerar df de exemplo
df <- data.frame(mês = sample(1:12, 30, replace = TRUE),
                 dia = sample(1:28, 30, replace = TRUE),
                 ano = sample(2010:2020, 30, replace = TRUE),
                 valor = rnorm(30))

# Concatenar colunas numéricas
df$data <- paste0(df$dia, "/", df$mês, "/", df$ano)

# Concatenar colunas strings
df$Coluna_3 <- paste(df$Coluna_1, df$Coluna_2, sep = "")
```

### Remover todos caracteres `não-alfanuméricos` (- , . ` ") 
> O primeiro argumento de `gsub` é uma expressão regular, que especifica os caracteres que devem ser substituídos. Nesse caso, o argumento `"[[:punct:]]"` indica que todos os caracteres de pontuação devem ser substituídos.
```
df$Coluna_1 <- gsub("[[:punct:]]", "", df$Coluna_1)
```

### Remover todos caracteres `não-numéricos`
> O primeiro argumento de `gsub` é uma expressão regular, que especifica os caracteres que devem ser substituídos. Nesse caso, o argumento `"[^0-9]"` indica que todos os caracteres que não são números de 0 a 9 devem ser substituídos.
```
# Método 1: com gsub
df$Coluna_1 <- gsub("[^0-9]", "", df$Coluna_1)

# Método 2: com pacote abjutils
df$Coluna_1 <- clean_cnj(df$Coluna_1)
```

### Remover todos caracteres `numéricos`
> O primeiro argumento de `gsub` é uma expressão regular, que especifica os caracteres que devem ser substituídos. Nesse caso, o argumento `'[[:digit:]]+'` indica que todos os caracteres que são números (`[[:digit:]]`) e ocorrem pelo menos uma vez (`+`) devem ser substituídos.
```
df$Coluna_1 <- gsub('[[:digit:]]+', '', df$Coluna_1)
```

### Remover todos `caracteres especiais`
> O primeiro argumento de `gsub` é uma expressão regular, que especifica os caracteres que devem ser substituídos. Nesse caso, o argumento `"[^[:alnum:]]"` indica que todos os caracteres que não são alfanuméricos (`[^[:alnum:]]`) devem ser substituídos.
```
df$Coluna_1 <- gsub('[^[:alnum:]]+', '', df$Coluna_1)
```

###  Gerar função personalizada para remover acentos e caracteres especiais
Fonte: [Retirar acentos de um Data Frame com a Linguagem R](https://www.thomazrossito.com.br/retirar-acentos-de-um-data-frame-com-a-linguagem-r/)

```
# Gerar função
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

# Aplicar função
df$Coluna_1<- rm_accent(df$Coluna_1)
```

### Remover linhas que contém  4 ou mais caracteres da Coluna_1
```
df = df[(which(nchar(df$Coluna_1) >= 4)),]
```

### Remover linhas com uma expressão exata
```
df <- subset(df, Coluna_1!="expressao")
```

### Remover caracteres iniciais e finais
```
# Remover 3 caracteres iniciais
df$Coluna_2 <- substr(df$var, 4, nchar(df$Coluna_1))

# Remover 3 caracteres finais
df$Coluna_2 <- substr(df$var, 1, nchar(df$Coluna_1) - 3)
```

### Deixar somente alguns dígitos 
```
# Deixar somente os 2 primeiros dígitos
df$Coluna_2 <- substr(df$Coluna_1, 1,2)

# Deixar somente o último dígito
df$Coluna_2 <- substr(df$Coluna_1, nchar(df$Coluna_1) - 1, nchar(df$Coluna_1))

# Deixar somente os últimos 4 digitos
df$Coluna_2 = substr(df$Coluna_1, nchar(df$Coluna_1)-3, nchar(df$Coluna_1))

# Deixar somente os digitos 2 ao 4
df$Coluna_2 <- substr(df$Coluna_1, 2, 4)
```

### Encodificar colunas para latin
> Este código é usado para definir o encoding da coluna "Coluna_1" como "latin1". O encoding é o modo como os caracteres são codificados em computadores, e a mudança para "latin1" significa que a coluna será codificada usando o conjunto de caracteres específico para a língua portuguesa. Isso pode ser necessário quando há problemas de codificação ao ler dados em um arquivo ou ao processar dados textuais.
```
Encoding(df$Coluna_1) <- 'latin1'
```

### Substitua caracteres latinos estendidos por Unicode
> A função `escape_unicode` (do pacote stringi) codifica caracteres unicode em sequências de escape unicode. Em outras palavras, ele transforma caracteres unicode em representações de texto que possam ser lidas e processadas por computadores. Em português, a função `escape_unicode` codifica caracteres unicode em sequências de escape unicode.
```
escape_unicode()
```

### Comparar duas colunas strings e gerar probabilidades baseado na semelhança 
>  `if(!require(RecordLinkage)){install.packages("RecordLinkage")}`   

> - A função "levenshteinSim" é uma medida de similaridade que quantifica o número mínimo de edições (inserções, remoções ou substituições) necessárias para transformar uma string na outra.    
> - A função "jarowinkler" é uma medida de similaridade que compara duas strings baseada nas posições dos caracteres comuns em ambas e na quantidade de prefixos comuns entre as strings.        
> -      
```
# Aplicar algoritmo levenshteinSim
df$Prob_levenshteinSim <- levenshteinSim(df$Coluna_1, df$Coluna_2)

# Aplicar algoritmo jarowinkler
df$Prob_jarowinkler <- jarowinkler(df$Coluna_1, df$Coluna_2)

# Comparar duas strings
jarowinkler("Andreas","Anreas")

# Comparar uma string com outras 
levenshteinSim("Andreas",c("Anreas","Andeas"))

# Comparar dois vetores strings
jarowinkler(c("Andreas","Borg"),c("Andreas","Bork"))
```

### Dividir (split) coluna em várias com `splitstackshape`  
>  `if(!require(splitstackshape)){install.packages("splitstackshape")}`   

> O código abaixo divide a coluna "Coluna_1" no dataframe "df" em várias colunas, baseado no separador "/". O resultado da divisão será armazenado no próprio dataframe "df", com cada coluna dividida obtendo um nome com base no nome da coluna original e um sufixo numerado.
> Exemplo: uma coluna com datas 01/01/2020
```
# Dividir coluna por "/"
df <- cSplit(df, "Coluna_1", "/") 
```

## Missings Values


###  Visualizar total de missings das colunas de um dataframe
`if(!require(funModeling)){install.packages("funModeling")} `
```
# Método 1: sem pacote
Missings <- as.matrix(colSums(is.na(df)))
print(Missings)

# Método 2: com pacote funModeling
df_status(df)

# Método 3: com lyrsapply
lyrsapply(df, function(x) sum(is.na(x))) 
```

###  Gerar tabela resumo de missings, zeros e vazios
```
resumo <- df_status(df)
resumo$vazias <- apply(df, 2, function(x) length(which(x == '')))
resumo$Obs_Total <- nrow(df)
resumo$perc_vazias = df$vazias / df$Obs_Total
```

###  Gerar nova coluna com o total de missings agregado por  id 
```
df<- df%>% dplyr::group_by(id) %>% dplyr::mutate(contagem = sum(!is.na(Coluna_1)))
```

###   Remover missing das colunas de um dataframe
```
# Remover missings da Coluna_1
df <- df[!is.na(df$Coluna_1),]

# Remover todas linhas missings do df
df <- df[complete.cases(df),]

# Remover missings de algumas colunas utilizando o índice
df <- df[complete.cases(df[, 2:10]),]
```

###   Remover linhas e colunas com valores missings
```
# Remover colunas com mais de 50% de NA
df[, which(colMeans(!is.na(df)) > 0.5)]

# Remover linhas com mais de 50% de NA
df[which(rowMeans(!is.na(df)) > 0.5),]

# Remover colunas e linhas com mais de 50% de NA
df[which(rowMeans(!is.na(df)) > 0.5), which(colMeans(!is.na(df)) > 0.5)]

# Remover linhas de colunas que apresentam apenas missings
df_novo <- df[!(is.na(df$Coluna_1)) | !(is.na(df$Coluna_2)) | !(is.na(df$Coluna_3)),]

# Remover valores missings agrupado por id e Ano utilizando o indice com `imputeTS`
df <- df %>% group_by(id, Ano) %>% na_remove(df[, 1:10])
```

###  Replace - substituir missings com valores de outras colunas `dplyr`
> A função "coalesce" para preencher os valores faltantes na coluna "Coluna_1" com o primeiro valor não nulo das colunas "Coluna_2" ou "Coluna_3".
```
# Método 1: com a função coalesce
df <- df %>% dplyr::mutate(Coluna_1 = coalesce(Coluna_1, Coluna_2, Coluna_3))

# Método 2: com a função ifelse
df$Coluna_1 <- ifelse(is.na(df$Coluna_1), df$Coluna_2, df$Coluna_1)
```

###   Replace - substituir de todas colunas com 'nan' para 'NA'
> A função "lapply" é aplicada aos nomes de todas as colunas no data frame "df". Para cada coluna, a função "set" é usada para localizar os valores NaN na coluna em questão e substituí-los por NA. A palavra-chave "invisible" é usada para suprimir a saída da função "lapply".
```
invisible(lapply(names(df),function(.name) set(df, which(is.nan(df[[.name]])), j = .name,value =NA)))
```

###   Imputar valores missings com os valores anteriores ou posteriores com `dplyr`      
Este código está em R e usa a sintaxe do pacote dplyr para preencher valores ausentes nas colunas "Coluna_1" e "Coluna_2" do data frame "df". O data frame é primeiro agrupado por "id" usando a função "group_by". Em seguida, a função "fill" é usada para preencher os valores ausentes com o valor mais próximo na mesma coluna, começando pela parte de baixo para cima e depois de cima para baixo (".direction = "downup").          
```
# Ordenar colunas
df <- df[order(df$id),]

# Imputar informações
df <- df %>% dplyr::group_by(id) %>%  dplyr::fill(c(Coluna_1, Coluna_2), .direction = "downup")
```

###   Imputar valores missings  com a média, mediana e interpolação geral da coluna com `dplyr`
```
# Imputar valores missings com a média
df$Coluna_1 = ifelse(is.na(df$Coluna_1), mean(df$Coluna_1, na.rm=TRUE), df$Coluna_1)

# Imputar valores missings com a mediana
df$Coluna_1 = ifelse(is.na(df$Coluna_1), median(df$Coluna_1, na.rm=TRUE), df$Coluna_1)

# Imputar valores missings com interpolação
df <- df %>%  dplyr::mutate_at(vars(Coluna_1, Coluna_2, Coluna_3), 
			  list(inter = ~na.approx(., na.rm = FALSE)))
```

###   Imputar valores missings  com a média e mediana  da coluna agrupada por id com `dplyr`
```
# Imputar valores missings com a média e mediana agrupada por id
impute.mean <- function(x) replace(x, is.na(x), mean(x, na.rm = TRUE))
df <- df %>% dplyr::group_by(id) %>% dplyr::mutate(Media_Coluna_1 = impute.mean(Coluna_1), 
                                                   Mediana_Coluna_1 = impute.mean(Coluna_1)) 
```

###  Imputar valores missings  com a média e mediana  da coluna agrupada por id com `datatable`
```
# Imputar valores missings com a média agregada por id
df <- df[is.na(df$Coluna_1), "Media_Coluna_1"] <- mean(na.omit(df$Coluna_1))

# Imputar valores missings com a mediana agregada por id
df <- df[is.na(df$Coluna_1), "Mediana_Coluna_1"] <- median(na.omit(df$Coluna_1))

# Imputar valores missings com a média agregada por id para uma lista de colunas
cols <- c("Coluna_1", "Coluna_2", "Coluna_3", "Coluna_4")

df <- df[,(cols):= lapply(.SD, function(x) nafill(x, type = "const", fill = median(x, na.rm = TRUE))), by = id, .SDcols = cols][]
```

###   Imputar valores missings com `imputeTS`  
> https://cran.rstudio.com/web/packages/imputeTS/vignettes/Cheat_Sheet_imputeTS.pdf
https://cran.r-project.org/web/packages/imputeTS/readme/README.html

> Outras funções do package
> - ggplot_na_distribution, 
> - ggplot_na_intervals, 
> - ggplot_na_gapsize, 
> - ggplot_na_imputations

> ` if(!require(imputeTS)){install.packages("imputeTS")}`
```
# Atribuir zeros aos valores missings de uma coluna
df$Coluna_1 <- na_replace(df$Coluna_1, 0)

# Atribuir zeros aos valores missings utilizando o índice das colunas 
df[, 1:20] <- na_replace(df[, 1:20], 0)

# Atribuir zeros aos valores missings de todas colunas do dataframe
df <- na_replace(df, 0)
```

###   Imputar valores missings com `tidyr` e  `imputeTS` 

> ` if(!require(tidyr)){install.packages("tidyr")}`
> ` if(!require(imputeTS)){install.packages("imputeTS")}`
```
## Criar lista com nome das colunas (col_names) e obter o índice das colunas (Col_number)
col_names <- c("Coluna_1", "Coluna_2", "Coluna_3", "Coluna_4")
Col_number <- which(names(df) %in% col_names )

# Imputar valores missings com MEDIANA agrupado por id e Ano
df <- df %>% group_by(id, Ano) %>% na_mean(df[, Col_number], option = "median")

# Imputar valores missings com MÉDIA agrupado por id e Ano
df <- df %>% group_by(id, Ano) %>% na_mean(df[, Col_number])

# Imputar valores missings com a MODA agrupado por id e Ano
df <- df %>% group_by(id, Ano) %>% na_mode(df[, Col_number])

# Imputar valores missings com INTERPOLAÇÃO agrupado por id e Ano
df <- df %>% group_by(id, Ano) %>% na_interpolation(df[, Col_number], option = "spline")

# Imputar valores missings com VALORES ALEATÓRIOS agrupado por id e Ano
df <- df %>% group_by(id, Ano) %>% na_random(df[, Col_number])

# Imputar valores missings com ZERO agrupado por id e Ano
df <- df %>% group_by(id, Ano) %>% na_replace(df[, Col_number], 0)
```

## Dummy (One Hot Encode)

### Gerar coluna dummy com ifelse
> Nota: se var for igual "abc" será atribuído ao valor de 1 caso contrário será 0
```
# Gerar coluna dummy se em alguma linha da Coluna_1 contém "Homem"
df$D_Masculino <- ifelse(df$Coluna_1 == "Homem",1,0)

# Gerar coluna dummy se em alguma linha da Sexo contém "Homem"
df$D_Masculino <- ifelse(df$Sexo == 'M', 1,0)

# Gerar coluna dummy se em alguma linha da Sexo contém "Feminino"
df$D_Feminino  <- ifelse(df$Sexo == 'F', 1,0)
```

### Gerar coluna dummy a partir de diversas condições
> O código cria uma nova coluna dummy  se os valores da Coluna_1 for igual (1, 10, 28) e os valores da Coluna_2 for igual a (2, 5, 23:26), neste caso, será atribuído ao valor de 1 D_Coluna e 0 caso contrário
```
df <- df %>% dplyr::mutate(D_Coluna = ifelse(Coluna_1 %in% c(1,10,28), 1,                   
                                      ifelse(Coluna_2 %in% c(2,5,23:26), 1,0)))
```

### Gerar coluna dummy com `fastDummies`  
`if(!require(fastDummies)){install.packages("fastDummies")}`          
```
# Gerar colunas dummy para cada valor da Coluna_1 
df <- dummy_cols(df, select_columns =c("Coluna_1"))
```

### Gerar coluna dummy a partir de uma string com `stringr`
```
# Gerar coluna dummy se a Coluna_str contém a expressão "teste"
df$D_coluna_str <- as.integer(str_detect(df$Coluna_str, "teste"))

# Gerar coluna dummy se a Coluna_str contém a expressão "teste" de outra forma
df$D_coluna_str <- 0
df$D_coluna_str[as.integer(str_detect(df$Coluna_str,"teste")) == 1] <- 1

# Gerar coluna dummy a partir de uma lista de strings
Palavras = c("Palavra_1|Palavra_2|Palavra_3|frase com espaços")
df$D_coluna_str <- as.integer(str_detect(df$Coluna_str, Palavras))
```

### Gerar coluna dummy com a função  str_detect do `stringr`
```
# Gerar df de exemplo
df <- data.frame(Coluna_str = c("abacate", "banana", "cenoura", "damasco"))

# Gerar coluna dummy se Coluna_str contém "a" em qualquer posição
df$D_coluna_str_1 <- as.integer(str_detect(df$Coluna_str, "a"))

# Gerar coluna dummy se Coluna_str contém "a" na posição inicial
df$D_coluna_str_2 <- as.integer(str_detect(df$Coluna_str, "^a"))

# Gerar coluna dummy se Coluna_str contém "a" na posição final
df$D_coluna_str_3 <- as.integer(str_detect(df$Coluna_str, "a$"))

# Gerar coluna dummy se Coluna_str contém "aeiou" em qualquer posição
df$D_coluna_str_4 <- as.integer(str_detect(df$Coluna_str, "[aeiou]"))
```


##  Colunas tipo `Date`

###   Converter coluna para date com `lubridate`
`if(!require(lubridate)){install.packages("lubridate")}`       

```
# df de exemplo
df <- data.frame(Data_str= c("2022-12-01", "2021-06-15", "2020-01-30"))

# Gerar nova coluna do tipo date
df$Data_date <- ymd(paste(df$Data_str))

# Gerar nova coluna extraindo apenas o ano
df$Ano <- format(as.Date(df$Data_str, format="%d/%m/%Y"),"%Y")

# Gerar nova coluna extraindo apenas o mês 
df$Mes <- format(as.Date(df$Data_str, format="%d/%m/%Y"),"%m")

# Gerar nova coluna extraindo apenas o dia
df$Mes <- format(as.Date(df$Data_str, format="%d/%m/%Y"),"%d")
```

## Outliers

### Identificar e tratar outliers com  `funModeling`                               
 `if(!require(funModeling)){install.packages("funModeling")}`      
 
> Ver mais em: http://pablo14.github.io/funModeling/articles/funModeling_quickstart.html   
    
>- Método 1:  **Botom and Top Limits**        
>O método de remoção de outliers botom and top limits de 1% é um método de limpeza de dados. Ele remove valores extremos de ambos os lados da distribuição - botom (inferior) e top (superior) - para limpar os dados e remover outliers. O método remove os valores 1% mais baixos e os 1% mais altos da distribuição, o que reduz o impacto de valores extremos sobre os resultados.      
>   
>- Método 2:  **Hampel**        
>A abordagem Hampel é baseada em medidas de dispersão (como a mediana e o desvio padrão) e define um intervalo para valores "normais". Valores fora desse intervalo são considerados outliers. Esse método é considerado robusto, pois é menos afetado por valores extremos.         

>- Método 3:  **Turkey**
> A abordagem Tukey utiliza um limite inferior e um limite superior definidos arbitrariamente para identificar e remover outliers. O limite inferior é geralmente definido como Q1 - 1,5 * IQR (onde Q1 é o primeiro quartil e IQR é a diferença interquartil) e o limite superior é definido como Q3 + 1,5 * IQR (onde Q3 é o terceiro quartil). Qualquer valor que esteja fora dos limites é considerado um outlier e é então removido. Esse método é útil para limpar dados e remover outliers, mas deve ser usado com cuidado para evitar a remoção de valores importantes.

> **# Gerar novas colunas tratadas**
```
# Gerar df de exemplo com outliers
set.seed(10)
df=data.frame(var1=rchisq(1000,df = 1), var2=rnorm(1000))
df=rbind(df, 1135, 2432) # forcing outliers
df$id=as.character(seq(1:1002))

# Método 1: Limite inferior e superior de 1%
df$var1_treated_tp = prep_outliers(data = df$var1,
                                   type='set_na',
                                   bottom_percent = 0.01, 
                                   top_percent  = 0.01, 
                                   method = "bottom_top")
                                   
# Método 2: Hampel
df$var1_treated_hampel = funModeling::prep_outliers(data = df$var1,
                                               method = "hampel",  
                                               type='stop')
                                               
# Método 2: Turkey
df$var1_treated_tukey = funModeling::prep_outliers(data = df$var1,
                                                   method = "tukey",  
                                                   type='stop')
```
> **# Gerar novos dataframes tratados** (ideal para tratar muitas colunas)
```
# Gerar df de exemplo com outliers
set.seed(10)
df=data.frame(var1=rchisq(1000,df = 1), var2=rnorm(1000))
df=rbind(df, 1135, 2432) # forcing outliers
df$id=as.character(seq(1:1002))

# Método 1: Limite inferior e superior de 1%
df_treated_tp = prep_outliers(data = df 
                              input = c('var1', 'var2'), 
                              type='set_na',
                              bottom_percent = 0.01, 
                              top_percent  = 0.01, 
                              method = "bottom_top")   
                                                        
# Método 2: Hampel
df_treated_hampel = funModeling::prep_outliers(data = df,
                                               input = c('var1', 'var2'),
                                               method = "hampel",  
                                               type='stop')
# Método 2: Turkey
df_treated_tukey = funModeling::prep_outliers(data = df,
                                              input = c('var1', 'var2'),
                                              method = "tukey",  
                                              type='stop')
```

### Identificar e tratar outliers com  Z-SCORE      
> Z-Score é uma medida de distância, usada para identificar outliers. É definido como a diferença entre um valor e a média da sua coluna, dividido pelo desvio padrão. Por exemplo, se um valor estiver a mais de 3 desvios padrões da média, isso significa que ele é um outlier. Z-Score é usado principalmente para identificar outliers em conjuntos de dados.                         
```
# Calcular o z-score das variáveis
df$Z_Coluna_1 <- scale(df$Coluna_1)

# Identificar os outliers (3 desvios padrões)
Outliers_Coluna_1 <- which(df$Z_Coluna_1 > 3 | df$Z_Coluna_1 < -3)

# Remover os outliers
df <- subset(df, !(row.names(df) %in% Outliers_Coluna_1))
```

###   Plotar gráfico de dispersão com (ggplot2, tigerstats e plotly)
> O gráfico de dispersão é uma ferramenta muito importante para identificar outliers/valores discrepantes. Ao visualizar os dados em um gráfico de dispersão, é possível ver rapidamente se há pontos que estão muito distantes dos demais. Esses pontos são chamados de outliers.

> `if(!require(pacman)){install.packages("pacman")}`
> `p_load(ggplot2, tigerstats, plotly)`

```
# Plotar gráfico de dispersão simples (sem pacote)
plot(df$Coluna_1, df$Coluna_2)

# Plotar gráfico de dispersão condicional a dummy de tratamento com (tigerstats)
xyplot(df$Coluna_1 ~ df$Coluna_2 | df$D_tratamento) 

# Plotar gráfico de dispersão simples com (ggplot2)
ggplot(df, aes(x=Coluna_1, y=Coluna_2)) + geom_point()

# Plotar gráfico de dispersão condicional a dummy de tratamento com (tigerstats)
ggplot(df, aes(x=Coluna_1, y=Coluna_2, color=D_tratamento)) + 
  geom_point(aes(color = ifelse(D_tratamento == 1, "D_tratamento 1", "D_tratamento 0")))

# Plotar gráfico de dispersão simples com (plotly)
plot_ly(df, x = df$Coluna_1, y = df$Coluna_2)

# Plotar gráfico de dispersão condicional a dummy de tratamento com (plotly)
plot_ly(df, x=df$Coluna_1, y=df$Coluna_2, color=df$D_tratamento) %>%
  add_trace(color=ifelse(df$D_tratamento == 1, "Dummy 1", "Dummy 0"))
```

###   Plotar gráfico boxplot com (ggplot2  e plotly)
> Os gráficos boxplot são uma ferramenta útil para identificar outliers/valores discrepantes. O boxplot mostra a distribuição de dados ao longo de um eixo e representa as observações em quartis. Os outliers são pontos que estão fora dos limites do boxplot (ou seja, pontos que estão muito distantes dos quartis). O boxplot também permite avaliar a simetria da distribuição dos dados e identificar pontos discrepantes, que podem ser devido a erros de entrada de dados, erros de medição ou outros fatores. Assim, os gráficos boxplot são uma ferramenta importante para identificar outliers.
> 
> `if(!require(pacman)){install.packages("pacman")}`
> `p_load(ggplot2, plotly)`
```
# Plotar boxplot com outliers
boxplot(df$Coluna_1, outline = TRUE)

# Plotar boxplot para mais de uma coluna com outliers
boxplot(df[, c("Coluna_1", "Coluna_2")], main="df"

# Plotar boxplot sem outliers
boxplot(df$Coluna_1, outline = FALSE)

# Visualizar valores dos outliers
boxplot.stats(df$Coluna_1)$out 

# Plotar boxplot na horizontal com outliers utilizando (ggplot2)
ggplot(df, aes(x=Coluna_1)) + geom_boxplot()

# Plotar boxplot na vertical com outliers utilizando (ggplot2)
ggplot(df, aes(y=Coluna_1)) + geom_boxplot(orientation = "v")

# Plotar boxplot na vertical com outliers agrupado pela dummy de tratamento utilizando (ggplot2)
ggplot(df, aes(y=Coluna_1)) + geom_boxplot(orientation = "v") + facet_wrap(~D_tratamento)

# Plotar boxplot com outliers utilizando (plotly)
plot_ly(df, x = df$Coluna_1, type = 'box')
```

### Plotar gráfico de densidade
```
plot(density(df$Coluna_1), ylab='Density', xlab='Coluna_1')
```


## Estatísticas descritivas e AED


### Estatísticas descritivas sem pacotes
```
# Estatísticas descritivas de todo o dataframe
summary(df)

# Estatísticas descritivas de apenas duas colunas
summary(df$Coluna_1, df$Coluna_2)

# Estatísticas descritivas por id
tapply(df$Coluna_1, df$id, summary)
```

### Estatísticas descritivas com  `funModeling`
> Este pacote contém um conjunto de funções relacionadas à análise exploratória de dados (AED) . 
> 
> Ver mais: [funModeling quick-start {#quick_start} (r-project.org)](https://cran.r-project.org/web/packages/funModeling/vignettes/funModeling_quickstart.html)
>
>  `if(!require(funModeling)){install.packages("funModeling")}`
```
# Estatísticas descritivas de todo o dataframe
profiling_num(df)

# Estatísticas descritivas de apenas uma coluna
profiling_num(df$Coluna_1)

# Estatísticas descritivas (arredondando para 3 casas decimais)
profiling_num(df) %>% dplyr::mutate_if(is.numeric, ~round(., 3))
```

### Estatisticas Descritivas com `stargazer`       
> Este pacote  cria código LATEX, código HTML e texto ASCII para tabelas de regressão bem formatadas, com vários modelos lado a lado, bem como para tabelas estatísticas resumidas, quadros de dados, vetores e matrizes.
> 
> Ver mais: [stargazer.pdf (r-project.org)](https://cran.r-project.org/web/packages/stargazer/vignettes/stargazer.pdf)
> 
>  `if(!require(stargazer)){install.packages("stargazer")} `                 
```
# Estatísticas descritivas de todo o df (Visualização rápida)
stargazer(df, type = "text", out = "Descritivas.txt")

# Estatísticas descritivas de todo o df (Visualização rápida e exportar como .txt)
stargazer(df, type = "text", out = "Descritivas.txt")

# Estatísticas descritivas de todo o df e arredondar para 3 casas decimais (Exportar.doc)
stargazer(df, type = "html",title="Descritivas", digits=3, out = "Descritivas.doc")

# Escolher as estatísticas descritivas que serão apresentadas
columns <- colnames(df)
Desc <- stargazer( df[,columns], type = "text",
  summary.stat = c("min", "p25", "median", "p75", "max", "median", "sd"))
Desc 
```

### Estatisticas Descritivas com `fields`
> Este pacoate  é uma coleção de funções para  dados espaciais e estatísticas espaciais.  
>
>Ver mais: [pacote de campos - RDocumentation](https://www.rdocumentation.org/packages/fields/versions/3.3.1) 
>
`if(!require(fields)){install.packages("fields")} `
```
# Estatísticas descritivas de todo o df
stats(df)

# Estatísticas descritivas de uma coluna por id
stats(df$Coluna_1, by=df$id)

# Gerar tabela de estatísticas descritivas de algumas colunas arredondando para 3 decimais
Tabela_descritivas <- cbind(stats(df$Coluna_1), stats(df$Coluna_2), stats(df$Coluna_3))
colnames(Tabela_descritivas) <- c("Coluna_1","Coluna_2", "Coluna_3")
round(Tabela_descritivas, 3)
```

### Estatisticas Descritivas com `pastecs`
> Este pacote é para Análise de Série Ecológica Espaço-Tempo
>
> Ver mais :[pastecs package - RDocumentation](https://www.rdocumentation.org/packages/pastecs/versions/1.3.21)
>
>`if(!require(pastecs)){install.packages("pastecs")}`
```
# Estatísticas descritivas de todo o df na vertical
stat.desc(df) 

# Estatísticas descritivas de todo o df na horizontal
t(stat.desc(df))

# Estatísticas descritivas de colunas específicas
stat.desc(df[,c("coluna_1", "coluna_2", "coluna_3")])

# Estatísticas descritivas de colunas específicas com mais estatisticas e teste
stat.desc(df[,c("coluna_1", "coluna_2", "coluna_3")], basic=TRUE, desc=TRUE, norm=TRUE, p=0.95)

# Estatísticas descritivas de todo o df na horizontal com valores arredondados (necessário o pacote `dplyr`)
t(stat.desc(df) %>% dplyr::mutate_if(is.numeric, ~round(., 3)))

# Exportar estatísticas descritivas para .xlsx (necessário `dplyr` e `openxlsx` )
Descritivas <- as.data.frame(t(stat.desc(df) %>% dplyr::mutate_if(is.numeric, ~round(., 3))))
write.xlsx(Descritivas, "Descritivas.xlsx", row.names = TRUE)
```

### Matriz de correlação sem pacote
> As três medidas de correlação (Pearson, Kendall e Spearman) são usadas para quantificar a relação linear ou não linear entre duas variáveis. Aqui estão as diferenças entre elas:

>1.  Correlação de Pearson: é uma medida de associação linear entre duas variáveis. A correlação de Pearson é baseada no cálculo do coeficiente de correlação, que varia de -1 a 1, onde -1 indica uma correlação negativa perfeita, 1 indica uma correlação positiva perfeita e 0 indica ausência de correlação linear.
    
>2.  Correlação de Kendall: é uma medida de associação não linear entre duas variáveis. A correlação de Kendall é baseada no cálculo do coeficiente de Kendall, que também varia de -1 a 1, onde -1 indica uma correlação negativa perfeita, 1 indica uma correlação positiva perfeita e 0 indica ausência de correlação.
    
>3.  Correlação de Spearman: é uma medida de associação não linear que usa as classificações das variáveis ao invés dos valores reais. A correlação de Spearman é baseada no cálculo do coeficiente de Spearman, que varia de -1 a 1, onde -1 indica uma correlação negativa perfeita, 1 indica uma correlação positiva perfeita e 0 indica ausência de correlação.
    
> Em resumo, a correlação de Pearson é a mais ampla e é usada para relações lineares, enquanto as correlações de Kendall e Spearman são usadas para relações não lineares.
```
# Matrix de correlação de pearson de todo o dataframe
cor(df)

# Matrix de correlação de pearson de todo o dataframe arredondando para 2 decimais
round(cor(df), 2)

# Matrix de correlação Pearson de colunas específicas
cor(df[,c("coluna_1","coluna_2","coluna_3")])

# Correlação de Pearson entre duas colunas (Pearson é o padrão)
cor(df$coluna_1, df$coluna_2, method = "pearson")

# Correlação de Kendall entre duas colunas
cor(df$coluna_1, df$coluna_2, method = "kendall")

# Correlação de spearman entre duas colunas
cor(df$coluna_1, df$coluna_2, method = "spearman")

# Para apresentar as correlações de forma organizada em formato markdown
knitr::kable(cor(df))
```

### Matriz de correlação com `funModeling`                
```
# Matrix de correlação de todas as colunas em relação a coluna_1
correlation_table(df, "coluna_1")
```

### Matriz de correlação com `stargazer`
```
# Matrix de correlação de todas as colunas
correlation.matrix <- cor(df[,c("coluna_1", "coluna_2", "coluna_3")]) 
stargazer(correlation.matrix, title="Matriz de Correlação", type = "text")
```

### Plotar correlograma  com `corrplot`
> O pacote corrplot fornece uma ferramenta exploratória visual na matriz de correlação que oferece suporte à reordenação automática de variáveis para ajudar a detectar padrões ocultos entre as variáveis.
> 
>O corrplot é muito fácil de usar e oferece uma ampla gama de opções de plotagem no método de visualização, layout gráfico, cor, legenda, rótulos de texto, etc. Ele também fornece valores-p e intervalos de confiança para ajudar os usuários a determinar a significância estatística das correlações.

> Ver mais: [Visualize correlation matrix using correlogram - Easy Guides - Wiki - STHDA](http://www.sthda.com/english/wiki/visualize-correlation-matrix-using-correlogram)
>
>`if(!require(corrplot)){install.packages("corrplot")}`

```
# Correlograma com circulos coloridos indicando a correlação
corrplot(cor(df), method = "circle")

# Correlograma com quadrados coloridos indicando a correlação
corrplot(cor(df), method = "square")

# Correlograma com quadrados coloridos indicando a correlação
corrplot(cor(df), method = "color")

# Correlograma com quadrados coloridos indicando a correlação
corrplot(cor(df), method = "number")

# Correlograma com gráficos de pizza coloridos indicando a correlação
corrplot(cor(df), method = "pie")

# Correlograma com quadrados hachurado oloridos indicando a correlação
corrplot(cor(df), method = "shade")

# Correlograma par-a-par de todas colunas
pairs(swiss)
```

###  Tabela de frequências (para colunas categóricas)
```
# (Tabular) contagem de ocorrências de uma coluna categórica
table(df$Coluna_1)

# (Tabular) contagem de ocorrências utilizando loop para as colunas categórica de 1 a 10
apply(df[,1:10],2,function(x) table(x))

# (Tabular) contagem de ocorrências utilizando loop com varias colunas categórica por (Ano)
apply(df[,1:10],2,function(x) table(x, df$Ano))

# Frequência e proporção relativa
prop.table(table(df$Coluna_1))
```

### Tabular dados e plotar  com `funModeling` 
> `if(!require(funModeling)){install.packages("funModeling")}`
```
# (Tabular) contagem de ocorrências de uma coluna categórica  
freq(df, "Coluna_1")                     

# Plotar contagem de ocorrências de todas colunas
plot_num(df, path_out = ".")

# (Tabular) contagem de ocorrências de uma coluna categórica, pedindo somente as 5 primeiras categorias
head(freq(df, "Coluna_1"), 5) 
```

### Plotar gráfico Histograma sem pacote
```
hist(df$Coluna_1, breaks = 5, col = 'grey', xlab = 'Coluna_1')
```

## Merge, Join, Append

> Fazer um join ou um merge nada mais é do que juntar dois conjuntos de dados por meio de um ou mais campos em comum (chaves/key).
> Ver mais : 
> * https://rpubs.com/CristianaFreitas/311735
> * [Fulljoin: Tudo sobre Joins (merge) em R](https://www.fulljoin.com.br/posts/2016-05-12-tudo-sobre-joins/)


###  Append (empilhar data frames)
> Existem algumas condições que devem ser cumpridas para que a função `rbind` possa ser usada com sucesso:
> 1.  Os dois dataframes devem ter o mesmo número de colunas.   
> 2.  Os nomes das colunas dos dois dataframes devem ser os mesmos.  
> 3.  Os tipos de dados das colunas dos dois dataframes devem ser os mesmos.
```
# Append de dois dataframes
df_3 <- rbind(df_1, df_2)

# Append de três ou mais dataframes
df_novo <- rbind.data.frame(df1, df2, df3)

# Append de dois ou mais dataframes com o pacote `data.table`
df_novo <- data.table::rbindlist(list(df1,df2))
```

### Merge

> A função `merge` junta dois dataframes baseados nas colunas especificadas na lista `by`. Isso significa que as linhas dos dataframes `df_1` e `df_2` serão combinadas de acordo com o valor das colunas em `by`. Se o valor dessas colunas for o mesmo em ambos os dataframes, as linhas serão combinadas em uma única linha no resultado final.
> 
> A opção `all` pode ser definida como `TRUE` ou `FALSE`. Se `all = TRUE`, as linhas presentes em um dos dataframes serão mantidas no resultado final, mesmo que não haja correspondente na outra. Se `all = FALSE` (padrão), apenas as linhas que correspondem a ambos os dataframes serão incluídas no resultado final.

> Existem algumas condições que devem ser cumpridas para que a função `merge` possa ser usada com sucesso:
>1.  Os dois dataframes devem ter pelo menos uma coluna comum que possa ser usada para juntá-los.   
>2.  As colunas especificadas em `by` devem existir em ambos os dataframes.
    
> Se essas condições não forem atendidas, a função `merge` retornará um erro.

> Ver mais : 
> * https://rpubs.com/CristianaFreitas/311735
> * [Fulljoin: Tudo sobre Joins (merge) em R](https://www.fulljoin.com.br/posts/2016-05-12-tudo-sobre-joins/)
```
# Merge para quando os nomes das colunas chaves são iguais em ambos dfs
df_3 <- merge(df_1, df_2, by=c('id','Ano'), all=TRUE)

# Merge para quando os nomes das colunas chaves são diferentes em ambos dfs
df_3 <- merge(df_1, df_2, by.x='id', by.y='ID', all=TRUE)
```

###  Left_join com `dplyr` 
> `if(!require(tidyverse)){install.packages("tidyverse")}`
> 
> O mesmo código serve para `left _join`  `right_join`  `inner_join`  `full_join`
> 
> `left_join` é uma função do pacote `dplyr` que permite juntar dois dataframes baseados em colunas comuns. 

> A função `left_join` junta dois dataframes baseados nas colunas comuns. Isso significa que as linhas de `df_1` serão combinadas com as linhas correspondentes em `df_2`, se existirem. As linhas em `df_1` que não têm correspondência em `df_2` serão mantidas no resultado final sem valores para as colunas de `df_2`.

> Existem algumas condições que devem ser cumpridas para que a função `left_join` possa ser usada com sucesso:
>  1.  Os dois dataframes devem ter pelo menos uma coluna comum que possa ser usada para juntá-los.
>  2.  As colunas comuns devem ter o mesmo nome em ambos os dataframes.
>  
> Ver mais : 
> * https://rpubs.com/CristianaFreitas/311735
> * [Fulljoin: Tudo sobre Joins (merge) em R](https://www.fulljoin.com.br/posts/2016-05-12-tudo-sobre-joins/)
```
# Left join sem especificar as colunas chaves (o algoritmo identifica automaticamente as colunas com mesno nomes)
df_3 <- left_join(df_1, df_2) 

# Left join para quando os nomes das colunas chaves são iaguais em ambos df
df_3 <- left_join(df_1, df_2, by = c("id"))

# Left join para quando os nomes das colunas chaves são diferentes em ambos df
df_3 <- left_join(df_1, df_2, by = c("id" = "ID"))

# Left join para unir mais de dois dataframes
joined <- list(df_1, df_2, df_3, df_4, df_5, df_6, %>% 
               reduce(left_join, by = c("id", "Ano"), fill=TRUE)

# Left join e adicionar sufixo aos nome das colunas 
df_3 <- left_join(df_1, df_2, by = "id", suffix = c(".df_1", ".df_2"))

# Left join sem linhas adicionais no df resultante
df_3 <- left_join(df_1, df_2, by = "id") %>% distinct(id, .keep_all = TRUE)
```


### Left_join  para grande volume de dados com  `tibble`
> `if(!require(tibble)){install.packages("tibble")}`
> 
> `as.tibble` é uma função que converte um objeto do R em um tibble, que é um tipo de dataframe especializado fornecido pelo pacote `tibble`. Tibbles são similares a dataframes normais, mas têm algumas diferenças, como uma formatação de saída mais legível e a preservação de valores faltantes na representação de saída.

> `lazy_dt` é uma função do pacote `lazy.dt` que ativa o modo lazy evaluation para o tibble. Isso significa que os dados do tibble não serão avaliados até que sejam realmente necessários, o que pode aumentar a velocidade de processamento em grandes quantidades de dados.
```
# Converter o data.frame para tibble
df_1 <- as.tibble(df_1) %>% lazy_dt()
df_2 <- as.tibble(df_2) %>% lazy_dt()

# Join
df_3 <- left_join(df_1, df_2, by=c("id", "Ano")) %>% as_tibble()
```


## Importar e exportar dados

### Formatos de arquivo suportados e seus pacotes
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


### Importar arquivo Excel *`.xlsx`* com `readxl`
> `if(!require(readxl)){install.packages("readxl")}`
```
df <- read_excel("D:\Planilha.xlsx", sheet = "Planilha1")
```

### Importar e exportar arquivo Excel *`.xlsx`* com `openxlsx`
> `if(!require(openxlsx)){install.packages("openxlsx")}`
```
# Importar planilha .xlsx
df <- read.xlsx('D:\Planilha.xlsx')

# Exportar planilha .xlsx
write.xlsx(df, "D:\Planilha.xlsx")
```

### Exportar arquivo Excel *`.xlsx`* para diferentes  sheet com `xlsx`
> `if(!require(xlsx)){install.packages("xlsx")}`
```
write.xlsx(df, 
           "D:\Planilha.xlsx", 
           sheetName = "Sheet1", 
           col.names = TRUE, 
           row.names = TRUE, 
           append = FALSE))
```

### Importar arquivos do stata `*.dta*` com `haven`

> O pacote `haven` do R é usado para ler dados de diferentes formatos, como SPSS, SAS e Stata. As funções `zap_empty()`, `zap_formats()`, `zap_label()` e `zap_widths()` são algumas das funções de limpeza que o pacote `haven` fornece para ajudar a limpar e preparar dados importados.

> 1.  `zap_empty()`: Esta função remove colunas vazias do dataframe importado.   
> 2.  `zap_formats()`: Esta função remove informações de formatação, como formato de data e moeda, do dataframe importado.
> 3.  `zap_label()`: Esta função remove informações de rótulo das variáveis, como descrições detalhadas, do dataframe importado.
> 4.  `zap_widths()`: Esta função remove informações sobre a largura das variáveis, como o número máximo de caracteres, do dataframe importado.
    
> Essas funções podem ser úteis para remover informações desnecessárias dos dados importados, o que pode ajudar a tornar o trabalho com esses dados mais fácil e eficiente. Além disso, a remoção de informações desnecessárias também pode ajudar a economizar espaço de armazenamento e recursos de processamento.
> 
> > `if(!require(haven)){install.packages("haven")}`
> 
> ver mais: https://rdrr.io/cran/haven/man/zap_labels.html
```
# Importar dados stata mantendo label e outras informações do stata
read_dta("D:/Arquivo.dta")

# Importar dados stata e remover label e outras informações do stata
read_dta(D:/Arquivo.dta") %>% zap_label() %>% zap_formats()

# Exportar arquivo stata .dta
write_dta(df, "D:/Arquivo.dta")
```

### Importar e exportar .csv com `data.table`
>  `if(!require(data.table)){install.packages("data.table")}`

> ver mais:  https://www.rdocumentation.org/packages/data.table/versions/1.14.2/topics/fread
```
# Importar csv com fread data.table
df <- read.table("arquivo.csv", 
                  header=TRUE, 
                  sep=",", 
                  quote="", 
                  stringsAsFactors=FALSE, 
                  comment.char="", 
                  nrows=n)

# Exportar arquivo .csv
write.table(df,"arquivo.csv",sep=",")
```

### Importar .csv com  `sqldf`      
>  `if(!require(sqldf)){install.packages("sqldf")}`                 
```
SQL_df <- read.csv.sql("D:/arquivo.csv",dbname=NULL))
```

### Importar vários arquivos .csv e fazer append (Método 1)
> É necessário que todas as colunas das tabelas tenham o mesmo nome e tipo
```
list_data <- list.files(path = "D:/pasta_arquivos", pattern = ".csv", full.names = TRUE)

read_data = function(list_data){
  read.csv2(list_data, encoding = "UTF-8", stringsAsFactors=FALSE)
}
myfiles = lapply(X = list_data, FUN = read_data)

# Fazer append
data_demand = data.table::rbindlist(myfiles)
```

### Importar varios arquivos .csv fazer append (Método 2)
> É necessário que todas as colunas das tabelas tenham o mesmo nome e tipo
```
file_names <- ldply(list.files(path = "D:/pasta_arquivos", pattern = "*.csv", full.names = T), read.csv, header=TRUE, sep = ";", skip = 0, dec = ",", fill = TRUE)
```

### Importar varios arquivos .csv fazer append e gerar uma coluna com nome dos arquivos
> É necessário que todas as colunas das tabelas tenham o mesmo nome e tipo
```
# Ler e carregar arquivos
file_names <- list.files(path = "D:/pasta_arquivos", pattern = "*.csv", full.names = T)
file_list <- lapply(file_names, function(x){
                    ret <- read_csv2(x, skip = 0,locale = default_locale(),trim_ws = TRUE, col_select = NULL,)
                    ret$origin <- x
                    return(ret)})
  
# Fazer append                  
df <- rbindlist(file_list)
```


### Importar varios arquivos .csv e usar o endereço e nome do arquivo como nome da tabela 
> É necessário que todas as colunas das tabelas tenham o mesmo nome e tipo
```
files<- list.files(path = "Arquivos", pattern="*.csv", full.names=T)
for (i in files){
    iname=sub("*.csv","",i)
    f=read.csv(i, header=TRUE, sep = ";", skip = 0, dec = ",", fill = TRUE)
    rownames(f)=paste(rownames(f),iname,sep = "_")
    assign(paste0(iname),f)
}
```

### Apagar arquivos do computador diretamente do R.
```
# Remover arquivos independente do tipo de extenção
file.remove("D:/arquivo.R")
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

## Tarefas Prontas

### Ao iniciar um novo script utilizar os seguintes comandos
```
# Limpar tudo
rm(list=ls())
gc()

# Instalar e carregar packages
if(!require(pacman)){install.packages("pacman")}
p_load(data.table, tidyverse, tidyr)  

# Impedir notação cientifica 
options(scipen=999)

# Setar diretório de trabalho
setwd("D:/")
```

### Loop para importar arquivos .xlsx de varios anos, tratar as colunas e gerar dataframes separados
```
anos <- c(2018, 2019, 2020)

for (ano in anos) {
  # Carregar dados
  df <- read_excel(paste0("Tabela", ano, ".xlsx"))
  
  # Manipulações das colunas Ex:
  df$Col_concat <- paste(df$Coluna_1, df$Coluna_2, sep = "_")
  
  # Remover colunas
  df <- subset(df, select = -c(Coluna_3, Coluna_4))
  
  # Gerar coluna Ano
  df$Ano = ano
  
  # Salvar dataframe para cada ano
  assign(paste0("df_", ano), df)
}
```

### Gerar coluna `first_treat` para os estimadores de diferença-em-diferenças
```
# Gerar dataframe de exemplo
id = c(rep(1,9),rep(2,9),rep(3,9),rep(4,9)) 
Ano = rep(2000:2008, 4) 
D_treat <- c(0,0,0,0,1,1,1,1,1,0,0,1,1,0,0,1,1,0,1,1,1,1,1,1,1,1,1,0,0,0,0,0,0,0,0,0)
df = data.frame(id, Ano, D_treat)

# Gerar coluna coluna `first_treat` com pacote `data.table`
df = data.table(df)
df[, first_treat := ifelse(max(D_treat) == 1, Ano[which.max(D_treat == 1)], 0), by = id]

# # Gerar coluna coluna `first_treat` com pacote `dplyr`
df<- df %>%
  group_by(id) %>%
  mutate(first_treat = ifelse(max(D_treat) == 1, Ano[which(D_treat == 1)[1]], 0))
```

### Gerar coluna identificadora  `id` a partir de uma ou mais colunas
```
df <- df %>% dplyr::group_by(Coluna_1,Coluna_2) %>% 
             dplyr::mutate(id = cur_group_id())
```
  
### Gerar código IBGE dos municípios, com 6 dígitos *`id6`* a partir da coluna código com 7 dígitos *`id7`*
```
df$id6<- substr(df$id7, 1, (nchar(df$id7)-1))
```

### Gerar código IBGE das UF  a partir do código do municípios
```
# Se o código ibge do municípios for de 7 dígitos 
df$Cod_UF <- substr(df$id7, 1, (nchar(df$id7)-5))

Se o código ibge do municípios for de 6 dígitos 
df$Cod_UF <- substr(df$id7, 1, (nchar(df$id7)-4))
```

### Trabalhar com CPF    
> Nota:  os CPF tem zeros nos primeiros caracteres (zeros a esquerda), se importarmos os dados  como numéricos os zeros serão removidos, portanto uma boa pratica é trabalhar com eles em string
>  O CPF contém 11 números
```
# Importar arquivo .csv contendo uma coluna com CPF
df <- read.csv("D:/arquivo.csv", colClasses=c(CPF="character"),)

# Caso a coluna CPF tenha sido convertida para numérica é possível adicionar os zeros a esquerda e converter para string
df$CPF <- str_pad(df$CPF, width = 11, pad = "0", side = "left")

# Remover ponto e traço da coluna CPF  
df$CPF <- gsub("\\W","",df$CPF)
```

### Padronização de  escala das colunas do df
> Padronização é um processo estatístico que transforma uma coluna de dados para que ela tenha média 0 e desvio padrão 1. Isso é frequentemente feito em problemas de aprendizado de máquina para que as diferentes características tenham a mesma escala e, portanto, a mesma importância.
```
# Padronizar e gerar novo dataframe
df_pad = scale(df[,1:4]) 

# Padronizar algumas colunas sem gerar novo dataframe
df[,1:4] = scale(df[,1:4]) 
```

### Normalização de  escala entre  0 e 1  com `scales`
> Normalização é um processo estatístico que transforma uma coluna de dados para que os valores estejam dentro de um determinado intervalo, geralmente entre 0 e 1. Isso é frequentemente feito em problemas de aprendizado de máquina para que as diferentes características tenham a mesma escala e, portanto, a mesma importância. A normalização é diferente da padronização, na qual os dados são transformados para terem média 0 e desvio padrão 1.
> -   Min-Max normalization: A normalização Min-Max transforma os dados para que estejam entre 0 e 1, usando a fórmula: `(valor - valor_min) / (valor_max - valor_min)`

> `if(!require(scales)){install.packages("scales")}` 
```
# Normalizar uma coluna
df$Coluna_norm <- rescale(df$Coluna) 

# Normalizar varias colunas
df <- df %>% dplyr::mutate_at(c(1:10), funs(c(scale(.))))
```

### Gerar faixa etárias a partir da coluna idade 
> O código está criando uma nova coluna chamada "faixa_etaria" no data frame "df". A função `cut()` é usada para separar as idades em faixas etárias, com base em um determinado conjunto de "breaks". O argumento `breaks = seq(0, 100, by = 5)` gera uma sequência de números a partir de 0 até 100, com um intervalo de 5 anos.

> O argumento `right = FALSE` indica que as faixas etárias devem ser definidas a partir do limite esquerdo (0, por exemplo) e não incluir o limite direito (4, por exemplo).

> O argumento `labels` é usado para fornecer os rótulos para cada faixa etária. A função `paste0()` é usada para juntar as faixas etárias, usando o símbolo "-" como separador. O resultado é uma coluna "faixa_etaria" no data frame "df", com faixas etárias de 0 a 95 anos, em intervalos de 5 anos.
```
# Criar  coluna de faixa etária com 5 anos de intervalo (sem sobreposição)
df$faixa_etaria <- cut(df$idade, breaks = seq(0, 100, by = 5), right = FALSE, labels = paste0(seq(0, 95, by = 5), "-", seq(4, 100, by = 5)))

# Criar  coluna de faixa etária com 10 anos de intervalo (sem sobreposição)
df$faixa_etaria <- cut(df$idade, breaks = seq(0, 100, by = 10), right = FALSE, labels = paste0(seq(0, 90, by = 10), "-", seq(9, 99, by = 10)))
```

### Gerar faixa de renda a partir da coluna renda
> A função `cut` é usada para agrupar valores em intervalos ou "bins". O argumento `df$renda` especifica qual coluna será usada para agrupar os dados.
> O argumento `breaks` especifica os limites entre os intervalos, que são criados com a função `seq`, com os limites mínimo e máximo da coluna de renda e com um passo de 500. Isso significa que serão criados intervalos com tamanho 500.
> O argumento `right` é usado para especificar se o limite superior do intervalo está incluído ou não. Com o valor `FALSE`, o limite superior não está incluído, ou seja, o valor máximo do intervalo é o valor anterior ao limite superior.
> O argumento `labels` é usado para especificar rótulos para cada intervalo. É criado com a função `paste0` que concatena strings. O primeiro elemento é o começo do intervalo e o segundo é o final.
> A coluna `faixa_salarial` é criada armazenando o resultado da função `cut` no data frame.
```
# Arredondar os valores na coluna renda para o número mais próximo de 500
renda_redondos <- round(renda / 500) * 500

# Juntar a coluna em um data frame
df <- data.frame(renda = renda_redondos)

# Gerar coluna de faixas salariais com intervalos de 500
breaks <- seq(min(df$renda), max(df$renda), by = 500)
labels <- paste0(breaks[-1], "-", tail(breaks, -1) + 500)
df$faixa_salarial <- cut(df$renda, breaks = breaks, right = FALSE, labels = labels)
```

### Deflacionar colunas com  `deflateBR`

> O  `deflateBR`  automatiza três processos para deflacionar uma série. Primeiro, ele extrai dados de um dos seguintes índices de preços da API do IPEA: IPCA e INPC, desenvolvidos pelo IBGE; e IGP-M, IGP-DI e IPC, desenvolvidos pela FGV. Segundo, ele compatibiliza as datas mensais desses índices com as datas dos valores nominais da série. Feito isso, enfim, ele deflaciona e retorna os valores corrigidos.
> 
> A função principal do pacote,  `deflate`, requer apenas três argumentos: um vetor numérico de valores nominais; um vetor com as datas nominais; e uma data de referência no formato MM/AAAA. Um exemplo usando o IPCA:
                                
> Ver mais: [Deflacionando séries com o deflateBR | Fernando Meireles (fmeireles.com)](https://fmeireles.com/blog/rstats/deflacionar-series-no-r-deflatebr/)

> `if(!require(deflateBR)){install.packages("deflateBR")}` 
> `if(!require(lubridate)){install.packages("lubridate")}` 
```
# Gerar coluna com a data de 31 de dezembro a partir da coluna Ano
df <- df %>% mutate(Data = as.Date(as.yearmon(paste0(Ano,"-12"), "%Y-%m")) + days(31))

# Converter converter a coluna data para o formato date com `lubridate`
df$Data <- as.Date(df$Data)

# Selecionar colunas que serão deflacionadas
Cols_Deflate <- c("var_1", "var_2", "var_3", "var_4")

# Deflacionar coluna utilizando o IPCA para o ano 2018
if(!require(deflateBR)){install.packages("deflateBR")}

# Deflacionar coluna utilizando o IPCA para o ano 2018
df$Valores_deflacionados <- ipca(df$Valores_nominais, df$Data, "12/2018")

# Deflacionar mais de uma coluna utilizando o IPCA para o ano 2018
for(i in 1:length(Cols_Deflate)) {
  df[ , i] <- ipca(df[ , i], df$Data, "12/2018")
}

# Comparar as colunas 
summary(df$Valores_nominais)
summary(df$Valores_deflacionados)
```

### Gerar coluna estações do ano a partir de uma coluna do tipo date
```
# Gerar df de exemplo
df <- data.frame(id = 1:100, 
                 date = seq(as.Date("2000-01-01"), 
                 by = "days", 
                 length.out = 100))

# Gerar função para criar as estações do ano a partir da coluna data
determine_season <- function(date) {
  month <- as.numeric(format(date, "%m"))
  if (month %in% c(12, 1, 2)) {
    return("Inverno")
  } else if (month %in% c(3, 4, 5)) {
    return("Primavera")
  } else if (month %in% c(6, 7, 8)) {
    return("Verão")
  } else if (month %in% c(9, 10, 11)) {
    return("outono")
  }
}

# Gerar coluna estações
df$Estacoes <- sapply(df$date, determine_season)
```

### Imputar missings com `mixgb` (Método 1)

> ver mais: https://github.com/agnesdeng/mixgb

> Por padrão, escolherá aleatoriamente uma variável incompleta como a resposta e construirá um modelo XGBoost  com outras variáveis usando os casos completos do conjunto de dados. Portanto, cada corrida é provável que  retorne resultados diferentes. Os usuários também podem especificar a resposta e covariáveis no argumento e,  respectivamente.mixgb_cv()mixgb_cv()responseselect_features
> 
> * Parâmetros do XGBoost https://xgboost.readthedocs.io/en/stable/parameter.html
> 
> Recomendações:
> 1. Os dados devem ser um quadro de dados.
> 2. O ID deve ser removido
> 3. Os valores perdidos devem ser codificados como NA não NaN
> 4. Inf ou -Inf não são permitidos
> 5. Células vazias devem ser codificadas como ou valores NA
> 6. Variáveis do tipo "string" devem ser convertidas em "fator" 
> 7. Variáveis do tipo "fator" devem ter pelo menos dois níveis
```
# Carregar pacotes
if(!require(pacman)){install.packages("pacman")}
p_load(tidyverse, data.table, funModeling, mixgb) 

# Semente
set.seed(2022)

# Converter as colunas 1 a 10 para numérico
df_original <- df_original %>% dplyr::mutate_at(c(1:10), as.numeric) 

# Visualizar resumo de missings zeros e linhas vazias
resumo <- df_status(df_original)
resumo$vazias <- apply(df_original, 2, function(x) length(which(x == '')))
resumo$OBS_Total <- nrow(df_original)
resumo$perc_vazias = resumo$vazias / resumo$OBS_Total

# Clonar df
df <- df_original

# Selecionar as colunas com missings que serão imputadas
col_missing <- c("Coluna_1", "Coluna_2", "Coluna_3")

# obter o nome das colunas que contém missings
col_missing <- names(which(colSums(is.na(df))>0)) 

# Parâmetros do XGboost
params <- list(max_depth = 2, gamma = 0.1, eta = 0.3, min_child_weight = 1, 
               subsample = 1, colsample_bytree = 1, colsample_bylevel = 1, 
               colsample_bynode = 1, nthread = 25, tree_method = "auto",
               gpu_id = 1, predictor = "auto")

imputed.data <- mixgb(data = cov[col_missing], m = 5, maxit = 1, ordinalAsInteger = TRUE,
                      bootstrap = TRUE, pmm.type = "auto", pmm.k = 5, pmm.link = "prob",
                      initial.num = "normal", initial.int = "mode", initial.fac = "mode",
                      save.models = FALSE, save.vars = NULL, xgb.params = params, 
                      nrounds = 150, print_every_n = 10L, early_stopping_rounds = 20, 
                      verbose = 0)

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

# Utilizar a média dos 5 modelos gerados
Mean_df_inputed <- rbindlist(list(imputed_data_1, imputed_data_2, imputed_data_3, imputed_data_4, imputed_data_5))[,lapply(.SD,mean), by= c("df$Ano")]
Mean_df_inputed <- rename(Mean_df_inputed, c("Ano" = "df$Ano"))

# Remover as colunas do df_original que foram imputadas 
df_original <- subset(df_original, select = -c(Coluna_1, Coluna_2, Coluna_3))

# Unir df com as colunas imputadas
df2 <- left_join(df_original, Mean_df_inputed, by = c("Ano"))

# Remover dfs desnecessários
rm(`imputed.data`, imputed_data_1, imputed_data_2, imputed_data_3, imputed_data_4, imputed_data_5, Mean_df_inputed, col_missing)
```

### Imputar missings com `xgboost` (Método 2)
> ver mais: https://github.com/agnesdeng/mixgb

> Por padrão, escolherá aleatoriamente uma variável incompleta como a resposta e construirá um modelo XGBoost  com outras variáveis usando os casos completos do conjunto de dados. Portanto, cada corrida é provável que  retorne resultados diferentes. Os usuários também podem especificar a resposta e covariáveis no argumento e,  respectivamente.mixgb_cv()mixgb_cv()responseselect_features
> 
> * Parâmetros do XGBoost https://xgboost.readthedocs.io/en/stable/parameter.html
```
# Carregar pacotes
if(!require(pacman)){install.packages("pacman")}
p_load(tidyverse, data.table, funModeling, xgboost) 

# Gerar dataframe de exemplo
df <- data.frame(id = 1:100, 
                 Coluna_1 = rnorm(100), 
                 Coluna_2 = rnorm(100), 
                 Coluna_3 = rnorm(100))
df[c(5, 25, 50, 75), 2] <- NA
df[c(10, 30, 40, 60), 3] <- NA

# selecionar dados sem missing da coluna 2 para treinar o modelo
train <- df %>% filter(!is.na(Coluna_2))

# definir matriz de treinamento e valor alvo
dtrain <- xgb.DMatrix(data = as.matrix(train[, c("id", "Coluna_1", "Coluna_3")]), label = train$Coluna_2)

# treinar o modelo
bst <- xgboost(data = dtrain, nrounds = 100, objective = "reg:linear")

# prever valores missing na coluna var2
preds <- predict(bst, newdata = as.matrix(df %>% filter(is.na(Coluna_2)) %>% select(id, Coluna_1, Coluna_3)))

# imputar valores missing com previsões
df$Coluna_2[is.na(df$Coluna_2)] <- preds

# Calcular o MSE
mse <- mean((preds - df$Coluna_2)^2)

# Verificar ajuste do modelo com MSE (Mean Squared Error) como MAE (Mean Absolute Error), RMSE (Root Mean Squared Error) e R-Squared [o correto é utilizar df de teste]
MSE <- mean((preds - df$Coluna_2)^2) # 
MAE <- mean(abs(preds - df$Coluna_2))
RMSE <- sqrt(mean((preds - df$Coluna_2)^2))
R_Squared <- 1 - sum((preds - df$Coluna_2)^2) / sum((mean(df$Coluna_2) - df$Coluna_2)^2)
results <- data.frame(MSE, MAE, RMSE, R_Squared)
print(results)
```

### Imputar missings com `mice`
> O pacote `mice` oferece diversos métodos para imputação de valores missing, incluindo:

> -   "**pmm**" (regressão linear por mínimos quadrados ponderados): utiliza uma regressão linear para imputar valores missing baseado nas outras variáveis do data frame.
> -   "**norm**" (imputação por média ou mediana): imputa valores missing utilizando a média ou a mediana da variável, dependendo da sua distribuição.
> -   "**knn**" (imputação por vizinhos mais próximos): utiliza a informação de observações próximas para imputar valores missing.
> -   "**rf**" (randomForest): utiliza a técnica de floresta aleatória para imputar valores missing.
> -   "**mean**" (imputação por média): imputa valores missing utilizando a média da variável.
> -   "**polr**" (regressão logística ordinal): imputa valores missing para variáveis categóricas ordinais utilizando uma regressão logística ordinal.
> -   "**cart**" (classificação e regressão de árvore): imputa valores missing utilizando uma árvore de classificação ou regressão.
    
> Estes são apenas alguns dos métodos disponíveis no pacote `mice`, e a escolha do método ideal depende do contexto específico de sua análise. É importante avaliar o impacto da imputação nos resultados e experimentar diferentes métodos para identificar o melhor desempenho.
```
# Carregar pacotes
if(!require(pacman)){install.packages("pacman")}
p_load(tidyverse, data.table, funModeling, mice) 

# Imputar missings com (MQO ponderados)
df_imputed <- mice(df, method = "pmm", seed = 123)
df_complete <- complete(df_imputed)

# Imputar missings com (randomForest)
df_imputed <- mice(df, method = "rf", seed = 123)
df_complete <- complete(df_imputed)
```

###  Bibliometria com `bibliometrix`
>O pacote bibliometrix  fornece um conjunto de ferramentas para pesquisa quantitativa em bibliometria e cienciometria.
>
>A bibliometria se torna a principal ferramenta da ciência, a análise quantitativa, sobre si mesmo. Essencialmente, a bibliometria é a aplicação de quantitativos análise e estatística para publicações como artigos de periódicos e suas contagens de citações que a acompanham. Avaliação quantitativa de os dados de publicação e citação são agora utilizados em quase todos os dados científicos campos para avaliar o crescimento, maturidade, autores líderes, conceitual e mapas intelectuais, tendências de uma comunidade científica.
>
> A bibliometria também é usada na avaliação de desempenho de pesquisa, especialmente em laboratórios universitários e governamentais, e também por formuladores de políticas, diretores e administradores de pesquisa, especialistas em informação e bibliotecários e os próprios estudiosos.

> ver mais:
> *  [Bibliometrix - Home](https://www.bibliometrix.org/home/)
> * [A brief introduction to bibliometrix](https://www.bibliometrix.org/vignettes/Introduction_to_bibliometrix.html)

> `if(!require(remotes)){install.packages("remotes")}`
> `install.packages("igraph", type="binary")`
> `remotes::install_github("massimoaria/bibliometrix")`
```
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

