# Webpack con Jon Mircha

### Introduccion
    Aqui estaran los apuntes sobre lo aprendido mediante el curso
<br><br><br>

## hay 4 conceptos muy importantes
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
