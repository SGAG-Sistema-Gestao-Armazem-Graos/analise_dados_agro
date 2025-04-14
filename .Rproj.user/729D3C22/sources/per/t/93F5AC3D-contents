# ANÁLISE ESTATÍSTICA DE DADOS DO AGRO
---
title: "ANÁLISE ESTATÍSTICA DE DADOS DO AGRO"
autores: Francismar Alves Martins Junior

output: html_notebook
---

## Introdução aos Dados da Planilha `"base_agro.xlsx"`

A planilha `base_agro.xlsx` reúne informações essenciais sobre diferentes tipos de cultivos agrícolas. Ela foi elaborada com o objetivo de analisar a produtividade agrícola em determinada região, considerando os seguintes aspectos:

*- Tipo de Cultivo:* identifica as culturas analisadas, como milho e cana-de-açúcar.

*- Quantidade de Produtores:* representa o número de agricultores que atuam em cada tipo de cultivo.

*- Produção por hectare (toneladas):* indica a média de produção para cada hectare cultivado, sendo um importante indicador de eficiência agrícola.

*-Classificação da Produtividade:* classifica a produtividade como Alta, Média ou Baixa, de acordo com critérios previamente estabelecidos.

Esses dados são úteis para diagnósticos sobre eficiência produtiva, planejamento de políticas públicas, orientação de investimentos e capacitação técnica para o setor agropecuário.

## INSTALAÇÃO DE PACOTE.

Sempre tera um # para que o pacote seja inicializado uma unica vez.
```{r}
# install.packages("readxl") # pacote para leitura de arquivos no formato (xlsx).

```
## CARREGANDO PACOTES.

```{r}
library(readxl)

```



## CARREGAMENTO DE ARQUIVO NO FORMATO XLSX.

Iremos carregar esse aquivo no formato `xlsx`, para transformar em um data frame que é o modelo otimo para manipular os dados.

```{r}
# Caminho do arquivo (ajuste conforme necessário)
arquivo <- "base_agro.xlsx"

# Carregar os dados da planilha e converter para data frame
dados <- as.data.frame(read_excel(arquivo))

# Convertendo os dado de Produção por hectare em toneladas de todos os produtores 
dados$`Produção por hectare (toneladas)` <- as.numeric(dados$`Produção por hectare (toneladas)`)


# Visualizar as primeiras linhas
head(dados)

```

Quando o programa copilou esse arquivo analisamos de `Tipo de Cultivo` -  são dados do tipo qualitativas nominal, `Quantidade de Produtores` - são dados de quantidativos discretos, `Produção por hectare` -  esta no formato qualitativo, mas vou fazer um tratamento nos dados para tranformar em quantitativo, e por ultimo, `Calssifição da Produtividade` - se refere a dados qualitativos ordinais e foram convertidos em quantitativos do continuos.

## SOBRE AS ANALISE ESTATISTICAS QUE SERAM REALIZADAS.

Iremos fazer análise quantitativa da coluna `Quantidade de Produtores` e `Producão por hectare`

### QUANTIDADE DE PRODUTORES - VARIAVEIS QUANTITATIVA DISCRETA

#### As Medidas de Tendência Central;

##### MEDIA

```{r}
# Média
media <- mean(dados$`Quantidade de Produtores`, na.rm = TRUE)
media

```

##### MODA

```{r}

# Moda (não tem função nativa, vamos criar)
moda <- function(x) {
  ux <- unique(x)
  ux[which.max(tabulate(match(x, ux)))]
}
moda(dados$`Quantidade de Produtores`)


```

##### MEDIANA

```{r}


# Mediana
mediana <- median(dados$`Quantidade de Produtores`, na.rm = TRUE)
mediana


```


#### As Medidas de Dispersão;

##### VARIÂNCIA
```{r}
# Variância
var(dados$`Quantidade de Produtores`, na.rm = TRUE)

```

##### DESVIO PADÃO
```{r}

# Desvio padrão
sd(dados$`Quantidade de Produtores`, na.rm = TRUE)

```

##### AMPLITUDE

```{r}


# Amplitude
range_valores <- range(dados$`Quantidade de Produtores`, na.rm = TRUE)
amplitude <- diff(range_valores)
amplitude


```


#### As Medidas Separatrizes;
##### QUARTIS

```{r}

# Quartis
quartis <- quantile(dados$`Quantidade de Produtores`, probs = c(0.25, 0.5, 0.75), na.rm = TRUE)
quartis

```

##### DECIS

```{r}

# Decis
decis<- quantile(dados$`Quantidade de Produtores`, probs = seq(0.1, 0.9, by = 0.1), na.rm = TRUE)
decis

```

