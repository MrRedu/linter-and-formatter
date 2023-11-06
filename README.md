# Linter / Formatter

### Linter

Herramienta que ayuda a detectar y corregir errores de código.

### Formatter

Herramienta que ayuda a dar formato y estructura al código de manera consistente y legible.

```js
const a = 5;     // <- El linter informa que la variable está declarada, pero no se utiliza en ninguna parte.
const a=      5; // <- El formatter agrega/borra espacios donde sea necesario, según las reglas establecidas.
```

### ¿Por qué deberían utilizarse?

Sea que trabajes en diferentes computadores o tengas más compañeros en el equipo de desarrollo, cada persona y sistema tiene una configuración distinta de cómo se escribirá el código. Estableciendo estas configuraciones por proyecto, dará como resultado que todo el código terminará siendo escrito con un mismo estilo basado en las mismas reglas. En caso contrario, se podrían crear commits fantasmas _(básicamente commits donde lo único que habrá cambiado es un espacio, un punto y coma, unos paréntesis, etc)_ y un millón de variantes del cómo se escribe código.

### Instalación manual de ESLint

_Es necesario tener instalada la extensión de [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)_

```bash
npm init @eslint/config

> To check syntax, find problems, and enforce code style
> JavaScript modules (import/export)
> React
> TypeScript? (No / Yes)
> Browser and/or Node
> Use a popular style guide
> Standard
> JSON
> pnpm / npm / yarn
```

[Archivo por defecto de la instalación anterior _(con algunas reglas agregadas)_](./configs/.eslintrc.json)

### Instalación manual de Prettier

_Es necesario tener instalada la extensión de [Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)_

```bash
npm i -D -E prettier
or
pnpm i -D -E prettier
```

[Agregar archivo para establecer reglas de Prettier](./configs/.prettierrc)

- Para que se formatee el archivo al guardar, es necesario ir a Settings de VSCode `(Ctrl + ,)`, y activar la regla que lleva por nombre: _"Editor: Format On Save"_
- [Recomendable: Agregar archivo .prettierrcignore](./configs/.prettierignore)

### Colisión/conflictos entre ESLint y Prettier

En caso que tengamos reglas de ESLint que estén ocasionando conflictos a reglas de Prettier (como podría ser el utlizar `;` o no), podemos instalar el paquete `eslint-config-prettier`, para así darle prioridad a Prettier en lo que le corresponde:

```bash
npm i -D -E eslint-config-prettier
or
pnpm i -D -E eslint-config-prettier
```

Y en el archivo [.eslintrc.json](./configs/.eslintrc.json), agregar:

```json
"extends": [
    "...",
    "eslint-config-prettier"
],
```

### [Agregar comandos en el package.json](./configs/package.json)

**¿Por qué deberíamos agregar comandos cuando el formateo/visualización de errores se realizan automáticamente con las extensiones?** <br>
Básicamente por esa misma razón, podrían haber personas sin las extensiones/configuraciones, por lo que siempre hay que dar una opción extra para realizar estas acciones desde el terminal. Además que se necesitaran para automatizaciones, despliegues, etc.

```json
"scripts": {
    "format": "prettier --write .",
    "lint": "eslint . --ext .js,.jsx,.ts,.tsx --report-unused-disable-directives --max-warnings 0"
},
```
