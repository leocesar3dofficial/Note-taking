# Inferência Estatística

## População e Amostra

- **População:** Refere-se ao conjunto completo de elementos ou observações que têm características em comum e são de interesse para o estudo. A população é o grupo total sobre o qual queremos fazer inferências.

- **Amostra:** É um subconjunto representativo da população. Coletar dados de toda a população muitas vezes não é prático, então usamos amostras para fazer inferências sobre a população maior.

## Seleção de Amostra

- **Amostragem Aleatória Simples:** Cada elemento da população tem uma chance igual de ser selecionado. Isso garante uma representatividade justa.

- **Amostragem Estratificada:** Divide a população em grupos (estratos) e depois seleciona aleatoriamente a partir de cada estrato. Isso é útil quando há subgrupos significativos na população.

- **Amostragem por Conglomerados:** Divide a população em clusters, seleciona aleatoriamente alguns clusters e, em seguida, realiza uma pesquisa completa dentro desses clusters.

## Estatística e Parâmetro

- **Estatística:** É uma medida que descreve uma característica da amostra. Exemplos incluem média, desvio padrão e proporção.

- **Parâmetro:** É uma medida que descreve uma característica da população. Exemplos incluem a média populacional, desvio padrão populacional e proporção populacional.

## Distribuições Amostrais

- **Distribuição Amostral da Média:** Se você calcular a média de várias amostras da mesma população, essas médias formarão uma distribuição própria, conhecida como distribuição amostral da média.

- **Distribuição Amostral da Proporção:** Similar à distribuição amostral da média, mas aplicada a proporções.

- **Teorema do Limite Central:** Afirma que, com um tamanho de amostra suficientemente grande, a distribuição amostral da média se aproximará de uma distribuição normal, independentemente da forma da distribuição populacional original.

## Estimação

- Fazer inferências sobre parâmetros populacionais com base em amostras.

### Pontual

- **Definição:** fornecer uma única estimativa específica para o valor de um parâmetro populacional desconhecido.
  
- **Exemplo:** Se quisermos estimar a média da altura dos estudantes de uma escola, uma estimação pontual seria fornecer um único valor como 1,70 metros.

- **Fórmula:** A estimação pontual muitas vezes é simplesmente a estatística de amostra que melhor estima o parâmetro populacional. Por exemplo, a média amostral ($ \bar{x} $) pode ser usada para estimar a média populacional ($ \mu $).

### Intervalar

- **Definição:** fornecer um intervalo (ou faixa) de valores dentro do qual acreditamos que o parâmetro populacional real provavelmente está contido, com um certo nível de confiança.

- **Exemplo:** Em vez de dizer que a média da altura dos estudantes é exatamente 1,70 metros, podemos dizer que estamos 95% confiantes de que a média está entre 1,65 metros e 1,75 metros.

- **Fórmula:** O intervalo de confiança geralmente é calculado usando a estatística de amostra e o erro padrão. Para a média populacional ($ \mu $), o intervalo de confiança é frequentemente formulado como:

$$ \bar{x} \pm Z \left(\frac{s}{\sqrt{n}}\right) $$

- Onde $ Z $ é o valor crítico da distribuição normal padrão associado ao nível de confiança desejado.

### Comparação

- **Precisão vs. Incerteza:** A estimação pontual fornece uma estimativa única e pontual, enquanto a estimação intervalar fornece uma gama de valores que leva em consideração a incerteza associada à amostragem.

- **Confiança:** A estimação intervalar é frequentemente preferida quando queremos levar em conta a variabilidade natural nas amostras e fornecer uma medida de confiança associada à nossa estimativa.

- **Exemplo Numérico:** Se estimarmos a média da altura dos estudantes como 1,70 metros com um intervalo de confiança de 95%, isso significa que se repetirmos o processo de amostragem muitas vezes, 95% dos intervalos de confiança calculados conterão a verdadeira média populacional.

## Fórmulas

### Média Amostral e Média Populacional

- **Média Amostral ($ \bar{x} $):**

$$ \bar{x} = \frac{\sum_{i=1}^{n} x_i}{n} $$

- Onde $ n $ é o tamanho da amostra e $ x_i $ é cada observação na amostra.

- **Média Populacional ($ \mu $):**

$$ \mu = \frac{\sum_{i=1}^{N} x_i}{N} $$

- Onde $ N $ é o tamanho da população.

### Desvio Padrão Amostral e Desvio Padrão Populacional

- **Desvio Padrão Amostral ($ s $):**

$$ s = \sqrt{\frac{\sum_{i=1}^{n} (x_i - \bar{x})^2}{n-1}} $$

- Onde $ n $ é o tamanho da amostra, $ x_i $ é cada observação na amostra, e $ \bar{x} $ é a média amostral.

- **Desvio Padrão Populacional ($ \sigma $):**

$$ \sigma = \sqrt{\frac{\sum_{i=1}^{N} (x_i - \mu)^2}{N}} $$

- Onde $ N $ é o tamanho da população.

### Estimativa da Proporção

- **Estimativa da Proporção ($ \hat{p} $):**
$ \hat{p} = \frac{x}{n} $
onde $ x $ é o número de sucessos na amostra e $ n $ é o tamanho da amostra.

### Distribuição Amostral da Média

- **Variância da Distribuição Amostral da Média** $ ( \sigma_{\bar{x}}^2 )$:

$$ \sigma_{\bar{x}}^2 = \frac{\sigma^2}{n} $$

- Onde $ \sigma $ é o desvio padrão populacional e $ n $ é o tamanho da amostra.

### Intervalo de Confiança para a Média

