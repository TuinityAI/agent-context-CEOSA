# INDEX.md — Guía de Scraping para Agentes (CEOSA Vault)

> **Propósito:** índice operativo, orientado a terminal, para que agentes IA (y humanos)
> localicen, filtren y extraigan información del workspace usando `rg` (ripgrep),
> `grep` y `find`. Todo el contenido vive en archivos `.md` con convenciones
> consistentes de nombres, tags, labels y campos `KEY:: valor`.
>
> **Mapa humano / scaffolding visual:** ver [`README.md`](./README.md)
> **Resumen ejecutivo del vault:** ver [`overview.md`](./overview.md)

---

## 0. TL;DR — los 10 comandos que más vas a usar

```bash
# 0.1 Listar todo el vault (sin .git)
find . -path ./.git -prune -o -type f -name '*.md' -print | sort

# 0.2 Buscar un término (case-insensitive, con número de línea)
rg -in 'cadera'                # ripgrep
grep -rin --include='*.md' 'cadera' .

# 0.3 Buscar un tag exacto en líneas tipo "## Tags"
rg -n '#cadera\b'
grep -rn --include='*.md' -E '#cadera\b' .

# 0.4 Buscar un campo estructurado KEY:: valor
rg -n '^idPersona::'
grep -rn --include='*.md' -E '^idPersona::' .

# 0.5 Buscar un doctor por apellido (en cualquier archivo)
rg -in 'ford sosa|edmundo ford'

# 0.6 Listar archivos de un dominio
find ./doctores  -type f -name '*.md' | sort
find ./servicios -type f -name '*.md' | sort

# 0.7 Datos LIVE (verdad operativa: IDs, agenda, citas)
find . -type f -iname '*LIVE*.md'

# 0.8 Datos RAW (capturas brutas de sitios/APIs)
find . -type f -iname '*RAW*.md'

# 0.9 Todos los tags únicos del vault
grep -rho --include='*.md' -E '#[A-Za-z][A-Za-z0-9_-]+' . | sort -u

# 0.10 Todos los KEY:: usados como campos estructurados
grep -rho --include='*.md' -E '^[A-Z][A-Z0-9_]+::' . | sort -u
```

> **Nota portabilidad:** si `rg` no está instalado, todo lo que sigue tiene
> equivalente con `grep -rn --include='*.md'`. Los ejemplos muestran ambos.

---

## 1. Estructura del vault — qué hay en cada carpeta

| Ruta                | Contenido                                                                  | Cómo barrerla                                       |
| ------------------- | -------------------------------------------------------------------------- | --------------------------------------------------- |
| `agente/`           | Material operativo del agente IA (FAQ, copies, flujos, contexto, raw)     | `find ./agente -name '*.md'`                        |
| `blog/`             | Artículos consolidados + carpeta `Artículos RAW/`                          | `find ./blog -name '*.md'`                          |
| `chatbot/`          | Prompt sistema, intents, entidades NER, respuestas plantilla              | `find ./chatbot -name '*.md'`                       |
| `cliniweb/`         | IDs reales, agenda LIVE, perfiles + `perfiles/` por doctor                 | `find ./cliniweb -name '*.md'`                      |
| `competidores/`     | Benchmarks COPAC, CORMED y análisis competitivo                            | `find ./competidores -name '*.md'`                  |
| `directorios/`      | Presencia en directorios externos (HSF, Chekiao, HuliHealth, InfoGuia…)    | `find ./directorios -name '*.md'`                   |
| `doctores/`         | 11 fichas resumen + `perfiles/` ampliados (carpetas para perfiles RAW)     | `find ./doctores -name '*.md'`                      |
| `fuentes/`          | Sitios personales, publicaciones académicas, LinkedIn, índice de fuentes  | `find ./fuentes -name '*.md'`                       |
| `institucion/`      | Contacto, ubicación, RRSS, flujo citas, mercado, aseguradoras             | `find ./institucion -name '*.md'`                   |
| `raw/`              | Capturas brutas: DOM del sitio, Google SERP, API Cliniweb                  | `find ./raw -name '*.md'`                           |
| `servicios/`        | Especialidades + `Condiciones y Diagnósticos/` + `Procedimientos Detallados/` + `Páginas RAW/` | `find ./servicios -name '*.md'`     |

