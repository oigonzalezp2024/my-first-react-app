## Guía de Aprendizaje Paso a Paso de React (Desde Cero y con Buenas Prácticas)

| Atrás | Paso Actual | Siguiente |
|:---|:---------------------------------------:|---:|
| <a href="./paso3.md">Atrás</a> | Paso 4: Explora la Estructura del Proyecto y Limpieza Inicial | <a href="./paso5.md">Siguiente</a> |

Abre la carpeta `C:\react-projects\my-first-react-app` (o el nombre de tu proyecto) en VS Code.

**Archivos y Carpetas Clave (Vite + React):**

  * **`node_modules/`**: Contiene todas las librerías que tu proyecto necesita. No necesitas modificar nada aquí.
  * **`public/`**: Archivos estáticos como `index.html` (el archivo HTML principal donde se "monta" tu aplicación React).
  * **`src/`**: **¡Aquí es donde trabajarás la mayor parte del tiempo\!** Contiene el código fuente de tu aplicación React.
      * **`main.jsx`**: Es el punto de entrada de tu aplicación React. Aquí es donde React "renderiza" tu componente principal (`App`) en el `index.html`.
      * **`App.jsx`**: Este es el componente principal de tu aplicación. Es el primer componente que se renderiza y donde empezarás a añadir tu propio código.
      * **`index.css`**: Estilos globales.
      * **`App.css`**: Estilos específicos para `App.jsx`.
      * **`assets/`**: Una carpeta para imágenes u otros recursos.
  * **`index.html`**: El archivo HTML principal de tu aplicación.
  * **`package.json`**: Contiene información sobre tu proyecto, incluyendo las dependencias y los scripts que puedes ejecutar (como `npm run dev`, `npm run build`, etc.).
  * **`vite.config.js`**: Archivo de configuración de Vite.

**Buena Práctica: Limpieza de Archivos No Necesarios de la Plantilla**

La plantilla de Vite es bastante limpia. Podemos eliminar el logo de React y el código del contador si no los vamos a usar inicialmente, para mantener el proyecto minimalista y enfocado.

1.  **Abre `src/App.jsx`**:

      * Elimina las líneas que importan `useState`, `reactLogo` y `viteLogo`.
      * Elimina los elementos `<a>` de los logos, el `div` con el botón del contador, y los párrafos relacionados con HMR y "read the docs".
      * Deja solo un `<p>` simple.

    <!-- end list -->

    ```javascript
    // src/App.jsx
    import './App.css' // Mantén la importación de estilos si los usarás

    function App() {
      return (
        <>
          <h1>¡Hola, React con Vite!</h1>
          <p>Esta es mi primera aplicación React.</p>
        </>
      )
    }

    export default App
    ```

    **Guarda `App.jsx`**. El navegador se actualizará automáticamente y verás una página más limpia.

-----
