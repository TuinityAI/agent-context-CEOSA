# Cliniweb — Lista Completa de Doctores LIVE

#tag/cliniweb #tag/live #tag/ids #tag/doctores

FUENTE:: cliniweb_doctores_list (Live API)
FECHA_EXTRACCIÓN:: 2026-04-25
NOTA:: Datos directamente de la API Cliniweb. Fuente de verdad para IDs.

---

## Tabla de IDs — Doctores CEOSA

| Nombre Completo          | idPersona | idEmpresa   | Cédula     | Cel             | Tel Lab         |
| ------------------------ | --------- | ----------- | ---------- | --------------- | --------------- |
| DR. EDMUNDO FORD SOSA    | 2017736   | 2012086     | 8-385-833  | 6678-4501       | —               |
| DR. EDMUNDO FORD MORA    | 2017751   | 2012086     | 8-741-1309 | 66733096        | —               |
| DR. JAIME AUGUSTO ALEMÁN | 2017739   | 2012086     | 8-260-389  | 6673-3183       | 391-8303        |
| ALESSANDRO ALESSANDRIA   | 2012087   | 2012086     | —          | 00507-6675-4858 | 00507-0229-3779 |
| DR. OCTAVIO MENDEZ       | 2138182   | 2012086     | 8-777-904  | —               | —               |
| DRA. MARISOL NIKOLAEV    | 2017757   | 2012086     | PE-11-2257 | —               | —               |
| DR. NELSON SOPALDA       | 2017763   | 2012086     | —          | —               | —               |
| DR. BOLÍVAR FRANCO       | 2017742   | **662185**  | —          | —               | —               |
| DR. LUIS FUENTES         | 2017016   | **6925365** | —          | —               | —               |
| DRA. JOLIEANNE MARXEN    | 2017746   | **6925365** | 8-719-580  | +50769808281    | 261-7275        |
| Dr. Olmedo Varela        | 7255402   | **4586558** | —          | —               | —               |
| Karla Vargas             | 4152938   | **4586558** | 8-809-1608 | 6673-6286       | —               |

### Staff / Personal No-Médico

| Nombre                           | idPersona | idEmpresa | Cédula     | Rol Estimado                  |
| -------------------------------- | --------- | --------- | ---------- | ----------------------------- |
| RACHEL NARETTE MONTENEGRO JORDAN | 2151401   | 2012086   | 4-770-2448 | Coordinadora/Recepcionista    |
| Licda. Angelica Arrazola         | 6246157   | 2011849   | 8-834-1520 | Fisioterapeuta / Coordinadora |

### Entradas Internas (No Doctores)

| Denominación       | id      | Función                    |
| ------------------ | ------- | -------------------------- |
| 1- TEMAS DEL DIA   | 2031427 | Slot interno de agenda     |
| 2 - Paciente Nuevo | 5999416 | Slot para nuevos pacientes |
| Clinica Ortopedica | 2197950 | Entrada genérica           |

---

## Datos Clave por Doctor

### DR. EDMUNDO FORD SOSA

```
idPersona:: 2017736
idEmpresa:: 2012086
cédula:: 8-385-833
seguroMedico:: HP1701001
cel:: 6678-4501
nickname_cliniweb:: edmundo-ford-sosa
idPerfilPublico:: 89
```

### DR. EDMUNDO FORD MORA

```
idPersona:: 2017751
idEmpresa:: 2012086
cédula:: 8-741-1309
seguroMedico:: 016-001-000052788-4
cel:: 66733096 (→ 6673-3096)
idEstado:: 32
```

### DR. JAIME AUGUSTO ALEMÁN

```
idPersona:: 2017739
idEmpresa:: 2012086
cédula:: 8-260-389
seguroMedico:: HP1701001
tel_laboral:: 391-8303
cel:: 6673-3183
```

### ALESSANDRO ALESSANDRIA

```
idPersona:: 2012087
idEmpresa:: 2012086
seguroMedico:: 99008195
tel_laboral:: 00507-0229-3779
cel:: 00507-6675-4858
```

### DR. OCTAVIO MENDEZ

```
idPersona:: 2138182
idEmpresa:: 2012086
cédula:: 8-777-904
```

### DRA. MARISOL NIKOLAEV

```
idPersona:: 2017757
idEmpresa:: 2012086
cédula:: PE-11-2257 (cédula extranjera)
seguroMedico:: 016-01-0019935 CERT 1 CO-PAGO 20.00
```

### DR. NELSON SOPALDA ⚠️ NUEVO — No en sitio web

