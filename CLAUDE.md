# Clases Codilab

Material de las clases de programación que da el usuario en Codilab. Cada clase es un `.mdx` que se ve en `index.html` (lo lee de `manifest.json` y lo renderiza con marked + highlight.js).

## Estructura

```
clases codilab/
├── index.html        visor de las clases (sidebar por curso)
├── manifest.json     lista de cursos y clases: { nombre, carpeta, clases: [{ titulo, archivo }] }
├── ejemplo.mdx       plantilla de una clase, con el formato de roblox/clase30.mdx
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

### Temario de cada curso (fuente de verdad del contenido)

El usuario deja el temario de cada curso en un `temario.txt` dentro de la carpeta del curso. Cada clase respeta lo que dice ahí: tema, misión y lo que se vio hasta ese momento.

- **Roblox:** `roblox/temario.txt` (2026-11-10). Son **36 clases** en 6 módulos. Del 31 al 36 todavía no hay `.mdx`: 31 DataStore, 32 Multijugador, 33 IA, 34 Optimización, 35 LinkedIn y 36 Presentación final. Por eso está bien que la 28, la 29 y la 30 manden a la **Clase 31** para DataStore
- **Scratch, Python y Web:** todavía faltan (el usuario los va a pasar). Mientras tanto, usar el Google Doc de los planes de estudio

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
| 2 | Roblox | Clase 28: El Salón de la Fama (Leaderboards) 🥇 | 2026-11-02 |
| 3 | Roblox | Clase 29: ¡Sube de Nivel! Sistema de XP 🌟 | 2026-11-02 |
| 4 | Roblox | Clase 27: Checkpoints y Vidas ❤️ | 2026-11-02 |
| 5 | Roblox | Clase 26: ¡A Ganar Robux! (Monetización) 💰 | 2026-11-03 |
| 6 | Roblox | Clase 1: ¡Hola, Roblox Studio! 🤩 | 2026-11-07 |
| 7 | Roblox | Clase 2: El Arte de Crear Paisajes 🏞️ (repaso) | 2026-11-07 |
| 8 | Roblox | Clase 3: Construyendo con Bloques 🧱 (repaso) | 2026-11-07 |
| 9 | Roblox | Clase 4: ¡A Mover el Esqueleto! (Animaciones con Editor) 🕺 | 2026-11-07 |
| 10 | Roblox | Clase 5: Rig Personalizado + Animación 🧍‍♂️✨ | 2026-11-07 |
| 11 | Roblox | Clase 6: Nuestro primer print 💻 | 2026-11-07 |
| 12 | Roblox | Clase 7: Bloque de la muerte y supersalto 💀🦘 | 2026-11-07 |
| 13 | Roblox | Clase 8: Bloque teletransportador 🔀 | 2026-11-07 |
| 14 | Roblox | Clase 9: Programación creativa 🎨🎮 | 2026-11-07 |
| 15 | Roblox | Clase 10: ¡Hola, Amigo NPC! 👋 | 2026-11-07 |

### Estado (actualizado 2026-11-07)

- **Repaso de la Clase 30 (2026-11-10):** cumple el formato, está probada y queda **tal como está** (pedido del usuario). Es el modelo para todas las clases

- Roblox 27, 28, 29 y 30: hechas con el estilo nuevo y probadas en Studio. La 30 vende solo poderes simples (Super Velocidad y Super Salto), porque el usuario no quiere cosas elaboradas que no entran en la clase
- Roblox 29: el código no se tocó; se agregó **TextColor3 blanco** al `TextoNivel`, porque en negro no se leía sobre el fondo gris
- Roblox 27: el código no se tocó; se sumó el aviso de `SetAttribute` con dos t (error que tuvo el usuario en el chat)
- Roblox 26 (2026-11-03): el usuario la pidió **más corta pero funcional**. Se rehízo de 635 a ~250 líneas: un solo LocalScript en `TiendaGui` (los dos botones, textos fijos, sin pedir el precio), un solo Script `Compras` (Pase + `ProcessReceipt`), sin `MODO_PRUEBA`, sin `compraConfirmada`, sin `finBoost` (cada compra suma 10 y `task.delay(60)` resta 10) y sin el extra de varios Pases. Probado en Studio: velocidad 16→26→36→26→16 y la Linterna sigue al morir
- Datos de prueba de la 26: experiencia `Clase 26 - Compras con Robux` (id 10774578210, privada), Pase `Linterna Premium` 2070421465 (25 R$), Producto `Velocidad +10` 3728068772 (10 R$). Proyecto en `codilab\clase26.rbxlx`
- **Pases en Studio:** el creador del juego ya es dueño de sus Pases (`UserOwnsGamePassAsync` da true y la compra dice "Ya tienes este objeto"), así que el flujo de compra del Pase no se puede ver con la cuenta del creador. Los Productos sí: Studio muestra "compra de prueba" y no cobra
- **Siguiente (2026-11-07):** Roblox 1 a 10 terminadas, aprobadas y pusheadas (commit `e32ba97`). Sigue **Roblox 11** (la espada) en adelante, de corrido, y el usuario revisa en bloque. Después, los otros cursos
- **Revisar los ejemplos de Roblox (pedido del 2026-11-07):** en cada clase, revisar si cada ejemplo es la mejor forma de hacerlo y la más fácil para un alumno. Si no, buscar la mejor forma posible (documentación oficial, prácticas recomendadas) y proponerla en el resumen, sin cambiar el código hasta que el usuario lo apruebe
- **Roblox 1 a 5, decisiones del usuario (2026-11-07):** aprobó todos los cambios del resumen. Clase 1: probar con Play, guardar (Guardar en Roblox / en archivo), cámara con GIF. Clase 2: Esculpir para colinas, plantilla Flat Terrain, ClockTime + Atmosphere + Clouds (Sky como extra). Clase 3: CanCollide, Transparency, ajuste de 1 stud, menú Pieza y ejemplo del castillo paso a paso. Clase 4: rig **R15 de "Mi avatar"** (Inicio → Personaje → Generar rig → R15 → Mi avatar), Avatar → Editor de clips, primero el saludo y después el caminar, explicar guardar y publicar. Clase 5: **se queda con RigLink**, que para el usuario es lo mejor y lo más fácil
- **Código cambiado en Roblox 6–10 (2026-11-07, aprobado y pusheado):** 6 y 8: `clon.Script:Destroy()` después de `Clone()` (sin eso, la 6 hacía 81 bloques con "Maximum re-entrancy depth" y la 8 dejaba un clon para siempre); la 6 además corre la copia 8 studs con `Position`. 10: el LocalScript pasó de StarterPlayerScripts a **StarterCharacterScripts** con `script.Parent` como personaje (antes, al morir, el texto quedaba congelado). 7 y 9: código igual; se avisa del error rojo del accesorio (se arregla con `if` en la 19, porque antes no se ven condicionales). 9: BodyVelocity pasado a LinearVelocity el 2026-11-10. GIF de 7, 8 y 9 agregados (cámara fija desde el cliente: Scriptable, arriba y detrás del SpawnLocation; bloques adelante)
- **Notas de Studio (2026-11-07):** el Animation Editor ahora es **Avatar → Editor de clips**; para ver los anillos al posar hay que tocar **Girar** en la barra (lo dijo el usuario). RigLink está instalado (pestaña Plugins): Link Selected → Part0/Part1/Name + flechas del pivote → Confirm Link; crea el Motor6D en Part0 sin mover las piezas. No publicar animaciones en la cuenta del usuario al sacar capturas (cancelar la ventana)
- **Cambio de ritmo (2026-11-07, más tarde):** el usuario pidió hacer **Roblox 2 a 10 de corrido**, sin esperar su OK entre clases; él las revisa todas juntas al final. Las clases básicas (2 Terreno y 3 Bloques) van como un **repaso por arriba**, sin tanto detalle. **De la 4 en adelante, con más detalle**, porque son más rebuscadas. Si falta algo, se agrega. Hay que basarse en los **planes de estudio** (Google Doc, una pestaña por curso):
  - Roblox: https://docs.google.com/document/d/1RGVJiNUjVLDVjAyMF3nJi728Q9DsTvp4GSm8HTgLtEM/edit?tab=t.0
  - Desarrollo Web: https://docs.google.com/document/d/1RGVJiNUjVLDVjAyMF3nJi728Q9DsTvp4GSm8HTgLtEM/edit?tab=t.3ivtqhfxye8v
  - Scratch: https://docs.google.com/document/d/1RGVJiNUjVLDVjAyMF3nJi728Q9DsTvp4GSm8HTgLtEM/edit?tab=t.9sqyv17d1o0
  - Python: https://docs.google.com/document/d/1RGVJiNUjVLDVjAyMF3nJi728Q9DsTvp4GSm8HTgLtEM/edit?tab=t.pj4dptksahzy
- **Cómo seguimos (2026-11-07):** de a una clase: probarla en Studio, rehacerla con el estilo nuevo y mostrársela al usuario. Recién con su OK se pasa a la siguiente. El mismo estilo va para los 4 cursos (Roblox, Scratch, Python y Web). La idea es que el usuario entienda fácil lo que vemos: todo bien estructurado, corto, explicando para qué sirve cada cosa, con ejemplos, imágenes y GIF
- **Prueba rápida en Studio de Roblox 7–25 (2026-11-07), con el código tal cual está en los `.mdx`:**
  - ❌ 21 y 23: `daño` y `dañados` con ñ dan error de sintaxis (Luau no acepta ñ en nombres de variables)
  - ❌ 10: `jugador.Character` sin `or CharacterAdded:Wait()` (puede ser nil al arrancar). 25: el LocalScript de música reactiva usa `musica` sin definirla (por lectura, sin probar todavía)
  - ⚠️ 7 y 9: `mano.Parent.Humanoid` da error si toca un accesorio (pelo); usar `FindFirstChild("Humanoid")`. 8: el clon copia el Script y se clona solo, y quedan clones para siempre. 9 y 17: invisible y fuego titilan por `TouchEnded`; el que se achica desaparece de un toque. 20: el bloque que quita vida corta antes por `TouchEnded`. 21: el cofre imprime una vez por cada parte del cuerpo
  - ✅ 18, 19, 20 (bucles y cuenta regresiva), teletransporte de la 8, empuje de la 9 (BodyVelocity funciona) y SFX de la 25
  - Sin probar todavía: 10–16, 22–25 (NPC, armas, auto, animación, cinemática, menú, enemigo, trampa, obby, slider)
- El resto de las clases y cursos: sin revisar

### Formas viejas en el código de Roblox (2026-11-02)

El usuario pidió pasar todo a la forma recomendada (el BodyVelocity lo analizó él y pasó a LinearVelocity el 2026-11-10). Hecho el 2026-11-02:

| Forma vieja | Recomendada | Clases | Estado |
|---|---|---|---|
| `game.Players.LocalPlayer` | `local Players = game:GetService("Players")` y `Players.LocalPlayer` (`LocalPlayer` en sí no es viejo) | 10, 12, 15, 24, 25 | ✅ Hecho |
| `wait(n)` | `task.wait(n)` | 7, 8, 9, 20, 23, 24 | ✅ Hecho |
| `MouseButton1Click` | `Activated` (mouse, toque y joystick) | 16, 23, 24 | ✅ Hecho (en la 16 también el texto que lo explicaba) |
| `for _, x in ipairs(t)` / `pairs(t)` | `for _, x in t` | 21, 22, 24, 26, 27 | ✅ Hecho |
| `BodyVelocity` y `.Velocity` | `LinearVelocity` con un Attachment (BodyVelocity está obsoleto) | 9 | ✅ **Hecho (2026-11-10):** el usuario comparó en Studio y eligió `LinearVelocity` + Attachment, con `ForceLimitMode` PerAxis y `MaxAxesForce` (X y Z sin límite, Y en 0). Antes: El bloque entero (con su `wait(0.5)`) quedó sin tocar |

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
- `## Objetivos` → `## Contenido` con Partes con emoji (`### 🏆 Parte 1: ...`) y adentro Pasos (`### Paso 1: ...`), como la Clase 30
- Pasos numerados y concretos: "Click derecho en **ServerScriptService** → Insert Object → **Script**", "Lo renombrás `Leaderboard`"
- Tablas de propiedades (Propiedad | Valor | Para qué sirve)
- Árbol del Explorer en bloque de texto (`├──`, `└──`)
- Código comentado línea por línea, en español **sin tildes dentro del código**, y debajo viñetas que explican las partes clave
- Notas con `> 💡` (tip) y `> ⚠️` (error común)
- Referencias a clases anteriores ("Como en la Clase 7…")
- Cierre: "Probar todo", "Estructura final en el Explorer", "Problemas comunes", "Extras", `## Ejercicio` (consigna + pistas) y `## Recursos` (links a la documentación oficial)
- **Decidido por el usuario (2026-11-10), igual en todas las clases:**
  - "Problemas comunes" lleva 2 columnas: `Problema | Solución`. La causa va adentro de la solución: "La causa. Lo que hay que hacer". Hecho en la 1 a la 10
  - "Estructura final en el Explorer" lleva **las dos cosas**: primero el árbol en texto (solo lo que arma la clase, con sangría `└──` y el tipo entre paréntesis) y después la captura. Hecho en la 26 a la 30 (en la 30 solo se agregó el árbol)
  - **La 1 a la 10 pasaron al formato de la 30 (2026-11-10):** Pasos que arrancan en 1 en cada Parte; "Probar todo" como último Paso (en la 6 y la 10 se juntó con el paso "Probar"); cierre con `###` adentro de Contenido; la Parte 5 Extra de la 4 (Editor facial) pasó a Extras; el árbol de la 5 se movió al Explorer final; la 9 tiene Extras nuevo (color al azar y medio fantasma, probado en Studio y aprobado por el usuario). El Explorer final de la 1 a la 10 ya tiene árbol y captura (2026-11-10). Las escenas se armaron con Lua en una Baseplate nueva, sin guardar. Los objetos se marcan con el atributo `_demo` y `Selection:Set` abre las carpetas del Explorer. Antes hay que agrandar el Explorer bajando el divisor (y≈465 del monitor). Si un rig abierto no entra, se unen dos recortes en una imagen, como en la 10. Ver `herramientas-studio\explorer-final.ps1` y `explorer-head.lua`