### Archivos en la raíz (resúmenes transversales)

| Archivo            | Rol                                                            |
| ------------------ | -------------------------------------------------------------- |
| `README.md`        | Mapa humano / scaffolding gráfico del workspace                |
| `INDEX.md`         | **Este archivo** — guía `rg`/`grep`/`find` para agentes        |
| `overview.md`      | Overview ejecutivo del vault                                   |
| `AGENTS.md`        | Punto de entrada de agentes (apunta a `README.md`)             |
| `CLAUDE.md`        | Punto de entrada Claude (apunta a `AGENTS.md`)                 |
| `SEO.md`           | Consolidado SEO                                                |
| `RRSS.md`          | Consolidado redes sociales                                     |
| `formacion.md`     | Resumen transversal de formación de doctores                   |
| `aseguradoras.md`  | Resumen transversal de cobertura aseguradoras                  |
| `hospital.md`      | Hospital sede (San Fernando) y entorno                         |
| `prices.md`        | Precios y rangos referenciales                                 |

```bash
# Listar solo archivos raíz
find . -maxdepth 1 -type f -name '*.md' | sort
```

---

## 2. Convención de nombres de archivo (file naming)

El nombre del archivo es **buscable** y aporta señal semántica. Patrones clave:

| Sufijo / Patrón en el nombre   | Significado                                          | Búsqueda                                  |
| ------------------------------ | ---------------------------------------------------- | ----------------------------------------- |
| `* LIVE.md`                    | Datos en vivo (verdad operativa, agenda, IDs)        | `find . -iname '*LIVE*.md'`               |
| `* RAW.md` / `*Páginas RAW*`   | Captura bruta, sin procesar                          | `find . -iname '*RAW*.md'`                |
| `* COMPLETO.md`                | Versión completa/long-form de una fuente             | `find . -iname '*COMPLETO*.md'`           |
| `Dr. *.md` / `Dra. *.md`       | Ficha de un doctor o doctora                         | `find ./doctores -iname 'Dr*.md' -o -iname 'Dra*.md'` |
| `* - Cliniweb.md`              | Perfil del doctor en Cliniweb                        | `find ./cliniweb/perfiles -name '*.md'`   |
| `NN - Tema.md` (`01 -`, `02 -`) | Capítulos numerados dentro de un perfil ampliado    | `find ./doctores/perfiles -regex '.*/[0-9]+ - .*\.md'` |
| `CEOSA en *.md`                | Presencia de CEOSA en un directorio externo          | `find ./directorios -iname 'CEOSA en*.md'` |
| `Articulo - *.md`              | Artículo de blog en bruto                            | `find ./blog -iname 'Articulo*.md'`       |
| `Especialista en *.md`         | Página de servicio por especialidad                  | `find ./servicios -iname 'Especialista*.md'` |
| `Condiciones de *.md`          | Página de diagnósticos por región anatómica          | `find './servicios/Condiciones y Diagnósticos' -name '*.md'` |
| `Índice de *.md`               | Índices internos de un dominio                       | `find . -iname 'Índice*.md'`              |

> Atención: muchos archivos contienen **espacios, tildes y guiones** (`Dr. Edmundo Ford Sosa`,
> `Páginas RAW`, `Índice de Fuentes`). Cita siempre con comillas o usa `-iname`/`-regex`
> en `find`. En `rg`/`grep` los nombres de archivo no afectan la búsqueda de contenido.

---

## 3. Tags `#tag` — sistema de etiquetas

Casi todos los `.md` cierran con un bloque:

```
---

## Tags

#tag1 #tag2 #tag3 ...
```

Algunos archivos usan el formato extendido `#tag/categoria` (p. ej. `#tag/cliniweb`,
`#tag/live`, `#tag/ids`). Ambos coexisten — busca con un patrón que cubra los dos.

### 3.1 Listar todos los tags del vault

