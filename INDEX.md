# INDEX.md — Agent Scrap Guide (rg / grep / find)

Compact, agent-only. Human map: `README.md`. Exec summary: `overview.md`.

All content is `.md`. Conventions: `# H1` first line · `## Tags` block at end with
`#tag` (and `#tag/cat`) · structured fields as `KEY:: value` (Dataview-style).

---

## 0. Top commands

```bash
# list everything (no .git)
find . -path ./.git -prune -o -type f -name '*.md' -print | sort

# search content
rg -in 'cadera'
grep -rin --include='*.md' 'cadera' .

# search tag
rg -n '#cadera\b'
grep -rn --include='*.md' -E '#cadera\b' .

# search structured field
rg -n '^idPersona::'
grep -rn --include='*.md' -E '^idPersona::' .

# LIVE (operational truth)  /  RAW (raw evidence)
find . -iname '*LIVE*.md'
find . -iname '*RAW*.md'

# all unique tags
grep -rho --include='*.md' -E '#[A-Za-z][A-Za-z0-9_/-]+' . | sort -u

# all KEY:: fields used
grep -rho --include='*.md' -E '^[A-Z][A-Z0-9_]+::' . | sort -u
```

---

## 1. Folder map

| Path             | Content                                                         |
| ---------------- | --------------------------------------------------------------- |
| `agente/`        | Agent ops (FAQ, copies, flujos, contexto, raw)                  |
| `blog/`          | Articles + `Artículos RAW/`                                     |
| `chatbot/`       | System prompt, intents, NER entities, plantillas                |
| `cliniweb/`      | LIVE IDs + agenda + `perfiles/` per doctor                      |
| `competidores/`  | COPAC, CORMED, análisis competitivo                             |
| `directorios/`   | HSF, Chekiao, HuliHealth, InfoGuia, Localiza Tu Médico          |
| `doctores/`      | 11 fichas + `perfiles/` ampliados (carpetas con capítulos NN-)  |
| `fuentes/`       | Sitios personales, academia, LinkedIn, índice de fuentes        |
| `institucion/`   | Contacto, RRSS, flujo citas, mercado, aseguradoras              |
| `raw/`           | Sitio DOM, Google SERP, Cliniweb API                            |
| `servicios/`     | Especialidades + `Condiciones y Diagnósticos/` + `Procedimientos Detallados/` + `Páginas RAW/` |

Root resúmenes: `SEO.md` `RRSS.md` `formacion.md` `aseguradoras.md`
`hospital.md` `prices.md`. Entrypoints: `AGENTS.md` → `README.md` → `INDEX.md` / `overview.md`.

---

## 2. Filename patterns

| Pattern                        | Means                              | Find                                                  |
| ------------------------------ | ---------------------------------- | ----------------------------------------------------- |
| `* LIVE.md`                    | Live data (truth)                  | `find . -iname '*LIVE*.md'`                           |
| `* RAW.md`, `Páginas RAW/`     | Raw scrape (evidence only)         | `find . -iname '*RAW*.md'`                            |
| `* COMPLETO.md`                | Long-form source dump              | `find . -iname '*COMPLETO*.md'`                       |
| `Dr. *.md` / `Dra. *.md`       | Doctor file                        | `find ./doctores -iname 'Dr*.md'`                     |
| `* - Cliniweb.md`              | Cliniweb public profile            | `find ./cliniweb/perfiles -name '*.md'`               |
| `NN - Tema.md`                 | Numbered chapter inside profile    | `find ./doctores/perfiles -regex '.*/[0-9]+ - .*\.md'`|
| `CEOSA en *.md`                | External directory presence        | `find ./directorios -iname 'CEOSA en*.md'`            |
| `Articulo - *.md`              | Blog draft                         | `find ./blog -iname 'Articulo*.md'`                   |
| `Especialista en *.md`         | Service page                       | `find ./servicios -iname 'Especialista*.md'`          |
| `Condiciones de *.md`          | Diagnoses by region                | `find './servicios/Condiciones y Diagnósticos' -name '*.md'` |
| `Índice de *.md`               | Domain index                       | `find . -iname 'Índice*.md'`                          |

Filenames may contain spaces and accents — quote them or use `-iname`/`-regex`.

---

## 3. Tag system

Most files end with:

```
## Tags
#tag1 #tag2 #tag/cat
```

```bash
# files with tag
rg -l '#cadera\b'

# AND (intersection)
rg -l '#cadera\b' | xargs -I{} rg -l '#reemplazo\b' {}

# OR
rg -l -e '#cadera\b' -e '#rodilla\b' -e '#columna\b'

# top tags
grep -rho --include='*.md' -E '#[A-Za-zÁÉÍÓÚñ][A-Za-zÁÉÍÓÚñ0-9_/-]+' . \
  | sort | uniq -c | sort -rn | head -30
```

Tag families (~300 unique total):

- Estructurales: `#ceosa #vault #overview #contexto #agente`
- Anatomía: `#cadera #rodilla #hombro #codo #columna #pelvis #acetabulo #mano`
- Procedimientos: `#artroscopia #reemplazo #artroplastia #PRP #MIS`
- Personas: `#doctor #doctora #aleman #alessandria #bolivar-franco #varela …`
- Operativa: `#cliniweb #chekiao #directorio #chatbot #citas #agendamiento`
- Datos: `#live #ids #datos-brutos #extraccion #academia`
- Geo: `#panama #san-fernando #costa-del-este #colombia #españa`
- Negocio: `#aseguradoras #bupa #cobertura #costo #estimados`

---

## 4. Structured fields `KEY:: valor`

