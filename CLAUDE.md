# Clases Codilab

Material de las clases de programación que da el usuario en Codilab. Cada clase es un `.mdx` que se ve en `index.html` (lo lee de `manifest.json` y lo renderiza con marked + highlight.js).

## Estructura

```
clases codilab/
├── index.html        visor de las clases (sidebar por curso)
├── manifest.json     lista de cursos y clases: { nombre, carpeta, clases: [{ titulo, archivo }] }
├── ejemplo.mdx       plantilla base de una clase
├── roblox/           curso de Roblox (Luau) — clase1.mdx ... clase27.mdx
├── scratch/          curso de Scratch — clase1.mdx ... clase29.mdx (NO son borradores)
├── python/           curso de Python
└── desarrollo/       curso de Desarrollo Web
```

Proyectos fuera de esta carpeta, en `Escritorio\codilab\`:
- Roblox: `claseNN.rbxlx` (ej. `clase28.rbxlx`)
- Python: `python clases\`
- Web: `desarrollo clases\claseNN\`

Si se agrega una clase nueva, hay que sumarla también a `manifest.json` o no aparece en el visor.

## El trabajo acordado (2026-10-19)

Revisar y mejorar **todas las clases, desde la 1 hasta la última, de a una y paso a paso**, con su proyecto y con capturas. **No arrancar hasta que el usuario lo diga.** Cuando arranquemos, trabajar una sola clase por vez y mostrarle el resultado antes de pasar a la siguiente.

Para cada clase:
1. Leer el `.mdx` actual y el proyecto, si existe
2. Corregir errores y explicaciones confusas. Completar los pasos que falten para que un alumno pueda seguirlos sin ayuda
3. Armar o verificar el proyecto de la clase
4. Agregar capturas (y videos o GIF donde ayuden)
5. Actualizar `manifest.json` si cambia el título o se agrega la clase

### Referencia de calidad: Clase 28 de Roblox

La Clase 28 (Tablas de Puntos / Leaderboards) es el modelo a seguir. Por ahora existe como `Escritorio\Clase 28 - Tablas de Puntos.pdf` y `codilab\clase28.rbxlx`; **todavía falta pasarla a `roblox/clase28.mdx` y sumarla al manifest**. La clase tiene 4 piezas: la carpeta `Monedas` en Workspace, el `BloqueMuerte` (para probar las muertes) y los scripts `Leaderboard` y `Monedas` en ServerScriptService. Extra opcional: la columna Rango.

## Formato de cada clase

Igual que `roblox/clase27.mdx` y la Clase 28:

- Frontmatter con `title` y `mision`, después `# Título` y una descripción corta
- `## Objetivos` → `## Contenido` con secciones numeradas (`### 1.`, `### 2.`…) agrupadas en Partes con emoji (`### 🏆 Parte 1: ...`)
- Pasos numerados y concretos: "Click derecho en **ServerScriptService** → Insert Object → **Script**", "Lo renombrás `Leaderboard`"
- Tablas de propiedades (Propiedad | Valor | Para qué sirve)
- Árbol del Explorer en bloque de texto (`├──`, `└──`)
- Código comentado línea por línea, en español **sin tildes dentro del código**, y debajo viñetas que explican las partes clave
- Notas con `> 💡` (tip) y `> ⚠️` (error común)
- Referencias a clases anteriores ("Como en la Clase 7…")
- Cierre: "Probar todo", "Estructura final en el Explorer", "Problemas comunes" (Problema | Causa | Solución), "Extras", `## Ejercicio` (consigna + pistas) y `## Recursos` (links a la documentación oficial)
- Español rioplatense con voseo ("le das Play", "tocás", "apretá")
- Studio del usuario está **en español**: incluir los nombres de los menús en español ("Insertar → Insertar objeto…", "Servidor y clientes") junto a los nombres en inglés

## Capturas y videos

- Las capturas van en `<curso>/img/claseNN/` con nombres numerados y descriptivos: `01-insertar-script.png`, `02-propiedades-moneda.png`
- En el `.mdx` se referencian **relativas a `index.html`**, no al `.mdx`: `![Descripción](roblox/img/clase28/01-insertar-script.png)`. Debajo va una línea en cursiva que explica qué mirar
- Estilo: recortadas a la zona que importa y con **cuadros rojos** marcando dónde hacer click o qué propiedad cambiar (como en el PDF de la Clase 28)
- Videos o GIF cortos solo donde ayuden a ver un movimiento (por ejemplo, tocar una moneda y ver cómo suben los puntos). Se guardan en `<curso>/img/claseNN/` como `.mp4` o `.gif`
- Grabar la pantalla: ffmpeg con `gdigrab` está en `C:\Users\Agust\AppData\Local\Programs\Python\Python313\Lib\site-packages\imageio_ffmpeg\binaries\ffmpeg-win-x86_64-v7.1.exe` (no está en el PATH). Puede capturar la pantalla entera o una sola ventana por título
- **Claude no puede hacer clicks en Roblox Studio** (solo puede controlar Chrome). En Studio se trabaja así: Claude arranca la captura, el usuario hace los pasos y avisa, y Claude recorta, marca y exporta
