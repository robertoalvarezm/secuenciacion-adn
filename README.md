# 🧬 Guía Visual de la Secuenciación del ADN — Sitio Quarto

Sitio web académico sobre los cinco métodos fundamentales de secuenciación del ADN.
Nivel: Maestría en Biología Molecular / Genómica.

---

## Estructura del Proyecto

```
secuenciacion-adn/
├── _quarto.yml          ← Configuración del sitio
├── styles.css           ← Estilos personalizados
├── index.qmd            ← Página de inicio
├── contexto.qmd         ← Proyecto Genoma Humano y costos
├── sanger.qmd           ← Secuenciación de Sanger
├── pirosecuenciacion.qmd ← Piroseucenciación 454
├── illumina.qmd         ← Illumina / SBS
├── pacbio.qmd           ← PacBio SMRT
├── nanoporos.qmd        ← Nanoporos (ONT)
├── comparacion.qmd      ← Tabla comparativa + línea de tiempo
├── curiosidades.qmd     ← 10 datos curiosos y raros
└── referencias.qmd      ← Referencias académicas
```

---

## Requisitos Previos

### 1. Instalar Quarto

Descarga e instala Quarto desde: https://quarto.org/docs/get-started/

**macOS (Homebrew):**
```bash
brew install quarto
```

**Windows / Linux:**
Descarga el instalador desde https://quarto.org/docs/get-started/

Verifica la instalación:
```bash
quarto --version
```
Debe mostrar `1.4.x` o superior.

### 2. (Opcional) R o Python para el gráfico de comparación

La página `comparacion.qmd` incluye un gráfico en R opcional.
Si no tienes R instalado, el gráfico simplemente no se renderizará pero
el resto del sitio funcionará perfectamente.

**Para instalar R:** https://www.r-project.org/

---

## Cómo Renderizar el Sitio

### Paso 1: Navega al directorio del proyecto

```bash
cd secuenciacion-adn
```

### Paso 2: Renderiza el sitio completo

```bash
quarto render
```

Esto generará el sitio en la carpeta `_site/`.

### Paso 3: Abre el sitio en tu navegador

**Opción A — Vista previa en vivo (recomendado):**
```bash
quarto preview
```
Abre automáticamente el navegador y recarga el sitio al guardar cambios.

**Opción B — Abrir directamente:**
```bash
open _site/index.html        # macOS
start _site/index.html       # Windows
xdg-open _site/index.html    # Linux
```

---

## Publicar en GitHub Pages (Opcional)

Si quieres publicar el sitio en línea gratuitamente:

```bash
# 1. Renderiza el sitio
quarto render

# 2. Publica en GitHub Pages
quarto publish gh-pages
```

O en Quarto Pub (gratuito):
```bash
quarto publish quarto-pub
```

---

## Personalización

### Cambiar el tema
En `_quarto.yml`, modifica la línea:
```yaml
theme: [cosmo, styles.css]
```
Temas disponibles de Bootswatch: `cosmo`, `flatly`, `litera`, `lux`, `minty`, `pulse`, `sandstone`, `simplex`, `sketchy`, `slate`, `solar`, `spacelab`, `superhero`, `united`, `yeti`.

### Agregar páginas
1. Crea un nuevo archivo `.qmd`
2. Agrégalo al menú en `_quarto.yml` bajo `website > navbar`

### Cambiar colores
Edita `styles.css`. Las variables principales están al inicio:
```css
:root {
  --navy:  #0F2044;
  --blue:  #1565C0;
  --gold:  #C9A232;
  /* ... */
}
```

---

## Contenido Incluido

| Sección | Contenido |
|---------|-----------|
| Inicio | Overview, stats clave, video introductorio |
| Contexto | HGP, "guerra genómica", revolución del costo |
| Sanger | Fred Sanger, Ray Wu, Plus-Minus, ddNTPs, automatización |
| Piroseucenciación 454 | Nyren, cascada PPi→luciferasa, GS20, legado |
| Illumina | Solexa, flow cell, bridge amplification, aplicaciones |
| PacBio SMRT | ZMWs, SMRTbell, rolling-circle, long reads |
| Nanoporos | α-hemolisina, ONT, MinION, IA/basecalling |
| Comparación | Tabla, guía de uso, línea de tiempo completa (1955–2021) |
| Curiosidades | 10 datos sorprendentes verificados |
| Referencias | 20 artículos científicos primarios + recursos online |

---

## Problemas Comunes

**Error: "quarto not found"**
→ Quarto no está en el PATH. Reinicia la terminal o sigue las instrucciones del instalador.

**El gráfico de comparación no aparece**
→ Instala R o simplemente elimina el bloque ```{r} en `comparacion.qmd`.

**Los videos no cargan**
→ Necesitas conexión a internet. Los videos están embebidos desde YouTube.

**El sitio se ve sin estilo**
→ Asegúrate de que `styles.css` esté en el mismo directorio que `_quarto.yml`.

---

## Créditos

- **Contenido científico:** Asimov Press & Evan DeTurk (2026)
- **Estructura del sitio:** Generado con [Quarto](https://quarto.org)
- **Videos:** YouTube — canales de Illumina, PacBio, Oxford Nanopore, NHGRI
- **Tema base:** Cosmo (Bootswatch)
