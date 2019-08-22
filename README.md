# Documentando JavaScript con JSDoc

### Instalación global
`npm install -g jsdoc`

### Instalación en proyecto
`npm install --save-dev jsdoc`

### Uso

#### Ejemplo simple
```javascript
/**
 * Obtiene los datos del usuario
 */
const getDataUser = async (usr) => {
}
```

#### Ejemplo full
```javascript
/**
 * Obtiene los datos del usuario
 * @async
 * @method
 * @param {String} usr - Data
 * @returns {User} object
 * @throws {NotFoundError} Si no encuentra datos
 */
const getDataUser = async (usr) => {
}
```

### Generar documentación
para un archivo en particular `jsdoc foo.js`
para todos los archivos del proyecto `jsdoc -r`

### Creación de archivo de configuración
Ejemplo: *config.js*
```javascript
{
    "source": {
        "includePattern": ".+\\.js(doc|x)?$",
        "include": ["."],
        "exclude": ["node_modules"]
    },
    "recurseDepth": 7,
    "opts": {
        "destination": "./docs/",
        "recurse": true
    }
}
```
Lo podemos ejecutar desde el *package.json*
```javascript
"scripts": {
    "generate-docs": "jsdoc -c config.js"
}
```

### Resultado
```
├───out/
│   ├───fonts/
│   ├───scripts/
│   ├───styles/
│   ├───foo.js.html
│   ├───global.html
│   └───index.html
├───foo.js
└───README.md
```