##### PERCENTIS

```{r}

# Percentis
percentis <- quantile(dados$`Quantidade de Produtores`, probs = seq(0.01, 0.99, by = 0.01), na.rm = TRUE)
percentis

```

#### Uma análise gráfica.
##### HISTOGRAMA

```{r}
# Histograma
hist(dados$`Quantidade de Produtores`,
     main = "Distribuição da Quantidade de Produtores",
     xlab = "QUANTIDADE DE PRODUTORES",
     col = "skyblue", border = "white")



```

##### BOXPLOT

```{r}

# Boxplot
boxplot(dados$`Quantidade de Produtores`,
        main = "Boxplot da Quantidade de Produtores",
        ylab = "Quantidade",
        col = "lightgreen", horizontal = TRUE)

```


### PRODUÇÃO POR HECTARE - VARIAVEIS QUANTITATIVO CONTINUAS

#### As Medidas de Tendência Central;

##### MEDIA

```{r}
# Média
media <- mean(dados$`Produção por hectare (toneladas)`, na.rm = TRUE)
media

```

##### MODA

```{r}

# Moda (não tem função nativa, vamos criar)
moda <- function(x) {
  ux <- unique(x)
  ux[which.max(tabulate(match(x, ux)))]
}
moda(dados$`Produção por hectare (toneladas)`)


```

##### MEDIANA

```{r}


# Mediana
mediana <- median(dados$`Produção por hectare (toneladas)`, na.rm = TRUE)
mediana


```


#### As Medidas de Dispersão;

##### VARIÂNCIA
```{r}
# Variância
var(dados$`Quantidade de Produtores`, na.rm = TRUE)

```

##### DESVIO PADÃO
```{r}

# Desvio padrão
sd(dados$`Produção por hectare (toneladas)`, na.rm = TRUE)

```

##### AMPLITUDE

```{r}


# Amplitude
range_valores <- range(dados$`Produção por hectare (toneladas)`, na.rm = TRUE)
amplitude <- diff(range_valores)
amplitude


```


#### As Medidas Separatrizes;
##### QUARTIS

```{r}

# Quartis
quartis <- quantile(dados$`Produção por hectare (toneladas)`, probs = c(0.25, 0.5, 0.75), na.rm = TRUE)
quartis

```

##### DECIS

```{r}

# Decis
decis<- quantile(dados$`Produção por hectare (toneladas)`, probs = seq(0.1, 0.9, by = 0.1), na.rm = TRUE)
decis

```

##### PERCENTIS

```{r}

# Percentis
percentis <- quantile(dados$`Produção por hectare (toneladas)`, probs = seq(0.01, 0.99, by = 0.01), na.rm = TRUE)
percentis

```

#### Uma análise gráfica.
##### HISTOGRAMA

```{r}
# Histograma
hist(dados$`Produção por hectare (toneladas)`,
     main = "Distribuição da Produção por hectare (toneladas)",
     xlab = "tonelada por hectares",
     col = "skyblue", border = "white")



```

##### BOXPLOT

```{r}

# Boxplot
boxplot(dados$`Produção por hectare (toneladas)`,
        main = "Boxplot da Produção por hectare (toneladas)",
        ylab = "Tonelada por hectare",
        col = "lightgreen", horizontal = TRUE)

```

## TIPOS DE CULTURA - GRAFICO PARA OS DADOS QUALITATIVOS.
### GRAFICO DE BARRA PARA MOSTRAR A QUANTIDADE DE CULTURAS ANALIZADAS .
#### VARIAVIES QUANTITATIVA CARDINAL

```{r}

# Tabela de frequências
tabela_tipo_de_cultura <- table(dados$`Tipo de Cultivo`)

# Gráfico de barras
barplot(tabela_tipo_de_cultura,
        main = "Distribuição Tipos de Cultura",
        xlab = "Tipos de Culturas",
        ylab = "Frequência",
        col = "steelblue",
        las = 2)  # Gira os nomes no eixo x para facilitar leitura


```



### GRAFICO DE BARRA PARA MOSTRAR COMO ESTÁ A CLASSIFIÇÃO DOS PRODUÇÃO ANALIZADAS .
#### VARIAVIES QUANTITATIVA ORDINAL

```{r}

# Tabela de frequências
tabela_tipo_de_cultura <- table(dados$`Classificação da Produtividade`)

# Gráfico de barras
barplot(tabela_tipo_de_cultura,
        main = "Distribuição Classificação da Produtividade",
        xlab = "Classificação da Produtividade",
        ylab = "Frequência",
        col = "steelblue",
        las = 2)  # Gira os nomes no eixo x para facilitar leitura


```









