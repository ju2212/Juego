# Documento de Diseño del Juego (GDD)

> **Nombre provisorio:** *Proyecto PRISMA* (el nombre definitivo se decide más adelante)
> **Estado:** en diseño, todavía sin código
> **Última actualización:** 19/11/2026

Este documento junta todas las decisiones tomadas. Cada vez que decidamos algo nuevo, se actualiza acá.

---

## 1. Visión general

| Tema | Decisión |
|---|---|
| Género | Aventura de acción / supervivencia en 3D |
| Plataforma | Teléfono, en el navegador (web 3D). Se juega abriendo un enlace y se puede agregar a la pantalla de inicio |
| Tecnología | **Babylon.js** (motor 3D para la web) |
| Orientación | Horizontal, con las dos manos |
| Cámara | Tercera persona (detrás del hombro) |
| Controles | Dos joysticks virtuales (mover / cámara y apuntar) + botones de acción |
| Estilo visual | Lo más realista posible, dentro de lo que permite un celular |
| Tono | Aventura emocionante con momentos de humor |
| Mundo | Mundo abierto que **arranca chico** (una zona) y crece de a poco |
| Público | Proyecto para aprender; si gusta, mejor |

### Cómo trabajamos
- El usuario trabaja **solo desde el teléfono**.
- Claude escribe el código en la nube, lo prueba y publica un **enlace para jugar** en el celular.
- El usuario prueba, opina y se itera. Todo se guarda en git.

---

## 2. Premisa e historia

En un futuro cercano, la inteligencia artificial cambió la sociedad y dañó el planeta. El aire, el agua y la comida escasean, y una **IA hostil** controla gran parte de la tecnología.

El protagonista tiene que **sobrevivir usando tecnología e IA**: contra el mundo que quedó y contra la propia IA. Cuenta con una **IA aliada** que puede meterse en distintas máquinas para ayudarlo.

- **Cantidad de historia:** algo de historia, con una introducción, diálogos y objetivos.
- **Objetivo grande:** recuperar territorio, mantener viva a la familia y decidir el destino de los sobrevivientes. Algunas personas conviene **mandarlas a una colonia fuera de la Tierra** y otras **quedarse a luchar**.

---

## 3. Personajes jugables

Se puede **elegir el protagonista** entre cuatro. Cada uno tiene sus propias habilidades y su propia familia.

| Personaje | Fortaleza | Debilidad | Familia (a definir en detalle) |
|---|---|---|---|
| **Técnico / reparador** | Repara y fabrica mejor; hackea más barato | Menos resistente en combate | — |
| **Ex soldado / guardia** | Combate y puntería; más vida | Hackea más lento (depende de la IA aliada) | — |
| **Exprogramador de la IA** | Hackeo avanzado; conoce los puntos débiles de la IA hostil | El más frágil | — |
| **Sobreviviente común** | Equilibrado; mejor en recolectar y racionar | Sin especialidad | — |

**Acciones de todos:** correr, saltar, trepar y colgarse, empujar y usar objetos, pelear cuerpo a cuerpo y disparar.

---

## 4. La IA aliada

- **No tiene cuerpo propio**: **salta de una máquina a otra** (cámaras, puertas, autos, drones, robots).
- Mientras controla una máquina, puede usarla para ayudar: abrir caminos, distraer, pelear o vigilar.
- **Progresa**: empieza controlando cosas chicas (cámaras, luces) y termina controlando máquinas grandes.
- Gasta **energía**: hay que conseguir baterías y puntos de carga.
- Aporta parte del **humor** con sus comentarios.

---

## 5. Enemigos y la IA hostil

| Tipo | Descripción |
|---|---|
| Drones voladores | Patrullan, vigilan y atacan desde el aire |
| Robots de seguridad | Máquinas terrestres armadas que persiguen al jugador |
| Humanos | Gente controlada por la IA o bandas que aprovechan el caos |
| Sistemas de la ciudad | Cámaras, torretas, puertas y autos usados en contra del jugador |

**Regla clave:** casi cualquier máquina enemiga se puede **destruir o poner a favor** del jugador mediante hackeo.