```bash
# Tags únicos (incluye #tag/xxx)
grep -rho --include='*.md' -E '#[A-Za-zÁÉÍÓÚñ][A-Za-zÁÉÍÓÚñ0-9_/-]+' . \
  | sort -u

# Tags con conteo (top 30)
grep -rho --include='*.md' -E '#[A-Za-zÁÉÍÓÚñ][A-Za-zÁÉÍÓÚñ0-9_/-]+' . \
  | sort | uniq -c | sort -rn | head -30
```

### 3.2 Buscar archivos por tag

```bash
# Archivos con #cadera
rg -l '#cadera\b'
grep -rl --include='*.md' -E '#cadera\b' .

# Archivos con #cadera Y #reemplazo (intersección)
rg -l '#cadera\b' | xargs -I{} rg -l '#reemplazo\b' {}

# Archivos con cualquiera de varios tags
rg -l -e '#cadera\b' -e '#rodilla\b' -e '#columna\b'
```

### 3.3 Familias de tags útiles (no exhaustivo)

> El vault contiene **~300+ tags** únicos. Estas son las familias más útiles para scraping.

| Categoría                | Ejemplos de tags                                                                    |
| ------------------------ | ----------------------------------------------------------------------------------- |
| Estructurales            | `#ceosa` `#overview` `#vault` `#contexto` `#agente`                                 |
| Dominio clínico          | `#ortopedia` `#trauma` `#cirugia` `#fisioterapia` `#deporteslesion` `#emergencias`  |
| Anatomía / región        | `#cadera` `#rodilla` `#hombro` `#codo` `#columna` `#pelvis` `#acetabulo` `#mano`    |
| Procedimientos           | `#artroscopia` `#reemplazo` `#artroplastia` `#PRP` `#MIS` `#CirugiaMinimaInvasiva`  |
| Personas                 | `#doctor` `#doctora` `#aleman` `#alessandria` `#bolivar-franco` `#varela` …        |
| Operativa / canales      | `#cliniweb` `#chekiao` `#directorio` `#chatbot` `#bot` `#citas` `#agendamiento`     |
| Marketing / contenido    | `#blog` `#articulos` `#copies` `#SEO` `#contenido` `#educacion-pacientes`           |
| Datos / estados          | `#live` `#ids` `#datos-brutos` `#extraccion` `#academia` `#academica`               |
| Geografía                | `#panama` `#san-fernando` `#costa-del-este` `#colombia` `#argentina` `#españa`      |
| Aseguradoras / negocio   | `#aseguradoras` `#bupa` `#cobertura` `#costo` `#estimados`                          |

```bash
# Extraer la familia anatomía+procedimiento para un doctor
rg -l -e '#cadera\b' -e '#rodilla\b' ./doctores
```

---

## 4. Campos estructurados `KEY:: valor`

Muchos archivos contienen metadatos línea por línea con la sintaxis `KEY:: valor`
(estilo Dataview/Obsidian). Es la forma más **fiable** de extraer datos limpios.

### 4.1 Catálogo de claves frecuentes

```bash
# Ver todas las claves usadas en el vault
grep -rho --include='*.md' -E '^[A-Z][A-Z0-9_]+::' . | sort -u
```

