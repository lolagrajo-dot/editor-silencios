# 🎬 Editor de silencios

Web que **une varios clips de video en uno solo** y **elimina automáticamente los silencios** (pausas) de cada clip.

👉 **Abrir la web:** https://lolagrajo-dot.github.io/editor-silencios/

Todo el procesamiento ocurre **dentro del navegador** con [ffmpeg.wasm](https://ffmpegwasm.netlify.app/): tus videos **no se suben a ningún servidor**. La función opcional de título con IA envía solo unos fotogramas y un fragmento de audio a Google Gemini.

## Cómo se usa

1. Abre la web y arrastra tus videos (o haz clic para elegirlos).
2. Revisa el orden de los clips (se ordenan por nombre de archivo; puedes cambiarlo con ↑ ↓).
3. Pulsa **1 · Analizar silencios** y revisa el plan de corte.
4. Pulsa **2 · Generar video unido** y espera (en el navegador tarda más que un programa nativo).
5. Reproduce el resultado y pulsa **Descargar MP4**.
6. Opcional: añade tu clave de Gemini y pulsa **Regenerar** para que la IA vea el video y proponga **título y hashtags**.

## Título y hashtags con IA (opcional)

- Consigue una clave gratuita en [Google AI Studio](https://aistudio.google.com/apikey).
- Pégala en la tarjeta **✨ Título y hashtags** y pulsa **Guardar clave**.
- La clave se guarda **solo en tu navegador** (`localStorage`); no está dentro de la web ni se envía a ningún servidor nuestro.
- Para deducir el tema se envían a Google Gemini **6 fotogramas y hasta 60 s de audio** del video unido. El archivo completo no se sube.
- Después puedes editar el título y los hashtags y copiarlos con un clic. Si no configuras la clave, la web sugiere un título básico sin IA.

## Ajustes

| Ajuste | Descripción |
|---|---|
| Preset | Suave / Normal / Agresivo (tiempo mínimo de pausa a eliminar) |
| Umbral de silencio (dB) | Nivel de volumen por debajo del cual se considera silencio |
| Pausa mínima (s) | Duración mínima de la pausa para recortarla |
| Margen (s) | Aire que se conserva a cada lado del corte |
| Resolución de salida | 720×1280 (rápido) o 1080×1920 (máxima) |
| Calidad | Rápida / Estándar / Alta (más calidad = más tiempo de proceso) |

## Consejos

- La primera vez tarda unos segundos en cargar el motor (~32 MB) y luego queda en caché.
- Si tus videos tienen música de fondo o ruido constante, sube el umbral (por ejemplo −25 dB) o usa el preset **Agresivo**.
- Salida: MP4 vertical 720×1280 a 24 fps (ideal para TikTok / Reels / Shorts); puedes elegir 1080×1920. Los videos horizontales se adaptan con bandas.

## Créditos

Hecho con [ffmpeg.wasm](https://github.com/ffmpegwasm/ffmpeg.wasm). Sin servidores, sin subidas, sin registro.
