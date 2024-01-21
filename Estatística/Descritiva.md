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
  | 20--30  | 50         | $ f\_{ant} $   |
  | 30--40  | 70         | $ f\_{modal} $ |
  | 40--50  | 60         | $ f\_{post} $  |
  | 50--60  | 10         | $ l_i $        |
  | Total   | 220        |                |

  $$
  Mo_{Czuber} = 30 + \left[10 \times \left(\frac{70 - 50}{(2 \times 70) - (50 + 60)}\right) \right] = 36,67
  $$