$$ \text{Intervalo de Confiança} = \bar{x} \pm Z \left(\frac{s}{\sqrt{n}}\right) $$

- $ Z $ é o valor crítico da distribuição normal padrão associado ao nível de confiança desejado.

### Teste de Hipóteses para a Média Populacional

$$ t = \frac{\bar{x} - \mu}{\frac{s}{\sqrt{n}}} $$

- $ t $ é o valor t, usado para comparar com o valor crítico para determinar se a diferença é estatisticamente significativa.

### Teste para Amostras Independentes

**Cenário:** Quando temos duas amostras independentes de duas populações diferentes e queremos comparar as médias dessas populações.

#### Formulação do Teste t para Amostras Independentes

$$ t = \frac{\bar{x}_1 - \bar{x}_2}{\sqrt{\frac{s_1^2}{n_1} + \frac{s_2^2}{n_2}}} $$

- $ \bar{x}_1, \bar{x}_2 $: Médias das amostras 1 e 2.
- $ s_1, s_2 $: Desvios padrões amostrais das amostras 1 e 2.
- $ n_1, n_2 $: Tamanhos das amostras 1 e 2.

#### Procedimento

1. **Formulação de Hipóteses:**
   - Hipótese Nula ($H_0$): $ \mu_1 = \mu_2$ (as médias populacionais são iguais).
   - Hipótese Alternativa ($H_1$): $ \mu_1 \neq \mu_2$ (as médias populacionais são diferentes).

2. **Nível de Significância ($\alpha$):**
   - Escolha um valor crítico ou um intervalo de confiança para $\alpha$ (geralmente 0,05 ou 0,01).

3. **Cálculo do Estatístico t:**
   - Substitua os valores amostrais na fórmula para calcular $t$.

4. **Decisão Estatística:**
   - Compare o valor calculado de $t$ com o valor crítico. Se $|t|$ for maior que o valor crítico, rejeite a hipótese nula.

### Teste para Amostras Dependentes (Pareadas)

**Cenário:** Quando as duas amostras estão relacionadas ou pareadas, como em um estudo de antes e depois, ou quando as observações em uma amostra estão relacionadas com as observações na outra.

#### Formulação do Teste t para Amostras Dependentes

$$ t = \frac{\bar{d}}{\frac{s_d}{\sqrt{n}}} $$

- $ \bar{d} $: Média das diferenças ($\bar{x}_1 - \bar{x}_2$).
- $ s_d $: Desvio padrão das diferenças.
- $ n $: Tamanho da amostra de diferenças.

#### Procedimento

1. **Formulação de Hipóteses:**
   - Hipótese Nula ($H_0$): $ \mu_d = 0$ (as médias populacionais das diferenças são iguais).
   - Hipótese Alternativa ($H_1$): $ \mu_d \neq 0$ (as médias populacionais das diferenças são diferentes).

2. **Nível de Significância ($\alpha$):**
   - Escolha um valor crítico ou um intervalo de confiança para $\alpha$ (geralmente 0,05 ou 0,01).

3. **Cálculo do Estatístico t:**
   - Substitua os valores amostrais na fórmula para calcular $t$.

4. **Decisão Estatística:**
   - Compare o valor calculado de $t$ com o valor crítico. Se $|t|$ for maior que o valor crítico, rejeite a hipótese nula.

### Teste de Independência (Qui-Quadrado)

**Cenário:** Utilizado quando se deseja avaliar a associação ou independência entre duas variáveis categóricas.

#### Procedimento

1. **Formulação de Hipóteses:**
   - Hipótese Nula ($H_0$): As variáveis são independentes.
   - Hipótese Alternativa ($H_1$): As variáveis são dependentes ou associadas.

2. **Tabela de Contingência:**
   - Organize os dados em uma tabela de contingência, cruzando as duas variáveis.

3. **Cálculo do Estatístico Qui-Quadrado ($\chi^2$):**

    $$ \chi^2 = \sum \frac{(O_i - E_i)^2}{E_i} $$

    - onde $O_i$ são as frequências observadas e $E_i$ são as frequências esperadas.

4. **Graus de Liberdade ($df$):**
   - $df = (r-1) \times (c-1)$, onde $r$ é o número de linhas e $c$ é o número de colunas na tabela de contingência.

5. **Decisão Estatística:**
   - Compare o valor calculado de $\chi^2$ com o valor crítico da distribuição qui-quadrado ou utilize um teste de significância.

### Teste para o Coeficiente de Correlação (Teste t de Pearson)

**Cenário:** Utilizado para avaliar se existe uma relação linear significativa entre duas variáveis contínuas.

#### Procedimento

1. **Formulação de Hipóteses:**
   - Hipótese Nula ($H_0$): Não há correlação linear entre as variáveis ($ \rho = 0 $).
   - Hipótese Alternativa ($H_1$): Existe correlação linear entre as variáveis ($ \rho \neq 0 $).

2. **Cálculo do Estatístico t de Pearson ($t$):**

   $$ t = \frac{r \sqrt{n-2}}{\sqrt{1-r^2}} $$

   - Onde $r$ é o coeficiente de correlação amostral e $n$ é o tamanho da amostra.

3. **Graus de Liberdade ($df$):**
   - $df = n-2$, onde $n$ é o tamanho da amostra.

4. **Decisão Estatística:**
   - Compare o valor calculado de $t$ com o valor crítico da distribuição t de Student ou utilize um teste de significância.

5. **Intervalo de Confiança para $ \rho $:**
   - Pode-se calcular o intervalo de confiança para o coeficiente de correlação para fornecer uma estimativa da precisão da medida.