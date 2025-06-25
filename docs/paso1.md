## Guía de Aprendizaje Paso a Paso de React (Desde Cero y con Buenas Prácticas)

| Atrás | Paso Actual | Siguiente |
|:---|:---------------------------------------:|---:|
| <a href="../README.md">Atrás</a> | Paso 1: Instalar Node.js y npm (usando nvm) | <a href="./paso2.md">Siguiente</a> |

React se construye con JavaScript y utiliza herramientas que se ejecutan en Node.js. **`npm`** (Node Package Manager) es la herramienta que usaremos para instalar librerías.

**Buena Práctica Recomendada:** Usa **`nvm` (Node Version Manager)**. Te permite instalar y gestionar múltiples versiones de Node.js en tu sistema, lo cual es muy útil si trabajas en diferentes proyectos.

1.  **Desinstala cualquier versión previa de Node.js:** Si ya tienes Node.js instalado, lo mejor es desinstalarlo para evitar conflictos con `nvm`. Puedes hacerlo desde el "Panel de control" \> "Programas y características" en Windows.

2.  **Instala `nvm`:**

      * **Para Windows:** Ve a la página de lanzamientos de `nvm-windows` en GitHub: [https://github.com/coreybutler/nvm-windows/releases](https://github.com/coreybutler/nvm-windows/releases). Descarga el archivo `nvm-setup.zip` de la última versión disponible (la 1.2.2 es la que tienes y funciona bien) y ejecuta el instalador. Sigue las instrucciones.
      * **Para macOS/Linux:** Abre tu terminal y ejecuta el siguiente comando:
        ```bash
        curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
        ```
        Después de la instalación, reinicia tu terminal o ejecuta `source ~/.bashrc` (o `~/.zshrc` si usas Zsh) para que `nvm` esté disponible.

3.  **Verifica la instalación de `nvm`:**

    ```bash
    nvm --version
    ```

    Deberías ver el número de versión de `nvm` (como `1.2.2` en tu caso).

4.  **Instala la última versión estable (LTS) de Node.js con `nvm`:**

    ```bash
    nvm install --lts
    ```

    El parámetro `--lts` (Long Term Support) te instala la última versión estable y recomendada de Node.js, lo cual es una **buena práctica** para la mayoría de los proyectos. Según tu log, esta fue la `22.17.0`.

5.  **¡IMPORTANTE\! Activa la versión de Node.js que acabas de instalar:**
    Este es el paso crucial que resuelve el error de `npm` no reconocido. Le estás diciendo a tu sistema que "use" esta versión de Node.js.

    ```bash
    nvm use 22.17.0
    ```

    Asegúrate de usar el número de versión exacto que `nvm install --lts` te mostró.

6.  **Verifica que Node.js y npm estén ahora disponibles:**

    ```bash
    node -v
    npm -v
    ```

    Ahora deberías ver los números de versión de Node.js (`v22.17.0` o similar) y npm, confirmando que el sistema los reconoce correctamente.

-----
