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

#### Função

```python
def nome_da_funcao():
  # todo o código identado faz parte da função
  print("aprendendo funções")
```

#### Executar arquivo Python diretamente

- Executa o arquivo (pelo terminal) sem a necessidade de importar como um módulo.

```python
if (__name__ == "__main__"):
  chamFuncao()
```

#### Operadores lógico

- E (&&): _and_
- Negação (!): _not_
- Verdadeiro: _True_
- Falso: _false_

> Valores vazios ou zeros são considerado False, do contrário são considerados True.

- **Tupla** é uma lista imutável.
- **tuple()** converte uma lista em tupla.
- **list()** converte uma tupla em lista.
- Um set é uma coleção não ordenada de elementos. Cada elemento é único, isso significa que não existem elementos duplicados dentro do set.
- Dictionary é uma lista que nos "lembra um json".

#### List Comprehension

```python
palavra_secreta = "banana".upper()
letras_acertadas = ["_" for letra in palavra_secreta]
```

```python
inteiros = [1,3,4,5,7,8,9]
pares = [x for x in inteiros if x % 2 == 0]
```

#### Manipulação de arquivos

```python
arquivo = open("palavras.txt", "w")
arquivo.write("Vitor", "w")
arquivo.write("Vitor", "a")
arquivo.close()

logo = open('python-logo.png', 'rb')
data = logo.read()
```

- Além do **r, w e a** existe o modificador b que devemos utilizar quando queremos trabalhar no modo binário.

```python
with open("palavras.txt") as arquivo:
  for linha in arquivo:
    print(linha)
```

- Nesta abortagem de manipulação de arquivo não temos que nos preocupar em fechar o fluxo de controle.

> Há uma convenção que o nome de funções e de variáveis, usamos o padrão snake_case: imprime_mensagem()

#### Parâmetro opcional

```python
def carrega_palavra_secreta(nome_arquivo="palavras.txt"):
  arquivo = open(nome_arquivo, "r")
```

#### Constructor

```python
def __init__(self):
```

#### Classe

```python
class Conta:
  def __init__(self, numero, titular, saldo, limite):
    print("Construindo objeto...{}".format(self))
    self.numero = numero
    self.titular = titular
    self.saldo = saldo
    self.limite = limite

    def extrato(self):
      print("Saldo {} do titular {}".format(self.saldo, self.titular))

    def saca(self, valor):
      self.saldo -= valor

    def deposita(self, valor):
      self.saldo += valor
```

> Para definir um atributo como privado, adicionamos dois caracteres underscore (\_\_) antes do nome do atributo. <br>
> O Python **avisa** que o atributo foi criado para ser usado dentro da classe, por meio dos métodos. Porém, continuaremos a ter acesso aos valores.

```python
class Conta:

  def __init__(self, numero, titular, saldo, limite):
    print("Construindo objeto ... {}".format(self))
    self.__numero = numero
    self.__titular = titular
    self.__saldo = saldo
    self.__limite = limite
```

> Coesão é ligado ao principio de responsabilidade única. Uma classe deve ter apenas uma responsabilidade (ou deve ter apenas uma razão para existir), ela não deve assumir responsabilidades que não são delas.

#### @property

Métodos que dão acesso, nomeado de property.

```python
@property
  def nome(self):
    return self.__nome.title()
```

#### setter

Método que atribuem um atributo

```python
@nome.setter
def nome(self, nome):
  print("chamando setter nome()")
  self.__nome = nome
```

#### @staticmethod

- São métodos que podemos chamar sem ter nenhuma referência (sem ter criado um objeto)

```python
@staticmethod
def codigo_banco():
  return "001"

Conta.codigo_banco()
```

# PIP

## Listar pacotes instalados

```shell
pip list
```

## Instala pacotes de uma lista de dependências

```shell
pip install -r requirements.txt
```

## [Exportar pacotes de dependência](https://pip.pypa.io/en/stable/reference/pip_freeze/)

```sh
pip freeze > requeriments.txt
```

# [Ambiente virtual](https://docs.python.org/3/library/venv.html)

Requer a instalação do **python3-venv** apt-get install python3-venv.

```sh
apt-get install python3-venv
```

Criar ambiente:

```sh
python3 -m venv .venv
```
