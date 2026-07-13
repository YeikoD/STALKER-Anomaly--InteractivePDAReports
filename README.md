🔧 Instalación
Con Mod Organizer 2 (Recomendado):
Descargá el archivo comprimido del mod.

Hacé clic en el icono de instalar nuevo mod desde archivo en MO2.

Activá PJNews Interactive en tu lista de la izquierda.

¡Listo! Iniciá el juego.

Instalación Manual:
Extraé el contenido del archivo comprimido.

Copiá la carpeta gamedata y pegala dentro del directorio raíz de tu instalación de S.T.A.L.K.E.R. Anomaly (donde se encuentra el ejecutable AnomalyDX11.exe).

Reemplazá si te lo solicita (no debería pisar ningún archivo base).

✍️ Cómo añadir tus propias frases (XML)
¡Es sumamente fácil expandir los diálogos! Podés abrir cualquiera de los XML de la carpeta text/spa/ con un editor de texto (como Notepad++) y añadir strings numerados.

Regla de Oro para Reportes (Amistoso, Neutral, Enemigo, Víctima):
Los tres comodines %s que usa el motor se inyectan estrictamente en este orden:

%s (Primer parámetro) -> Nombre del Fallecido.

%s (Segundo parámetro) -> Mapa / Zona actual.

%s (Tercer parámetro) -> Nombre de la Facción del fallecido.

Ejemplo:

XML
<string id="st_pjnews_amistoso_1">
    <text>Encontré el cuerpo de %s en %s. Descansa en paz, camarada de %s.</text>
</string>
⚠️ ¡Atención! No uses indexadores como %1$s o %2$s en los diálogos del reporte del jugador. El formateador clásico de Lua en Anomaly dará un error fatal de string. Mantén siempre el formato clásico de tres %s planos de izquierda a derecha.

🤝 Créditos y Agradecimientos
Desarrollador Principal: YeikoD

Inspirado en la atmósfera cruda y viva de la Zona de S.T.A.L.K.E.R.

Agradecimientos a la comunidad de modding de Anomaly por las librerías de callbacks y la documentación de la API MCM.

Que la Zona los tenga en su gloria, stalkers. ¡Buena caza!
"""
