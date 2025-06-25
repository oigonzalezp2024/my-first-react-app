## Guía de Aprendizaje Paso a Paso de React (Desde Cero y con Buenas Prácticas)

| Atrás | Paso Actual | Siguiente |
|:---|:---------------------------------------:|---:|
| <a href="./paso2.md">Atrás</a> | Paso 3: Crear tu Proyecto React (La Manera Moderna y Recomendada: Vite) | <a href="./paso4.md">Siguiente</a> |


Aunque `create-react-app` ha sido popular, la **buena práctica** y la recomendación actual de la comunidad de React para nuevos proyectos es usar **Vite** o Next.js. Son más rápidos, ofrecen una mejor experiencia de desarrollo y están más optimizados.

Para esta guía, usaremos **Vite**, ya que es excelente para empezar y muy rápido.

1.  **Abre tu Terminal (PowerShell):** Navega a la carpeta donde quieres crear tu proyecto (por ejemplo, `C:\react-projects`).

    ```bash
    cd C:\react-projects
    ```

2.  **Crea un nuevo proyecto React con Vite:**

    ```bash
    npm create vite@latest
    ```

    **¡Importante\! Primera vez que usas `npm create vite`:** Es posible que veas un mensaje preguntando si deseas instalar `create-vite`.

    ```bash
    Need to install the following packages:
    create-vite@7.0.0
    Ok to proceed? (y)
    ```

    Si esto aparece, simplemente escribe `y` (de "yes") y presiona **Enter**. Es normal; `npm` necesita descargar esta herramienta auxiliar para poder crear el proyecto.

    Luego, Vite te hará algunas preguntas:

      * **`project name` (nombre del proyecto):** Escribe `my-first-react-app` (o el nombre que quieras, ¡en minúsculas y sin espacios\!). Presiona Enter.
      * **`Select a framework` (Selecciona un framework):** Usa las flechas para seleccionar `React`. Presiona Enter.
      * **`Select a variant` (Selecciona una variante):** Usa las flechas para seleccionar `JavaScript`. Presiona Enter.

    Vite creará la estructura básica del proyecto en una nueva carpeta con el nombre que le diste.

3.  **Navega a la carpeta de tu nuevo proyecto:**

    ```bash
    cd my-first-react-app
    ```

    (Reemplaza `my-first-react-app` con el nombre que le diste a tu proyecto).

4.  **Instala las dependencias del proyecto:**

    ```bash
    npm install
    ```

    Esto descargará todas las librerías necesarias para que tu aplicación funcione.

5.  **Inicia el servidor de desarrollo:**

    ```bash
    npm run dev
    ```

    Vite te dará una dirección local (por ejemplo, `http://localhost:5173/`). Abre esta dirección en tu navegador. ¡Verás la plantilla básica de Vite + React\!

-----
