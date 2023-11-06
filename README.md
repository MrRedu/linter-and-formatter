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

Sea que trabajes en diferentes computadores o tengas más compañeros en el equipo de desarrollo, cada persona y sistema tiene una configuración distinta de cómo se escribirá el código. Estableciendo estas configuraciones por proyecto, dará como resultado que todo el código terminará siendo escrito con un mismo estilo basado en las mismas reglas. En caso contrario, se podrían crear commits fantasmas _(básicamente commits donde lo único que habrá cambiado es un espacio, un punto y coma, etc)_.

### Instalación manual de Eslint
_Es necesario tener instalada la extensión de [Eslint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)_

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

[Archivo por defecto de la instalación anterior, con reglas agregadas](./configs/.eslintrc.json)
