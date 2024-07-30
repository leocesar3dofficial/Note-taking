# Estatística Descritiva

## Medidas de Tendência Central

### Média

1. Aritmética

   - **Simples**

     - É o quociente entre somatório das variáveis pelo
       número de variáveis.

       $$
       \bar{X*{a}} = \frac{\sum x_i}{n}
       $$

   - **Ponderada**

     - É o quociente entre o produto dos valores de uma
       variável pelos seus respectivos pesos ou frequências pela soma dos pesos ou
       frequências.

   $$
   \bar{X*{ap}} = \frac{\sum (f_i \cdot x_i)}{\sum f_i}
   $$

2. Harmônica

   - É o inverso da média aritmética dos inversos das variáveis.

   $$
   \bar{X_h} = \frac{n}{\sum {\frac{1}{x_i}}}
   $$

3. Geométrica

   - É a raiz n-ésima do produto de n valores.

   $$
   \bar{X_g} = \sqrt[n]{x_1 \cdot x_2 \cdot \ldots \cdot x_n}
   $$

### Mediana

- valor central em um conjunto de dados ordenado.

  $$
  \text{Mediana} =
  \begin{cases}
      x_{\frac{n+1}{2}}, & \text{se } n \text{ é ímpar} \\
      \frac{x_{\frac{n}{2}} + x_{\frac{n}{2} + 1}}{2}, & \text{se } n \text{ é par}
  \end{cases}
  $$

### Moda de King

- Calcular a moda de uma distribuição estatística.

  $$
  Mo*{King} = l_i + \left[c \times \left(\frac{f*{modal} - f*{ant}}{(2 \times f*{modal}) - (f*{ant} + f*{post})}\right) \right]
  $$

- Descrição das variáveis:

  - $ Mo\_{King} $ : Representa a Moda de King, que é um tipo específico de moda em um conjunto de dados.

  - $ l_i $ : Pode ser um termo inicial ou uma constante associada à Moda de King.

  - $ c $ : É uma constante multiplicativa que afeta o termo dentro dos colchetes.

  - $ f\_{modal} $ : Refere-se à frequência modal, que é a frequência mais comum em um conjunto de dados.

  - $ f\_{ant} $ : Representa uma frequência anterior, indicando uma referência temporal ou espacial anterior à frequência modal.

  - $ f\_{post} $ : Indica uma frequência posterior, sugerindo uma referência temporal ou espacial posterior à frequência modal.

- Exemplo

  | Classes | Freqüência | Variável       |
  | ------- | ---------- | -------------- |
  | 10--20  | 30         | $ c $          |
  | 20--30  | 50         | $ f_{ant} $   |
  | 30--40  | 70         | $ f_{modal} $ |
  | 40--50  | 60         | $ f_{post} $  |
  | 50--60  | 10         | $ l_i $        |
  | Total   | 220        |                |

  $$
  Mo_{Czuber} = 30 + \left[10 \times \left(\frac{70 - 50}{(2 \times 70) - (50 + 60)}\right) \right] = 36,67
  $$

## Medidas Separatrizes

- São valores que separam o rol (os dados ordenados) em quatro (quartis), dez (decis)
ou em cem (percentis) partes iguais.
- **Ordene os dados:** Coloque os dados do rol em ordem crescente.

### Quartis 

1. **Encontre Q1:** é o valor que separa os 25% inferior dos dados.

$$ Q1 = \frac{{n + 1}}{4} $$

2. **Encontre Q2 (Mediana):** é o valor que separa os 50% inferior dos dados. Se $ n $ for ímpar, Q2 é o valor no meio dos dados ordenados. Se $ n $ for par, Q2 é a média dos dois valores no meio.

3. **Encontre Q3:** é o valor que separa os 75% inferior dos dados.

$$ Q3 = \frac{{3(n + 1)}}{4} $$

### Decis

- São os nove pontos que dividem a distribuição em 10 partes
iguais. 

### Percentis ou Cetis

- São os 99 valores que dividem a distribuição em 100
partes iguais, abrangendo, cada um, 1% do número total da distribuição.

## Medidas de dispersão

- Avaliar o grau de variabilidade ou dispersão dos dados em um conjunto.
- Elas oferecem insights sobre o quão "espalhados" os valores estão em relação à média.

### Amplitude

- A amplitude é a diferença entre o maior e o menor valor em um conjunto de dados.
- **Fórmula:** $ \text{Amplitude} = \text{Máximo} - \text{Mínimo} $

### Variância

- A variância é uma medida que expressa o quão longe cada valor do conjunto está da média.
- Fórmula para a variância populacional $ \sigma^2 $:

  $$ \sigma^2 = \frac{\sum_{i=1}^{n}(X_i - \mu)^2}{n} $$

- Fórmula para a variância amostral ($ s^2 $):

  $$ s^2 = \frac{\sum_{i=1}^{n}(X_i - \bar{X})^2}{n-1} $$
  
- **Onde:**
  - $ X_i $ são os valores individuais,
  - $ \mu $ é a média populacional,
  - $ \bar{X} $ é a média amostral,
  - $ n $ é o número de observações.

### Desvio Padrão