- **Títulos (2026-11-10):** los títulos siguen al `temario.txt`, más el emoji si el temario no lo tiene, y "Cutscenes" bien escrito. Cambiaron la 4 (+ "(Animaciones con Editor)"), la 15 (🧊) y la 28 ("El Salón de la Fama (Leaderboards) 🥇"). En `manifest.json`, los títulos de Roblox son iguales al `title` de cada `.mdx`
- **La plantilla es `ejemplo.mdx`:** tiene el formato de la 30 con todas las reglas en comentarios. Toda clase nueva o rehecha arranca de ahí
- Español rioplatense con voseo ("le das Play", "tocás", "apretá")
- Studio del usuario está **en español**: incluir los nombres de los menús en español ("Insertar → Insertar objeto…", "Servidor y clientes") junto a los nombres en inglés

## Capturas y videos

- Las capturas van en `<curso>/img/claseNN/` con nombres numerados y descriptivos: `01-insertar-script.png`, `02-propiedades-moneda.png`
- En el `.mdx` se referencian **relativas a `index.html`**, no al `.mdx`: `![Descripción](roblox/img/clase28/01-insertar-script.png)`. Debajo va una línea en cursiva que explica qué mirar (menos la captura del Explorer final, que va sin cursiva: los cuadros rojos ya lo dicen)
- Estilo: recortadas a la zona que importa y con **cuadros rojos** marcando dónde hacer click o qué propiedad cambiar (como en el PDF de la Clase 28)
- **Sin texto dentro de las imágenes ni de los GIF** (ni carteles, ni etiquetas, ni números): solo cuadros rojos. La explicación va en la línea en cursiva de abajo y en las tablas. Todas las clases tienen que verse iguales (pedido del usuario, 2026-11-07)
- Videos o GIF cortos solo donde ayuden a ver un movimiento (por ejemplo, tocar una moneda y ver cómo suben los puntos). Se guardan en `<curso>/img/claseNN/` como `.mp4` o `.gif`
- Grabar la pantalla: ffmpeg con `gdigrab` está en `C:\Users\Agust\AppData\Local\Programs\Python\Python313\Lib\site-packages\imageio_ffmpeg\binaries\ffmpeg-win-x86_64-v7.1.exe` (no está en el PATH). Puede capturar la pantalla entera o una sola ventana por título
- **Studio se puede manejar desde PowerShell** (SetCursorPos/mouse_event/SendKeys): la escena se arma pegando Lua en la barra de comandos y ejecutándolo con Ctrl+Enter, y se prueba con Play, Tab, WASD y E. Hay dos monitores: el principal (donde está Studio) arranca en (1080, 522) de la captura `gdigrab -i desktop`. Cuidado: Ctrl+A/Supr con un script abierto en el editor lo borra, y arrastrar la barra de título de un panel lo desacopla. Después de apretar Stop, confirmar con una captura que la prueba terminó (pestañas Cliente/Servidor). Al agrandar el Explorer para la captura final, el divisor queda pegado a la barra de título de Propiedades: si se agarra la barra, el panel queda flotando; se vuelve a acoplar arrastrándolo sobre el Explorer y soltándolo en la guía de abajo. Al darle Play, el cliente puede tardar más de 20 s en cargar: esperar a ver el personaje antes de moverlo. Para probar muertes y checkpoints, caminar de verdad (W/S): teletransportar con `PivotTo` desde el cliente da resultados falsos, porque el servidor todavía ve al personaje en el lugar anterior. Si la clase renombra la SpawnLocation de la plantilla, guardar sus valores y devolverlos al limpiar
- **Herramientas guardadas:** los scripts para manejar Studio y hacer capturas/GIF están en `Escritorio\codilab\herramientas-studio\` (ver su `LEEME.md`). Para GIF con personaje: cámara fija desde el cliente (`CameraType = Scriptable`, arriba y detrás del SpawnLocation, mirando a los bloques), click en la vista antes de caminar (si no, las teclas van a la barra de comandos) y bloques anchos adelante del SpawnLocation. Si el modo de prueba queda en **Ejecutar** (por F8), volver a **Probar** con el desplegable de arriba a la izquierda
- **Finales de línea:** no todos son iguales: la mayoría de los `.mdx` están en CRLF, pero algunos (por ejemplo roblox 22 a 25) están en LF. Mantener el que tenga cada archivo. `sed -i` de Git Bash los pasa a LF: editar con Python (`newline='
'`) o restaurarlos después
- **Generar una clase sin tocar el código:** escribir una plantilla con `{{C0}}`, `{{C1}}`… y llenarla con los bloques de código sacados del `.mdx` original, y comprobar que quedaron idénticos
