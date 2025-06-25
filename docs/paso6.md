## Guía de Aprendizaje Paso a Paso de React (Desde Cero y con Buenas Prácticas)

| Atrás | Paso Actual | Siguiente |
|:---|:---------------------------------------:|---:|
| <a href="./paso5.md">Atrás</a> | Paso 6: Primer Componente Nuevo (Modular y Reutilizable con Props) | <a href="./paso7.md">Siguiente</a> |


Vamos a crear un componente `Saludo` que reciba un nombre como propiedad, haciéndolo flexible y reutilizable.

1.  Dentro de la carpeta `src`, crea una nueva carpeta llamada `components`. Esto es una **buena práctica** para organizar todos tus componentes personalizados y mantener la carpeta `src` ordenada.

2.  Dentro de `src/components`, crea un nuevo archivo llamado `Saludo.jsx`.

3.  Abre `src/components/Saludo.jsx` y pega el siguiente código:

    ```javascript
    // src/components/Saludo.jsx
    import React from 'react'; // Necesario para que JSX funcione correctamente

    // Buena Práctica: Usa destructuring para las props ({ nombre })
    function Saludo({ nombre }) {
      return (
        <div>
          <h2>¡Hola, {nombre}!</h2> {/* Accedemos a la propiedad 'nombre' directamente */}
          <p>Desde Cúcuta, Colombia, aprendiendo React con las mejores prácticas.</p>
        </div>
      );
    }

    export default Saludo; // Exporta el componente para que pueda ser importado en otros archivos
    ```

    **Buenas Prácticas Aplicadas:**

      * Los nombres de los componentes (`Saludo`) siempre empiezan con **mayúscula** (PascalCase).
      * Usamos **`props`** para hacer el componente **reutilizable** y para pasar datos de un componente padre a un componente hijo.
      * Las `props` son **inmutables**: un componente hijo nunca debe intentar modificar sus props.
      * Usamos **destructuring** (`{ nombre }`) en los parámetros de la función para acceder a las props de forma más limpia y directa.

-----
