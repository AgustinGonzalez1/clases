# Clases Codilab

Material de las clases de programación que da el usuario en Codilab. Cada clase es un `.mdx` que se ve en `index.html` (lo lee de `manifest.json` y lo renderiza con marked + highlight.js).

## Estructura

```
clases codilab/
├── index.html        visor de las clases (sidebar por curso)
├── manifest.json     lista de cursos y clases: { nombre, carpeta, clases: [{ titulo, archivo }] }
├── ejemplo.mdx       plantilla base de una clase
├── roblox/           curso de Roblox (Luau) — clase1.mdx ... clase30.mdx
├── scratch/          curso de Scratch — clase1.mdx ... clase29.mdx (NO son borradores)
├── python/           curso de Python
└── desarrollo/       curso de Desarrollo Web
```

Proyectos fuera de esta carpeta, en `Escritorio\codilab\`:
- Roblox: `claseNN.rbxlx` (ej. `clase28.rbxlx`)
- Python: `python clases\`
- Web: `desarrollo clases\claseNN\`

Si se agrega una clase nueva, hay que sumarla también a `manifest.json` o no aparece en el visor.

## El trabajo acordado

**Desde el 2026-11-02 vamos a full:** revisar y terminar **todas las clases anteriores de todos los cursos**, de a una, con el estilo nuevo (ver "Formato de cada clase"), probadas de verdad y con capturas. Mostrarle cada clase al usuario antes de pasar a la siguiente.

Para cada clase:
1. Leer lo acordado en el chat del curso (abajo), el `.mdx` actual y el proyecto, si existe
2. Corregir errores y completar los pasos que falten, para que un alumno pueda seguirlos sin ayuda
3. Armar y probar el proyecto de la clase
4. Agregar capturas y GIF entre los pasos
5. Actualizar `manifest.json` si cambia el título o se agrega la clase

No cambiar el código ya acordado sin avisar. Si hace falta, decir qué se cambió y por qué.

### Chats de cada curso (claude.ai)

Ahí se discute cada clase antes de armarla. Se leen con el navegador.

- **Roblox:** https://claude.ai/chat/59923915-71ca-4c3a-aea4-1af7a7b7526d
- **Desarrollo Web:** https://claude.ai/chat/bc265383-4aa9-44eb-99c0-332d15e95c57
- **Python:** https://claude.ai/chat/703476b4-1b6a-40bd-a033-b5987d8f8306
- **Scratch:** https://claude.ai/chat/47137210-1274-4a86-acfc-c9161a3b8a1f

### Clases terminadas con el estilo nuevo

Lista para no pisarnos: si una clase está acá, ya está hecha y probada, y no se vuelve a rehacer sin que el usuario lo pida. Al terminar una clase, **sumarla al final de esta lista** (y a la memoria).

| # | Curso | Clase | Fecha |
|---|---|---|---|
| 1 | Roblox | Clase 30: Tiendas y Monedas Virtuales 🛍️ | 2026-11-02 |
| 2 | Roblox | Clase 28: Tablas de Puntos (Leaderboards) 🏆 | 2026-11-02 |
| 3 | Roblox | Clase 29: ¡Sube de Nivel! Sistema de XP 🌟 | 2026-11-02 |
| 4 | Roblox | Clase 27: Checkpoints y Vidas ❤️ | 2026-11-02 |
| 5 | Roblox | Clase 26: ¡A Ganar Robux! (Monetización) 💰 | 2026-11-03 |

### Estado (2026-11-03)

- Roblox 27, 28, 29 y 30: hechas con el estilo nuevo y probadas en Studio. La 30 vende solo poderes simples (Super Velocidad y Super Salto), porque el usuario no quiere cosas elaboradas que no entran en la clase
- Roblox 29: el código no se tocó; se agregó **TextColor3 blanco** al `TextoNivel`, porque en negro no se leía sobre el fondo gris
- Roblox 27: el código no se tocó; se sumó el aviso de `SetAttribute` con dos t (error que tuvo el usuario en el chat)
- Roblox 26 (2026-11-03): el usuario la pidió **más corta pero funcional**. Se rehízo de 635 a ~250 líneas: un solo LocalScript en `TiendaGui` (los dos botones, textos fijos, sin pedir el precio), un solo Script `Compras` (Pase + `ProcessReceipt`), sin `MODO_PRUEBA`, sin `compraConfirmada`, sin `finBoost` (cada compra suma 10 y `task.delay(60)` resta 10) y sin el extra de varios Pases. Probado en Studio: velocidad 16→26→36→26→16 y la Linterna sigue al morir
- Datos de prueba de la 26: experiencia `Clase 26 - Compras con Robux` (id 10774578210, privada), Pase `Linterna Premium` 2070421465 (25 R$), Producto `Velocidad +10` 3728068772 (10 R$). Proyecto en `codilab\clase26.rbxlx`
- **Pases en Studio:** el creador del juego ya es dueño de sus Pases (`UserOwnsGamePassAsync` da true y la compra dice "Ya tienes este objeto"), así que el flujo de compra del Pase no se puede ver con la cuenta del creador. Los Productos sí: Studio muestra "compra de prueba" y no cobra
- Siguiente: Roblox 25 hacia atrás, y después los otros cursos. Esperar la orden del usuario
- El resto de las clases y cursos: sin revisar

### Formas viejas en el código de Roblox (2026-11-02)

El usuario pidió pasar todo a la forma recomendada **menos el BodyVelocity**, que lo quiere analizar él. Hecho el 2026-11-02:

| Forma vieja | Recomendada | Clases | Estado |
|---|---|---|---|
| `game.Players.LocalPlayer` | `local Players = game:GetService("Players")` y `Players.LocalPlayer` (`LocalPlayer` en sí no es viejo) | 10, 12, 15, 24, 25 | ✅ Hecho |
| `wait(n)` | `task.wait(n)` | 7, 8, 9, 20, 23, 24 | ✅ Hecho (en la 9, menos el bloque del BodyVelocity) |
| `MouseButton1Click` | `Activated` (mouse, toque y joystick) | 16, 23, 24 | ✅ Hecho (en la 16 también el texto que lo explicaba) |
| `for _, x in ipairs(t)` / `pairs(t)` | `for _, x in t` | 21, 22, 24, 26, 27 | ✅ Hecho |
| `BodyVelocity` y `.Velocity` | `LinearVelocity` con un Attachment (BodyVelocity está obsoleto) | 9 | ⏳ **Pendiente: lo analiza el usuario.** El bloque entero (con su `wait(0.5)`) quedó sin tocar |

Están bien y no hay que tocarlas: `Heartbeat`, `animator:LoadAnimation` (ya usan el Animator), `task.delay`. De acá en adelante, todo código nuevo va con las formas recomendadas.

Falta probar en Studio las clases 7 a 26 con estos cambios: se van a probar cuando se rehaga cada una con el estilo nuevo.

## Formato de cada clase

**Al grano (pedido del usuario, 2026-11-02):** nada de intros largas. Después del título va una sola línea de descripción y los objetivos cortos, y enseguida `### 🪙 Parte 1: ...` con `### Paso 1: ...`, `### Paso 2: ...`. Cada paso tiene una explicación breve (una o dos líneas o pocas viñetas), no párrafos. Las imágenes y GIF van **entre los pasos**, justo donde ayudan a ver el resultado ("Probalo: …" + captura), no todas al final. Modelo: `roblox/clase30.mdx`.

