# SEO Completo — CEOSA

#tag/seo #tag/sitemap #tag/meta #tag/analytics #tag/tracking #tag/keywords #tag/urls

DOMINIO:: ortopedasdepanama.com
PLATAFORMA:: WordPress (probable)
ÚLTIMA_VERIFICACIÓN:: 2026-04-25
FUENTE:: Consolidado desde Sitemap, Meta y Estructura, Analytics y Tracking

---

## Mapa Rápido SEO

| Área                    | Estado           | Prioridad  |
| ----------------------- | ---------------- | ---------- |
| URLs / Sitemap          | ✅ Documentado   | 🔴 Crítica |
| Meta Tags               | ⚠️ Estimados     | 🔴 Crítica |
| Schema Markup           | ❌ No confirmado | 🔴 Crítica |
| Google Business Profile | ⚠️ Verificar     | 🔴 Crítica |
| Analytics GA4           | ⚠️ Verificar     | 🟡 Alta    |
| Search Console          | ⚠️ Verificar     | 🟡 Alta    |
| Core Web Vitals         | ❌ Sitio lento   | 🔴 Crítica |

---

## URLs Completas del Sitio

```
HOME
https://ortopedasdepanama.com/

DOCTORES / ESPECIALISTAS
https://ortopedasdepanama.com/doctores/
https://ortopedasdepanama.com/especialistas/

SERVICIOS
https://ortopedasdepanama.com/especialista-en-rodilla-en-panama/
https://ortopedasdepanama.com/especialista-en-cadera-y-pelvis-en-panama/
https://ortopedasdepanama.com/especialista-en-hombro-y-codo-en-panama/
https://ortopedasdepanama.com/especialista-en-mano-y-muneca-en-panama/
https://ortopedasdepanama.com/especialista-en-pie-y-tobillo-en-panama/
https://ortopedasdepanama.com/especialista-en-medicina-deportiva-en-panama/
https://ortopedasdepanama.com/especialista-en-columna-vertebral-en-panama/
https://ortopedasdepanama.com/traumatologia-general/
https://ortopedasdepanama.com/cirugia-articular-y-reemplazos/

PERFILES DOCTORES
https://ortopedasdepanama.com/dr-edmundo-ford/
https://ortopedasdepanama.com/dr-edmundo-ford-mora/
https://ortopedasdepanama.com/dr-olmedo-varela/
https://ortopedasdepanama.com/dr-luis-fuentes/
https://ortopedasdepanama.com/dra-jolieanne-marxen/
https://ortopedasdepanama.com/dra-marisol-nikolaev/
https://ortopedasdepanama.com/dr-octavio-mendez/
https://ortopedasdepanama.com/dr-jaime-aleman/
https://ortopedasdepanama.com/dr-alessandro-alessandria/
https://ortopedasdepanama.com/dr-bolivar-franco/
https://ortopedasdepanama.com/dra-karla-vargas/

BLOG
https://ortopedasdepanama.com/blog/

CONTACTO
https://ortopedasdepanama.com/contacto/

CITAS
https://ortopedasdepanama.com/citas/ (o link externo Cliniweb)

SITEMAP XML (probable)
https://ortopedasdepanama.com/sitemap.xml
```

### URLs Externas CEOSA

```
CLINIWEB (CITAS ONLINE)
https://www.cliniweb.com/ortopedas-de-panama-ceosa/
https://www.cliniweb.com/dr-edmundo-ford-sosa/

SITIOS PERSONALES DOCTORES
https://doctoredford.com/           ← Dr. Edmundo Ford Mora (cuatrilingüe ES/EN/FR/PT)
https://drolmedovarela.com/          ← Dr. Olmedo Varela (trilingüe ES/EN/PT)

GOOGLE BUSINESS PROFILE
https://maps.google.com/?cid=CEOSA (verificar CID)

FACEBOOK
https://www.facebook.com/EspecialidadesOrtopedicasPA/

INSTAGRAM
https://www.instagram.com/especialidadesortopedicaspa/

CHEKIAO
https://chekiao.com/listing/edmundo-ford-sosa/

BUPA NETWORK
https://contenidos.bupasalud.com/en/jolieanne-ysabel-marxen-ruiz
```

### Patrón URL — Análisis SEO

- `/especialista-en-rodilla-en-panama/` — Keyword geolocalizada en URL ✅
- `/especialista-en-hombro-y-codo-en-panama/` — Keyword long-tail ✅
- `/especialista-en-medicina-deportiva-en-panama/` — Competitiva y clara ✅
- `/muneca/` en lugar de `/muñeca/` — manejo correcto de caracteres especiales ✅
- ⚠️ BUG CONFIRMADO: "Especialista en Columna" en menú enlaza a `/cirugia-de-la-mano-en-panama/`

---

## Meta Tags (Estimados por Página)

