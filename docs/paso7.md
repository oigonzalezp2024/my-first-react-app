## Guía de Aprendizaje Paso a Paso de React (Desde Cero y con Buenas Prácticas)

| Atrás | Paso Actual | Siguiente |
|:---|:---------------------------------------:|---:|
| <a href="./paso6.md">Atrás</a> | Paso 7: Usa tu Nuevo Componente en `App.jsx` | <a href="../README.md">Siguiente</a> |

Ahora que tienes tu componente `Saludo`, vamos a añadirlo a tu componente principal `App.jsx`.

1.  Abre `src/App.jsx`.

2.  En la parte superior del archivo, **importa** tu nuevo componente:

    ```javascript
    import Saludo from './components/Saludo'; // ¡La ruta es importante y refleja la organización de carpetas!
    ```

    **Buena Práctica:** Las rutas de importación deben ser claras y reflejar la estructura de tu proyecto, haciendo que sea fácil encontrar los archivos.

3.  Dentro del `return` de la función `App`, añade tu componente `Saludo` como una etiqueta HTML, pasándole la propiedad `nombre`:

    ```javascript
    // src/App.jsx
    import './App.css';
    import Saludo from './components/Saludo'; // Importa el componente Saludo

    function App() {
      return (
        <>
          <h1>¡Hola, React con Vite!</h1>
          <p>Esta es mi primera aplicación React.</p>

          {/* Usamos el componente Saludo y le pasamos una 'prop' llamada 'nombre' */}
          <Saludo nombre="Oscar" />
          <Saludo nombre="Amigo Desarrollador" /> {/* Podemos reutilizarlo con diferentes datos */}
        </>
      )
    }

    export default App
    ```

4.  **Guarda `App.jsx`**.

Vuelve a tu navegador. Ahora deberías ver los dos mensajes de saludo, uno con tu nombre y otro con "Amigo Desarrollador". ¡Has creado y usado tu primer componente personalizado y reutilizable con props\!

-----