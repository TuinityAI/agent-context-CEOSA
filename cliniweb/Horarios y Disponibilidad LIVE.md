# Cliniweb — Horarios y Disponibilidad LIVE

#tag/cliniweb #tag/live #tag/horarios #tag/slots

FUENTE:: cliniweb_citas_available_slots (Live API)
FECHA_EXTRACCIÓN:: 2026-04-25
NOTA:: Horarios válidos al momento de extracción. Consultar live para disponibilidad actual.

---

## Dr. Edmundo Ford Sosa — Slots Semana 28 Apr–7 May 2026

```
idPersona: 2017736
idLocalidad: 4014762
duracion_turno: 15 min

SLOTS_DISPONIBLES:

Martes 28 Abril:
  11:15 | 11:30 | 11:45 | 12:00 | 12:15 | 12:30 | 12:45
  13:00 | 13:15 | 13:30 | 13:45

Miércoles 29 Abril:
  10:45 | 11:15 | 11:30 | 11:45 | 12:00 | 12:15 | 12:30
  12:45 | 13:00 | 13:15 | 13:30 | 13:45

Jueves 30 Abril:
  10:30 | 10:45 | 11:00 | 11:15 | 11:30 | 11:45 | 12:00
  12:15 | 12:30 | 12:45 | 13:00 | 13:15 | 13:45

Martes 5 Mayo:
  10:30 | 10:45 | 11:00 | 11:15 | 11:30 | 11:45 | 12:00
  12:15 | 12:30 | 12:45 | 13:00 | 13:15 | 13:30 | 13:45

Miércoles 6 Mayo:
  10:30 | 10:45 | 11:15 | 12:00 | 12:15 | 12:30 | 12:45
  13:00 | 13:15 | 13:30 | 13:45

Jueves 7 Mayo:
  10:30 | 10:45 | 11:00 | 11:15 | 11:30 | 11:45 | 12:00
  12:15 | 12:30 | 12:45 | 13:00 | 13:15 | 13:30 | 13:45
```

**Análisis horario Ford Sosa:**

- Atiende Mar–Jue (confirmado por slots disponibles)
- Horario: ~10:30–13:45 (mañanas)
- SIN tardes (no hay slots PM para este doctor)
- Primer slot disponible: **Martes 28 Abr a las 11:15**
- Total slots semana típica: ~35–40 consultas

---

## Dr. Edmundo Ford Mora — Slots Semana 27 Apr–8 May 2026

```
idPersona: 2017751
idLocalidad: 4014762
duracion_turno: 15 min

SLOTS_DISPONIBLES:

Domingo 27 Abril:
  10:45 | 11:45 | 14:30 | 14:45 | 16:00 | 16:15 | 17:00 | 17:15 | 17:30 | 17:45

Lunes 28 Abril:
  09:00 | 09:15 | 09:30 | 09:45 (AM temprano)
  11:15 | 11:30 | 11:45 | 12:00 | 12:15 | 12:30 | 12:45
  13:00 | 13:15 | 13:30 | 13:45 | 14:00 | 14:15

Martes 29 Abril:
  10:45 | 11:00 | 11:15 | 11:30 | 11:45
  14:45 | 15:00 | 15:15

Miércoles 30 Abril:
  11:15 | 11:30 | 11:45
  14:30 | 14:45 | 15:15 | 15:30 | 15:45 | 16:15 | 16:30 | 16:45
  17:00 | 17:15 | 17:30 | 17:45

Lunes 4 Mayo:
  09:00 | 09:15 | 09:30 | 09:45 | 10:00 | 10:15 | 10:30 | 10:45
  11:00 | 11:15 | 11:30 | 11:45
  15:00 | 15:15 | 15:30 | 15:45 | 16:00 | 16:15 | 16:30 | 16:45
  17:00 | 17:15 | 17:30 | 17:45

Martes 5 Mayo:
  08:30 | 08:45 | 09:00 | 09:15 | 09:30 | 09:45 | 10:00 | 10:15
  10:30 | 10:45 | 11:00 | 11:15 | 11:30 | 11:45
  12:00 | 12:15 | 12:30 | 12:45 | 13:00 | 13:15 | 13:30 | 13:45
  14:15

Miércoles 6 Mayo:
  14:30 | 14:45 | 15:15 | 15:30 | 15:45 | 16:00 | 16:15 | 16:30
  16:45 | 17:15 | 17:30 | 17:45

Jueves 7 Mayo:
  10:30 | 10:45 | 11:00 | 11:15 | 11:30 | 11:45
  14:30 | 14:45 | 15:00 | 15:15 | 15:30 | 15:45
  16:15 | 16:30 | 16:45 | 17:00 | 17:15 | 17:30 | 17:45

Viernes 8 Mayo:
  08:30 | 08:45 | 09:00 | 09:15 | 09:30 | 09:45 | 10:00 | 10:15
  10:30 | 10:45 | 11:15 | 11:30 | 11:45
  14:30 | 14:45 | 15:00 | 15:15 | 15:30 | 15:45
  16:15 | 16:30 | 16:45 | 17:00 | 17:15 | 17:45
```

**Análisis horario Ford Mora:**

- Atiende Dom–Vie (muy amplio, incluyendo domingos)
- Horario mañana: 8:30–12:00 (algunos días)
- Horario tarde: 14:30–17:45
- MUCHO más disponibilidad que Ford Sosa
- Primer slot disponible: **Domingo 27 Abr a las 10:45 (HOY)**
- Total slots semana típica: ~60–80 consultas

---

## Patrones de Horario Inferidos

```
FORD_SOSA_PATRON:
  DÍAS:: Mar, Mié, Jue (solo días de semana, 3 días)
  HORAS:: 10:30–13:45 (solo mañanas)
  SLOTS_SEMANA:: ~35
  NOTA:: Agenda más restringida. Posiblemente también opera cirugías en otros días.

FORD_MORA_PATRON:
  DÍAS:: Dom, Lun, Mar, Mié, Jue, Vie (6 días)
  HORAS:: 8:30–12:00 (mañanas) + 14:30–17:45 (tardes)
  SLOTS_SEMANA:: ~70–80
  NOTA:: Agenda muy amplia. Mayor disponibilidad inmediata.
```

---

## Instrucciones para el Agente Chatbot

```python
# Para dar disponibilidad al paciente en tiempo real:
tool: cliniweb_citas_available_slots
params: {
  idEmpresa: 2012086,
  idResponsableServicio: [ID DEL DOCTOR],
  idLocalidad: 4014762,
  fechaInicio: [hoy en ISO8601],
  fechaFin: [hoy + 14 días en ISO8601]
}

# Si no hay slots en 14 días, ampliar a 30 días
# Presentar al usuario las 5-10 opciones más próximas
```

---

## Links Internos

- [[Cliniweb Doctores List LIVE]] | [[Skill Gestión Citas Cliniweb]]
- [[Dr. Edmundo Ford Sosa]] | [[Dr. Edmundo Ford Mora]]
