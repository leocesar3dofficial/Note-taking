# Python Syntax

## Basics

- **Know the type:** `type(<object>)`

- **Code documentation (docstring):**
  ```python
  """
  Function description, Arguments: ...
  """
  ```

## JSON

- **`json.load(arquivo.json)`**
  Converte um arquivo JSON em um dicionário

- **`json.loads(stringJSON)`**
  Converte uma string JSON em um dicionário

- **`json.dump(estruturaDeDadosPython, nomeDoArquivo)`**
  Codifica e armazena dados em um arquivo no formato JSON

- **`json.dumps(estruturaDeDadosPython, indentação)`**
  Converte um objeto Python em uma string JSON

## Vetores

### Operações matemáticas

- Operações aritméticas: não precisa importar bibliotecas
- Operações complexas: precisa importar bibliotecas

### Seleção de elementos

```python
array
  [
    Primeiro a incluir :
    Índice a excluir (pode ser omitido) :
    Passo (pode ser omitido)
  ]

  # exemplo

  my-array[-1::-2]

  # começa do último e pula de dois em dois de trás pra frente
```

## Functions

### Inner or Nested function

```python
def outer_function(x):
    def inner_function(y):
        return x + y

    result = inner_function(5)
    print("Result from inner function:", result)

outer_function(10)
```

In this example, `outer_function` takes a parameter `x`, and within `outer_function`, there's a nested function `inner_function` that takes another parameter `y`. When `outer_function` is called with an integer argument, it passes that integer to `inner_function`, which adds it to `5`. Then, the result is printed out. When you call `outer_function(10)`, it will output `15` since `10 + 5 = 15`.