| Categoría        | Claves                                                                                              |
| ---------------- | --------------------------------------------------------------------------------------------------- |
| Identidad        | `NOMBRE::` `NAME::` `HEADLINE::` `ESPECIALIDAD::` `IDIOMAS::` `SEXO::`                              |
| IDs Cliniweb     | `idPersona::` `idEmpresa::` `EMPRESA_ID::` `DOCTOR_*_idPersona::`                                   |
| Contacto         | `TEL::` `PHONE::` `WHATSAPP::` `EMAIL::` `EMAIL_PRINCIPAL::` `EMAIL_CEOSA::` `URL::` `WEB::`        |
| Ubicación        | `ADDRESS::` `LUGAR::` `PISO::` `LOCALIDAD_SAN_FERNANDO::` `MAPA_URL::` `CEOSA_CONSULTORIO::`        |
| Agenda / citas   | `HORARIO::` `SLOT_DURATION::` `PRIMERA_CITA_DISPONIBLE::` `PRIORIDAD_CITAS::` `URGENCIAS::`         |
| Procedencia/raw  | `FUENTE::` `SCRAPE_DATE::` `FECHA::` `PLATAFORMA::` `URL_BASE::` `URL_TEST::` `QUERY::`             |
| RRSS             | `FACEBOOK_*::` `INSTAGRAM_*::` `LINKEDIN_*::` `YOUTUBE::` `TIKTOK::` `TWITTER::`                    |
| Académico        | `PUBLICACIONES::` `REVISTA::` `AUTOR::` `ESTUDIO::` `TEMA::` `NIVEL::` `EXPERIENCIA::`              |
| Negocio / SEO    | `KEYWORD_OBJETIVO::` `IMPACTO_SEO::` `LEADS_FORMULARIO::` `VELOCIDAD_CARGA::` `ESTRATEGIA::`        |
| Cobertura        | `BUPA_DRA_MARXEN::` `URL_BUPA_MARXEN::` `NOMBRE_BUPA::`                                             |

### 4.2 Patrones de extracción

```bash
# Todos los idPersona del vault con su archivo
grep -rn --include='*.md' -E '^idPersona::' .

# Todos los teléfonos
grep -rhE --include='*.md' '^(TEL|PHONE|WHATSAPP)::' . | sort -u

# Todos los emails
grep -rhE --include='*.md' '^EMAIL[A-Z_]*::' . | sort -u

# URLs scrapeadas
grep -rhE --include='*.md' '^(URL|WEB|MAPA_URL|URL_BASE)::' . | sort -u

# Fecha de extracción de cualquier dato live/raw
rg -n '^(SCRAPE_DATE|FECHA|FECHA_EXTRACCIÓN)::'

# Sólo el VALOR (sin la clave) de un campo
grep -rhE --include='*.md' '^idPersona::' . | sed 's/^idPersona:://; s/^[[:space:]]*//'
```

> Existen también variantes en línea (`idPersona:: 2017736` dentro de bloques de
> código). El patrón `^KEY::` cubre el 95 % de los casos; añade `'KEY::'` (sin
> `^`) si necesitas capturarlas también dentro de tablas o code-fences.

---

## 5. Recetas por tarea (cookbook)

### 5.1 Encontrar el ID Cliniweb de un doctor

```bash
# Por apellido — ID + archivo donde aparece
rg -n -B1 'idPersona:: *[0-9]+' ./cliniweb ./doctores | rg -i 'ford sosa|idPersona'

# Tabla maestra de IDs (fuente de verdad)
sed -n '/^| Nombre/,/^$/p' './cliniweb/Doctores List LIVE.md'
```

### 5.2 Listar todos los servicios y sus tags

```bash
for f in $(find ./servicios -maxdepth 1 -name '*.md' | sort); do
  echo "=== $f ==="
  grep -E '^# |^## Tags' "$f"
  grep -E '^#[a-zA-Z]' "$f" | tail -1
done
```

### 5.3 Encontrar todo lo relacionado con un dominio clínico

```bash
# Cadera: archivos que la mencionan en cuerpo o tags
rg -lin 'cadera|#cadera' .

# Cadera + reemplazo articular
rg -l '#cadera\b' | xargs -I{} rg -l -e '#reemplazo\b' -e 'reemplazo articular' {}
```

### 5.4 Datos LIVE vs RAW vs procesado

```bash
find . -iname '*LIVE*.md'                    # verdad operativa
find . -iname '*RAW*.md' -o -iname '*Brutos*.md'  # capturas crudas
# Cualquier otro .md fuera de lo anterior se considera procesado/curado
```

### 5.5 Auditar consistencia de tags

```bash
# Archivos SIN sección "## Tags"
for f in $(find . -path ./.git -prune -o -type f -name '*.md' -print); do
  grep -q '^## Tags' "$f" || echo "FALTA TAGS: $f"
done

# Archivos sin H1 (#) inicial
for f in $(find . -path ./.git -prune -o -type f -name '*.md' -print); do
  head -1 "$f" | grep -q '^# ' || echo "FALTA H1: $f"
done
```

