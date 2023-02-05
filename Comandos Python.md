# Códigos Python para data science
![enter image description here](https://i0.wp.com/learn.onemonth.com/wp-content/uploads/2019/07/image3-1.png?fit=756%2C277&ssl=1)

**Autores:**              
Silvio da Rosa Paula                             
Dianifer Leal Borges          

## Operadores de Comparação:

| Operador |   Significado    |
|----------|------------------|
|     ==   | igual a          |
|     !=   | diferente de     |
|     >    | maior que        |
|     <    | menor que        |
|     >=   | maior ou igual a |
|     <=   | menor ou igual a |

## Operadores de Atribuição

Esse operadores são utilizados no momento da  **atribuição**  de valores à variáveis e controlam como a atribuição será realizada.
| Operador | Equivalente a |
| -------- | ------------- |
| =        | x = 1         |
| +=       | x = x + 1     |
| -=       | x = x - 1     |
| *=       | x = x * 1     |
| /=       | x = x / 1     |
| %=       | x = x % 1     |

##  Operadores Lógicos:
Também conhecidos como operadores booleanos, permitem trabalhar com múltiplas condições relacionais na mesma expressão, e retornam valores lógicos verdadeiro ou falso..

| Operador |   Descrição    |                  Explicação                                   |
|----------|----------------|---------------------------------------------------------------|
|    and    | AND lógico     |Versão vetorizada. Compara dois elementos do tipo vetor e retorna um vetor de TRUEs e FALSEs
|    or     | OR lógico      |Versão vetorizada. Compara dois elementos do tipo vetor e retorna um vetor de TRUEs e FALSEs
|    not     | NOT lógico     |Negação lógica. Retorna um valor lógico único ou um vetor de TRUE / FALSE.

##  Operadores  Aritméticos

| Operador |   Descrição      |
|----------|------------------|
|     +    | adição           |
|     -    | subtração	      |
|     *    | multiplicação    |
|     /    | divisão          |
|     //   | divisão inteira  |
|     **   |  exponencial     |
|    %     | módulo           |

## Atalhos

| Atalho         | Ação                                                                           
| -------------- | ----------------------- |
| ***Acessando paleta de comandos*** |      |                                                                          
| Ctrl + Shift + P   |  paleta de comandos      
| Ctrl + Shift + F   |  paleta de comandos                                                       
|                    |                      |
| Comandos em modo de navegação             |                                                                                
| Esc |  entra no modo de navegação         |
| B   |  insere uma nova célula abaixo      |
| M   |  muda o tipo de texto para markdown |
| Y   |  muda o tipo de texto para código   |
| A   |  insere uma nova célula acima       |
| C   |  copia a célula selecionada         |
| X   |  recorta a célula selecionada       |
| V   |  cola célula copiada/recortada abaixo da célula selecionada       |
| Shift + V  |  cola célula copiada/recortada acima da célula selecionada |
| J e K      |  navegação pelas células                                   |
| ↓ e ↑      |  navegação pelas células                                   |
| D + D      |  deleta célula                                             |
| Z          |  desfaz última deleção de célula                           |
| 1 a 6      |  insere cabeçalhos do markdown                             |
| Shift + ↓ ou J  |  seleciona múltiplas células para baixo               |                                      
| Shift + ↑ ou K  |  seleciona múltiplas células para cima                |                                      
| Shift + M       |  mescla múltiplas células selecionadas                |                                         
| Shift + L       |  exibe os números das linhas das células com código   |                            
| S               |  salva notebook e cria checkpoint                     |                                            
| Ctrl + S        |  salva notebook e cria checkpoint                     |                                           
| F               |  busca e substitue texto da célula                    |                                        
| O               |  esconde output da célula                             |                                            
| H               |  exibe painel com atalhos de teclado                  |                                    
| I + I           |  interrompe o kernel                                  |                                            
| 0 + 0           |  reinicia o kernel                                    |                                                  
| Space           |  rola notebook para baixo                             |                                    
| Shift + Space   |  rola notebook para cima                              |                                    
|  ***Comandos em modo de edição***   |                                   |                                             
| Enter       |  entra no modo de edição                                                       |
| Shift + Tab |  exibe documentação da função (o cursor deve estar posicionado sobre a função) |
| Ctrl + Shift + - |  divide a célula a partir da posição do cursor  |     
| Tab         |  completa código                                     |
| Ctrl + ]    |  indenta código                                      |
| Ctrl + [    |  desfaz indentação do código                         |
| Ctrl + A    |  seleciona todo o texto da célula                    |
| Ctrl + Z    |  desfaz alterações do texto da célula                |
| Ctrl + /    |  Comenta código                                      |
| Ctrl + Shift + Z  |  redo                                          |      
| Ctrl + Home       |  vai para o início da célula                   |      
| Ctrl + ↑          |  vai para o início da célula                   |      
| Ctrl + End        |  vai para o final da célula                    |      
| Ctrl + ↓          |  vai para o final da célula                    |      
| Ctrl + ←          |  anda para próxima palavra à esquerda          |      
| Ctrl + →          |  anda para próxima palavra à direita           |      
| Ctrl + Del        | deleta a palavra posterior                     |       
| Ctrl + Backspace  | deleta a palavra anterior                      |                                                                               
| ***Comandos independentes dos modos de navegação e de edição***    | |                                                                       
| Ctrl + Enter     |  executa texto da célula                        |                              
| Shift + Enter    |  executa texto da célula e passa para célula abaixo |                           
| Alt + Enter      |  executa texto da célula e insere nova célula abaixo |                          

## Instalar e Carregar Pacotes

### Instalar pacotes
```
# Com Jupyter Notebook
!pip install nome_do_pacote

# Com Anaconda
!conda install nome_do_pacote

# Instalar vários pacotes de uma vez com Jupyter Notebook
!pip install pandas, matplotlib, seaborn
```

### Instalar versão específica de um pacote
```
# Com Jupyter Notebook
!pip install nome_do_pacote==versão_desejada

# Exemplo com Jupyter Notebook
!pip install pandas==0.20.3

# Com Anaconda
!conda install nome_do_pacote=versão_desejada
```

###  Atualizar pacotes
```
# Com Jupyter Notebook
!pip install --upgrade nome_do_pacote

# Para atualizar todos os pacotes instalados no seu ambiente
!pip freeze --local | grep -v '^\-e' | cut -d = -f 1 | xargs -n1 pip install -U

# Com Anaconda
!conda update nome_do_pacote
```

###  Carregar pacotes
```
# # Com Jupyter Notebook, Exemplo: 
import pandas as pd

# Se você quiser carregar vários pacotes de uma vez
import pandas as pd, numpy as np, matplotlib.pyplot as plt
```

###  Carregar funções específicas de um pacote
```
# Para importar apenas a função "read_csv" do pacote Pandas, Exemplo:
from pandas import read_csv
```

###  Desinstalar um pacote
```
# Com Jupyter Notebook
!pip uninstall nome_do_pacote

# Com Anaconda
!conda remove nome_do_pacote
```

###  Unload packages
```
# Exemplo com 'del'
del pd

# Exemplo com o módulo `sys` para remover um pacote da sessão atual
import sys
del sys.modules['nome_do_pacote']
```

###  Verificar versão do pacote
```
# Com Jupyter Notebook
!pip show nome_do_pacote

# Ou
print(pandas.__version__)
```

###  Instalar e carregar pacotes automaticamente**
```
# O código verifica se o pacote está instalado, se não estiver, ele vai instalar usando o pip e depois carrega o pacote.

import importlib
def load_package(package):
    try:
        importlib.import_module(package)
    except ImportError:
        !pip install {package}
    finally:
        globals()[package] = importlib.import_module(package)

load_package("pandas")
load_package("numpy")
load_package("matplotlib")
```

###  Limpar todas as variáveis e objetos do ambiente atual
```
# limpar todas as variáveis e objetos do ambiente atual.
%reset -f

# para remover cada objeto individualmente
del objeto1
del objeto2
del objeto3

# Com o método `clear` da classe `globals()`
globals().clear()
```

###  Definir pasta / diretório de trabalho
```
# Exemplo:                      
import os os.chdir("C:\\Documents")

# Para verificar o diretório de trabalho atual.
import os
print(os.getcwd())
```

###  Abrir diretório de trabalho
```
# Exemplo:               
import os
import subprocess
subprocess.call(['explorer', os.getcwd()])
```

###  Acessar documentação de um pacote
```
# # Exemplo: para acessar a documentação do pacote Pandas
import pacote
help(pacote)

# ou
print(pacote.__doc__)

# acessar a documentação de uma função ou método específico dentro do pacote
help(pacote.read_csv)

# ou 
print(pacote.read_csv.__doc__)
```


## Configurações de Memória e Processador.

### Expandir memória
> Em alguns casos, é necessário selecionar uma quantidade específica de memória, Isso pode ser feito usando o módulo `psutil` e a função `virtual_memory()`. 
> - O psutil é um módulo que permite obter informações sobre o sistema, incluindo a memória disponível. 
>  - A função `virtual_memory()` retorna informações sobre a memória virtual do sistema, incluindo a memória total e a memória livre.
```
import psutil

# Obter informações sobre a memória virtual
mem = psutil.virtual_memory()

# Definir limite de memória em bytes
limit = 2 * (1024 ** 3)  # 2GB em bytes

# Verificar se a memória livre atual é maior que o limite desejado
if mem.available > limit:
    # Configurar limite de memória
    limit_bytes = limit
else:
    # Se não houver memória suficiente, usar a memória disponível
    limit_bytes = mem.available

# Imprimir limite de memória em GB
print(limit_bytes / (1024 ** 3), "GB")
```

### Limpar a memória ocupada por objetos sem removê-los completamente.
```
# Utizar o Garbage Collector (Coletor de Lixo) do Python
import gc
gc.collect()

# Utizar  a biblioteca `psutil` para liberar a memória não utilizada
import psutil
psutil.virtual_memory().free
psutil.swap_memory().free
```

###  Definir quantos threads do CPU serão utilizados
```
# Definindo um número especifico de threads 
from concurrent.futures import ThreadPoolExecutor
with ThreadPoolExecutor(max_workers=4) as executor:

# Utizar o número máximo de threads disponíveis
import os
from concurrent.futures import ThreadPoolExecutor
```

## Visualização de Dataframes

###  Visualizar todas as linhas  do dataframe
```
# Método 1: sem pandas
df

# Método 2: com pandas
import pandas as pd
print(df)
```

### Visualizar  100 linhas do df
```
# Visualizar as 100 primeiras linhas do df
df.head(100)

# Visualizar as 100 últimas linhas do df
df.tail(100)
```

### Visualizar colunas específicas de um df
```
# Método 1: usar o print
print(df[["coluna_1", "coluna_2"]])

# Método 2: pedir direto
df[["coluna_1", "coluna_2"]]

# Método 3: usar o atributo `loc` do df para selecionar as colunas usando rótulos
df.loc[:, ["coluna_1", "coluna_2"]]

# Método 4: usar o atributo `iloc` para selecionar as colunas usando índices
df.iloc[:, [0, 1]]
```

### Visualizar 100 linhas de colunas específicas de um df 
```
# Método 1:
print(df[["coluna_1", "coluna_2"]].head(100))

# Método 2:
df[["coluna_1", "coluna_2"]].head(100)

# Método 3: usar o atributo `loc`
df.loc[:99, ["coluna_1", "coluna_2"]]
```

###  Visualizar nome das colunas do df
```
# Método 1: usando o atributo `columns` do df.
print(df.columns)

# Método 2:
df.columns

# Método 3: usar o método `to_list()` do atributo `columns` para transformar os nomes das colunas em uma lista.
colunas = df.columns.to_list()
```

###  Obeter nome das colunas a partir do índice
```
# Método 1:
print(df.columns[0])

# Método 2:
df.columns[0]

# Método 3: visualizar o nome das primeiras três colunas:
df.columns[:3]
```

###  Visualizar índice atribuido a cada coluna a partir do nome
```
# Método 1:
print(df.columns.get_loc("nome"))

# Método 2:
df.columns.get_loc("nome")
```

###  Verificar se uma coluna específica existe no dataframe
```
if "nome" in df.columns:
    print("A coluna existe no dataframe.")
else:
    print("A coluna não existe no dataframe.")
```

###  Visualizar  dimensões do dataframe (colunas e linhas)
```
# Método 1:
print(df.shape)

# Método 2:
df.shape

# Método 3:
num_colunas = len(df.columns)
num_linhas = len(df.index)
```

###  Visualizar classes / tipos das colunas
```
# Método 1:
print(df.dtypes)

# Método 2:
df.dtypes

# Método 3:
df.apply(lambda x: x.dtype)
```

###  Visualizar classe / tipo de uma coluna do df 
```
# Método 1: utilizando o nome
print(df["nome_da_coluna"].dtype)

# Método 2: utilizando o nome
df["nome_da_coluna"].dtype

# Método 3: utilizando o índice
print(df.iloc[:, índice_da_coluna].dtype)

# Método 4: utilizando o índice
df.iloc[:, índice_da_coluna].dtype
```

###  Visualizar classe de um objeto
```
# Método 1:
print(type(objeto))

# Método 2:
objeto.__class__
```

###  Listar objetos na memória
```
# Método 1:
print(dir())

# Método 2:
dir()
```

## Manipular Dataframes

###  Criar DataFrame de exemplo
```
import pandas as pd
d = {'Nome': ['João', 'Maria', 'Pedro', '', 'Lucas'],
     'Idade': [25, 30, 35, 20, 0],
     'Nota': [7.5, 8.0, None, 9.0, None],
     'Status': ['Aprovado', 'Reprovado', '', 'Aprovado', 'Reprovado']}

df = pd.DataFrame(data=d)
df

```
###  Ordenar alfabeticamente as colunas do df
```
# ordenar as colunas do df alfabeticamente 
df = df.sort_index(axis=1)

# ordenar as colunas de forma decrescente
df = df.sort_index(axis=1, ascending=False)
```

###  Ordenar alfabeticamente uma lista de colunas do df pelo nome 
```
colunas_ordenadas = ['coluna_1', 'coluna_2', 'coluna_3', 'coluna_4', ...]
df = df.reindex(columns=colunas_ordenadas)
```

###  Ordenar coluna de forma crescente e decrescente
```
# 1 - Ordenar de forma crescente
df = df.sort_values(by='coluna_x')

# 2 - Ordenar de forma crescente
df = df.sort_values(by='coluna_x', kind='mergesort')

# 3 - Ordenar de forma crescente
df = df.sort_values(by=['coluna_x', 'coluna_y'])

# 1 - Ordenar de forma decrescente
df = df.sort_values(by='coluna_x', ascending=False)

# 2 - Ordenar de forma decrescente
df = df.sort_values(by='coluna_x', ascending=True)

# 3 - Ordenar de forma decrescente
df = df.sort_values(by=['coluna_x', 'coluna_y'], ascending=False)
```

###  Remover  colunas específicas
```
# Remover utilizando o nome da coluna
df = df.drop(columns='coluna_x')

# Remover utilizando o nome da coluna
df = df.drop(columns=['coluna_x', 'coluna_y'])

# Remover utilizando o índice da coluna
df = df.drop(columns=[df.columns[1]])

# Remover utilizando o índice da coluna
df = df.drop(columns=[df.columns[1], df
```

###  Remover  colunas quem contêm determinada expressão
```
# Remover todas as colunas cujos nomes contenham a expressão "x"
df = df.filter(regex='x', axis=1)

# Remover colunas cujos nomes contenham mais de uma expressão
df = df.filter(regex='x', axis=1).filter(regex='y', axis=1)

# Selecionar as colunas cujos nomes contenham a expressão "x"
df = df.drop(df.filter(regex='x').columns, axis=1)
```

###  Remover ids que repetem apenas uma vez 
> Suponha que você tenha uma coluna chamada "id" em um dataframe chamado "df" e queira remover todos os ids que aparecem apenas uma vez. 
```
# 1º contar a frequência de cada id
id_counts = df['id'].value_counts()

# 2º selecionar apenas os ids que aparecem mais de uma vez
id_counts = id_counts[id_counts > 1]

# 3º Remover os ids que aparecem apenas uma vez:
df = df[df['id'].isin(id_counts.index)].drop_duplicates()
```

###  Remover linhas duplicadas de um df baseado em várias colunas
```
# Remover linhas duplicadas baseado em duas colunas
df = df.drop_duplicates(subset=['coluna_x', 'coluna_y'])

# Remover linhas duplicadas baseado em todas colunas
df = df.drop_duplicates()
```

###  Escolher quais linhas duplicadas de um df desejo manter
> Para escolher quais linhas duplicadas manter. 
> - Manter a primeira ocorrência dos valores duplicados e remover as demais com 'first'
> - Manter a última ocorrência dos  valores duplicados e remover as demais com 'last'
```
# Manter a primeira ocorrência dos valores duplicados
df = df.drop_duplicates(subset=['coluna_x', 'coluna_y'], keep='first')

# Manter a última ocorrência dos valores duplicados
df = df.drop_duplicates(subset=['coluna_x', 'coluna_y'], keep='last')
```

###  Gerar amostra do dataframe
```
# Gerar amostra apenas com as colunas coluna_x coluna_y
df_sample = df[['coluna_x', 'coluna_y']]

# Gerar amostra aleatória de tamanho 10 com as colunas coluna_x coluna_y
df_sample = df[['coluna_x', 'coluna_y']].sample(n=10)
 
# Gerar amostra sem as colunas coluna_x coluna_y
df_sample = df.drop(columns=['coluna_x', 'coluna_y']).

# Gerar amostra aleatória de tamanho 10 sem as colunas coluna_x coluna_y
df_sample = df.drop(columns=['coluna_x', 'coluna_y']).sample(n=10)
```

###  Gerar amostra do dataframe baseado em condições
```
# Gerar amostra onde todas as linhas da coluna "coluna_x" é igual a "inf"
df_sample = df.loc[df['coluna_x'] == 'inf']

# Gerar amostra onde todas as linhas da coluna "coluna_y" é maior ou igual a 2009.
df_sample = df.loc[df['coluna_y'] >= 2009]

# Gerar amostra onde todas as linhas das colunas "coluna_x" é igual a "inf" e "coluna_y" é maior ou igual a 2009.
df_sample = df.loc[(df['coluna_x'] == 'inf') & (df['coluna_y'] >= 2009)]

# Gerar amostra onde todas as linhas da coluna "coluna_x" é igual a "inf" ou "coluna_y" é maior ou igual a 2009
df_sample = df.loc[(df['coluna_x'] == 'inf') | (df['coluna_y'] >= 2009)]
```

###  Gerar amostra se a coluna contém uma determinada expressão string
```
df_sample = df.loc[df['coluna_x'].str.contains("string_desejada")]
```

###  Gerar amostra com linhas onde a coluna_x não contém uma determinada string
```
df_sample = df.loc[~df['coluna_x'].str.contains("string_desejada")]
```
		     
###  Gerar amostra com período delimitado
```
# Gerar uma amostra com período entre 2009 e 2017
df_sample = df.loc[(df['Ano'] >= 2009) & (df['Ano'] <= 2017)]

# Gerar uma amostra até o Ano de 2017 
df_sample = df.loc[df['Ano'] <= 2017]

# Gerar uma amostra com o período igual e após 2009
df_sample = df.loc[df['Ano'] >= 2009]
```

###  Gerar amostra com 1000 linhas do df
```
# Primeiras linhas
df_sample = df.head(1000)

# Últimas linhas
df_sample = df.tail(1000)
```

###  Reshape de long para wide (Painel de dados)
> suponha que você tenha um dataframe chamado "df" com as colunas "id", "ano" e "valor" e queira reshapear o dataframe de formato "long" (com uma coluna para cada ano) para formato "wide" (com uma coluna para cada id e uma coluna para cada ano).
```
# Método 1: 
df_wide = df.pivot_table(index='id', columns='Ano', values='Valor')

# Método 2: 
df_long = df.melt(id_vars=["id"], 
        var_name="Ano", 
        value_name="Valor")
df_wide = df_long.pivot(index='id', columns='Ano', values='Valor')
```

###  Reshape de wide (Painel de dados) para long
> suponha que você tenha um dataframe chamado "df" com as colunas "id", "ano1", "ano2", "ano3" e queira reshapear o dataframe de formato "wide" (com uma coluna para cada ano) para formato "long" (com uma coluna para cada id e uma coluna para o ano e o valor associado)
```
# Método 1: 
df_long = df.melt(id_vars=["id"], 
        var_name="ano", 
        value_name="valor")
```

###  Clonar uma coluna do df
```
# Método 1: 
df["coluna_x_clonada"] = df["coluna_x"]

# Método 2: 
df = df.assign(coluna_x_clonada = df.coluna_x)
```

###  Deixar somente os objetos selecionados 
> suponha que você tenha os objetos "obj1", "obj2", "obj3" e "obj4" armazenados na memória
```
# listar todos os objetos em memória
all_obj = globals()

# Método 1: Excluir "obj2" e "obj4" e manter "obj1" e "obj3".
del obj2, obj4

# Método 2: listar todos os objetos em memória e, selecionar os objetos desejados e usar o `del` para excluir os demais.
all_obj = globals()
obj_list = ["obj1", "obj3"]
for obj in all_obj:
    if obj not in obj_list:
        del obj
```

###  Clonar um  objeto
```
# Método 1: clonar df para uma nova variável chamada "df_clonado"
df_clonado = df.copy()

# Método 2: usar a função `pd.DataFrame()` para clonar
df_clonado = pd.DataFrame(df)
```

###  Renomear colunas de um dataframe
```
# Método 1: Renomear uma coluna
df = df.rename(columns={"coluna_x":"nova_coluna_x"})

# Método 2: Renomear mais de uma coluna
df = df.rename(columns={"coluna_x":"nova_coluna_x", "coluna_y":"nova_coluna_y"})

# Método 3: Renomear uma coluna
df.rename(columns={"coluna_x":"nova_coluna_x"}, inplace=True)
```

###  Renomear múltiplas colunas utilizando o índice
> Lembre-se que no python a indexação começa em 0
```
# Método 1: Renomear uma coluna
df.columns.values[0] = "nova_coluna_1"
df.columns.values[1] = "nova_coluna_2"

# Método 2: Renomear mais de uma coluna
df.columns[1:4] = ["nova_coluna_1", "nova_coluna_2", "nova_coluna_3"]
df.columns[4:7] = ["nova_coluna_4", "nova_coluna_5", "nova_coluna_6"]
```

###  Adicionar prefixo ou sufixo ao nome das colunas
```
# Adicionar prefixo "prefixo_" ao nome de todas as colunas
df = df.add_prefix("prefixo_")

# Adicionar sufixo "_sufixo" ao nome de todas as colunas
df = df.add_suffix("_sufixo")

# Adicionar prefixo "prefixo_" e sufixo "_sufixo" ao nome de uma coluna "coluna_x"
df.coluna_x = df.coluna_x.str.add("_prefixo")

# Adicionar prefixo "prefixo_" a uma lista de colunas "coluna1", "coluna2" e "coluna3".
df.rename(columns={"coluna1":"prefixo_coluna1", "coluna2":"prefixo_coluna2", "coluna3":"prefixo_coluna3"}, inplace=True)

# ou
df.coluna1 = df.coluna1.str.add("_prefixo")
df.coluna2 = df.coluna2.str.add("_prefixo")
df.coluna3 = df.coluna3.str.add("_prefixo")
```

###  Gerar nova coluna utilizando operações aritméticas
```
# gerar nova coluna numérica igual a 0
df["nova_coluna"] = 0

# Soma
df["nova_coluna"] = df["coluna_x"] + df["coluna_y"]

# Subtração
df["nova_coluna"] = df["coluna_x"] - df["coluna_y"]

# Multiplicação
df["nova_coluna"] = df["coluna_x"] * df["coluna_y"]

# Divisão
df["nova_coluna"] = df["coluna_x"] / df["coluna_y"]
```

###  Gerar nova coluna utilizando o logaritmo natural
```
# Adicionar nova coluna chamada "log_coluna_x" que contém o logaritmo natural da coluna "coluna_x"
import numpy as np
df["log_coluna_x"] = np.log(df["coluna_x"])

# Se a "coluna_x" tiver zeros ou números negativos usar o método `np.log1p()` que calcula o logaritmo natural de cada valor + 1.
df["log_coluna_x"] = np.log1p(df["coluna_x"])
```

###  Gerar novas colunas a partir de colunas existentes com o logaritmo natural e adicionar o prefixo ln_ nas novas colunas 
> Suponha que você tenha um dataframe chamado "df" e queira adicionar novas colunas com o logaritmo natural de uma lista de colunas existentes chamadas "coluna1", "coluna2", "coluna3" e adicionar o prefixo "ln_" às novas colunas geradas.
```
#  Utilizando uma lista de nomes de colunas
import numpy as np
colunas = ["coluna1", "coluna2", "coluna3"]
for coluna in colunas:
    df["ln_" + coluna] = np.log1p(df[coluna])

#  Utilizando uma lista de índices das colunas
colunas = [1,2,3]
for coluna in colunas:
    df["ln_" + df.columns[coluna]] = np.log1p(df[df.columns[coluna]])
```

###  Adicionar label (descrição) a uma coluna
> Suponha que você tenha um dataframe chamado "df" e queira adicionar uma descrição à coluna "coluna_x" chamada "Descrição da Coluna X"
```
# Adicionar uma descrição à coluna "coluna_x" chamada "Descrição da Coluna X":
df["coluna_x"].name = "Descrição da Coluna X"

# Usar a função `rename()` para renomear a coluna e adicionar a descrição.
df = df.rename(columns = {'coluna_x':'Descrição da Coluna X'})
```

###  Converter coluna do tipo numérica para string
```
# Converter a "coluna_x" de inteiro (int númerico) para string
df['coluna_x'] = df['coluna_x'].astype(str)

# Converter cada valor da coluna para string.
df['coluna_x'] = df['coluna_x'].apply(str)
```

###  Converter coluna do tipo string para numérico
```
# Converter a coluna "coluna_x" de string para inteiro (int númerico)
df['coluna_x'] = df['coluna_x'].astype(int)

# Converter a coluna "coluna_x" de string para inteiro (float númerico com decimal)
df['coluna_x'] = df['coluna_x'].astype(float)

# Converter a coluna "coluna_x" de string para númerico com pandas
df['coluna_x'] = pd.to_numeric(df['coluna_x'])
```

###  Converter coluna numérico para factor / categórico
```
# Converter a coluna "coluna_x" de inteiro para fator:
df['coluna_x'] = pd.factorize(df['coluna_x'])[0]

# Converter a coluna para categórica com a função `pd.Categorical()`
df['coluna_x'] = pd.Categorical(df['coluna_x'])
```

###  Converta strings BRL (valores com Cifrão) para númerico
> Para converter uma coluna de strings BRL (com o formato "R$ xxx.xx") para um número, você pode usar o método `pd.to_numeric()` junto com uma expressão regular para remover o símbolo "R$" e substituir a vírgula por um ponto
```
df['coluna_x'] = pd.to_numeric(df['coluna_x'].str.replace(r'[R$\,]', ''), errors='coerce')
```

###  Converter fator (categorical)
> Para converter uma coluna fator (categorical) em um dataframe do pandas para numérico, você pode usar o método `.cat.codes`:
> Esse código atribuirá um código numérico inteiro para cada valor da categoria na coluna. Por exemplo, se a coluna tem três categorias "A", "B" e "C", então "A" será codificado como 0, "B" como 1 e "C" como 2.
> Caso essa coluna contenha valores missing (NA), eles serão codificados como -1, então caso precise você pode utilizar alguma função para tratar esses valores, como o `fillna()`.
```
# Coluna com categorias strings
df['coluna_x'] = df['coluna_x'].cat.codes

# Coluna com categorias numérica
df['coluna_x'] = df['coluna_x'].astype(int) # Converter para número inteiro
df['coluna_x'] = df['coluna_x'].astype(float) # converter para número com decimal
df['coluna_x'] = df['coluna_x'].fillna(-1).astype(int) # se contém missings values
```

###  Converter uma lista de colunas para numérico
```
# Método 1: utilizando os nomes das colunas e pandas
colunas = ['coluna_1', 'coluna_2', 'coluna_3']
df[colunas] = df[colunas].apply(pd.to_numeric, errors='coerce')

# Método 2: utilizando os índices das colunas e pandas
indices = [1, 2, 3]
df.iloc[:, indices] = df.iloc[:, indices].apply(pd.to_numeric, errors='coerce')

# Método 3: Se tiver missings 
df[colunas] = df[colunas].fillna(-1).apply(pd.to_numeric)
```

###  Converter uma lista de colunas para string
```
# Método 1: utilizando os nomes das colunas e pandas
colunas = ['coluna_1', 'coluna_2', 'coluna_3']
df[colunas] = df[colunas].astype(str)

# Método 2: utilizando os índices das colunas e pandas
indices = [1, 2, 3]
df.iloc[:, indices] = df.iloc[:, indices].astype(str)
```

###  Converter todas colunas do df para numérico
```
# Método 1: sem missings
df = df.apply(pd.to_numeric, errors='coerce')

# Método 2: Se você quiser lidar com valores missing (NA)
df = df.fillna(-1).apply(pd.to_numeric)
```

###   Gerar coluna categórica com baseada em uma lista de condição
> Exemplo: suponha que temos uma coluna categórica com difentes tipos de produtos e queremos gerar uma nova coluna categóricas agregando esses produtos. A saída deste comando resulta e uma variável com 4 categorias, 0,1,2,3,4
```
import numpy as np
df['var_cat'] = np.where(df['Var_Produto'].isin(list(range(1,25))+[28,35,99]), 1,
                        np.where(df['Var_Produto'].isin([26,34]), 2,
                        np.where(df['Var_Produto'].isin([25,32,33]), 3, 0)))
```

###   Arredondando valores de colunas 
> Se você quiser arredondar para uma quantidade específica de casas decimais, você pode passar esse valor como argumento para o método `round()`. Por exemplo, se você quiser arredondar para 4 casas decimais, `round(4)`
```
# Arredondar valores de uma coluna
df['coluna_1'] = df['coluna_1'].round(2)

# Arredondar valores de uma lista de colunas
colunas = ['coluna_1', 'coluna_2', 'coluna_3']
df[colunas] = df[colunas].round(2) # duas casas decimais

# Arredonar valores de todas as colunas do df
df = df.apply(lambda x: x.round(2))

# Arredondar valores de todas as colunas exceto a 'coluna_1'
cols_to_round = df.columns[df.columns != 'coluna_1']
df[cols_to_round] = df[cols_to_round].round(2)

# Arredondar valores de todas as colunas cujo nome começa por Qtd
qtd_cols = [col for col in df.columns if col.startswith('Qtd')]
df[qtd_cols] = df[qtd_cols].round(2)

# Arredondar valores apenas das colunas numéricas
num_cols = df.select_dtypes(include=['float64', 'int64']).columns 
df[num_cols] = df[num_cols].round(2)
```

###   Agregar colunas por id e Ano ignorando os missings values
```
# agrupar por 'id' e 'ano' e calcular média, mínimo, máximo, contagem e soma dos valores ignorando valores ausentes
agg_func = {'valor': ['mean', 'min', 'max', 'count', 'sum'],
             'valor2': ['mean', 'min', 'max', 'count', 'sum']}
result = df.groupby(['id', 'ano']).agg(agg_func)

# adicionar resultado ao DataFrame original
df_agg = df.merge(result, left_on=['id', 'ano'], right_index=True)
print(df_agg)
```

###   Contar valores únicos de uma coluna agrupando por id
```
# agrupar por 'id' e contar valores únicos na coluna 'coluna' 
result = df.groupby('id')['coluna'].nunique()
print(result)
```

###   Contar linhas sem missings por id 
```
# agrupar por 'id' e contar linhas não-nulas na coluna 'coluna'
result = df.groupby('id')['coluna'].count()
print(result)
```

###  Contar o número de caracteres das linhas de uma coluna
```
# criar nova coluna com o tamanho de cada linha na coluna 'coluna'
df['tamanho_coluna'] = df['coluna'].str.len()
```

###  substituir valores 1 na coluna_1 com valores da coluna_2 quando coluna_2==1
```
df.loc[df['coluna_2']==1, 'coluna_1'] = df['coluna_2']
```

###  Replace virgula e ponto
```
# Replace virgula para ponto
df['coluna'] = df['coluna'].str.replace(',', '.')

# Replace ponto para virgula
df['coluna'] = df['coluna'].str.replace('.', ',')
```

###  Replace decimal de colunas numéricas
```
# substituir ponto decimal por vírgula na coluna 'coluna1' 
df['coluna1'] = df['coluna1'].apply(lambda x: format(x, ',') if  type(x) is  float  else x)

# substituir ponto decimal por vírgula em todas as colunas numéricas
df = df.applymap(lambda x: x if type(x) is not float else format(x, ','))

# substituir vírgula decimal por ponto em todas as colunas numéricas
df = df.applymap(lambda x: x if type(x) is not float else format(x, '.'))

# substituir vírgula decimal por ponto na coluna 'coluna1' 
df['coluna1'] = df['coluna1'].apply(lambda x: format(x, '.') if  type(x) is  float  else x)
```

###  Replace valores de uma coluna, se outra coluna contém determinada expressão.
> Suponha que a coluna Municipio contém o nome do municipio + '_' + Sigla do UF. Ex:São Paulo_SP, para gerar uma coluna UF somente com SP.
```
# substituir valores na coluna 'uf' com a sigla do estado, extraída da coluna 'municipio'
df['uf'] = df['municipio'].str.split('_').str[1]

# substituir valores na coluna 'uf' somente para os municipios com sigla 'SP'
## 1- cria uma coluna uf com valores nulos
df['uf'] = None

## 2- substituir valores na coluna 'uf' somente para os municipios com sigla 'SP'
df.loc[df['municipio'].str.contains('SP'), 'uf'] = df['municipio'].str.split('_').str[1]
```

###  Remover a primeira e última linha de uma coluna
```
df = df.iloc[1:-1]
```

###  Gerar categorias a partir de uma variável númericas  
```
# Método 1: Pré-definido

## exemplo de DataFrame
import pandas as pd
df = pd.DataFrame({'coluna1': [1, 2, 3, 4, 5],
                   'coluna2': [5.6, 6.8, 7.9, 8.1, 8.5]})

## criar categorias a partir da coluna 'coluna1'
bins = [0, 2, 4, 6]
labels = ['categoria1', 'categoria2', 'categoria3']
df['categoria'] = pd.cut(df['coluna1'], bins=bins, labels=labels)

# Método 2: Quantile

import pandas as pd
## criar categorias a partir da coluna 'coluna1' utilizando quebras estruturais
pd.qcut(df['coluna1'], q=[0, .25, .5, .75, 1], labels=['categoria1', 'categoria2', 'categoria3','categoria4'])

# Método 3: Jenkis

import pandas as pd
from data_science_tools import data_science_tools as dst
## criar categorias a partir da coluna 'coluna1' utilizando quebras estruturais (Jenkis)
df['categoria'] = dst.jenks_breaks(df['coluna1'], n_classes=4, labels=['categoria1', 'categoria2', 'categoria3','categoria4'])
```

###   Transpor linha por colunas
```
df_transposed = df.transpose()
```

###  Somar uma lista de colunas ignorando os missings
```
# Utilizando nomes
colunas = ['coluna1', 'coluna2', 'coluna3']
df['soma'] = df[colunas].sum(axis=1, skipna=True)

# Utilizando índices
colunas = [0, 1, 2]
df['soma'] = df[colunas].sum(axis=1, skipna=True)
```

##  Colunas do tipo (Date)

###   Converter coluna para date
> Nota: ymd representa a ordem em que a data deve estar, ou seja:
 y=ano, m=mês, d=dia
```
df['Data'] = pd.to_datetime(df['Data'], format='%Y%m%d')
```

###  Extrair Ano, Mês e dia  da coluna date
```
# Extrair Ano
df['ano'] = df['coluna1'].dt.year 

# Extrair Mês
df['mes'] = df['coluna1'].dt.month 

# Extrair Dia
df['dia'] = df['coluna1'].dt.day
```

## Missings Values

###  Gerar nova coluna a partir da soma de duas colunas desconsiderando os missings
```
# Método 1: utilizando o argumento `fill_value=0`
df["nova_coluna"] = df["coluna_x"].add(df["coluna_y"], fill_value=0)

# Método 2: utilizando o argumento `skipna=True`
df["nova_coluna"] = df[["coluna_x", "coluna_y"]].sum(axis=1, skipna=True)

# Método 3: utilizando o método `.fillna()` para substituir os missing values por um valor específico, como exemplo ZERO
df["nova_coluna"] = df[["coluna_x", "coluna_y"]].fillna(0).sum(axis=1)

# Método 4: utilizando o método `.dropna()` para excluir as linhas que contenham missing e depois soma os valores das duas colunas
df["nova_coluna"] = df[["coluna_x", "coluna_y"]].dropna().sum(axis=1)
```

###  Remover missings de uma coluna especifica e gerar novo dataframe
```
# Remover as linhas que contenham missing values na coluna "coluna_x"
df_sem_missing = df.dropna(subset=["coluna_x"])

# Remover as linhas que contenham missing values em mais de uma coluna
df_sem_missing = df.dropna(subset=["coluna_x", "coluna_y"])
```

###  Remover missings das colunas a partir dos índices
```
# Remover as linhas que contenham missing values das colunas 2 a 10
df_sem_missing = df.dropna(subset=df.columns[2:11])
```

###   Replace 'NA' por missings em todas as colunas
```
df = df.replace('NA', pd.np.nan)
```

###   Replace missings por valores de outras colunas
```
# substituir valores ausentes na coluna_1 com valores da coluna_2
df['coluna_1'] = df['coluna_1'].fillna(df['coluna_2'])

# Substitui valores NaN da "coluna_1" com valores da "coluna_2" caso este seja igual a 0 df['coluna_1'] = df['coluna_1'].where(df['coluna_2'] != 0, 
df['coluna_1'].replace(np.nan, df['coluna_2']))
```

###  Replaces missings 
```
import pandas as pd 
import numpy as np

# Replace NaN values da "coluna_1" como 0  
df['coluna_1'] = df['coluna_1'].replace(float('nan'), 0)

# Replace NaN values da "coluna_1" como 0 
df['coluna_1'] = df['coluna_1'].replace(np.nan, 0)

# Replace 0 da "coluna_1" como NaN 
df['coluna_1'] = df['coluna_1'].replace(0, np.nan)

# Replace 0 da "coluna_1" como NaN 
df = df.replace({'coluna_1': {0:np.nan}})

# Substiuir missings por zero de uma lista de colunas
cols = ['coluna_1','coluna_2','coluna_3']
df[cols] = df[cols].fillna(0)
```

###   Imputar missings values com zero, média, mediana, moda, min, max e interpolação
```  
import pandas as pd

# Substitui todos os valores ausentes (missings) do dataframe por 0 
df = df.fillna(0)

# Imputar a MEDIANA agrupado por id e Ano aos missings da coluna_1
df['coluna_1'] = df.groupby(['id','Ano'])['coluna_1'].apply(lambda x: x.fillna(x.median()))

# Imputar a MÉDIA agrupado por id e Ano aos missings da coluna_1
df['coluna_1'] = df.groupby(['id','Ano'])['coluna_1'].apply(lambda x: x.fillna(x.mean()))

# Imputar a MODA agrupado por id e Ano aos missings da coluna_1
df['coluna_1'] = df.groupby(['id','Ano'])['coluna_1'].apply(lambda x: x.fillna(x.mode()[0]))

# Imputar utilizando INTERPOLAÇÃO agrupado por id e Ano aos missings da coluna_1
df['coluna_1'] = df.groupby(['id','Ano'])['coluna_1'].apply(lambda x: x.interpolate())

# Imputar com valores ALEATÓRIOS agrupado por id e Ano aos missings da coluna_1, respeitando os limites inferiores e superiores.
import random
df['coluna_1'] = df.groupby(['id','Ano'])['coluna_1'].apply(lambda x: x.apply(lambda y: random.randint(0,10) if pd.isna(y) else y))
```

###  Visualizar o total de missings das colunas de um dataframe
```
missing_values = df.isna().sum()
print(missing_values)
```

###  Visualizar o total de celulas vazias de uma coluna string
```
empty_values = df['Nome'].isnull().sum()
print(empty_values )
```

###  Gerar tabela com o total de missings, zeros e vazios de todas as colunas do df
```
# Método 1: Gerar uma função
def contar_missings_zeros_vazios(df):
    # Contando o número de missings em cada coluna
    missings = df.isnull().sum()

    # Contando o número de zeros em cada coluna
    zeros = (df == 0).sum()

    # Contando o número de valores vazios (strings vazias) em cada coluna
    vazios = (df == "").sum()

    # Criando a tabela com os resultados
    resultado = pd.DataFrame({"missings": missings, "zeros": zeros, "vazios": vazios})

    return resultado

# Utilizando a função
resultado = contar_missings_zeros_vazios(df)
print(resultado)
```

###  Visualizar apenas linhas com missings de uma coluna
```
missing_mask = df['coluna_1'].isna()
missing_rows = df[missing_mask]
print(missing_rows)
```

###  Remover missings e deixar o dataframe completo sem NaN
```
df.dropna()
```

###  Removendo cédulas vazias  de um dataframe
```
df = df.dropna(axis=1, how='all')
```

###  Remover missings baseado em uma  coluna
```
df = df.dropna(subset=['coluna_1', 'coluna_2'])
```

###  Substituir de missings de uma coluna por valores de outra coluna
```
df['coluna_1'] = df['coluna_1'].fillna(df['coluna_2'])
```

###  Removendo as colunas com mais de 50% de missings 
```
thresh = len(df) * 0.5 df = df.dropna(thresh=thresh, axis=1)
```

###  Remover linhas que apresentam apenas missings com base em varias colunas
```
df = df.dropna(subset=['coluna_1', 'coluna_2'], how='all')
```


## Outliers

###  Plotar gráfico de dispersão para detectar outliers
```
# Método 1: 
import matplotlib.pyplot as plt 
import pandas as pd

plt.scatter(df['coluna_1'], df['coluna_2']) 
plt.xlabel('coluna_1') 
plt.ylabel('coluna_2') 
plt.show()

# Método 2: 
import seaborn as sns
import pandas as pd

sns.scatterplot(data = df, x = 'coluna_1', y = 'coluna_2')
```

###  Plotar boxplot para detectar outliers
```
import seaborn as sns  

# Método 1:
sns.boxplot(x=df['coluna_1'])

# Método 2: 
sns.boxplot(data=df.coluna_1)
```

###  Identificar e plotar outliers
```
```
###  Pacotes para tratar outliers
> Ver mais em: [Top 3 Python Packages for Outlier Detection | by Cornellius Yudha Wijaya | Towards Data Science](https://towardsdatascience.com/top-3-python-packages-for-outlier-detection-2dc004be9014)
```
```

## Estatísticas 

###  Estatisticas Descritivas
> Onde o argumento '.T' inverte linhas por colunas
```
# Obtendo estatísticas descritivas de todas as colunas numéricas
df.describe().T

# Estatisticas descritivas de duas colunas
df[["coluna_1","coluna_2"]].describe().T

# Estatisticas descritivas (arredondando para 3 casas decimais)
df[["coluna_1","coluna_2"]].describe().round(3)

# Gerar dataframe a partir das  descritivas
desc_df = df.describe().round(3).T

# Descritivas por grupos (Tratamento e controle)
df.groupby(D_Tratamento).describe()

# Exportar Descritivas para excel
!pip install openpyxl
desc_df = df.groupby(grupo).describe().round(3)          
desc_df.to_excel("estatisticas_descritivas.xlsx")
```

###  Matriz de correlação
```
corr_matrix = df.corr() 
print(corr_matrix)
```

###  Correlação de todas colunas em relação a uma coluna especifica              
```
corr_matrix = df.corrwith(df['coluna_1'], method='pearson')
print(corr_matrix)
```

###  Plotar matriz de correlação (heatmap)
```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Calculando a matriz de correlação
corr_matrix = df.corr()

# Plotando a matriz de correlação
sns.heatmap(corr_matrix, annot=True, cmap='coolwarm')
plt.show()
```

###  Plotar matriz de correlação par a par 
```
import pandas as pd
import seaborn as sns

# Plotando a matriz de correlação par a par
sns.pairplot(df)
plt.show()
```

###  Gerar correlograma
```
# Método 1: 

## Importar packages
import plotly.graph_objs as go
from plotly.subplots import make_subplots
import plotly.express as px

## Calculando a matriz de correlação
corr_matrix = df.corr()

## Gerando o correlograma
fig = px.imshow(corr_matrix, labels=dict(x='', y=''))
fig.show()

# Método 2:

## Importar packages 
!pip install plotly
import plotly.graph_objs as go

##  Calculando a matriz de correlação
corr_matrix = df.corr()

##  Criando o gráfico
fig = go.Figure(data=go.Heatmap(
    z=corr_matrix,
    x=corr_matrix.columns,
    y=corr_matrix.columns,
    colorscale='Viridis'))
fig.show()
```

###  Exportar matriz de correlação para excel
```
!pip install openpyxl

# Calculando a matriz de correlação 
corr_matrix = df.corr() 

# Salvando a matriz de correlação em um arquivo Excel corr_matrix.to_excel("matriz_correlacao.xlsx")
```


## Strings

### Concatenar colunas 
> suponha que temos 3 colunas que queremos unir-las (Ano, Mês e Dia)
```
df['Data'] = pd.concat([df['Ano'], df['Mes'], df['Dia']], axis=1).apply(lambda x: '/'.join(x.astype(str)), axis=1)
```

### Concatenar duas colunas strings
```
# Concatena as colunas "Coluna1" e "Coluna2" 
df['Concatenado'] = df['Coluna1'] + ' ' + df['Coluna2']
```

### Replace  (substituir) caracteres
```
# Substitui "-" por "" na coluna "Coluna1" 
df['Coluna1'] = df['Coluna1'].str.replace("-", "")

# Substitui "[" por "" na coluna "Coluna1" 
df['Coluna1'] = df['Coluna1'].str.replace("[","") 

# Substitui "," por "" na coluna "Coluna1" 
df['Coluna1'] = df['Coluna1'].str.replace(",","") 

# Substitui "." por "" na coluna "Coluna1" 
df['Coluna1'] = df['Coluna1'].str.replace(".","") 

# Substitui "(" por "" na coluna "Coluna1" 
df['Coluna1'] = df['Coluna1'].str.replace("(","") 

# Substitui ")" por "" na coluna "Coluna1" 
df['Coluna1'] = df['Coluna1'].str.replace(")","") 

# Substitui "*" por "" na coluna "Coluna1" 
df['Coluna1'] = df['Coluna1'].str.replace("*","") 

# Substitui "+" por "" na coluna "Coluna1" 
df['Coluna1'] = df['Coluna1'].str.replace("+","")

# Substitui "[", ",", ".", "(", ")", "*" e "+" por "" na coluna "Coluna1" 
df['Coluna1'] = df['Coluna1'].str.replace("[","").str.replace(",","").str.replace(".","").str.replace("(","").str.replace(")","").str.replace("*","").str.replace("+","")
```

### # Remover caracteres específicos do início e final das linhas da coluna 
```
# Remover do inicio e final
df['coluna'] = df['coluna'].str.strip('x')

# Remover apenas do início
df['coluna'] = df['coluna'].str.lstrip('x_')

# Remover apenas do final
df['coluna'] = df['coluna'].str.rstrip('_x')
```

### Remover linhas que contém  4 ou mais caracteres 
```
condition = df['coluna'].str.len() < 4
df = df[condition]
```

### Removendo caracteres não-alfanuméricos das linhas da coluna
```
df['coluna'] = df['coluna'].str.replace("[^0-9a-zA-Z]", "")
```

### # Removendo caracteres não-numéricos das linhas da coluna
```
df['coluna'] = df['coluna'].str.replace("[^0-9]", "")
```

### Remover todos caracteres numéricos das linhas da coluna
```
df['coluna'] = df['coluna'].str.replace("[0-9]", "")
```

### Remover caracteres especiais (acentuação) das linhas da coluna
```
df['coluna'] = df['coluna'].str.normalize('NFKD').str.encode('ascii', errors='ignore').str.decode('utf-8')
```

### Encodificar coluna para latin1
```
df['coluna'] = df['coluna'].str.encode('latin1')
```

### Substituair caracteres latinos por Unicode
```
df['coluna'] = df['coluna'].str.replace('á', 'a\u0301') 
df['coluna'] = df['coluna'].str.replace('é', 'e\u0301') 
df['coluna'] = df['coluna'].str.replace('í', 'i\u0301') 
df['coluna'] = df['coluna'].str.replace('ó', 'o\u0301') 
df['coluna'] = df['coluna'].str.replace('ú', 'u\u0301')
```

### Converter letras minúsculas em MAIÚSCULA
```
df['coluna'] = df['coluna'].str.upper()
```

### Converter letras MAIÚSCULA em minúsculas
```
df['coluna'] = df['coluna'].str.lower()
```

### Converter a primeira letra para  MAIÚSCULA
```
df['coluna'] = df['coluna'].str.capitalize()
```

### Remover linhas com a expressão específica
```
df = df[~df['coluna'].str.contains("ln_")]
```

### Remover espaços iniciais e finais
```
df['coluna'] = df['coluna'].str.strip()
```

###  Replace  expressões das strings (substituir "abc" por "xyz")
```
df['coluna'] = df['coluna'].str.replace("abc", "xyz")
```

### Contar quantos caracteres tem cada linha de uma coluna
```
df['num_caracteres'] = df['coluna'].str.len()
```

###  Deixar ou remover os primeiros e ultimos caracteres das linhas de uma coluna
```
# Deixar somente os 2 primeiros caracteres de uma coluna string
df['coluna'] = df['coluna'].str.slice(stop=2)

# Removeros 3 primeiros caracteres de uma coluna string
df['coluna'] = df['coluna'].str.slice(start=3)

# Deixar somente os últimos 3 dígitos de uma coluna numérica
 df['coluna'] = df['coluna'].apply(lambda x: x % 1000)
 
# Deixar somente os primeiros 3 dígitos de uma coluna numérica
df['coluna'] = df['coluna'].apply(lambda x: int(str(x)[:3]))

# Deixar os digitos da posição 2 a 5 de uma coluna numérica
df['coluna'] = df['coluna'].apply(lambda x: int(str(x)[1:5]))
```

###  Dividir coluna em várias outras utilizando a `,`                                                 
```
df[['coluna1', 'coluna2']] = df['coluna'].str.split(',', expand=True)
```

###  Comparar duas colunas strings e gerar probabilidades baseado na semelhança       
> `token_set_ratio`, `SequenceMatcher` e `token_sort_ratio` são três funções de comparação de strings que são fornecidas pelo pacote `fuzzywuzzy`. 

-   `token_set_ratio` é uma função que compara as strings baseando-se nas ocorrências de cada token (palavra). Ela retorna uma pontuação entre 0 e 100, onde 100 indica uma semelhança perfeita entre as strings. Essa função é mais indicada para comparações de strings que possuem a mesma ordem de palavras, mas com variações de espaçamento ou acentuação.
    
-   `SequenceMatcher` é uma função mais avançada, que compara as strings baseando-se nas operações de edição necessárias para transformar uma string na outra. Ela retorna uma pontuação entre 0 e 1, onde 1 indica uma semelhança perfeita entre as strings. Essa função é indicada para comparações de strings que possuem variações de ordem de palavras ou inserção/remoção de palavras.
    
-   `token_sort_ratio` é uma função que compara as strings baseando-se nas ocorrências de cada token (palavra) nas strings, mas ordenando as palavras em ambas as strings antes de compará-las. Ela retorna uma pontuação entre 0 e 100, onde 100 indica uma semelhança perfeita entre as strings. Essa função é indicada para comparações de strings que possuem variações de ordem de palavras.
    

Portanto, é importante entender as necessidades específicas da sua comparaç                               
```
!pip install fuzzywuzzy 
from fuzzywuzzy import fuzz
import pandas as pd

# Criar um exemplo de dataframe
df = pd.DataFrame({'coluna1': ['abcdef', 'ghijkl', 'mnopqr'], 'coluna2': ['abcd', 'ghijk', 'mnopq']})

# Método 1: token_set_ratio
# Adicionar uma nova coluna com as probabilidades de semelhança entre as colunas
df['prob_token_set_ratio'] = df.apply(lambda x: fuzz.token_set_ratio(x['coluna1'], x['coluna2']), axis=1)

# Método 2: SequenceMatcher
# Adicionar uma nova coluna com as probabilidades de semelhança entre as colunas 
df['prob_SequenceMatcher'] = df.apply(lambda x: fuzz.SequenceMatcher(None, x['coluna1'], x['coluna2']).ratio(), axis=1)

# Método 3: token_sort_ratio
df['prob_token_sort_ratio'] = df.apply(lambda x: fuzz.token_sort_ratio(x['coluna1'], x['coluna2']), axis=1)
```


## Join e Append


###  Append de dois dataframes
```
df3 = df1.append(df2)
```

###  Left join
```
# Left join quando os nomes das colunas chaves são iguais
df3  = pd.merge(df1, df2, on='key', how='left')

# Left join quando os nomes das colunas chaves são diferentes
df3  = pd.merge(df1, df2, left_on='key1', right_on='key2', how='left')
```

###   Right join
```
# Right join quando os nomes das colunas chaves são iguais
df3  = pd.merge(df1, df2, on='key', how='Right ')

# Right join quando os nomes das colunas chaves são diferentes
df3  = pd.merge(df1, df2, left_on='key1', right_on='key2', how='Right ')
```

###   Full join
```
# Full join quando os nomes das colunas chaves são iguais
df3  = pd.merge(df1, df2, on='key', how='outer')

# Full join quando os nomes das colunas chaves são diferentes
df3  = pd.merge(df1, df2, left_on='key1', right_on='key2', how='outer')
```

###   Inner join
```
# Inner join quando os nomes das colunas chaves são iguais
df3  = pd.merge(df1, df2, on='key', how='inner')

# Inner join quando os nomes das colunas chaves são diferentes
df3  = pd.merge(df1, df2, left_on='key1', right_on='key2', how='inner')
```

### Left join (para mais de dois dataframes)
> Por exemplo, se você tiver uma lista de DataFrames chamada `df_list` e desejar realizar um left join entre eles nas colunas `key1`, `key2`, `key3`, etc, respectivamente, você pode fazer o seguinte:
```
from functools import reduce

df3 = reduce(lambda left,right: pd.merge(left,right,on='key', how='left'), df_list)
```

### Left join (adicionar sufixo e prefixo nas colunas)
> Se você deseja adicionar um prefixo ou sufixo nas colunas de um DataFrame resultante de um left join, você pode usar os parâmetros `suffixes` no método `merge()`. Esses parâmetros especificam os sufixos a serem adicionados às colunas dos DataFrames secundários (à direita da junção) para evitar conflitos de nomes de colunas.
> - Por exemplo, se você tiver dois DataFrames chamados `df1` e `df2` e desejar realizar um left join entre eles nas colunas `key1` e `key2`, respectivamente, e adicionar um prefixo "_left" e um sufixo "_right" nas colunas do DataFrame secundário (df2), você pode fazer o seguinte:
```
```

###  Left join (Sem linhas adicionais no df original)
```
df3 = pd.merge(df1, df2, left_on='key1', right_on='key2', how='left', suffixes=('_left', '_right'))
```

## Dummy (One Hot Encode)

###   Para gerar um dummy a partir de uma coluna de string que contém a expressão "abc"
```
df['dummy_col'] = df['string_col'].str.contains('abc').map({True:1,False:0})
```

###   Gerar dummy a partir de varias expressões contida em uma string
> Para gerar um dummy (variável binária) a partir de uma coluna de string que contém várias expressões, como "pecuaria", "gado" e "vaca", você pode usar o método `str.contains()` do Pandas para verificar se cada expressão está presente na coluna, e então usar o método `any()` para verificar se pelo menos uma das expressões está presente.
```
expressions = ["pecuaria","gado","vaca"]
df['dummy_col'] = df['string_col'].str.contains('|'.join(expressions), case=False)
df['dummy_col'] = df['dummy_col'].map({True:1,False:0})
```

###   Gerar dummy a partir de diversas condições
> Para gerar um dummy (variável binária) a partir de várias condições em uma coluna, como "coluna_1 contém (1,10,28) ou coluna_2 contém (2,5,23:26)", você pode usar o método `str.contains()` do Pandas para verificar se cada condição está presente nas colunas, e então usar operações lógicas (`|` para ou, `&` para e) para combinar as condições.
```
df['dummy_col'] = (df['coluna_1'].str.contains('|'.join(['1','10','28'])) | df['coluna_2'].str.contains('|'.join(['2','5','23:26'])))
df['dummy_col'] = df['dummy_col'].map({True:1,False:0})
```

###   Gerar dummy a partir de uma coluna categorica
> Para gerar dummies a partir de uma coluna categórica em Python, você pode usar a função `pd.get_dummies()` do Pandas. Essa função cria novas colunas para cada valor único da coluna categórica, e preenche essas novas colunas com 1 ou 0 de acordo com se o valor da coluna original corresponde ou não ao valor da nova coluna.
```
df_dummies = pd.get_dummies(df, columns=['categorical_col'])
```

###   Gerar dummies a partir de varias colunas
> Exemplo: criar novas colunas para cada valor único das colunas `sexo` e `faixa_etaria`
```
df_dummies = pd.get_dummies(df, columns=['sexo', 'faixa_etaria'])
```

###   Codificar variáveis categóricas
> Existem várias maneiras de codificar variáveis categóricas em Python, dependendo do seu objetivo e do seu conjunto de dados. Algumas das maneiras mais comuns incluem:

> - Método 1:  `LabelEncoder`: Esse método é uma das formas mais simples de codificar variáveis categóricas. Ele atribui um inteiro para cada valor único na coluna. Por exemplo, se você tiver uma coluna `sexo` com valores "masculino" e "feminino", o `LabelEncoder` atribuirá o valor 0 para "masculino" e o valor 1 para "feminino".

> - Método 2: `OneHotEncoder`: Esse método cria uma nova coluna para cada valor único na coluna categórica e preenche com 1 ou 0 de acordo com se o valor original corresponde ou não ao valor da nova coluna. Ele é útil quando você tem muitos valores únicos e não quer atribuir valores arbitrários.
```
# Método 1: LabelEncoder

from sklearn.preprocessing import LabelEncoder

# Inicialize o encoder
le = LabelEncoder()

# Aplique o encoder à coluna desejada
df['sexo_codificado'] = le.fit_transform(df['sexo'])

# Método 2: OneHotEncoder

from sklearn.preprocessing import OneHotEncoder

# Inicialize o encoder
enc = OneHotEncoder()

# Aplique o encoder à coluna desejada, e armazene o resultado em um novo dataframe
df_encoded = enc.fit_transform(df[['sexo']])

# Converta o resultado em um dataframe
df_encoded
```

###   Outras aplicações com dummy
> Suponha que temos um df com a coluna frutas ("apple", "banana", "pear", "pinapple")
```
# Gerar dummy de se a linha conter "a" em qualquer lugar posição
df['frutas_contem_a'] = df['frutas'].str.contains('a', case=False)
df_dummies = pd.get_dummies(df, columns=['frutas_contem_a'])

# Gerar dummy de se a linha conter "a" no início
df['frutas_inicia_a'] = df['frutas'].str.startswith('a', na=False)
df_dummies = pd.get_dummies(df, columns=['frutas_inicia_a'])

# Gerar dummy de se a linha conter "a" no final 
df['frutas_termina_a'] = df['frutas'].str.endswith('a', na=False)
df_dummies = pd.get_dummies(df, columns=['frutas_termina_a'])

# Gerar dummy de se a linha conter as letras "aeiou" em qualquer posição independete da ordem
import re
df['frutas_contem_vogais'] = df['frutas'].apply(lambda x: bool(re.search(r'[aeiou]', x, re.IGNORECASE)))
df_dummies = pd.get_dummies(df, columns=['frutas_contem_vogais'])

```

## Tarefas Prontas


###  Gerar coluna first_treat para o estimador diferença-em-diferenças de Callaway e Sant'anna
> A coluna de interesse, first_treat indica o primeiro ano onde a unidade recebeu pela primeira vez o tratamento.
```
# Gerar um dataframe de exemplo
id <- c(1,1,1,1,1,1,1,1,1,2,2,2,2,2,2,2,2,2,3,3,3,3,3,3,3,3,3,4,4,4,4,4,4,4,4,4)
Ano <- c(2000,2001,2002,2003,2004,2005,2006,2007,2008,2000,2001,2002,2003,2004,2005,2006,2007,2008,2000,2001,2002,2003,2004,2005,2006,2007,2008,2000,2001,2002,2003,2004,2005,2006,2007,2008)
D_treat <- c(0,0,0,0,1,1,1,1,1,0,0,1,1,0,0,1,1,0,1,1,1,1,1,1,1,1,1,0,0,0,0,0,0,0,0,0)
df = data.frame(id, Ano, D_treat)

# Gerar a coluna first_treat
df['first_treat'] = df.groupby('id')['Ano'].transform(lambda x: x[df.D_treat==1].min())
df['first_treat'] = df['first_treat'].fillna(0).astype(int)
```

###   Desabilitar notação científica
```
import numpy as np
np.set_printoptions(suppress=True)
```

###  Apagar um arquivo salvo em alguma pasta do computador diretamente do python
```
import os
file_path = 'C:\\Users\\username\\Desktop\\example.txt' # On Windows
#file_path = '/Users/username/Desktop/example.txt' # On Mac/Linux
os.remove(file_path)
```

### Remover linhas duplicadas de uma coluna, agrupando os dados por (id e Ano)
```
df.drop_duplicates(subset=["id", "Ano"], inplace=True)
```

### Visualizar linhas duplicadas e gerar coluna com número de ocorrências, agrupando os dados por (id e Ano)
```
df["count"] = df.groupby(["id", "Ano"])["id"].transform("size")
```

### Visualizar quantas observações sem serem duplicados existem no df
```
# Total de observações únicas em todo o df
unique_df = df.drop_duplicates()
print("Número de observações únicas:", unique_df.shape[0])

# Total de observações únicas de uma coluna
print("Número de observações únicas:", df["Coluna_1"].nunique())
```

### Obter o valor mínimo baseado em duas  colunas
```
# Sem agrupar 
valor_minimo = df["valor"].min()
print(valor_minimo)

# Caso houver missings 
valor_minimo = df["valor"].min(skipna=True)

# Sem agrupar e armazenar em uma nova coluna
df["valor_minimo"] = df["valor"].min()

# Agrupando por id e Ano
df.groupby(["id", "ano"])["valor"].min()

# Agrupando por id e Ano e armazenar em uma nova coluna
df["valor_minimo"] = df.groupby(["id", "ano"])["valor"].transform("min")
```

###  Padronização de  escala
> Padronização é um processo estatístico que transforma uma coluna de dados para que ela tenha média 0 e desvio padrão 1. Isso é frequentemente feito em problemas de aprendizado de máquina para que as diferentes características tenham a mesma escala e, portanto, a mesma importância.
```
# Padronizar apenas uma coluna
from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
valor_padronizado = scaler.fit_transform(df[["valor"]])

# Padronizar uma lista de colunas
from sklearn.preprocessing import StandardScaler
colunas = ["valor1", "valor2", "valor3"]
scaler = StandardScaler()
df[colunas] = scaler.fit_transform(df[colunas])
```

###  Normalização de colunas do df
> Normalização é um processo estatístico que transforma uma coluna de dados para que os valores estejam dentro de um determinado intervalo, geralmente entre 0 e 1. Isso é frequentemente feito em problemas de aprendizado de máquina para que as diferentes características tenham a mesma escala e, portanto, a mesma importância. A normalização é diferente da padronização, na qual os dados são transformados para terem média 0 e desvio padrão 1.

> Existem várias técnicas de normalização, cada uma com seus próprios benefícios e limitações. Alguns exemplos incluem:

> -   Min-Max normalization: A normalização Min-Max transforma os dados para que estejam entre 0 e 1, usando a fórmula: (valor - valor_min) / (valor_max - valor_min)

> -   Z-Score normalization: A normalização Z-Score transforma os dados para que a média seja 0 e o desvio padrão 1, usando a fórmula: (valor - média) / desvio_padrão

> -   L2 normalization: A normalização L2 transforma os dados de modo que a soma dos quadrados dos valores seja igual a 1.
```
# Normalizar uma coluna
from sklearn.preprocessing import MinMaxScaler
scaler = MinMaxScaler()
df["valor"] = scaler.fit_transform(df[["valor"]])

# Normalizar todo o dataframe
df_normalizado = df.copy()
df_normalizado["valor"] = scaler.fit_transform(df[["valor"]])

# Normalizar uma lista de colunas
colunas_a_normalizar = ["valor1", "valor2", "valor3"]
min_max_scaler = MinMaxScaler()
df[colunas_a_normalizar] = df[colunas_a_normalizar].apply(lambda x: min_max_scaler.fit_transform(x.values.reshape(-1,1)))

# ou Normalizar uma lista de colunas
from sklearn.pipeline import make_pipeline
colunas_a_normalizar = ["valor1", "valor2", "valor3"]
df[colunas_a_normalizar] = make_pipeline(MinMaxScaler()).fit_transform(df[colunas_a_normalizar])
```

###  Gerar lag e lead de uma coluna agrupada por id e Ano
```
# Gerar lag -1 
df["lead1"] = df.groupby(["id","Ano"])["valor"].shift(-1)

# Gerar lag -2
df["lead2"] = df.groupby(["id","Ano"])["valor"].shift(-2)

# Gerar lead +1 
df["lag1"] = df.groupby(["id","Ano"])["valor"].shift(1)

# Gerar lead +2
df["lag2"] = df.groupby(["id","Ano"])["valor"].shift(2)
```

###  Gerar lag e lead de uma coluna agrupada por id e Ano (utilizando a média dos valores anteriores e posteriores com uma janela de 3 anos.
> irá calcular a média dos valores anteriores e posteriores com uma janela de 3 linhas e deslocá-los uma posição para trás e uma posição para frente, respectivamente, para cada combinação única de "id" e "Ano" e armazenar os valores resultantes nas colunas "lag3_mean" e "lead3_mean" do DataFrame.

> - Lembre-se de que essas colunas de deslocamento só serão preenchidas para as linhas onde há valores suficientes para preenchê-las, ou seja, nas primeiras linhas do grupo pode ser que as colunas estejam NaN.
```
# lag
df["lag3_mean"] = df.groupby(["id","Ano"])["valor"].rolling(3, min_periods=1).mean().shift(1)

# lead
df["lead3_mean"] = df.groupby(["id","Ano"])["valor"].rolling(3, min_periods=1).mean().shift(-1)

# lag (se conter missings)
df["lag3_mean"] = df.groupby(["id","Ano"])["valor"].apply(lambda x: x.rolling(3, min_periods=1).mean().shift(1)).reset_index(level=0, drop=True)

# lead (se conter missings)
df["lead3_mean"] = df.groupby(["id","Ano"])["valor"].apply(lambda x: x.rolling(3, min_periods=1).mean().shift(-1)).reset_index(level=0, drop=True)
```

###  Gerar (id) identificador numérico a partir de uma ou mais colunas agrupadas
```
# Agrupar pelas colunas CPF
grouped = df.groupby(['CPF_1', 'CPF_2'])

# Gerar id numérico identificador para cada combinação de CPFs
df['id'] = grouped.cumcount()
```

###  Shapefile com códigos IBGE `geobr`
> [Introduction to geobr (Python) • geobr (ipeagit.github.io)](https://ipeagit.github.io/geobr/articles/python-intro/py-intro-to-geobr.html)
```
# Instalar geobr
!pip install geobr

# Carregar geobr
import geobr
import pandas as pd

# Visualizar dados disponíveis
geobr.list_geobr()

# Baixar o shapefile e mais informações dos municipios para o ano de 2019
Municipios = geobr.read_municipality(year=2019)
Municipios 
```

### Importar coluna CPF como string    
Nota:  os CPF tem zeros nos primeiros caracteres (zeros a esquerda), se importarmos os dados  como numéricos os zeros serão removidos, portanto uma boa pratica é trabalhar com eles em string
```
df = pd.read_csv("meu_arquivo.csv", delimiter=",", dtype={"CPF": str})
```

### Caso o CPF tenha sido convertido em numérico, é possível adicionar os zeros a esquerda novamente
```
df['CPF'] = df['CPF'].apply(lambda x: '{:011}'.format(x))
```

###  Gerar faixas etárias a partir da coluna idade
```
# Gerar uma única coluna de faixas etárias a partir da coluna idade
# Definindo as faixas etárias
bins = [0, 5, 10, 15, 20, 25, 30, 35, 40, 45, 50, 55, 60, 65, 70, 75, 80, 85, 90, 95, 100]

# Criando a coluna 'faixa_etaria' com base nas faixas definidas acima
df['faixa_etaria'] = pd.cut(df['idade'], bins, labels=["1-5", "6-10", "11-15", "16-20", "21-25", "26-30", 
                                          "31-35", "36-40", "41-45", "46-50", "51-55", "56-60", 
                                          "61-65", "66-70", "71-75", "76-80", "81-85", "86-90", 
                                          "91-95", "96-100"])
```

###  Balancear classes para  Machine Learning        
> 1.  Oversampling: O método de oversampling consiste em aumentar a quantidade de exemplos da classe minoritária para equilibrar o número de exemplos das classes. Isso é feito através da função resample() do scikit-learn, onde é selecionada a classe minoritária e é feita uma cópia dos dados até que o número de exemplos seja igual ao número de exemplos da classe majoritária.
    
> 2.  Undersampling: O método de undersampling consiste em diminuir a quantidade de exemplos da classe majoritária para equilibrar o número de exemplos das classes. Isso é feito através da função resample() do scikit-learn, onde é selecionada a classe majoritária e é removido aleatoriamente alguns exemplos até que o número de exemplos seja igual ao número de exemplos da classe minoritária.
    
> 3.  SMOTE: O SMOTE (Synthetic Minority Over-sampling Technique) é uma técnica de balanceamento de classes que cria exemplos sintéticos da classe minoritária. Isso é feito através da biblioteca imbalanced-learn. O SMOTE seleciona aleatoriamente exemplos da classe minoritária e cria novos exemplos sintéticos a partir deles, de forma a aumentar o número de exemplos dessa classe.
    
> Em resumo, os três métodos são utilizados para equilibrar as classes, mas tem aproximações diferentes, no oversampling é copiado os dados da classe minoritária, no undersampling é removido alguns dados da classe majoritária e no SMOTE é criado dados sintéticos da classe minoritária para equilibrar as classes.
```
# Método 1: Oversampling
from sklearn.utils import resample

## Selecionando a classe minoritária e a classe majoritária
minority_class = df[df.target==0]
majority_class = df[df.target==1]

## Aumentando a quantidade de exemplos da classe minoritária
oversampled_minority_class = resample(minority_class, 
                                      replace=True, 
                                      n_samples=len(majority_class), 
                                      random_state=42)
## Concatenando as classes balanceadas
balanced_df = pd.concat([oversampled_minority_class, majority_class])

# Método 2: Undersampling
from sklearn.utils import resample

## Selecionando a classe minoritária e a classe majoritária
minority_class = df[df.target==0]
majority_class = df[df.target==1]

## Diminuindo a quantidade de exemplos da classe majoritária
undersampled_majority_class = resample(majority_class, 
                                       replace=False, 
                                       n_samples=len(minority_class), 
                                       random_state=42)
## Concatenando as classes balanceadas
balanced_df = pd.concat([minority_class, undersampled_majority_class])

# Método 3: SMOTE
from imblearn.over_sampling import SMOTE

# Selecionando as features e alvo
X = df.drop('target', axis=1)
y = df['target']

# Aplicando o SMOTE
smote = SMOTE(random_state=42)
X_resampled, y_resampled = smote.fit_resample(X, y)
```

###  Deflacionar variáveis monetárias   com `deflateBR`                             
> [deflateBR · PyPI](https://pypi.org/project/deflateBR/)
> `deflateBR` é um pacote usado para desinflar reais nominais usando vários índices de preços populares. Trata-se de uma reimplementação do  [pacote grande deflateBR R](https://cran.r-project.org/web/packages/deflateBR/index.html)  de  [Fernando Meireles](https://twitter.com/meirelesff).`Python`

> Nos bastidores, solicita dados da API do  [IPEADATA](http://www.ipeadata.gov.br/)  em um desses cinco Índices de preços brasileiros:  [IPCA](https://ww2.ibge.gov.br/english/estatistica/indicadores/precos/inpc_ipca/defaultinpc.shtm)  e  [INPC,](https://ww2.ibge.gov.br/english/estatistica/indicadores/precos/inpc_ipca/defaultinpc.shtm)  mantido pelo  [IBGE;](https://ww2.ibge.gov.br/home/)  e IGP-M,  [IGP-DI](http://portalibre.fgv.br/main.jsp?lumChannelId=402880811D8E34B9011D92B6160B0D7D),[](http://portalibre.fgv.br/main.jsp?lumChannelId=402880811D8E34B9011D92B6160B0D7D)  e  [IPC](http://portalibre.fgv.br/main.jsp?lumChannelId=402880811D8E34B9011D92B7350710C7)  mantido pela  [FGV/IBRE.](http://portalibre.fgv.br/main.jsp?lumChannelId=402880811D8E2C4C011D8E33F5700158)  Para selecionar um dos índices de preços disponíveis, basta fornecer um dos seguintes opções para o argumento: , , , , e . A seguir, o índice INPC é usado.`deflateBR``index =``ipca``igpm``igpdi``ipc``inpc`
```
!pip install deflateBR
import pandas as pd
import deflatebr as dbr

# Gerar exemplo de df
df = pd.DataFrame({'Valor_nominal_1':[100,200,300,400],
				  'Valor_nominal_2':[100,200,300,400],
				  'Valor_nominal_3':[100,200,300,400],
                  'datas':['2015-01-01', '2015-02-01', '2015-10-01', '2015-12-01']})

# Deflacionar uma coluna
df['Valor_real_ipca'] = dbr.deflate(nominal_values = df.Valor_nominal_1,
                                    nominal_dates = df.datas, 
                                    real_date='2020-01',
                                    progress_bar=True, 
                                    on_jupyter=True,
                                    index='ipca')
df

# Deflacionar mais de uma coluna coluna
colunas = ['Valor_nominal_1', 'Valor_nominal_2', 'Valor_nominal_3']

for coluna in colunas:
    df[coluna + '_deflated'] = dbr.deflate(nominal_values = df[coluna], 
                                           nominal_dates = df.datas, 
                                           real_date='2020-01',
                                           progress_bar=True, 
                                           on_jupyter=True,
                                           index='ipca')
df
```

###  Gerar variável Data (Ex: 31-12-xxx)  a partir de uma coluna Ano
```
df['Data'] = pd.to_datetime(df['Ano'], format='%Y') + pd.offsets.YearEnd(0)
```

### Gerar estações do ano a partir de uma variável do tipo date
```   
import calendar

# Converter a coluna data para type date
df['Data'] = pd.to_datetime(df['Data'])

# Gerar função para criar as estações do ano
def get_season(date):
    if date.month >= 3 and date.month <= 5:
        return 'Primavera'
    elif date.month >= 6 and date.month <= 8:
        return 'Verão'
    elif date.month >= 9 and date.month <= 11:
        return 'Outono'
    else:
        return 'Inverno'

# Adição da coluna "Estação"
df['Estação'] = df['Data'].apply(get_season)
```

###  Preencher dados que podem se repetir
>  Ex: informações que não mudam ao longo do tempo como (data de nascimento, sexo, cor) que aparecem para alguns anos no dataframe, porém sem informações para outros anos.
```
```

## Importar e Exportar Dados

###   Importar e Exportar planilha do Excel 
```
import pandas as pd

# Importar.xls
df = pd.read_excel('caminho/do/arquivo.xls')
df = pd.read_excel('caminho/do/arquivo.xls', sheet_name='planilha')

# Importar.xlsx
!pip install openpyxl
df = pd.read_excel('caminho/do/arquivo.xlsx')
df = pd.read_excel('caminho/do/arquivo.xlsx', sheet_name='planilha')

# Exportar.xls
df.to_excel("caminho/do/arquivo.xls")
df.to_excel("caminho/do/arquivo.xls", sheet_name="planilha")

# Exportar.xlsx
!pip install openpyxl
df.to_excel("caminho/do/arquivo.xlsx", sheet_name="planilha")
df.to_excel("caminho/do/arquivo.xlsx")
```

###   Importar e Exportar dados do stata .dta
> Alguns dos parâmetros utilizados neste código são:
>  Importar .dta
>-   `convert_categoricals`: indica se as variáveis categóricas devem ser convertidas em tipo categoria
>-   `convert_missing`: indica se os valores ausentes devem ser convertidos em NaN
>-   `preserve_dtypes`: indica se os tipos de dados originais devem ser preservados
>-   `convert_dates`: indica se as variáveis de data devem ser convertidas em tipo data
>-   `encoding`: a codificação do arquivo
>-   `index_col`: a coluna a ser usada como índice
>-   `data_label`: indica se as etiquetas dos dados devem ser incluídas
>-   `variable_labels`: indica se as etiquetas das variáveis devem ser incluídas
>  Exportar .dta
>  -   `convert_categoricals`: indica se as variáveis categóricas devem ser convertidas em tipo categoria
> -   `write_index`: indica se o índice deve ser escrito no arquivo
> -   `byteorder`: a ordem de bytes a ser usada
> -   `time_stamp`: a data e hora a ser incluída no cabeçalho do arquivo
> -   `data_label`: a etiqueta dos dados a ser incluída no arquivo
> -   `variable_labels`: as etiquetas das variáveis a serem incluídas no arquivo
> -   `version`: a versão do formato .dta a ser usada
> -   `convert_dates`: indica se as variáveis de data devem ser convertidas em tipo data

É importante observar que alguns desses parâmetros são opcionais e podem ser omitidos de acordo com suas necessidades.
```
import pandas as pd

# Importar.dta com labels
df = pd.read_stata("caminho/do/arquivo.dta",  
				   convert_categoricals=True, 
				   convert_missing=True, 
                   preserve_dtypes=False, 
                   convert_dates=True,
                   encoding='latin-1', 
                   index_col=None, 
                   convert_strl=False, 
                   iterator=False, 
                   chunksize=None, 
                   columns=None, 
                   order_categoricals=True, 
                   data_label=True, 
                   variable_labels=True, 
                   byteorder=None, 
                   missing_values=None)

# Exportar .dta 
df.to_stata("caminho/para/salvar/arquivo.dta", 
		    convert_categoricals=True, 
            write_index=True, byteorder=None, 
            time_stamp=None, 
            data_label=None, 
            variable_labels=None, 
            version=114, 
            convert_dates=True)
```

###   Importar e Exportar  arquivos .csv
> Importar .csv
>-   `header`: indica qual linha deve ser usada como cabeçalho
>-   `index_col`: indica qual coluna deve ser usada como índice
>-   `names`: fornece nomes para as colunas
>-   `skiprows`: indica quantas linhas devem ser puladas no início do arquivo
>-   `skipfooter`: indica quantas linhas devem ser puladas no final do arquivo

> Exportar  .csv
> -   `index`: indica se o índice deve ser incluído no arquivo exportado (padrão é True)
>-   `header`: indica se as colunas devem ser incluídas no arquivo exportado (padrão é True)
>-   `na_rep`: indica o valor a ser usado para substituir valores faltantes (padrão é "")
>-   `encoding`: indica a codificação do arquivo exportado
```
import pandas as pd

# Importar arquivo .csv separado por ","
df = pd.read_csv("caminho/do/arquivo.csv", sep=",")

# Exportar  arquivo .csv separado por ","
df.to_csv("caminho/para/arquivo.csv", sep=",")
```

###   Importar arquivo .csv e fazer append                                             
```
import glob
import pandas as pd

path = "caminho/dos/arquivos/*.csv"
files = glob.glob(path)

dfs = []
for file in files:
    df = pd.read_csv(file)
    dfs.append(df)

result = pd.concat(dfs)
```

###   Importar varios arquivos .csv,  fazer append das tabelas e gerar uma coluna com nome dos arquivos csv
> No código abaixo, a variável `path` armazena o caminho para os arquivos e a extensão desejada. A função `glob.glob()` encontra todos os arquivos com essa extensão no caminho especificado. Em seguida, um loop é usado para importar cada arquivo, adicionando uma coluna chamada "nome_arquivo" com o nome do arquivo e adicionando-o a uma lista de DataFrames. Por fim, a função `pd.concat()` é usada para concatenar todos os DataFrames na lista em um único DataFrame. O parâmetro ignore_index=True irá redefinir o indice, evitando que fique com índice duplicado.

> É importante observar que, caso os arquivos possuam colunas diferentes, pode ser necessário realizar algum tratamento para unificar as colunas.
```
import glob
import pandas as pd

path = "caminho/dos/arquivos/*.csv"
files = glob.glob(path)

dfs = []
for file in files:
    df = pd.read_csv(file)
    df['nome_arquivo'] = file.split("/")[-1] # adicionando coluna com o nome do arquivo
    dfs.append(df)

result = pd.concat(dfs, ignore_index=True)
```

###   Importar varios arquivos .csv e utilizar o endereço e nome do arquivo como nome de cada tabela 
> No código acima, a variável `path` armazena o caminho para os arquivos e a extensão desejada. A função `glob.glob()` encontra todos os arquivos com essa extensão no caminho especificado. Em seguida, um loop é usado para importar cada arquivo, pegando o nome do arquivo sem extensão e armazenando-o como nome da tabela e adicionando-o ao dicionário tables.
```
import glob
import pandas as pd

path = "caminho/dos/arquivos/*.csv"
files = glob.glob(path)

tables = {}
for file in files:
    df = pd.read_csv(file)
    table_name = file.split("/")[-1].split(".")[0] # pegando nome do arquivo sem extensão
    tables[table_name] = df

# para acessar uma tabela específica, basta utilizar o nome do arquivo sem extensão como chave do dicionário, por exemplo:
tabela1 = tables['arquivo1']
```

### Arquivo .csv no databricks e converter para pandas
```
# Importar pandas
import pandas as pd

# Importar .csv carregado no databricks
df_spark = spark.read.csv("/FileStore/tables/Arrecadacao_total.csv", header=True, inferSchema=True)

# Converter para pandas
df = df_spark.toPandas()
```

-----------------------------------