### Homepage

```html
<title>
  Centro de Especialidades Ortopédicas | Ortopedas en Panamá | CEOSA
</title>
<meta
  name="description"
  content="CEOSA - Centro de Especialidades Ortopédicas en Panamá. Especialistas en rodilla, cadera, hombro, columna, pie y cirugía deportiva. Hospital San Fernando."
/>
<meta
  name="keywords"
  content="ortopedia panama, traumatología panama, cirugía rodilla panama, reemplazo cadera panama, ortopeda panamá"
/>
```

### Página Rodilla

```html
<title>Especialista en Rodilla en Panamá | Dr. Edmundo Ford | CEOSA</title>
<meta
  name="description"
  content="Especialista en cirugía de rodilla en Panamá. Reemplazo total, artroscopía, LCA, menisco. Hospital San Fernando. Citas disponibles."
/>
```

### Página Cadera

```html
<title>Especialista en Cadera y Pelvis en Panamá | CEOSA</title>
<meta
  name="description"
  content="Cirugía de cadera en Panamá. Reemplazo total, artroscopía, FAI, fractura cadera. Dr. Ford Mora, Dr. Olmedo Varela. Hospital San Fernando."
/>
```

---

## Schema Markup (Structured Data)

### LocalBusiness / MedicalClinic

```json
{
  "@context": "https://schema.org",
  "@type": "MedicalClinic",
  "name": "Centro de Especialidades Ortopédicas (CEOSA)",
  "url": "https://ortopedasdepanama.com",
  "telephone": "+507-229-3779",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "Hospital San Fernando, Vía España",
    "addressLocality": "Panamá",
    "addressCountry": "PA"
  },
  "medicalSpecialty": "Orthopedic Surgery",
  "openingHoursSpecification": [
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday"],
      "opens": "08:00",
      "closes": "17:00"
    }
  ]
}
```

### Physician Schema (Por Doctor)

```json
{
  "@context": "https://schema.org",
  "@type": "Physician",
  "name": "Dr. Edmundo Ford Sosa",
  "medicalSpecialty": "Orthopedic Surgery",
  "worksFor": {
    "@type": "MedicalClinic",
    "name": "Centro de Especialidades Ortopédicas"
  },
  "alumniOf": "Universidad Autónoma de Guadalajara"
}
```

---

## Keywords Objetivo

### Keywords Principales

| Keyword                     | Intención               | Competencia | Prioridad  |
| --------------------------- | ----------------------- | ----------- | ---------- |
| ortopeda panamá             | Informacional/Comercial | Alta        | 🔴 Crítica |
| especialista rodilla panamá | Comercial               | Media       | 🔴 Crítica |
| cirugía rodilla panamá      | Transaccional           | Media       | 🔴 Crítica |
| reemplazo rodilla panamá    | Transaccional           | Baja        | 🟡 Alta    |
| reemplazo cadera panamá     | Transaccional           | Baja        | 🟡 Alta    |
| artroscopía rodilla panamá  | Transaccional           | Baja        | 🟡 Alta    |
| dolor rodilla panamá        | Informacional           | Alta        | 🟢 Media   |
| médico deportivo panamá     | Comercial               | Media       | 🟡 Alta    |
| hombro congelado panamá     | Informacional           | Baja        | 🟢 Media   |
| túnel carpiano panamá       | Informacional/Comercial | Media       | 🟡 Alta    |
| columna vertebral panamá    | Informacional           | Alta        | 🟢 Media   |
| pie plano adulto panamá     | Informacional           | Baja        | 🟢 Media   |

### Keywords Long-tail (Oportunidades)

- "especialista en cadera joven panamá"
- "ruptura LCA cirugía panamá"
- "prótesis rodilla costo panamá"
- "ortopeda acepta ASSA panamá"
- "ortopeda habla inglés panamá"
- "cirugía hombro mínima invasiva panamá"
- "knee replacement Panama" (inglés para expats)
- "hip replacement Panama doctor" (turismo médico)

---

## Google Business Profile (GBP)

### Datos a Mantener Actualizados

```
NOMBRE:: Centro de Especialidades Ortopédicas
CATEGORÍA_PRIMARIA:: Clínica ortopédica
CATEGORÍAS_SECUNDARIAS:: Traumatólogo, Cirujano ortopédico, Médico especialista en deporte
DIRECCIÓN:: Hospital San Fernando, Vía España, Panamá Ciudad
TELÉFONO:: (507) 229-3779
WEB:: https://ortopedasdepanama.com
HORARIO:: L-V 8:00–17:00
FOTOS:: ≥10 fotos (consultorio, doctores, procedimientos)
RESEÑAS:: Responder 100% de reseñas (positivas y negativas)
POSTS_GBP:: 1x semana (tips de salud, servicios)
```

### Importancia SEO Local

