# CIELO Interactivo — galaxias en tu computador

Explorador web del proyecto **CIELO** (simulaciones cosmológicas
hidrodinámicas; Tissera et al. 2025). Permite viajar en el tiempo cósmico y
ver cómo se forma y evoluciona una galaxia, con sus estrellas y su gas, a lo
largo de ~13.800 millones de años.

Corre **completamente en el navegador** (Python compilado a WebAssembly con
[voici](https://github.com/voila-dashboards/voici)): no hay que instalar nada
ni tener una cuenta.

### ▶ Probar

**https://cicasanueva.github.io/cielo-interactivo/voici/render/app.html**

(La primera carga tarda unos segundos en arrancar el motor de Python.)

## Qué se ve

- Una galaxia simulada del proyecto CIELO, época por época, con sus
  **estrellas** y su **gas** en colores distintos.
- Una línea de tiempo cósmica con hitos (Big Bang, primeras galaxias,
  mediodía cósmico, formación del Sol, hoy).
- La historia de la galaxia: masa estelar y ritmo de formación estelar
  frente a la edad del universo.
- Controles para mover el tiempo, cambiar el campo de visión, el modo de
  visualización y los colores.

Pensado como material de divulgación: público escolar y docentes.

## Estructura del repositorio

- `app.ipynb` — el notebook del explorador (numpy, scipy, matplotlib, ipywidgets)
- `environment.yml` — paquetes del kernel WebAssembly
- `data/` — datos livianos: posiciones de partículas por época y cosmología
  precalculada (`meta.json`)
- `docs/` — sitio estático que sirve GitHub Pages

## Reconstruir el sitio

El sitio se genera con `voici` a partir del notebook y los datos:

```bash
voici build --contents . --output-dir docs
```

Luego GitHub Pages publica la carpeta `docs/`.

## Créditos

Datos: simulaciones cosmológicas **CIELO** (Tissera et al. 2025).

Desarrollado en el marco de la postulación a la *ALMA Fund for the
Development of Chilean Astronomy 2026* (categoría Difusión).
