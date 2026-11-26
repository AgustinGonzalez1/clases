# Python v2: plan (borrador del 2026-11-21)

Reglas de la v2:

- Cada clase usa **solo lo ya visto**. Nada de `if` antes de la 5 ni bucles antes de la 10
- El código **crece clase a clase** con un hilo conductor: un héroe y su aventura
  - 1 a 18: juego de texto en la consola
  - 19 a 36: el mismo héroe pasa a Pygame
- La **misión del temario** es el ejercicio de cada clase, y el ejemplo usa el hilo conductor
- Sin ejemplos rebuscados como la carta formal, la etiqueta de producto o el cajero
- El jugador y los enemigos de Pygame van con **diccionarios**, no con clases (decisión del 2026-11-21)
- Formato y estilo, iguales a los otros cursos (modelo: `roblox/clase30.mdx`). Cada clase dura 1 h

## Módulo 1 (1 a 9): el héroe en la consola

| Clase | Tema | Ejemplo del hilo |
|---|---|---|
| 1 | `print` | La pantalla de inicio del juego |
| 2 | Variables y tipos | La ficha del héroe: nombre, vida, oro |
| 3 | `input` y cuentas | Elegir el nombre y comprar pociones (oro − precio × cantidad), sin `if` |
| 4 | Comparaciones y `and`/`or` | `print(oro >= precio)` da `True`/`False`, sin `if` |
| 5 | `if`/`else` | La puerta del castillo: ¿tenés la llave? |
| 6 | `elif` y anidados (de verdad) | El clima del mapa decide qué equipo llevar |
| 7 | Listas y conjuntos | El inventario (`append`, `remove`, `in`) y los logros sin repetir, sin bucles |
| 8 | Diccionarios y tuplas | El héroe como diccionario y la posición `(x, y)` como tupla |
| 9 | Métodos (con punto) | `.upper()`, `.split()`, `.sort()`, `.count()` sobre el inventario y los mensajes |

## Módulo 2 (10 a 18): el código se ordena

| Clase | Tema | Ejemplo del hilo |
|---|---|---|
| 10 | `for` y `range` | Recorrer el inventario |
| 11 | `while` y `break` | Adivinar un número secreto **fijo** y un menú que se repite |
| 12 | Funciones integradas (sin punto) | `len`, `max`, `min`, `sum`, `abs`, `round` con los puntajes. No se pisa con la 9 |
| 13 | `def` | `mostrar_ficha(heroe)` |
| 14 | `return` | `calcular_danio(ataque, defensa)` |
| 15 | `lambda` | Ordenar el ranking por puntaje |
| 16 | Módulos | `random` (dados; el número secreto de la 11 pasa a ser al azar) y `math` |
| 17 | Turtle | Dibujar el mapa o la casa del héroe |
| 18 | POO | `class Heroe` con `atacar()` y `curar()` en un combate en la consola |

## Módulos 3 y 4 (19 a 36): el héroe en Pygame

Se sigue el temario, pero con estos cambios respecto de la v1:

- Bordes con 4 `if` desde la 21 (sin `max(0, min(...))`)
- El `QUIT` se revisa **una sola vez**, arriba del bucle, y no en cada estado
- Una función `dibujar_texto(texto, x, y)` desde la 25, en vez de repetir render y blit
- La dificultad sube **cada 10 monedas** (como dice el temario) con `if vel > 0: vel += 1`, sin `// abs`
- La animación cambia de cuadro con `if frame == 0: frame = 1`, sin `% len`
- La 31 y la 32 (IA) quedan como en la v1, adaptadas al código nuevo
- 33 a 36, iguales a la v1: proyecto final en 2 partes, revisión final y presentación

## Pendiente de decidir con el usuario

- Carpeta de la v2 (por ejemplo `python-v2/`) y cómo aparece en `manifest.json`
- Si las clases 1 a 18 de la v1 se reescriben o se arman de cero
