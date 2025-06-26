## Guía Paso a Paso para Realizar Pruebas Lighthouse y Optimizar tu Aplicación Web

| Atrás | Paso Actual | Siguiente |
|:---|:---------------------------------------:|---:|
| <a href="../README.md">Atrás</a> | Pruebas Lighthouse y Optimizar tu Aplicación Web | <a href="./buenas_practicas.md">Siguiente</a> |

Esta guía se basa en la experiencia reciente de optimización de una aplicación Vite + React, demostrando la importancia de probar la versión de producción de tu sitio.

### Paso 1: Desarrolla tu Aplicación (Fase de Desarrollo)

Durante esta fase, te enfocas en construir la funcionalidad de tu aplicación. Estás trabajando con un servidor de desarrollo (como el que Vite ejecuta en `localhost:5173`). En esta etapa, no te preocupes demasiado por las puntuaciones de Lighthouse, ya que los servidores de desarrollo no están optimizados para rendimiento.

### Paso 2: Prepara tu Aplicación para Producción (Construcción)

Una vez que tu aplicación esté lista para ser desplegada, es crucial generar una versión optimizada para producción.

1.  **Abre tu terminal** en la raíz de tu proyecto (donde se encuentra `package.json`).

2.  **Ejecuta el comando de construcción:**
    Para la mayoría de los proyectos modernos (como React con Vite, create-react-app, Next.js, Vue CLI, etc.), el comando estándar es:

    ```bash
    npm run build
    # o si usas Yarn:
    yarn build
    # o si usas pnpm:
    pnpm build
    ```

    *Este comando ejecutará un proceso de empaquetado (bundling) que minificará tu código (JavaScript, CSS, HTML), aplicará tree-shaking (eliminación de código no utilizado), y otras optimizaciones. El resultado será una carpeta (comúnmente llamada `dist`, `build`, o `public`) que contiene todos los archivos estáticos listos para ser servidos.*

    **Verificación:** Deberías ver una salida en tu terminal similar a la que obtuvimos, indicando los archivos generados y sus tamaños (comprimidos y sin comprimir). Por ejemplo:

    ```
    dist/index.html               0.58 KiB   gzip: 0.36 KiB
    dist/assets/index-XXXX.js     188.05 KiB gzip: 59.21 KiB
    dist/assets/index-YYYY.css    1.37 KiB   gzip: 0.70 KiB
    ✓ built in 1.03s
    ```

### Paso 3: Sirve la Versión de Producción Localmente (Para Pruebas)

Para ejecutar Lighthouse de manera efectiva en tu máquina local, necesitas servir los archivos de la carpeta de producción que acabas de generar.

1.  **Instala un servidor estático local (si no lo tienes):**
    Una herramienta popular y sencilla es `serve`. Si aún no la tienes, instálala globalmente:

    ```bash
    npm install -g serve
    ```

    *Nota: Si prefieres no instalar globalmente, puedes usar `npx serve -s dist` en el Paso 3.2.*

2.  **Inicia el servidor en tu carpeta de producción:**
    Desde la raíz de tu proyecto, ejecuta:

    ```bash
    serve -s dist
    ```

    *Reemplaza `dist` por el nombre de la carpeta de salida de tu build si es diferente (ej. `build`).*

    *Este comando iniciará un pequeño servidor HTTP que pondrá a disposición los archivos de tu carpeta `dist` en una URL local (generalmente `http://localhost:3000` o `http://localhost:5000`). La opción `-s` es importante para aplicaciones de una sola página (SPA), ya que le dice al servidor que sirva `index.html` para cualquier ruta que no encuentre un archivo específico.*

3.  **Abre la URL proporcionada** por el comando `serve` en tu navegador Chrome (ej. `http://localhost:3000`).

### Paso 4: Ejecuta Lighthouse en Chrome DevTools

Ahora que tu aplicación optimizada está sirviéndose localmente, es el momento de usar Lighthouse.

1.  **Abre las Herramientas de Desarrollador de Chrome:**

      * Haz clic derecho en cualquier parte de tu página y selecciona "Inspeccionar".
      * O usa el atajo: `Ctrl + Shift + I` (Windows/Linux) o `Cmd + Option + I` (macOS).

2.  **Navega a la pestaña "Lighthouse":**

      * Si no la ves, puede que esté oculta detrás de un doble `>>` o que necesites ajustar el tamaño de tu ventana de Herramientas de Desarrollador.

3.  **Configura tu Auditoría:**

      * En la pestaña Lighthouse, asegúrate de que **"Categorías"** estén seleccionadas (Performance, Accessibility, Best Practices, SEO).
      * En **"Modo"**, selecciona "Navigation" (es el predeterminado y el más común).
      * En **"Dispositivo"**, generalmente es mejor empezar con "Mobile" (Móvil), ya que es más estricto y a menudo las optimizaciones para móvil también benefician al escritorio.

4.  **Genera el Reporte:**

      * Haz clic en el botón **"Analyze page load"** (o "Generate report").
      * Lighthouse tomará un momento para auditar tu página.

### Paso 5: Analiza los Resultados y Optimiza

Una vez generado el reporte, revisa las diferentes secciones:

1.  **Puntuaciones Globales:** Observa las puntuaciones para Performance, Accessibility, Best Practices y SEO. **Un 100 en todas ellas (como lograste) es el objetivo.**

      * Si tu puntuación de Performance es baja, eso indica áreas de mejora en la velocidad de carga y la interactividad.

2.  **Métricas Clave:** Lighthouse te mostrará las Core Web Vitals (LCP, CLS, TBT) y otras métricas importantes con sus valores.

3.  **Oportunidades (Opportunities):** Esta sección te dará sugerencias específicas para mejorar el rendimiento. Ejemplos comunes incluyen:

      * "Serve images in next-gen formats"
      * "Enable text compression"
      * "Eliminate render-blocking resources"
      * "Reduce initial server response time"

4.  **Diagnósticos (Diagnostics):** Esta sección proporciona información más detallada sobre cómo tu aplicación se está ejecutando, incluyendo:

      * "Minify JavaScript/CSS" (si no los has minimizado aún)
      * "Reduce unused JavaScript/CSS" (si tienes mucho código muerto o sin usar)
      * "Avoid long main-thread tasks"
      * "Avoid chaining critical requests"

5.  **Auditorías Pasadas:** Muestra las auditorías que tu sitio ya cumple.

### Paso 6: Iterar y Mejorar

  * **Identifica las áreas de mayor impacto:** Concéntrate primero en las oportunidades que ofrecen los mayores ahorros (`Est savings of X KiB` o `Est savings of X s`).
  * **Implementa los cambios:** Basado en las recomendaciones, modifica tu código, tus assets o tu configuración de servidor.
  * **Repite el proceso:** Vuelve al **Paso 2 (Construir)**, luego al **Paso 3 (Servir)** y finalmente al **Paso 4 (Ejecutar Lighthouse)** para ver cómo tus cambios han impactado las puntuaciones.

**Consejo Adicional:**

  * **No te obsesiones con el 100 perfecto** si tu aplicación es muy compleja o depende de muchos scripts de terceros. Apunta a una puntuación alta (90+ en Performance) que garantice una buena experiencia de usuario.
  * **Considera el entorno de despliegue real:** Si tu sitio está en un servidor de producción real (no `localhost`), haz las pruebas de Lighthouse directamente en la URL pública.
  * **Herramientas de despliegue:** Servicios como Netlify, Vercel, o Firebase Hosting suelen aplicar muchas optimizaciones automáticamente y facilitan el despliegue de las versiones de producción.
