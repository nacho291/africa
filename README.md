# Atlas de África 🗺️

Mapa interactivo para estudiar los **55 países de África y sus capitales**, pensado para usarse desde el móvil. Un solo archivo HTML, sin dependencias ni backend.

## Modos de estudio

| Modo | Qué hace |
|------|----------|
| **Explorar** | Tocas un país y ves su nombre y su capital. El mapa se va tiñendo de verde con lo que ya dominas. |
| **Localizar** | Te dice un país y tienes que tocarlo en el mapa. |
| **Nombrar** | Se ilumina un país y eliges su nombre entre cuatro opciones. |
| **Capitales** | Preguntas de país → capital y de capital → país (tocando el mapa). |

Las islas pequeñas (Cabo Verde, Santo Tomé y Príncipe, Comoras, Mauricio y Seychelles) aparecen como puntos grandes para que se puedan tocar. Se puede hacer zoom con dos dedos y mover el mapa arrastrando.

## Puntuación

- Rondas de **10 preguntas**, con hasta 3 intentos por pregunta.
- **100 puntos** si aciertas a la primera, 60 a la segunda, 30 a la tercera.
- **Bonus de rapidez** de hasta +50 y **bonus de racha** de hasta +50.
- Al terminar: estrellas (1 a 3), aciertos a la primera, mejor racha, repaso de fallos y récord por modo.
- Cada país tiene un **nivel de dominio** (0 a 3): sube al acertar a la primera y se reinicia si fallas tres veces. Un país cuenta como dominado a partir del nivel 2.
- Las preguntas priorizan los países menos dominados, así que la ronda se adapta a lo que te cuesta.
- Rangos según países dominados: Novato → Aprendiz (8) → Explorador (20) → Cartógrafo (35) → Maestro de África (50).

El progreso se guarda en el propio dispositivo (`localStorage`); no hay cuentas ni servidor.

## Despliegue

Está publicado en **Netlify** como sitio estático, sin paso de build. La configuración está en `netlify.toml`.

Para desplegar tu propia copia:

1. Haz un fork de este repositorio.
2. En [app.netlify.com/start](https://app.netlify.com/start), elige **GitHub** y selecciona el repositorio.
3. Deja el comando de build vacío y el directorio de publicación en `.` (ya viene en `netlify.toml`) y pulsa **Deploy**.

Cada cambio que se sube a `main` se publica automáticamente.

También funciona en GitHub Pages (Settings → Pages → rama `main`, carpeta `/ (root)`) o en cualquier hosting estático. Para probarlo en local basta con abrir `index.html` en el navegador.

## Estructura

```
index.html   La aplicación completa (HTML + CSS + JS + geometría del mapa)
netlify.toml Configuración de Netlify
LICENSE      Licencia MIT
README.md
```

## Personalización

Todo está en `index.html`:

- La lista de países y capitales está en la constante `C` (código ISO → `[nombre, capital]`).
- `FICHA` marca los países cuya capital aparece en la ficha del colegio (se muestran con ★ en Explorar).
- `ROUND` controla el número de preguntas por ronda.
- Los colores están definidos como variables CSS en `:root`, con versión clara y oscura.

## Licencia

Publicado bajo licencia MIT: puedes usarlo, copiarlo y modificarlo libremente. Consulta el archivo [LICENSE](LICENSE).

## Créditos

- Geometría de los países: [Natural Earth](https://www.naturalearthdata.com/) (dominio público) a través de [world-atlas](https://github.com/topojson/world-atlas), proyectada con d3-geo.
- Nombres en español según la ficha escolar de Anaya, con las capitales completadas.