**Al grano, pero explicando todo (pedido del usuario, 2026-11-02):**
- Toda tabla de propiedades lleva la columna **Para qué sirve**: `Propiedad | Valor | Para qué sirve`. Lo mismo si las propiedades van en una lista: cada una con su para qué
- **Todas las propiedades que se ven en el panel del objeto nuevo, no solo las que cambiamos:** por ejemplo, en un ProximityPrompt van ActionText, ObjectText, HoldDuration, KeyboardKeyCode, Exclusivity, RequiresLineOfSight, etc., cada una con su para qué. Las que cambiamos se marcan con ✏️. Si hay una captura de Propiedades, se explican las que aparecen en la captura (el usuario las ve y pregunta qué son). Modelo: el ProximityPrompt de `roblox/clase30.mdx`
- Cada objeto o funcionalidad nueva lleva una nota corta: `> 📝 **Qué es un ProximityPrompt:** …` (una o dos líneas)
- Cada bloque de código lleva debajo viñetas que resumen qué hace
- **Ordenado, no agregado así nomás (pedido del usuario):** primero la nota de qué es el objeto, después su tabla. Una sola tabla por objeto, con ✏️ en lo que se cambia; si Studio agrupa por secciones (Aspecto, Colisión…), la tabla sigue esas secciones y va al lado de su captura. Solo las propiedades que sirven o que el alumno va a ver y preguntar; las que no se usan se nombran en una línea ("Las demás… quedan como vienen"). Nada explicado dos veces. Al terminar, releer la clase entera de corrido

En lo demás:

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
- **Studio se puede manejar desde PowerShell** (SetCursorPos/mouse_event/SendKeys): la escena se arma pegando Lua en la barra de comandos y ejecutándolo con Ctrl+Enter, y se prueba con Play, Tab, WASD y E. Hay dos monitores: el principal (donde está Studio) arranca en (1080, 522) de la captura `gdigrab -i desktop`. Cuidado: Ctrl+A/Supr con un script abierto en el editor lo borra, y arrastrar la barra de título de un panel lo desacopla. Después de apretar Stop, confirmar con una captura que la prueba terminó (pestañas Cliente/Servidor). Al agrandar el Explorer para la captura final, el divisor queda pegado a la barra de título de Propiedades: si se agarra la barra, el panel queda flotando; se vuelve a acoplar arrastrándolo sobre el Explorer y soltándolo en la guía de abajo. Al darle Play, el cliente puede tardar más de 20 s en cargar: esperar a ver el personaje antes de moverlo. Para probar muertes y checkpoints, caminar de verdad (W/S): teletransportar con `PivotTo` desde el cliente da resultados falsos, porque el servidor todavía ve al personaje en el lugar anterior. Si la clase renombra la SpawnLocation de la plantilla, guardar sus valores y devolverlos al limpiar
- **Finales de línea:** no todos son iguales: la mayoría de los `.mdx` están en CRLF, pero algunos (por ejemplo roblox 22 a 25) están en LF. Mantener el que tenga cada archivo. `sed -i` de Git Bash los pasa a LF: editar con Python (`newline='
'`) o restaurarlos después
- **Generar una clase sin tocar el código:** escribir una plantilla con `{{C0}}`, `{{C1}}`… y llenarla con los bloques de código sacados del `.mdx` original, y comprobar que quedaron idénticos
