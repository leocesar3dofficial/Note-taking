# Probabilidade

## Conceitos

- **Probabilidade:** é uma medida numérica da chance de que um evento ocorra. Ela varia de 0 (impossibilidade) a 1 (certeza).

- **Espaço Amostral (S):** Conjunto de todos os resultados possíveis de um experimento aleatório.
- **Evento (E):** Subconjunto do espaço amostral. Pode consistir em um ou mais resultados.

- **Probabilidade (P):** Medida de quão provável é que um evento ocorra.

$$ P(E) = \frac{n(E)}{n(S)} $$

- Onde $ n(E) $ é o número de resultados favoráveis ao evento E e $ n(S) $ é o número total de resultados possíveis.

## Probabilidade Condicional e Independência

- **Probabilidade Condicional (P(A|B)):** Probabilidade de A ocorrer dado que B ocorreu.

- **Teorema de Bayes:**

$$ P(A|B) = \frac{P(A \cap B)}{P(B)} $$

- onde:

  - $ P(A|B) $ é a probabilidade condicional de A dado B.
  - $ P(A \cap B) $ é a probabilidade conjunta de A e B.
    - Ou $ P(B|A) \cdot P(A) $
  - $ P(B) $ é a probabilidade marginal de B.

- **Independência:** Dois eventos, A e B, são independentes se a ocorrência de um não afeta a ocorrência do outro.

$$ P(A \cap B) = P(A) \cdot P(B) $$

## Variáveis Aleatórias Discretas e Contínuas

- **Variável Aleatória:** Função que atribui um valor numérico a cada resultado em um espaço amostral.

- **Variável Aleatória Discreta:** Pode assumir apenas valores distintos e isolados. Exemplos incluem contagem de itens, como o número de caras em três lançamentos de uma moeda.

- **Variável Aleatória Contínua:** Pode assumir qualquer valor em um intervalo. Exemplos incluem medidas precisas, como altura, peso ou tempo.

- **Função de Massa de Probabilidade (FMP) para Variáveis Discretas:** A função que associa a probabilidade a cada valor possível da variável discreta.

- **Função Densidade de Probabilidade (FDP) para Variáveis Contínuas:** Descreve a probabilidade relativa de que uma variável aleatória assuma um determinado valor.

## Distribuição binomial

- É um modelo estatístico que descreve o número de sucessos em um número fixo de tentativas independentes, cada uma com a mesma probabilidade de sucesso.
- Ela é amplamente utilizada em estatística para modelar situações em que um evento pode ter apenas dois resultados possíveis: sucesso ou fracasso.

- Os principais requisitos para que um experimento siga uma distribuição binomial são:

  1. Existem um número fixo de tentativas ou ensaios (n).
  2. Cada tentativa é independente das outras.
  3. A probabilidade de sucesso (denotada por p) é constante em todas as tentativas.

$$ P(X = k) = \binom{n}{k} \cdot p^k \cdot (1-p)^{n-k} $$

- **Onde:**
  - $ P(X = k) $ é a probabilidade de obter exatamente $ k $ sucessos,
  - $ \binom{n}{k} $ é o coeficiente binomial, representando o número de maneiras diferentes de escolher $ k $ sucessos em $ n $ tentativas,
  - $ p $ é a probabilidade de sucesso em uma tentativa,
  - $ (1-p) $ é a probabilidade de fracasso em uma tentativa,
  - $ n $ é o número total de tentativas.
