# uniconhub-meetups

Planeación y documentación de cada edición de las **UniconHub Devs Meetups**.

UniconHub es una comunidad de jóvenes en tecnología (México · Colombia · Argentina).
Sitio: <https://uniconhub.org> · "Build. Connect. Repeat."

## Estructura del repo

```
protocolo-de-bienvenida.md   Deck MAESTRO de bienvenida (Marp). Slides 1–6 estables.
theme/uniconhub.css          Tema Marp de la comunidad.
venues/<host>/               Planos y material de emergencia por venue (reutilizable).
_template/                    Se copia para arrancar una edición nueva.
NN-mes-meetup/                Una carpeta por edición (prefijo = número de edición).
  ├── README.md              Índice + checklist de estado de la edición.
  ├── objective.md           El "por qué" de esa edición.
  ├── itinerary.md           El "cómo y cuándo": agenda, speakers, logística.
  └── protocolo-de-bienvenida.md   Copia del maestro con slides 7 (planos) y 8 (host).
CONTRIBUTING.md              Cómo trabajamos aquí (ramas, PRs, VoBo de Roni).
```

## Cómo trabajamos

`main` es la verdad aprobada. Todo entra por **Pull Request** y cada PR necesita
el **VoBo de Roni** antes de mergear. Detalles en [CONTRIBUTING.md](CONTRIBUTING.md).

## Generar las slides

Con [Marp](https://marp.app/) vía `npx` (no hace falta instalar nada):

```bash
# desde la raíz del repo
npx @marp-team/marp-cli@latest protocolo-de-bienvenida.md \
  --theme-set theme/uniconhub.css --pdf --allow-local-files
# también: --pptx  |  --html
```

En VS Code: extensión **Marp for VS Code** para preview en vivo.

## Empezar una edición nueva

```bash
cp -R _template 05-noviembre-meetup     # ajusta el número y el mes
cp protocolo-de-bienvenida.md 05-noviembre-meetup/
# luego: llena objective.md → itinerary.md → personaliza slides 7 (planos) y 8 (host)
```