```bash
# catalog of keys
grep -rho --include='*.md' -E '^[A-Z][A-Z0-9_]+::' . | sort -u
```

| Group        | Keys                                                                                  |
| ------------ | ------------------------------------------------------------------------------------- |
| Identity     | `NOMBRE` `NAME` `HEADLINE` `ESPECIALIDAD` `IDIOMAS` `SEXO`                            |
| Cliniweb IDs | `idPersona` `idEmpresa` `EMPRESA_ID` `DOCTOR_*_idPersona`                             |
| Contact      | `TEL` `PHONE` `WHATSAPP` `EMAIL` `EMAIL_PRINCIPAL` `EMAIL_CEOSA` `URL` `WEB`          |
| Location     | `ADDRESS` `LUGAR` `PISO` `MAPA_URL` `CEOSA_CONSULTORIO`                               |
| Agenda       | `HORARIO` `SLOT_DURATION` `PRIMERA_CITA_DISPONIBLE` `PRIORIDAD_CITAS` `URGENCIAS`     |
| Source/raw   | `FUENTE` `SCRAPE_DATE` `FECHA` `PLATAFORMA` `URL_BASE` `URL_TEST` `QUERY`             |
| RRSS         | `FACEBOOK_*` `INSTAGRAM_*` `LINKEDIN_*` `YOUTUBE` `TIKTOK` `TWITTER`                  |
| Academic     | `PUBLICACIONES` `REVISTA` `AUTOR` `ESTUDIO` `TEMA` `NIVEL` `EXPERIENCIA`              |
| SEO/biz      | `KEYWORD_OBJETIVO` `IMPACTO_SEO` `LEADS_FORMULARIO` `VELOCIDAD_CARGA` `ESTRATEGIA`    |

Extraction:

```bash
# all idPersona with file:line
grep -rn --include='*.md' -E '^idPersona::' .

# values only
grep -rhE --include='*.md' '^idPersona::' . | sed 's/^idPersona:://; s/^[[:space:]]*//'

# any phone/email/url
grep -rhE --include='*.md' '^(TEL|PHONE|WHATSAPP)::' . | sort -u
grep -rhE --include='*.md' '^EMAIL[A-Z_]*::'           . | sort -u
grep -rhE --include='*.md' '^(URL|WEB|MAPA_URL|URL_BASE)::' . | sort -u

# scrape provenance
rg -n '^(SCRAPE_DATE|FECHA|FECHA_EXTRACCIÓN)::'
```

`^KEY::` covers ~95%. Drop the `^` to include matches inside tables/code-fences.

---

## 5. Cookbook

```bash
# 5.1 doctor's Cliniweb ID
rg -n -B1 'idPersona:: *[0-9]+' ./cliniweb ./doctores | rg -i 'ford sosa|idPersona'
sed -n '/^| Nombre/,/^$/p' './cliniweb/Doctores List LIVE.md'   # master table

# 5.2 list services + their tag line
for f in $(find ./servicios -maxdepth 1 -name '*.md' | sort); do
  echo "=== $f ==="; grep -E '^# |^#[a-zA-Z]' "$f" | head -3
done

# 5.3 cross dimension: doctor × service
rg -lin 'Olmedo Varela' | xargs -I{} rg -l -e '#cadera\b' -e 'cadera' {}

# 5.4 audit: files without ## Tags or H1
for f in $(find . -path ./.git -prune -o -type f -name '*.md' -print); do
  grep -q '^## Tags' "$f" || echo "NO_TAGS: $f"
  head -1 "$f" | grep -q '^# ' || echo "NO_H1:   $f"
done

# 5.5 wikilinks [[Note]]
grep -rhoE --include='*.md' '\[\[[^]]+\]\]' . | sort -u
grep -rhoE --include='*.md' '\[\[[^]]+\]\]' . | sed 's/^\[\[//; s/\]\]$//' | sort -u \
  | while read n; do find . -iname "${n}.md" -print -quit | grep -q . || echo "BROKEN: [[$n]]"; done

# 5.6 dossier per topic
T=rodilla; { rg -lin "$T" .; rg -hN "^#.*$T" .; rg -n "$T" . | rg '::'; } > /tmp/dossier-$T.txt

# 5.7 LIVE / RAW / curated split
find . -iname '*LIVE*.md'        # truth
find . -iname '*RAW*.md'          # evidence
# everything else .md = curated
```

---

## 6. Glossary

| Term       | Meaning                                                                |
| ---------- | ---------------------------------------------------------------------- |
| **LIVE**   | Verified vs external source on `SCRAPE_DATE` — operational truth       |
| **RAW**    | Unprocessed capture — evidence only, do not quote to end users         |
| **CEOSA**  | Centro de Especialidades Ortopédicas (the institution)                 |
| **HSF**    | Hospital San Fernando (physical site)                                  |
| **Cliniweb** | Booking platform · source of truth for `idPersona` / `idEmpresa`     |
| **Skill**  | Documented agent capability (e.g. *Skill Citas Cliniweb*)              |

---

## 7. Rules of thumb

1. Start at `overview.md` + this file. Never at a random `.md`.
2. Operational data → `*LIVE*` + `KEY::`. Never paraphrase from prose.
3. `*RAW*` is evidence, not user-facing copy.
4. Filter with **tags**, extract with **`KEY::`**.
5. Quote filenames (spaces/accents) or use `find -iname`.
6. Before writing new content, search first across `cliniweb/`, `directorios/`,
   `fuentes/`, `doctores/`, `servicios/`, `institucion/`.

---

## Tags

#index #scraping #rg #grep #find #agentes #vault #ceosa #convenciones
