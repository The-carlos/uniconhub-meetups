# Cómo trabajamos en este repo

Este repo es la **planeación viva** de las UniconHub Devs Meetups. El objetivo es
preparar cada edición de forma ordenada y con una sola persona que da el visto
bueno final.

## Reglas base

1. **`main` = verdad aprobada.** Nunca se commitea directo a `main`; todo entra por Pull Request.
2. **Ramas pequeñas, un tema por PR.** Nombra la rama por el entregable:
   - `edNN/objective`, `edNN/itinerary`, `edNN/bienvenida` — para una edición
   - `identidad/...` — para las slides 1–6 del `protocolo-de-bienvenida.md`
   Un PR debe poder revisarse en pocos minutos.
3. **VoBo de Roni.** En cada PR:
   - Rellena el checklist de la plantilla de PR.
   - Asigna a **Roni** como reviewer.
   - Mergea (squash) **solo** después de su `Approve`. Ese Approve es el VoBo.
4. **Idioma:** español. Los taglines de marca en inglés ("Build. Connect. Repeat.") se dejan tal cual.

## Ciclo de vida de una edición

1. **Crear la carpeta** copiando la plantilla:
   ```bash
   cp -R _template 05-noviembre-meetup   # ajusta número y mes
   ```
2. **`objective.md`** — el "por qué": tema, público, objetivos medibles. Se aprueba primero.
3. **`itinerary.md`** — el "cómo y cuándo": fecha, venue, agenda, speakers, logística.
4. **Speakers** — confirmar y reflejarlos en `itinerary.md`.
5. **Taggear el deck de la edición anterior** antes de tocarlo:
   ```bash
   git tag ed04-bienvenida <commit-del-deck-final-de-la-04>
   git push origin ed04-bienvenida
   ```
   Anota el tag en el `README.md` de esa edición.
6. **`protocolo-de-bienvenida.md`** (raíz) — actualizar las **slides 7 en adelante** para
   esta edición: planos de emergencia del nuevo venue (subir imágenes a `venues/<host>/`) y
   la slide "Gracias a nuestro host".
7. **`bienvenida-extra.md`** de la carpeta — solo si la edición necesita slides extra: se
   redactan ahí y, ya aprobadas, se pegan en el deck de la raíz antes de "Gracias a nuestro host".
8. **Post-evento** — retro y enlaces (fotos, episodio de podcast, artículos de blog)
   en el `README.md` de la edición.

Marca cada paso en el checklist del `README.md` de la edición.

## El deck de bienvenida

Hay **un solo** `protocolo-de-bienvenida.md`, en la raíz. Es el deck que se proyecta en cada
meetup; **no hay copias por edición**.

- **Slides 1–6** = identidad de UniconHub (portada, qué es, origen, energía, iniciativas,
  protocolo de emergencia genérico). Cambian solo por rama `identidad/...` + PR + VoBo de Roni.
- **Slides 7 en adelante** = planos del venue, gracias al host y extras. Se reemplazan al
  preparar cada edición (rama `edNN/bienvenida` + PR). En cualquier momento el archivo
  refleja la **próxima** edición.
- El deck exacto de una edición pasada se recupera de su tag:
  `git show ed04-bienvenida:protocolo-de-bienvenida.md`.

## Generar slides

```bash
# desde la raíz del repo
npx @marp-team/marp-cli@latest protocolo-de-bienvenida.md --theme-set theme/uniconhub.css --pdf --allow-local-files
```

Antes de pedir review, verifica que el deck compila sin errores si lo tocaste.
