# Sitio Principal ortopedasdepanama.com — DOM/Scrape Notes

#tag/raw #tag/scrape #tag/dom #tag/sitio-web

FUENTE:: ortopedasdepanama.com (scrape manual + Chrome MCP)
FECHA:: 2026-04-25
NOTA_TÉCNICA:: Sitio con carga lenta; Chrome MCP timeout frecuente. Datos reconstruidos de sesiones anteriores + conocimiento del dominio.

---

## Estructura del Sitio (Navegación Principal)

```html
HEADER_NAV: [Logo CEOSA] [Inicio] [Doctores / Especialistas] [Servicios] ├──
Especialista en Rodilla ├── Especialista en Cadera y Pelvis ├── Especialista en
Hombro y Codo ├── Especialista en Mano y Muñeca ├── Especialista en Pie y
Tobillo ├── Especialista en Medicina Deportiva ├── Especialista en Columna
Vertebral ├── Traumatología General └── Cirugía Articular y Reemplazos [Blog]
[Contacto] [Citas Online] ← CTA principal → Cliniweb
```

---

## Datos del Footer

```
FOOTER_CONTENT (reconstruido):
  Nombre empresa: Centro de Especialidades Ortopédicas
  Dirección: Hospital San Fernando, Vía España, Panamá
  Tel: (507) 229-3779 (o similar)
  Email: info@ortopedasdepanama.com (verificar)

  Links footer:
  - Política de privacidad
  - Términos y condiciones
  - Sitemap

  RRSS footer:
  - Facebook icon → link Facebook
  - Instagram icon → link Instagram
  - [Posiblemente WhatsApp, YouTube]

  Copyright: © 2024/2025 Centro de Especialidades Ortopédicas
```

---

## Homepage — Secciones Identificadas

### Hero Section

```
HEADLINE: "Especialistas en Ortopedia y Traumatología en Panamá"
SUBHEADLINE: "Centro de Especialidades Ortopédicas — Hospital San Fernando"
CTA_PRIMARIO: "Agendar Cita" → Cliniweb
BACKGROUND: Imagen médica / sala quirúrgica / hospital
```

### Sección Servicios (Grid)

```
SERVICIOS_GRID:
  [Rodilla] [Cadera] [Hombro] [Mano]
  [Pie y Tobillo] [Medicina Deportiva] [Columna] [Trauma]
  Cada card: ícono + nombre especialidad + link a página
```

### Sección Doctores (Grid)

```
DOCTORES_GRID: 10 perfiles en cards
  Cada card: Foto headshot + nombre + especialidad + link perfil
  ORDER (estimado):
  1. Dr. Edmundo Ford Sosa
  2. Dr. Edmundo Ford Mora
  3. Dr. Olmedo Varela
  4. Dr. Luis Fuentes
  5. Dra. Jolieanne Marxen
  6. Dra. Marisol Nikolaev
  7. Dr. Octavio Mendez
  8. Dr. Jaime Alemán
  9. Dr. Alessandro Alessandría
  10. Dr. Bolívar Franco
  (+Dra. Karla Vargas — verificar posición)
```

### Sección "¿Por qué elegirnos?" / Diferenciadores

```
BULLETS (estimado):
  ✓ Equipo multidisciplinario de 10+ especialistas
  ✓ Tecnología de última generación
  ✓ Hospital San Fernando (JCI acreditado)
  ✓ Cirugía mínimamente invasiva
  ✓ Citas online disponibles
  ✓ Aseguradoras principales aceptadas
```

### Sección Aseguradoras

```
LOGOS DE ASEGURADORAS:
  ASSA | Mapfre | Pan-American Life | SURA | Fedpa | Banistmo | [otras]
```

### Sección Blog (últimos artículos)

```
BLOG_PREVIEW: 3 últimos artículos
  Formato: Thumbnail + título + fecha + extracto + "Leer más"
```

### Sección Contacto / Ubicación

```
MAPA: Google Maps embed → Hospital San Fernando
FORMULARIO: Nombre, Email, Teléfono, Mensaje, Enviar
DATOS CONTACTO: Tel + Email + Dirección
```

---

## Páginas de Doctores — Estructura Tipo

```html
<h1>Dr. [Nombre] — [Especialidad]</h1>
<img src="foto-doctor.jpg" />
<section class="bio">
  <h2>Formación Académica</h2>
  <ul>
    <li>Médico Cirujano — [Universidad]</li>
    <li>Especialidad Ortopedia — [CSS/Hospital]</li>
    <li>Fellowship — [Institución internacional]</li>
  </ul>
</section>
<section class="servicios">
  <h2>Áreas de Especialización</h2>
  [lista de subespecialidades]
</section>
<section class="cita">
  <a href="cliniweb">Agendar Cita Online</a>
  <p>Tel: [número]</p>
</section>
```

---

## Performance del Sitio (Observaciones)

```
VELOCIDAD_CARGA:: Lenta (timeouts al scraper)
CAUSA_PROBABLE::
  - Imágenes sin optimizar (no WebP)
  - Sin CDN (directo servidor)
  - Hosting compartido posiblemente
  - Scripts bloqueo renderizado

HERRAMIENTA_VERIFICAR:: Google PageSpeed Insights
URL_TEST:: https://pagespeed.web.dev/analysis?url=ortopedasdepanama.com

IMPACTO_SEO::
  - Core Web Vitals posiblemente bajos
  - LCP (Largest Contentful Paint) probablemente >4s
  - Penalización SEO posible por velocidad

RECOMENDACIÓN::
  - CDN (Cloudflare gratuito)
  - Optimizar imágenes (WebP + lazy load)
  - Minificar CSS/JS
  - Cache de servidor
```

---

## Links Internos

- [[Sitemap CEOSA]] | [[Meta Tags y Estructura SEO]] | [[Analytics y Tracking]]
