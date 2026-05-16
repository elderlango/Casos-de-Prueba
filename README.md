# Swapiio - Pruebas E2E con Cucumber

![WebdriverIO](https://img.shields.io/badge/WebdriverIO-8.x-8B5CF6?logo=webdriverio&logoColor=white)
![Cucumber](https://img.shields.io/badge/Cucumber-BDD-23D96C?logo=cucumber&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-Required-339933?logo=node.js&logoColor=white)
![Chrome](https://img.shields.io/badge/Browser-Chrome-4285F4?logo=googlechrome&logoColor=white)

Suite de pruebas automatizadas end-to-end para la plataforma **Swapiio**, desarrollada con el patrón Page Object Model y escrita en Gherkin (BDD) mediante Cucumber.

---

## Descripcion

Este proyecto contiene 15 casos de prueba automatizados que validan las funcionalidades principales de la aplicacion web [Swapiio](https://swapiio.netlify.app), incluyendo autenticacion, gestion de productos, mensajeria y navegacion. Las pruebas estan escritas en formato BDD con Cucumber, facilitando la lectura y colaboracion entre perfiles tecnicos y no tecnicos.

---

## Casos de Prueba

| CP | Funcionalidad | Descripcion |
|----|---------------|-------------|
| 1-4 | Registro | Registro de usuarios con datos validos e invalidos |
| 5-6 | Inicio de sesion | Login con credenciales validas e invalidas |
| 7 | Pagina extrana | Navegacion a pagina de contenido especial |
| 8, 12 | Crear producto | Alta de productos con datos e imagen |
| 9 | Eliminar producto | Eliminacion de productos existentes |
| 10 | Editar producto | Modificacion de datos de un producto |
| 11 | Clonar producto | Duplicacion de un producto existente |
| 13 | Mensajeria | Envio de mensajes dentro de la plataforma |
| 14 | Ordenar contenido | Ordenamiento de elementos en la vista |
| 15 | Buscar contenido | Busqueda de articulos por texto |

---

## Tecnologias

- **WebdriverIO 8** - Framework de automatizacion de pruebas E2E
- **Cucumber** - Framework BDD con sintaxis Gherkin
- **TypeScript 5** - Lenguaje de programacion tipado
- **Page Object Model** - Patron de diseno para mantenibilidad
- **Chrome** - Navegador de ejecucion

---

## Estructura del Proyecto

```
.
├── features/
│   ├── signIn.feature              # Archivo Gherkin con los 15 escenarios
│   ├── pageobjects/
│   │   ├── page.ts                 # Clase base (URL comun)
│   │   ├── login.page.ts           # CP 5-6: Inicio de sesion
│   │   ├── signIn.page.ts          # CP 1-4: Registro
│   │   ├── producto.page.ts        # CP 8, 12: Crear producto
│   │   ├── CP_7.page.ts            # CP 7: Pagina extrana
│   │   ├── CP_9.page.ts            # CP 9: Eliminar producto
│   │   ├── CP_10.page.ts           # CP 10: Editar producto
│   │   ├── CP_11.page.ts           # CP 11: Clonar producto
│   │   ├── CP_13.page.ts           # CP 13: Mensajeria
│   │   ├── CP_14.page.ts           # CP 14: Ordenar contenido
│   │   └── CP_15.page.ts           # CP 15: Buscar contenido
│   └── step-definitions/
│       ├── CP_1_2_3_4.ts           # Steps: Registro
│       ├── CP_5_6.ts               # Steps: Login
│       ├── CP_7.ts                 # Steps: Pagina extrana
│       ├── CP_8_12.ts              # Steps: Crear producto
│       ├── CP_9.ts                 # Steps: Eliminar producto
│       ├── CP_10.ts                # Steps: Editar producto
│       ├── CP_11.ts                # Steps: Clonar producto
│       ├── CP_13.ts                # Steps: Mensajeria
│       ├── CP_14.ts                # Steps: Ordenar contenido
│       └── CP_15.ts                # Steps: Buscar contenido
├── wdio.conf.ts                    # Configuracion de WebdriverIO
├── tsconfig.json                   # Configuracion de TypeScript
└── package.json                    # Dependencias y scripts
```

---

## Instalacion

1. **Clonar el repositorio**

   ```bash
   git clone <url-del-repositorio>
   cd webdriver_io
   ```

2. **Instalar dependencias**

   ```bash
   npm install
   ```

3. **Requisitos previos**
   - Node.js 16 o superior
   - Google Chrome instalado
   - ChromeDriver compatible (WebdriverIO lo gestiona automaticamente)

---

## Ejecucion

### Ejecutar todos los casos de prueba

```bash
npm run wdio
```

### Ejecutar un caso especifico

Editar el archivo `wdio.conf.ts` y descomentar la linea del caso deseado en `cucumberOpts.require`:

```ts
require: [
    './features/step-definitions/CP_1_2_3_4.ts',  // Registro
    // './features/step-definitions/CP_5_6.ts',   // Login
    // ...
],
```

Luego ejecutar:

```bash
npm run wdio
```

> **Nota:** Por defecto solo el CP 15 esta habilitado en la configuracion. Descomenta los casos que necesites ejecutar.

---

## Posibles Mejoras

- Migrar selectores XPath a selectores CSS o data-testid para mayor robustez
- Agregar reportes HTML con `@wdio/allure-reporter`
- Implementar hooks de Cucumber para setup/teardown comun (login previo)
- Parametrizar la URL base y credenciales en variables de entorno
- Agregar validaciones de errores en escenarios negativos (CP 2-4, CP 6)
- Ejecutar en paralelo con multiples navegadores (cross-browser)
- Integrar con CI/CD (GitHub Actions)

---

## Creditos

Proyecto colaborativo universitario desarrollado como parte de la materia de Pruebas de Software.

---

## Licencia

ISC
