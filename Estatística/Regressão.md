# Regressão Estatística

- É uma técnica usada para entender a relação entre variáveis.
- A regressão linear simples modela a relação entre uma variável independente (x) e uma variável dependente (y) através de uma reta.
- O objetivo é encontrar a melhor reta que se ajusta aos dados observados.

## Regressão Linear Simples

- Há apenas uma variável independente.
- O modelo se torna mais simples, mas ainda assim pode ser poderoso para entender a relação entre as variáveis.
- O objetivo é encontrar os valores de $\beta_0$ e $\beta_1$ que minimizam a soma dos quadrados dos resíduos.

## Ajuste da Reta de Regressão pelo Método dos Mínimos Quadrados

- É um método para ajustar uma linha aos dados.
- Ele minimiza a soma dos quadrados das diferenças entre os valores observados e os valores preditos pela reta.
- **Equação da reta:**

$$ y = \beta_0 + \beta_1 \cdot x + \epsilon $$

- Onde:
    - $y$ é a variável dependente,
    - $x$ é a variável independente,
    - $\beta_0$ é o intercepto,
    - $\beta_1$ é o coeficiente angular,
    - $\epsilon$ é o erro residual.

## Intervalos de Confiança e Intervalo de Predição

- **Intervalo de Confiança (IC):** É uma estimativa do intervalo em que um parâmetro de população (como $\beta_1$) provavelmente se encontra. Um IC típico é de 95%, o que significa que há uma probabilidade de 95% de que o intervalo contenha o verdadeiro valor do parâmetro.

- **Intervalo de Predição (IP):** É um intervalo que dá uma estimativa para onde podemos esperar que uma nova observação individual caia. Diferentemente do IC, o IP leva em consideração a incerteza associada à previsão de um valor específico.

## Exemplo Prático

Suponha que você tenha um conjunto de dados (x, y) e queira ajustar uma reta de regressão. Você calcularia os coeficientes $\beta_0$ e $\beta_1$ usando o método dos mínimos quadrados. Em seguida, poderia calcular intervalos de confiança e predição para avaliar a precisão da sua previsão.

A interpretação estatística desses intervalos depende da distribuição dos resíduos, da normalidade dos dados e de outras suposições que você deve verificar ao realizar uma análise de regressão.