Consistencia NAP en GBP + InfoGuía + sitio web = mejor posición en Google Maps.

```
NAP (Name Address Phone) CEOSA:
NAME:: Centro de Especialidades Ortopédicas
ADDRESS:: Hospital San Fernando, Vía España, Panamá
PHONE:: (507) 229-3779
WEB:: https://ortopedasdepanama.com
```

---

## Análisis On-Page

### Fortalezas SEO

- URLs limpias y descriptivas con keywords geolocalizadas
- Cada especialidad tiene su propia página (arquitectura de silo)
- Dominio con keyword "ortopedas" + "panama"
- Blog activo → señales de contenido fresco
- Sitios personales de doctores generan backlinks naturales

### Oportunidades de Mejora

- **Schema markup** — Implementar Physician + MedicalClinic (no confirmado activo)
- **Velocidad de carga** — Sitio lento (timeouts en scraping) → CDN, optimizar imágenes
- **Core Web Vitals** — LCP, FID, CLS
- **HTTPS** — Verificar certificado SSL activo
- **Blog frecuencia** — Mínimo 2 artículos/mes para señales de frescura

---

## Analytics y Tracking

### Google Analytics 4 (GA4) — Eventos a Trackear

```javascript
// Click en número de teléfono
gtag("event", "click_telefono", {
  event_category: "contacto",
  event_label: "header_phone",
});

// Click en "Agendar Cita" (botón Cliniweb)
gtag("event", "click_cita", {
  event_category: "conversion",
  event_label: "boton_citas_cliniweb",
});

// Formulario de contacto enviado
gtag("event", "form_submit", {
  event_category: "leads",
  event_label: "formulario_contacto",
});
```

### Google Search Console — Keywords Monitoreadas

- "ortopeda panamá" — Objetivo posición <10
- "especialista rodilla panamá" — Objetivo posición <5
- "reemplazo rodilla panamá" — Objetivo posición <5

### Google Tag Manager (GTM) — Tags Recomendados

- GA4 base tag
- Pixel Facebook Ads
- Hotjar / Microsoft Clarity (mapas de calor)
- Conversion tracking Google Ads

---

## KPIs — Métricas Objetivo

### Adquisición

| Métrica                          | Objetivo 6 meses |
| -------------------------------- | ---------------- |
| Sesiones orgánicas/mes           | +30%             |
| Posición media "ortopeda panamá" | Top 5            |
| CTR promedio                     | >6%              |

### Conversión

| Métrica                       | Objetivo |
| ----------------------------- | -------- |
| Clics en teléfono / sesión    | >2%      |
| Formularios enviados / mes    | >20      |
| Citas Cliniweb originadas web | >15/mes  |
| Tasa rebote homepage          | <55%     |

### Blog

| Métrica                  | Objetivo |
| ------------------------ | -------- |
| Artículos nuevos / mes   | ≥2       |
| Backlinks generados      | ≥2/mes   |
| Páginas indexadas en GSC | +5/mes   |

---

## Campañas de Pago

### Google Ads — Keywords

```
BÚSQUEDA EXACTA:
[cirugía rodilla panamá]
[reemplazo rodilla panamá]
[ortopeda panamá]
[artroscopía rodilla panamá]

NEGATIVAS: gratis, gratuito, trabajo, empleo, carrera

EXTENSIONES: Llamada, Ubicación, Sitelinks (rodilla, cadera, hombro, contacto)
```

### Meta Ads (Facebook + Instagram)

```
AUDIENCIAS:
- Residentes Panama Ciudad + Panama Oeste 40+ años
- Intereses: salud, bienestar, artritis, deporte
- Lookalike de lista de pacientes

FORMATOS:
- Video testimonial (mayor conversión)
- Carrusel servicios
- Single image "¿Tiene dolor de rodilla?" → CTA "Agendar consulta"
```

### Pixel Facebook

```javascript
fbq("track", "ViewContent", {
  content_name: "Especialista en Rodilla",
  content_category: "ortopedia",
});
fbq("track", "Lead", { content_name: "Formulario Contacto" });
```

---

## Reporte Mensual Sugerido

```
FECHA:: [mes/año]
SESIONES_ORGÁNICAS:: X (vs mes anterior: +X%)
POSICIÓN_KEYWORDS_CLAVE::
  - ortopeda panamá: posición X
  - especialista rodilla panamá: posición X
LEADS_FORMULARIO:: X
CLICS_TELÉFONO:: X
CITAS_CLINIWEB_WEB:: X
TOP_PÁGINAS::
  1. /especialista-en-rodilla-en-panama/
  2. /especialista-en-cadera/
ACCIONES_TOMADAS:: [cambios contenido, nuevas páginas]
```

---

[[README]] | [[RRSS]] | [[metodologia/Metodologia y Fuentes]] | [[raw/Google Search Raw Data]]
