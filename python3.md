---
title: Python 3
published: false
description:
tags:
---

![Python Logo](https://i.imgur.com/AnQzJUL.png)

#### Acessa a documentação da linguagem

```python
help()
```

#### Print

```python
print()
```

#### Declarar uma variável

```python
variavel = valor
```

#### Obter o tipo da variável

```python
type(variavel)
```

- Python tem tipagem dinâmica, ou seja, não é necessário definir o tipo de uma variável.

#### Função de entrada de dados

```python
nome = input("Qual o seu nome?")
```

#### Condição if e else

```python
if (numero_secreto == chute):
  print("Você acertou!")
else:
  print("Você errou!")
```

- Se atentar pelo espaço (tab) dentro da condição e dos : (dois pontos) no final.

#### Converter string pra int

```python
chute_str = input("Digite o seu número: ")
print("Você digitou: ", chute_str)
chute = int(chute_str)
```

#### While

```python
n = 5
while n > 0:
  n -= 1
  print(n)

```

#### Interpolação de Strings

[Mais informações na documentação oficial](https://docs.python.org/3/library/string.html#formatexamples)

```python
print("Tentativa {} de {}".format(rodada, total_de_tentativas))

```

#### For

```python
for rodada in range(1,10):
  print(rodada)
```

#### Built-in Functions

São funções que não precissam ser importadas.
[Lista de funções](https://docs.python.org/3/library/functions.html)
