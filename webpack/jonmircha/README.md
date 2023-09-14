# Webpack con Jon Mircha

### Introduccion
    Aqui estaran los apuntes sobre lo aprendido mediante el curso
<br><br><br>

## Hay 4 conceptos muy importantes
- Entry, puntos de entrada.
- Output, archivos de salida.
- Loaders, nos permiten compilar distintos lenguajes.
- Plugins, realizan acciones en concreto.

### Comenzando a codear
Para empezar con la parte practica, lo primero que hacemos es iniciar un projecto de node con el comando "npm init". Luego instalamos webpack y webpack-cli como dependencias de desarroyo con el comando "npm i -D webpack webpack-cli". 
<br><br>
Luego agregamos el script "build" en el archivo "pakage.js" y lo seteamos en "webpack", y en "main" lo seteamos a "src/index.js".
A esta altura al ejecutar el comando "npm run build" nos daria un punto de salida que seria dist/main.js

## Modos de Webpack
Los modos hacen referencia al ambiente para el que va a empaquetar, si va a ser de produccion o desarroyo.
<br>
modificamos el archivo package.json para que en la parte de script quede de la siguiente manera
```
"scripts": {
    "dev": "webpack --mode development",
    "build": "webpack --mode production"
  },
```
mediante otras flags tambien se puede configurar aspectos como porejemplo elegir los Entry o los Ouput, etc.
<br>

## Loaders
<b>Explicación sencilla :</b><br>
Los “loaders” son herramientas que transforman y preprocesan archivos de diferentes tipos antes de ser usados en tu proyecto. Funcionan como “tasks” que se ejecutan al importar o “cargar” archivos. Permiten convertir archivos de un lenguaje a otro (por ejemplo, de TypeScript a JavaScript), cargar imágenes como enlaces de datos y hasta importar archivos CSS desde módulos de JavaScript. Son útiles para organizar y procesar los recursos en proyectos de desarrollo front-end.

<a href="https://webpack.js.org/loaders/" target="blank">de Documentación oficial : https://webpack.js.org/loaders/</a>
<br>
<br>
<br>
# Babel
Babel es un "compilador" (o transpilador) para JavaScript. Básicamente permite transformar código escrito con las últimas y novedosas características de JavaScript y transformarlo en un código que sea entendido por navegadores más antiguos.
<br><br><br>
instalamos babel como dependencias de desarrollo con el siguiente comando
```
npm install -D babel-loader @babel/core @babel/preset-env
```

Ahora creamos un archivo llamado "babelrc" en la carpeta "src" de nuestro proyecto, y le ponemos lo siguiente
```
{
    "presets": ["@babel/preset-env"]
}
```

Luego creamos el archivo "webpack.config.js" en la raiz
y en su interior colocamos la siguiente configuracion:
```
module.exports = {
    module : {
        rules : [{
            test: /\.js$/i,
            exclude: /node_modules/,
            use: {
                loader: 'babel-loader',
                options: {
                  presets: [
                    ['@babel/preset-env', { targets: "defaults" }]
                  ]
                }
              }
        }]
    }
}
```