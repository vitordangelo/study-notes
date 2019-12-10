# Notas de estudo sobre Alexa Skills

![Alexa](./images/alexa.png)

- Plataforma para criação de skills:
  [Alexa Developer](https://developer.amazon.com/alexa)

- É possível utilizar ambientes fora da AWS, basta ter os endpoits bem definidos.

## Skill Invocation Name

Configuração de qual sintaxe iremos chamar a assistente.

## LaunchRequestHandler

Classe utilizada para que a Alexa identifique qual "função" ela irá executar (iniciar uma interação).

## Ambiente

Atualmente podemos usar Python e NodeJS para desenvolver skills.

## Intents

Uma intenção representa uma ação que atende à solicitação falada de um usuário

## Slots

Conjunto de palavras pré definidas que se relacionam ao pedido de interação.

- Já existem algumas intents por padrão
- A intent define as perguntas que a disparam (utterance)
- Na definição da intent, devemos definir o slot
  - Um slot é uma variável que define alguns valores que precisam extrair da frase
  - Um slot possui um nome e tem um ou mais valores associados
  - Os valores podem ter sinônimos
  - Um slot pode ser obrigatório
  - Existem vários tipos de slots já pré-definidos
- Uma intent possui uma classe IntentHandler associada
  - No Handler, pegamos o valor do slot e buscamos informações
