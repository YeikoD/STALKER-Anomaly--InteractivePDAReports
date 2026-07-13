### 📡 ¿Qué es PJNews Interactive?

Es un mod de inmersión para **S.T.A.L.K.E.R. Anomaly** que hace que tu personaje deje de ser el mudo de la Zona y participe activamente en la red de la PDA.

- **Tu PJ ahora habla:** Cada vez que termines de saquear el cuerpo de un stalker, tu personaje va a mandar de forma automática un reporte de radio a la red general `[Todos]`. El mensaje cambia según tu relación con el finado (si era un amigo, un neutral, un enemigo, o si lo liquidaste vos mismo).
    
- **La Zona te responde:** Si hay stalkers aliados o de la misma facción vivos en el mapa, te van a contestar el mensaje por la PDA con un delay súper realista de entre 3 y 5 segundos (simulando que están leyendo y tipeando en su aparato).
    
- **Vos controlás la radio:** Mediante el menú de opciones (MCM), podés deslizar una barra para elegir qué tan seguido te responden (de 0% a 100%). Por defecto viene en un 40% para que sea recontra realista y no sature la pantalla.
    
- **Estilo 100% nativo:** Se integra perfecto con la interfaz del juego, mostrando los nombres y facciones reales en el encabezado de los mensajes.
    

Básicamente, es el mod definitivo para que sientas que de verdad hay gente del otro lado de la radio y que tus acciones en la Zona tienen repercusión en la red.
## 🔧 3. Guía de Instalación

### 📦 Opción A: Mod Organizer 2 (Recomendado)

1. **Descargá** el archivo comprimido del mod (`.zip` o `.7z`).
    
2. En MO2, hacé clic en el botón **"Instalar un nuevo mod desde un archivo"** (el ícono de la caja con el disco arriba a la izquierda).
    
3. Seleccioná el archivo descargado.
    
4. **Activá la casilla** del mod en el panel izquierdo de MO2.
    
5. ¡Listo! Ya podés iniciar el juego.
    

### 📂 Opción B: Instalación Manual

1. **Extraé** el contenido del archivo comprimido.
    
2. Copiá la carpeta `gamedata` resultante.
    
3. **Pegala** dentro de la carpeta raíz de tu **S.T.A.L.K.E.R. Anomaly** (donde se encuentra el ejecutable `AnomalyDX11.exe`).
    
4. Si el sistema te pide fusionar carpetas, seleccioná **Sí a todo**.
    

> ℹ️ _Nota: Este mod es limpio y no sobrescribe ningún archivo nativo del juego._

## ⚙️ 4. Configuración (Menú MCM)

Si tenés instalado **MCM (Mod Configuration Menu)**, podés ajustar el comportamiento del mod en tiempo real desde las opciones del juego:

- **Probabilidad de Respuesta (%):** Un slider interactivo que va de `0%` a `100%` (en pasos de 5% en 5%).
    
    - **0%:** Desactiva por completo las respuestas de los NPCs (solo verás tus propios reportes).
        
    - **40% (Por defecto):** El equilibrio recomendado para mantener el realismo sin saturar la PDA de spam.
        
    - **100%:** Los NPCs responderán siempre que haya un emisor válido en el mapa (ideal para testeos).
        

> 💡 **Compatibilidad:** Si no usás MCM, el mod lo detectará de forma segura y aplicará automáticamente el valor predeterminado del **40%** sin generar errores ni _crashes_.

## ✍️ 5. Localización y Expansión (XML)

Podés editar y agregar tus propias frases abriendo los archivos de la carpeta `gamedata/configs/text/` con cualquier editor de texto plano (como _Notepad++_ o _VS Code_).

### ⚠️ Regla de Oro para el Reporte del Jugador

_(Textos de estado: Amistoso, Neutral, Enemigo, Víctima)_

El script inyecta exactamente tres parámetros en tus textos. Debés usar **exactamente tres modificadores `%s`** (sin números ni signos de pesos), respetando estrictamente el orden de izquierda a derecha:

|**Modificador**|**Información que inyecta**|
|---|---|
|**Primer `%s`**|Nombre del fallecido.|
|**Segundo `%s`**|Mapa / Zona actual (Ej: _Cordon_).|
|**Tercer `%s`**|Nombre de la facción del fallecido.|

**Ejemplo de plantilla válida:**

XML

```
<string id="st_pjnews_amistoso_1">
    <text>Encontré el cuerpo de %s en %s. Descansa en paz, camarada de %s.</text>
</string>
```

### 💬 Regla para las Respuestas de los NPCs (`st_pjnews_respuestas.xml`)

Para las respuestas de los _stalkers_ que te escuchan por la radio, **el orden de las variables cambia**. Aquí sí está permitido (y se recomienda) indexar los parámetros para estructurar la frase como prefieras:

|**Variable**|**Información que representa**|
|---|---|
|**`%1$s`**|Tu nombre de jugador.|
|**`%2$s`**|Zona / Mapa actual.|
|**`%3$s`**|Nombre del fallecido.|

**Ejemplo de plantilla de respuesta válida:**

XML

```
<string id="st_pjnews_respuesta_amistoso_1">
    <text>¡No puede ser! Recibido %1$s, gracias por el aviso. Pobre pibe, cuidate el lomo en %2$s.</text>
</string>
```