### Hackeo: depende de la máquina
- **Chicas** (cámaras, puertas, luces): mantener apretado un botón unos segundos.
- **Medianas** (drones, torretas): minijuego corto.
- **Grandes** (robots pesados): primero hay que debilitarlas en combate y después hackearlas con un minijuego.

---

## 6. Supervivencia

- **Vida y curación:** botiquines y vendas.
- **Energía / baterías:** para gadgets, armas tecnológicas y la IA aliada.
- **Comida, agua y aire:** necesidades del personaje en un planeta dañado.
- **Recolectar y fabricar:** chatarra y piezas para armas, herramientas y mejoras.
- **Mantener con vida a la familia:** hay que llevarle recursos y protegerla.

---

## 7. Progreso

- Mejorar las **habilidades** de cada personaje.
- Mejorar a la **IA aliada** para que controle máquinas más grandes.
- Conseguir y mejorar **armas y equipo**.
- **Conquistar territorio** y ponerlo a favor del jugador.
- **Gestionar sobrevivientes**: decidir quién va a la colonia y quién se queda a luchar.

---

## 8. Mundo y primera zona

- **Ubicación:** Tandil (provincia de Buenos Aires), en un futuro dañado por la IA.
- **Primera zona:** **PRISMA**, una **fábrica de ventanas del futuro** (inventada, no copia de ninguna real), tomada por la IA hostil.
- **Objetivo de la zona:** **recuperar la fábrica** para poder usar sus máquinas.
- **Importancia en la historia:** de PRISMA salen **las primeras herramientas del juego**: la primera tecnología (software y hardware) y **la IA aliada**, que nace o se rescata ahí.
- Después se suman otras zonas de Tandil y alrededores.

### Sectores de la fábrica
| Sector | Contenido | Uso en el juego |
|---|---|---|
| Galpón de producción | Líneas robotizadas de ventanas inteligentes, prensas, cortadoras láser | Combate, trepar máquinas, obstáculos en movimiento |
| Depósito y playa de carga | Estanterías altas, perfiles, camiones y autoelevadores autónomos | Plataformas, máquinas para hackear, recolectar recursos |
| Oficinas y sala de servidores | Núcleo de la IA hostil en la fábrica | Objetivo final de la zona; acá aparece la IA aliada |
| Techos y exterior | Techos de chapa, pasarelas, paneles solares, el predio y las sierras de Tandil de fondo | Exploración, rutas alternativas, francotiradores/drones |

### Qué pasó en el mundo
Se mezcla todo: **varias IAs compitiendo** entre sí, **guerras por recursos** y un **clima destruido**. La sociedad se partió entre los que dependen de las IAs, los que las combaten y los que buscan irse a colonias.

> ⚠️ **A tener en cuenta:** si PRISMA es una empresa real, para un proyecto personal no hay problema, pero si el juego se publica conviene pedir permiso o usar un nombre ficticio parecido.

---

## 9. Alcance: qué construimos primero

Un juego así es enorme, así que se construye **por etapas**. Cada etapa termina con algo jugable en el celular.

1. **Prototipo de movimiento (PRIMERA PRIORIDAD):** personaje en tercera persona con joysticks, cámara, correr y saltar en un escenario simple.
2. **La fábrica (bloqueo):** la fábrica PRISMA armada con formas simples para probar recorridos.
3. **Combate básico:** disparar y un tipo de enemigo (dron).
4. **Hackeo e IA aliada:** tomar control de una cámara o una puerta.
5. **Supervivencia básica:** vida, energía y recolectar.
6. **Gráficos realistas:** reemplazar formas simples por modelos, texturas e iluminación.
7. **Historia de la primera zona:** intro, diálogos y objetivo "recuperar PRISMA".

Después: elegir personaje, familia, fabricación, colonia y nuevas zonas.

---

## 10. Pendientes por decidir

- [ ] Nombre del juego
- [ ] Nombres, aspecto e historia de cada personaje y de su familia
- [ ] Nombre y personalidad de la IA aliada y de la IA hostil
- [ ] Qué pasó exactamente en el mundo (cómo la IA cambió todo)
- [ ] Cómo funciona la colonia fuera de la Tierra
- [ ] Armas concretas
- [ ] Música y sonido
- [ ] Plano detallado de la fábrica (recorrido, entradas y salidas)
