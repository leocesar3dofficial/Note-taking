# Amostragem

- Permite que pesquisadores extraiam conclusões sobre uma população a partir de uma amostra representativa.
- A escolha entre amostragem probabilística e não probabilística depende dos objetivos da pesquisa, recursos disponíveis e características da população.
- A amostragem probabilística é geralmente preferida quando se busca generalização estatística, enquanto a não probabilística pode ser útil em situações onde a acessibilidade ou recursos limitados são fatores-chave.

## Amostragem Probabilística

- Cada elemento da população tem uma chance conhecida e não nula de ser selecionado na amostra.
- Permite a generalização dos resultados da amostra para a população com um grau de certeza estatística.

1. **Amostragem Aleatória Simples:**
   - Cada elemento da população tem uma chance igual de ser selecionado.
   - Pode ser realizado através de sorteios aleatórios ou usando números aleatórios.
   - Garante a representatividade da amostra.

2. **Amostragem Estratificada:**
   - A população é dividida em estratos (subgrupos) com características similares.
   - Uma amostra aleatória simples é então retirada de cada estrato.
   - Útil quando a população exibe grande heterogeneidade em certas características.

3. **Amostragem Sistemática:**
   - Os elementos são selecionados a intervalos regulares após a escolha aleatória do primeiro elemento.
   - A periodicidade é determinada pela razão entre o tamanho da população e o tamanho desejado da amostra.
   - Eficiente quando a população está ordenada de alguma maneira.

4. **Amostragem por Conglomerados:**
   - A população é dividida em grupos, ou conglomerados.
   - Um número limitado de conglomerados é selecionado aleatoriamente.
   - Todos os elementos dentro dos conglomerados escolhidos são incluídos na amostra.
   - Útil quando é impraticável listar todos os elementos da população.

## Amostragem Não Probabilística

- A seleção dos elementos não é baseada em uma probabilidade conhecida. - A representatividade da amostra em relação à população pode ser difícil de determinar.

1. **Amostragem por Conveniência:**
   - Os elementos são selecionados pela facilidade de acesso.
   - Rápida e econômica, mas pode resultar em viés.

2. **Amostragem por Julgamento:**
   - Os elementos são escolhidos com base no conhecimento do pesquisador.
   - Subjetiva e pode não representar a diversidade da população.

3. **Amostragem Quota:**
   - Os elementos são escolhidos para preencher quotas predefinidas com base em características específicas.
   - Pode ser menos representativa se as quotas não refletirem adequadamente a diversidade da população.

## Fórmulas

### Amostragem Aleatória Simples

1. **Tamanho da Amostra (n):**

   $$ n = \dfrac{N}{1 + \dfrac{N}{N-1} \cdot \dfrac{e^2}{\sigma^2}} $$

   Onde:
   - $ N $ é o tamanho da população.
   - $ e $ é o erro desejado na estimativa.
   - $ \sigma^2 $ é a variância populacional.

2. **Erro Padrão da Média (SE):**

   $$ SE = \dfrac{\sigma}{\sqrt{n}} $$

   Onde:
   - $ \sigma $ é o desvio padrão populacional.
   - $ n $ é o tamanho da amostra.

### Amostragem Estratificada

1. **Tamanho da Amostra Estratificada $ n_h $:**

   $$ n_h = \dfrac{n \cdot N_h}{N} $$

   Onde:
   - $ n_h $ é o tamanho da amostra no estrato $ h $.
   - $ n $ é o tamanho total da amostra.
   - $ N_h $ é o tamanho do estrato na população.
   - $ N $ é o tamanho total da população.

### Amostragem Sistemática

1. **Tamanho da Amostra $ n $:**

   $$ n = \dfrac{N}{k} $$

   Onde:
   - $ N $ é o tamanho da população.
   - $ k $ é o intervalo sistemático.

### Amostragem por Conglomerados

1. **Tamanho da Amostra $ n $:**

   $$ n = \dfrac{N}{M} \cdot n_c $$

   Onde:
   - $ N $ é o tamanho da população.
   - $ M $ é o número total de conglomerados.
   - $ n_c $ é o tamanho médio da amostra em cada conglomerado.

### Erro Padrão da Proporção

$$ SE(\hat{p}) = \sqrt{\dfrac{p(1-p)}{n}} $$

Onde:
- $ \hat{p} $ é a estimativa da proporção na amostra.
- $ p $ é a verdadeira proporção na população.
- $ n $ é o tamanho da amostra.
