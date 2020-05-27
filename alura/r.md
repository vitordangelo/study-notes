# Estatística I: Entenda seus dados com R

- Temos certeza que você já ouviu aquela frase: "existem mentiras, grandes mentiras e estatística". E isso não é tão mentira, porque se você não souber escolher o teste que irá aplicar, a função de média que usará, vai chegar em números que não explicam nada sobre o conjunto de dados que você tem.

- A estatística nos ajuda a entender um pouco mais sobre dados que envolvem a popularidade de um produto, daquilo que se vende menos, ajudando inclusive a predizer qual produto venderá mais, e quando isso vai ocorrer.

- O primeiro ponto a ser entendido sobre estatística é em relação a números, e os tipos de dados que estamos usando naquele momento. Imagine um formulário indagando sobre seu sexo, cujas opções são as seguintes:

```txt
( ) Masculino
( ) Feminino
( ) Não quero declarar
```

Trata-se de um tipo de dado que chamamos de **Categórico**, pois cada um é diferente do outro e não possuem relação ou hierarquia.

Outro tipo de dado comum é conhecido por dado **Ordinal**. Por exemplo, você acabou de fazer um curso e pedem para que o professor seja avaliado em uma escala de 1 a 10:

```txt
Nota: ( )1 ( )2 ( )3 ( )4 ( )5 ( )6 ( )7 ( )8 ( )9 ( )10
```

Neste tipo, existe uma ordem: 1 < 2 < 3 <...< 10. Mas não conseguimos fazer comparações do 1 para o 2. Existe a sensação de que de 1 para 2 é a mesma coisa que de 2 para 3, porém não conseguimos medir isto de maneira precisa. Esses intervalos podem variar de pessoa para pessoa.

A temperatura, então, é um exemplo de dado Intervalar, e a diferença entre cada valor é precisa e mensurável:

```txt
25ºC -- 25,2ºC -- 26ºC
```

- Outro tipo de dado, menos comum, é o Racional, bem parecido com o Intervalar, sendo composto de números em ordem, e cuja diferença de um para outro é mensurável. Porém, nesse tipo de dado, o 0 (zero) significa a ausência daquilo. Em se tratando da temperatura em Celsius, 0ºC significa que está frio, mas não a ausência de temperatura. Em graus Kelvin, 0K indica a ausência de temperatura. Nos estudos em Física, faz sentido lidar com os dados Racionais, porém em Estatística trabalharemos com os três primeiros tipos de dados: Categórico, Ordinal e Intervalar.

- Se traçarmos uma linha passando pelos topos desse gráfico, teremos uma curva muito importante chamada de Curva Normal. É essa curva que esperamos em uma distribuição comum. Se, por exemplo, desenharmos o histograma da altura de um homem brasileiro, teremos que poucos estarão nas faixas menores e maiores, e muitos nas faixas centrais.

Exemplo de Histograma:

