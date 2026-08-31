# Cómo trabajamos en este repo

Este repo es la **planeación viva** de las UniconHub Devs Meetups. El objetivo es
preparar cada edición de forma ordenada y con una sola persona que da el visto
bueno final.

## Reglas base

1. **`main` = verdad aprobada.** Nunca se commitea directo a `main`; todo entra por Pull Request.
2. **Ramas pequeñas, un tema por PR.** Nombra la rama por el entregable:
   - `ed04/objective`, `ed04/itinerary`, `ed04/bienvenida` — para una edición
   - `identidad/...` — para el deck maestro `protocolo-de-bienvenida.md`
   Un PR debe poder revisarse en pocos minutos.
3. **VoBo de Roni.** En cada PR:
   - Rellena el checklist de la plantilla de PR.
   - Asigna a **Roni** como reviewer.
   - Mergea (squash) **solo** después de su `Approve`. Ese Approve es el VoBo.
4. **Idioma:** español. Los taglines de marca en inglés ("Build. Connect. Repeat.") se dejan tal cual.

## Ciclo de vida de una edición

1. **Crear la carpeta** copiando la plantilla:
   ```bash
   cp -R _template 04-september-meetup
   cp protocolo-de-bienvenida.md 04-september-meetup/
   ```
2. **`objective.md`** — el "por qué": tema, público, objetivos medibles. Se aprueba primero.
3. **`itinerary.md`** — el "cómo y cuándo": fecha, venue, agenda, speakers, logística.
4. **Speakers** — confirmar y reflejarlos en `itinerary.md`.
5. **`protocolo-de-bienvenida.md`** de la carpeta — personalizar **solo las slides 6 y 7**
   (protocolo de emergencia con datos del venue · agradecimiento al host).
6. **Post-evento** — retro y enlaces (fotos, episodio de podcast, artículos de blog)
   en el `README.md` de la edición.

Marca cada paso en el checklist del `README.md` de la edición.

## El deck maestro de bienvenida

`protocolo-de-bienvenida.md` en la raíz es la fuente de las **slides 1–5** (identidad
de UniconHub). Cambios ahí van en una rama `identidad/...` y también necesitan VoBo de Roni.

Cada edición trabaja sobre **su propia copia**. Si el maestro cambia después de una
edición ya realizada, esa edición queda como **registro histórico** y no se re-sincroniza.

## Generar slides

```bash
# desde la raíz del repo
npx @marp-team/marp-cli@latest <archivo>.md --theme-set theme/uniconhub.css --pdf --allow-local-files
```

Antes de pedir review, verifica que cualquier deck Marp que hayas tocado compila sin errores.
