# Bem vindo ao caderno de anotações NumPy
O objetivo aqui é deixar registrado algumas funcionalidades dessa biblioteca, e também uma forma de medir o meu progresso conforme vou avançando no curso. Também revisar de tempos em tempos algumas funções já aprendidas.
`Espero que possa contribuir de alguma forma com o estudo de vocês.` 


## Sumário

- [Introducão a Matrizes Python e NumPy](#introducão-a-matrizes-python-e-numpy)
    - [Instalando o NumPy via terminal](#instalando-o-numpy-via-terminal)
    - [Noções básicas de NumPy](#noções-básicas-de-numpy)
    - [Vantagens de usar matrizes NumPy](#vantagens-de-usar-matrizes-numpy)
    - [Como criar arrays NumPy](#como-criar-arrays-numpy)
  
 
# Introducão a Matrizes Python e NumPy

### Primeiro repositório do curso matemática para aprendizado de máquina e ciência de dados

>### VS Code Terminal
![Untitled](https://github.com/user-attachments/assets/fb5ab264-eda7-441b-b83d-3e8ce7e59dc5)

>### CMD Terminal
![CMD](https://github.com/user-attachments/assets/6ea55671-d803-41c7-9401-f0aacce0bdf9)


## Noções básicas de NumPy
NumPy é o principal pacote para computação científica em Python. Ele executa uma ampla variedade de operações matemáticas avançadas com alta eficiência. Nesta guia prática, vamos aprender várias funções importantes que irá ajudar em tarefas futuras, como criar arrays, fatiar, indexar, remodelar e empilhar.

## Importando a biblioteca

```ruby
import numpy as np
```
Aqui o "as" é usado pra encurtar o nome da biblioteca, como se fosse um apelido, ao invés de chamarmos de NumPy sempre que formos utilizar, vamos chama-lo pelo apelido "np" mais prático.
```red
import numpy as np
```
## Vantagens de usar matrizes NumPy
Os arrays são uma das estruturas de dados principais da biblioteca NumPy, essenciais para organizarmos os dados. Podemos pensar neles como uma grade de valores, todos do mesmo tipo. São semelhantes as listas do Python, você pode armazenar diferentes tipos de dados. No entanto, as listas Python são limitadas em funções e ocupam mais espaço e tempo para processar do que os arrays NumPy. 
Os array são muito mais rápido e compacto do que as listas Python. A biblioteca oferece muitas funções embutidas que tornam a computação muito mais fácil com apenas algumas linhas de código, uma grande vantagem ao realizar operações matemáticas em grandes conjuntos de dados.

_O objeto array no NumPy é chamado de ndarray, que significa ‘array n-dimensional’ (1-D)_

## Como criar arrays NumPy

Podemos criar um array 1-D simplesmente usando a função `array()`, que recebe uma lista de valores como argumento e retorna um array 1-D.
```ruby
import numpy as np

# Criando e imprimindo um array NumPy 'array_1d' contendo os elementos 1, 2, 3
array_1d = np.array([1, 2, 3])
print(array_1d)
```
`[1 2 3]`

Outra maneira de implementar um array é usando `np.arange()`. Esta função retornará um array de valores uniformemente espaçados dentro de um determinado intervalo

````ruby
import numpy as np

# Criando um array com 5 inteiros, começando do inteiro 0 padrão
array_arange = np.arange(5)
print(array_arange)
````
`[0 1 2 3 4]`

_Obs: Os números em Python começa a contagem a partir do 0, por isso a lista imprimida foi de 0 - 4_
  
Vamos criar um array começando do 1 até 20, incrementando de 3 em 3, é bem simples de intender.
* O primeiro número `(1, __, __)` indica onde a contagem de começar.
* O segundo número `(__, 20, __)` indica onde deve terminar a contagem.
* E o terceiro número `(__, __, 3)` Indica o incremento, nesse exemplo de 3 em 3.

````ruby
 import numpy as np

# Criando um array que começa do inteiro 5 e termina em 20, incrementado por 3
array_incremento = np.arange(1, 20, 3)
print(array_incremento)

````
`[ 1  4  7 10 13 16 19]`

Vamos criar uma lista com 5 números que estejam igualmente espaçados entre 0 e 100. Para fazer isso, você precisa de três informações:

* O número inicial (0).
* O número final (100).
* Quantos números você quer na lista (5).  
Vamos utilizar a função chamada `np.linspace()` que ira fazer esse processo. np.linspace(0, 100, 5), ela irá criar uma lista assim, Basicamente pega o intervalo de 0 a 100 e divide em 5 partes iguais.

````ruby
import numpy as np

# 5 inteiros uniformemente espaçados no intervalo de 0 a 100
linspaced_array = np.linspace(0, 100, 5)
print(linspaced_array)

````
`[  0.  25.  50.  75. 100.]`

 No exemplo acima a saída da função é apresentada na forma de valor float (por exemplo, 25.00)? O motivo é que o tipo padrão para valores na função NumPy `np.linspace()` é ponto flutuante `(np.float64)`. Você pode especificar facilmente seu tipo de dados usando dtype. Para alterar o tipo para inteiros, vamos definir o `dtype` como `int`

 ````ruby
 import numpy as np

# Criando um array com valores inteiros
array_inteiros = np.linspace(0, 100, 5, dtype=int)
print(array_inteiros)

````
`[  0  25  50  75 100]`

criando um array do NumPy que contém uma string: 'Bem vindo ao caderno de anotações NumPy!'. `print(array_string)` Isso vai mostrar o conteúdo do array, que é a string. `print(array_string.dtype)` Isso vai mostrar o tipo de dado dos elementos do array. No caso, será `<U40` que significa que é um array de strings Unicode com até 40 caracteres.

````ruby
import numpy as np

# Crie um array de caracteres
array_string = np.array(["Bem vindo ao caderno de anotações NumPy!"])
print(array_string)
# Imprime o tipo de dados do array
print(array_string.dtype)

````
`['Bem vindo ao caderno de anotações NumPy!']
<U40`

O NumPy facilita muito a criação de arrays com funções embutidas. Aqui estão alguns exemplos simples:
`np.ones()`: Cria um novo array onde todos os valores são 1.

````ruby
import numpy as np

array_ones = np.ones(5)
print(array_ones) 
````
`[1. 1. 1. 1. 1.]`

`np.zeros()`: Cria um novo array onde todos os valores são 0.

````ruby
import numpy as np

array_zeros = np.zeros(5)
print(array_zeros)

````
`[0. 0. 0. 0. 0.]`

`np.random.rand()`: Cria um novo array com valores escolhidos aleatoriamente entre 0 e 1.

````ruby
import numpy as np
array_random = np.random.rand(5)
print(array_random) 

````
`[0.12135531 0.68194308 0.66779118 0.65169842 0.1697461 ]`

## Arrays Multidimensionais

Com NumPy, também podemos criar arrays com mais de uma dimensão. Nos exemplos acima, lidamos com arrays 1D, onde podemos acessar os elementos usando um único índice. Um array multidimensional tem mais de uma coluna. Pense em um array multidimensional como uma planilha do Excel, onde cada linha/coluna representa uma dimensão.