```
idPersona:: 2017763
idEmpresa:: 2012086
cédula:: N/A (no en API)
NOTA:: Aparece en Cliniweb bajo empresa CEOSA (2012086) pero NO está listado
en el sitio web ortopedasdepanama.com. Posible doctor nuevo incorporado recientemente.
ACCIÓN:: Verificar con administración CEOSA quién es el Dr. Nelson Sopalda.
```

### DRA. JOLIEANNE MARXEN

```
idPersona:: 2017746
idEmpresa:: 6925365 (empresa diferente a CEOSA main)
cédula:: 8-719-580
seguroMedico:: GP1700197
tel_laboral:: 261-7275
cel:: +50769808281
NOTA:: idEmpresa 6925365 puede ser su consultorio privado o una empresa
vinculada. Comparte empresa con Dr. Luis Fuentes.
```

### DRA. KARLA VARGAS

```
idPersona:: 4152938
idEmpresa:: 4586558 (empresa diferente — comparte con Dr. Olmedo Varela)
cédula:: 8-809-1608
cel:: 6673-6286
idEstado:: 32
```

### Dr. Olmedo Varela

```
idPersona:: 7255402
idEmpresa:: 4586558
NOTA:: Empresa 4586558 = probable consultorio propio de Dr. Olmedo / RontgenAI
```

### DR. BOLÍVAR FRANCO

```
idPersona:: 2017742
idEmpresa:: 662185 (empresa diferente)
NOTA:: Empresa 662185 diferente a CEOSA main. Verificar si es consultorio propio.
```

### DR. LUIS FUENTES

```
idPersona:: 2017016
idEmpresa:: 6925365 (comparte empresa con Dra. Marxen)
NOTA:: Empresa 6925365 podría ser "Spark Wellness Center" u otro consultorio compartido.
```

---

## Empresas en el Sistema

```
idEmpresa 2012086 → CEOSA principal (Centro de Especialidades Ortopédicas)
idEmpresa 4586558 → Dr. Olmedo Varela / Dra. Karla Vargas (RontgenAI?)
idEmpresa 6925365 → Dr. Luis Fuentes / Dra. Jolieanne Marxen (Spark Wellness?)
idEmpresa 662185  → Dr. Bolívar Franco (consultorio propio?)
idEmpresa 2011849 → Licda. Angelica Arrazola (fisioterapia?)
```

---

## Horarios Live — Dr. Edmundo Ford Sosa (2026-04-28 to 05-07)

```
HORARIO_DISPONIBLE_FORD_SOSA:
  Semana 1 (28 Apr–30 Apr):
    Lun 28 Abr: 11:15–13:45 (turnos de 15 min)
    Mar 29 Abr: 10:45–13:45
    Mié 30 Abr: 10:30–13:45
  Semana 2 (5–7 May):
    Mar 5 May: 10:30–13:45
    Mié 6 May: 10:30–13:45 (con gaps)
    Jue 7 May: 10:30–13:45

SLOT_DURATION:: 15 minutos
PRIMERA_CITA_DISPONIBLE:: 2026-04-28 11:15
```

## Horarios Live — Dr. Edmundo Ford Mora (2026-04-27 to 05-08)

```
HORARIO_DISPONIBLE_FORD_MORA:
  Dom 27 Abr: 10:45, 11:45, 14:30-14:45, 16:00-16:15, 17:00-17:45
  Lun 28 Abr: 09:00-09:45, 11:15-14:15 (amplio)
  Mar 29 Abr: 10:45-11:45, 14:45-15:15
  Mié 30 Abr: 11:15-11:45, 14:30-17:45 (amplia tarde)
  Lun 4 May: 09:00-12:00, 15:00-17:45
  Mar 5 May: 08:30-14:15 (muy amplio)
  Mié 6 May: 14:30-17:45
  Jue 7 May: 10:30-11:45, 14:30-17:45
  Vie 8 May: 08:30-11:45, 14:30-17:45

NOTA_FORD_MORA:: Agenda más amplia, incluye tardes y mañanas tempranas.
Disponible incluso domingo 27. Más flexibilidad que Ford Sosa.
PRIMERA_CITA_DISPONIBLE:: 2026-04-27 10:45 (HOY si se llama)
```

---

## Links Internos

- [[Dr. Edmundo Ford Sosa]] | [[Dr. Edmundo Ford Mora]] | [[Skill Citas Cliniweb]]
- [[Cliniweb API Raw Data]] | [[INDEX.md]]