- O desvio padrão é a raiz quadrada da variância. Ele fornece uma medida de dispersão mais fácil de interpretar.
- Fórmula para o desvio padrão populacional ($ \sigma $):

  $$ \sigma = \sqrt{\sigma^2} $$

- Fórmula para o desvio padrão amostral ($ s $):

  $$ s = \sqrt{s^2} $$

### Escore Z

- A pontuação z, também conhecida como escore padrão, é uma medida estatística que expressa a posição de um dado valor em relação à média de uma distribuição e é medida em termos de desvios padrão dessa média.
- Ela indica quantos desvios padrão um determinado valor está acima ou abaixo da média de uma distribuição.
- É útil para comparar valores em diferentes distribuições, pois ela normaliza os dados, permitindo que você avalie a posição relativa de um valor em relação à média e ao desvio padrão da distribuição.
- Uma pontuação z positiva indica que o valor está acima da média, enquanto uma pontuação z negativa indica que está abaixo da média.
- Uma pontuação z de 0 significa que o valor é igual à média da distribuição.

$$ z = \frac{{X - \mu}}{{\sigma}} $$

- **Onde:**
  - $ z $ é a pontuação z,
  - $ X $ é o valor individual,
  - $ \mu $ é a média da distribuição,
  - $ \sigma $ é o desvio padrão da distribuição.

## Medidas de forma

- Descrevem a forma da distribuição de dados.
- Fornecem informações sobre a simetria e a inclinação da distribuição.

### Assimetria (Skewness)

- Mede a falta de simetria em uma distribuição.
- **Positiva:** Curva de distribuição se estende mais para a direita (caudas mais longas à direita).
- **Negativa:** Curva de distribuição se estende mais para a esquerda (caudas mais longas à esquerda).

$$ \text{Assimetria} = \frac{n}{(n-1)(n-2)} \sum_{i=1}^{n} \left(\frac{x_i - \bar{x}}{s}\right)^3 $$

- **Onde:**
  - $n$ é o tamanho da amostra.
  - $x_i$ é cada valor na amostra.
  - $\bar{x}$ é a média da amostra.
  - $s$ é o desvio padrão da amostra.

### Curtose (Kurtosis)

- A curtose mede a quantidade de dados em uma distribuição de probabilidade que está centrada no meio (média) em comparação com as caudas.
- A curtose mede o pico (altura) e a forma das caudas de uma distribuição.
- Tipos:
  - Mesocúrtica: Curtose = 0.
    - Tem o mesmo achatamento que a distribuição normal.
  - Leptocúrtica: Curtose > 3.
    - Alta: (distribuição afunilada) têm caudas mais pesadas (mais valores extremos)
  - Platicúrtica: Curtose < 3.
    - Baixa: (distribuição achatada) têm caudas mais leves.

$$ \text{Curtose} = \frac{\frac{1}{n} \sum_{i=1}^{n} (x_i - \bar{x})^4}{\left(\frac{1}{n} \sum_{i=1}^{n} (x_i - \bar{x})^2\right)^2} - 3 $$

## Medidas de associação

- São utilizadas para avaliar o grau de relação entre duas variáveis.

### Coeficiente de Correlação de Pearson (r)

- *Tipo de Variáveis:* Variáveis quantitativas contínuas.
- *Interpretação:* Varia de -1 a 1. Quanto mais próximo de 1 ou -1, mais forte é a correlação, enquanto 0 indica ausência de correlação.

$$ r = \frac{\sum{(X_i - \bar{X})(Y_i - \bar{Y})}}{\sqrt{\sum{(X_i - \bar{X})^2} \sum{(Y_i - \bar{Y})^2}}} $$

- Onde $ \bar{X} $ e $ \bar{Y} $ são as médias de X e Y, respectivamente.

### Coeficiente de Correlação de Spearman (ρ ou rs)

- *Tipo de Variáveis:* Ordinais ou quando a relação não é linear.
- *Interpretação:* Varia de -1 a 1. Semelhante ao coeficiente de correlação de Pearson, mas não assume uma relação linear.
- *Cálculo:* Calcula-se a correlação de postos das observações.

### Coeficiente de Correlação de Kendall (τ ou tau)

- *Tipo de Variáveis:* Ordinais.
- *Interpretação:* Avalia a concordância entre as ordens das observações em ambas as variáveis.
- *Cálculo:* Baseia-se no número de pares concordantes e discordantes.

### Coeficiente de Determinação (R²)

- *Tipo de Variáveis:* Variável independente (X) e variável dependente (Y).
- *Interpretação:* Indica a proporção da variação em Y que é explicada pela variação em X.

$$ R^2 = \frac{\text{Variância explicada}}{\text{Variância total}} $$

### Qui-quadrado (χ²)

- *Tipo de Variáveis:* Variáveis categóricas (nominais ou ordinais).
- *Interpretação:* Testa a independência entre duas variáveis categóricas.
- *Cálculo:* Comparação das frequências observadas e esperadas em uma tabela de contingência.

### Coeficiente de Contingência (C)

- *Tipo de Variáveis:* Variáveis categóricas (nominais ou ordinais).
- *Interpretação:* Mede a força da associação entre duas variáveis categóricas.

$$ C = \sqrt{\frac{\chi^2}{n + \chi^2}} $$


