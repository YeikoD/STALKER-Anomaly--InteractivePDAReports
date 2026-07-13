### ¿Qué es Interactive PDA Reports?

Mod de inmersión para **S.T.A.L.K.E.R. Anomaly** que hace que tu personaje y los NPCs de la Zona se comuniquen por radio a través de la red de la PDA.

- **Tu PJ reporta:** Al saquear un cuerpo, tu personaje envía automáticamente un mensaje a `[Todos]`. El texto cambia según tu relación con el muerto:
  - **Amistoso** (relación ≥ 400): Lamento la pérdida de un aliado.
  - **Neutral** (entre -400 y 400): Reporte genérico de un cuerpo.
  - **Enemigo** (≤ -400, no lo mataste vos): Reportás el cuerpo de un enemigo.
  - **Víctima** (≤ -400, lo mataste vos): Te burlás de haberlo liquidado.

- **NPCs responden:** Si hay stalkers de la misma facción del muerto vivos en el mapa, uno de ellos te responde por PDA después de un delay aleatorio configurable. El tono de la respuesta coincide con tu reporte (si te burlaste, te responden con amenazas).

- **Comentario externo:** Además, un NPC de una facción distinta a la del muerto puede comentar lo ocurrido, con su propio delay. La segunda respuesta espera a que la primera se haya enviado antes de dispararse.

- **Factor Ego:** Controlá qué porcentaje de cuerpos se reportan realmente. A 100% se reportan todos; a 50% se reporta 1 de cada 2.

### Instalación

Opción A — **Mod Organizer 2**: Instalá el `.zip` o `.7z` desde el botón "Instalar un nuevo mod desde un archivo". Activá la casilla.

Opción B — **Manual**: Extraé la carpeta `gamedata` dentro de la raíz de S.T.A.L.K.E.R. Anomaly.

> El mod no sobrescribe archivos nativos del juego.

### Configuración (MCM)

Si tenés MCM instalado, aparece "Interactive PDA Reports" en el menú de opciones. Sliders disponibles:

| Slider | Descripción | Defecto |
|---|---|---|
| **Factor Ego** | Probabilidad de que un cuerpo sea reportado. 100% = siempre, 0% = nunca. | 100% |
| **Probabilidad de Respuesta** | Probabilidad de que un NPC de la misma facción conteste. | 40% |
| **Probabilidad de Comentario Externo** | Probabilidad de que un NPC de otra facción comente. | 30% |
| **Tiempo Respuesta 1 (Mín/Máx)** | Rango de delay (en decisegundos) para la primera respuesta. 30 = 3 seg. | 30-60 |
| **Tiempo Respuesta 2 (Mín/Máx)** | Rango de delay (en decisegundos) para el comentario externo. | 40-80 |

Si no usás MCM, el mod aplica los valores por defecto automáticamente.

### Localización y Expansión (XML)

Los textos están en `gamedata/configs/text/spa/`. Editá los archivos `st_ipreports_*.xml` y `st_pj_*.xml` con cualquier editor de texto.

#### Reporte del Jugador

Archivos: `st_pj_amistoso.xml`, `st_pj_neutral.xml`, `st_pj_enemigo.xml`, `st_ipreports_victima.xml`.

Tres `%s` en orden: **nombre del muerto**, **zona actual**, **facción del muerto**.

```xml
<string id="st_pjnews_amistoso_1">
    <text>Encontré el cuerpo de %s en %s. Descansa en paz, camarada de %s.</text>
</string>
```

#### Respuesta del NPC (primera)

Archivo: `st_pj_respuestas.xml`.

Usa `{player}`, `{zone}`, `{victim}` como placeholders (en cualquier orden y sin límite de cantidad).

```xml
<string id="st_pjnews_respuesta_victima_1">
    <text>¿Te haces el vivo, {player}? Te tenemos en la mira en {zone}.</text>
</string>
```

#### Comentario Externo (segunda respuesta)

Archivo: `st_ipreports_segunda_respuesta.xml`.

Usa `%s` simple en orden: **nombre del muerto**, **zona**, **facción del muerto**.

### Archivos del Mod

```
gamedata/
├── scripts/
│   ├── ipreports_interactive.script   # Lógica principal
│   └── ipreports_mcm.script           # Configuración MCM
└── configs/text/spa/
    ├── st_ipreports.xml               # Strings base (Todos, conexión)
    ├── st_ipreports_mcm.xml           # Traducciones del MCM
    ├── st_ipreports_victima.xml       # Frases de víctima (lo maté yo)
    ├── st_ipreports_segunda_respuesta.xml  # Comentarios externos
    ├── st_pj_amistoso.xml             # Frases de aliado muerto
    ├── st_pj_neutral.xml              # Frases de neutral muerto
    ├── st_pj_enemigo.xml              # Frases de enemigo muerto
    └── st_pj_respuestas.xml           # Respuestas de NPCs
```