### 5.6 Cross-references estilo Obsidian `[[Nota]]`

Algunos archivos enlazan con la sintaxis `[[Nombre de Nota]]`.

```bash
# Listar todos los wikilinks del vault
grep -rhoE --include='*.md' '\[\[[^]]+\]\]' . | sort -u

# Ver wikilinks rotos (apuntan a archivos que no existen)
grep -rhoE --include='*.md' '\[\[[^]]+\]\]' . \
  | sed 's/^\[\[//; s/\]\]$//' \
  | sort -u \
  | while read name; do
      find . -iname "${name}.md" -print -quit | grep -q . || echo "ROTO: [[$name]]"
    done
```

### 5.7 Renombrar/buscar por entidad (NER ya documentada)

```bash
# Las entidades del dominio están definidas aquí:
view ./chatbot/Entidades del Dominio CEOSA.md

# Buscar menciones de una entidad (p. ej., LCA = ligamento cruzado anterior)
rg -in '\bLCA\b|ligamento cruzado'
```

---

## 6. Plantillas de búsqueda combinada

### 6.1 Triángulo doctor × servicio × evidencia

```bash
DOC='Olmedo Varela'
SVC='cadera'
rg -lin "$DOC" | xargs -I{} rg -l -e "#${SVC}\\b" -e "$SVC" {}
```

### 6.2 Inventario de fuentes externas vs internas

```bash
# Externas
rg -hN '^URL::|^WEB::' ./fuentes ./directorios ./cliniweb \
  | sed 's/^[A-Z_]*:://' | sort -u

# Internas (rutas relativas en el vault)
rg -hoN '\]\([^)]+\.md\)' --no-filename | sort -u
```

### 6.3 “Dame todo el contexto de X” en una sola pasada

```bash
TOPIC='rodilla'
{
  echo "## Archivos del topic: $TOPIC"; rg -lin "$TOPIC" .
  echo; echo "## Tags relacionados"; grep -rho --include='*.md' -E '#[a-z][a-z0-9_-]+' . \
    | sort -u | grep -i "$TOPIC"
  echo; echo "## Campos KEY::"; rg -n "$TOPIC" . | rg '::'
} > /tmp/dossier-$TOPIC.txt
```

---

## 7. Glosario rápido para agentes

| Término    | Qué significa en este vault                                                       |
| ---------- | --------------------------------------------------------------------------------- |
| **LIVE**   | Datos verificados contra fuente externa (Cliniweb, sitio oficial) en `SCRAPE_DATE` |
| **RAW**    | Captura sin procesar — útil como evidencia, no para citar al usuario final         |
| **CEOSA**  | Centro de Especialidades Ortopédicas — la institución del vault                   |
| **HSF**    | Hospital San Fernando — sede física                                               |
| **Cliniweb** | Plataforma de agenda/citas; fuente de verdad para `idPersona` / `idEmpresa`     |
| **Skill**  | Capacidad documentada del agente (p. ej. *Skill Citas Cliniweb*)                  |

---

## 8. Reglas de oro al scrapear este vault

1. **Empieza por `overview.md` y este `INDEX.md`**; nunca por un archivo sin contexto.
2. **Para datos operativos (IDs, agenda, contacto) usa siempre `*LIVE*` y `KEY::`**, no prosa.
3. **Los `*RAW*` son evidencia**, no fuente para responder al usuario; cita la versión curada.
4. **Tags = filtro, KEY:: = extracción.** Combínalos: filtra archivos por tag, luego saca los campos.
5. **Nombres con espacios y tildes**: usa comillas o `find -iname`.
6. **Antes de crear contenido nuevo**, valida que no exista ya en
   `cliniweb/`, `directorios/`, `fuentes/`, `doctores/`, `servicios/` o `institucion/`.

---

## Tags

#index #scraping #rg #grep #find #agentes #vault #ceosa #convenciones #tags #labels