![Histograma](https://upload.wikimedia.org/wikipedia/commons/d/d8/Histograma_origin.png)

- Temos uma lista de alturas, em centímetros, das pessoas de uma universidade. E nesse caso, qual o tipo de dado?

  - Intervalar! A diferença entre um e outro é precisa, mas não existe ausência de altura.

- Uma locadora de filmes tem a lista de tipos de filme que cada usuário gosta. João gosta de romance, enquanto Maria gosta de ação. Qual o tipo desses dados?

  - Categórico. Alternativa correta! Afinal, são categorias.

- Um cientista tem a lista da temperatura diária no Deserto do Saara, em Kelvin. Esse exemplo representa que tipo de dado?

  - Racional. Alternativa correta! Kelvin é uma medida especial, pois 0 (zero) significa ausência de temperatura.

- Baseado no que você viu nesta aula, o que é um histograma?

  - Gráfico de barras que mostra a frequência de cada valor num conjunto de dados. Alternativa correta! É um gráfico que tem, no eixo X, o valor da variável sendo exibida (por exemplo, dinheiro, altura, temperatura, etc) e no outro eixo, a frequência (ou seja, quantidade de vezes que aquele item aparece na distribuição).

- A Média Aritmética é totalmente sensível aos valores que chamamos de outliers, ou pontos fora da curva.

- Para o cálculo da mediana, colocamos os valores dados em ordem crescente e escolhemos aquele que é central. Isso é fácil para quantidades ímpares de dados, pois haverá um número localizado bem no meio da amostra.

- Para quantidades pares de dados, pegamos os dois valores centrais e calculamos sua Média Aritmética.

  - Perceba que ela é menos suscetível aos outliers.

- Então, como saber qual das duas usar? Inicialmente, verifique se os outliers são muito grandes e distantes do resto da amostra. Outra regra é que, se o tipo de dado for Ordinal, a média não é um bom método.

- A moda é o elemento que mais se repete na distribuição.

- Com dados Ordinais usamos mediana ou moda;
  utilizamos a Média Aritmética em dados Intervalares, salvo aqueles que possuam outliers;
  desenhe um histograma e verifique se consegue desenhar uma linha parecida com a Normal. Se você tiver uma distribuição normal, o cálculo da média é um método razoável.

- Sobre a Média Aritmética, que soma todos os itens e divide pela sua quantidade total

- Que escolher a MA sem levar em consideração o tipo de dado pode nos levar à conclusões errôneas

- Que a MA é sensível aos outliers

- Sobre a mediana, elemento que fica no meio de uma distribuição ordenada

- Sobre a moda, elemento que mais se repete na distribuição
  Usamos mediana ou moda para dados Ordinais

- Outliers são números extremos, geralmente muito grandes ou muito pequenos, no meio de uma distribuição. Por conta disso, geralmente são números que eliminamos na hora de analisar. Colocar o salário do Sílvio Santos no meio dos salários dos brasileiros alterará o valor da média.

- Em um boxplot são exibidos a mediana, primeiro quartil, terceiro quartil, maior e menor elementos da distribuição.

- É necessário nos atentarmos quando formos comparar duas distribuições. Não podemos levar em conta apenas a Tendência Central, mas também o desvio padrão desses dados, e por aí vamos entender como tal distribuição está se comportando.

- O que um desvio padrão pequeno indica, em relação aos dados?
  - Que os dados estão próximos da média.

# R

## Atribuir uma variável a um valor

```R
numero <- 120
```

## Criar uma lista de valores

```R
lista <- c(1,2,3,4,5)
```

## Criar um histograma

```r
aulas <- c(2,4,4,6,6,6,8,8,10)
hist(aulas)
```

![Hist](https://i.imgur.com/OBQxNIv.png)

## Documentação de uma função

```r
?hist
```

## Média

```R
numeros <- c(1,2,3,4,5)
mean(numeros)
```

## Mediana

```R
numeros <- c(1,2,3,4,5)
median(numeros)
```

## Teste de Hipótese, teste se a distribuição obedece uma normal

```R
shapiro.test(numeros)
        Shapiro-Wilk normality test
data:  numeros
W = 0.9868, p-value = 0.9672
```

- Devemos observar o valor de **p-value**; se este for muito pequeno, algo em torno de 0,05, não é Normal. Nesse caso ele é próximo de 1, logo, devemos acreditar que trata-se de uma Normal.

## Sumário

```R
summary(lista)
   Min. 1st Qu.   Median    Mean 3rd Qu.    Max.
   1.00    3.00     7.00   13.09   13.50   67.00
```

## Boxplot

```R
numeros <- c(1,4,54,65,33,45,2,67,8,6,55,44,8,79,43,12,5,9,1,2,3,44,5,65,34,76,89,7)

boxplot(numeros)
```

![Boxplot](https://i.imgur.com/tHtS8Du.png)

## Salvar um gráfico em arquivo

```R
png(file="/home/vitor/Downloads/plot.png", width=700, height=700)
boxplot(numeros)
dev.off()
```

## Calcular o desvio padrão

```R
numeros <- c(1,4,54,65,33,45,2,67,8,6,55,44,8,79,43,12,5,9,1,2,3,44,5,65,34,76,89,7)

sd(numeros)
```

## Ler arquivo .csv

```R
nums <- read.csv(file="/home/vitor/Downloads/numbers.csv")
```

## Obter apenas os números da primeira coluna do csv

```R
nums <- read.csv(file="/home/vitor/Downloads/numbers.csv")
nums$X1
```

# Análise de dados: Introdução com R

## Valores de uma variável de um dataset

```R
aulas$section_id
```

## Ordenar valores de uma variável

```R
sort(aulas$section_id)
```

## Obter o total de valores únicos

```R
length(unique(aulas$section_id))
```

## Ordenar em uma tabela

```R
sort(table(aulas$section_id))
```

## Instalar o pacote plyr

```R
install.packages("plyr")
```

## Listar a quantidade de vezes que um elemento se repete

```R
library(plyr)

auxiliar <- count(aulas, vars = "course_id")
```

## Exportar um dataset

```R
write.csv(auxiliar, "popularidade.csv")
```

## Renomear colunas de um dataset

```R
duracao <- rename(duracao, replace = c("user_id" = "aluno", "course_id" = "curso", "timeToFinish" = "dias"))
```

## Customizar um histograma

```R
hist(duracao$dias, breaks = 20, main = "Histograma do Tempo", ylab = "Quantidade", xlab = "Tempo", ylim = c(0, 2500), col = "blue")
```

## Obter a média e ignorar os dados faltantes

```R
mean(duracao$dias, na.rm = TRUE)
```

## Obter a mediana e ignorar os dados faltantes

```R
median(duracao$dias, na.rm = TRUE)
```

## Juntar dois banco de dados

```R
popularidade_e_duracao <- merge(sumario_estatistico, popularidade, by = 'curso')
```

## Traçar uma linha de previsão

```R
modelo.linear <- lm(popularidade_e_duracao$popularidade~popularidade_e_duracao$dias)

abline(modelo.linear)
```

## Carregar a lib Shiny e subir o servidor

```R
library(shiny)
ui <- fluidPage()
server <- function(input, output) {}
shinyApp(ui = ui, server = server)
```

# [Tutorial Shiny](https://shiny.rstudio.com/tutorial/written-tutorial/lesson1/)

## Install Shiny

```R
install.packages("shiny")
```

## app.R

> app.R has three components:

- a user interface object
- a server function
- a call to the shinyApp function

The user interface (ui) object controls the layout and appearance of your app. The server function contains the instructions that your computer needs to build your app. Finally the shinyApp function creates Shiny app objects from an explicit UI/server pair.

> Note: Prior to version 0.10.2, Shiny did not support single-file apps and the ui object and server function needed to be contained in separate scripts called ui.R and server.R

## Shiny App 1

```r
library(shiny)

ui <- fluidPage(
  titlePanel("Vitor DAngelo - Shiny App"),
  sidebarLayout(
    sidebarPanel(
      sliderInput(
        inputId = "bins",
        label = "Number of bins:",
        min = 1,
        max = 50,
        value = 30)
    ),
    mainPanel(
      plotOutput(outputId = "distPlot")
    )
  )
)

server <- function(input, output) {
  output$distPlot <- renderPlot({
    x <- faithful$waiting
    bins <- seq(min(x), max(x), length.out = input$bins + 1)

    hist(x, breaks = bins, col = "#75AADB", border = "white",
      xlab = "Waiting time to next eruption (in mins)",
      main = "Histogram of waiting times")
    })
}
```
