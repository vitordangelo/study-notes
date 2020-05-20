# Webpack: Manipulando módulos na sua webapp

![Logo](https://i.imgur.com/KfUFhRj.png)

- Na sua essência, o webpack é um empacotador de módulo estático para aplicativos JavaScript modernos.

- Quando o webpack processa seu aplicativo, ele cria internamente um gráfico de dependência que mapeia todos os módulos de que seu projeto precisa e gera um ou mais pacotes configuráveis.

## webpack.config.js

```js
const path = require("path");

module.exports = {
  entry: "./app-src/app.js",
  output: {
    filename: "bundle.js",
    path: path.resolve(__dirname, "dist"),
  },
};
```
