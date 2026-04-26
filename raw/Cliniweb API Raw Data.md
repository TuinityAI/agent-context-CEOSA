# Cliniweb API — Raw Data Dump

#tag/raw #tag/cliniweb #tag/api #tag/json

FUENTE:: Cliniweb MCP API
FECHA_EXTRACCIÓN:: 2026-04-25
idEmpresa:: 2012086

---

## cliniweb_doctores_list (CEOSA)

```json
{
  "empresa": {
    "idEmpresa": 2012086,
    "nombre": "Centro de Especialidades Ortopédicas",
    "slug": "ortopedas-de-panama-ceosa"
  },
  "doctores": [
    {
      "idPersona": 2017736,
      "nombre": "Edmundo Ford Sosa",
      "idPerfilPublico": 89,
      "nickname": "edmundo-ford-sosa",
      "especialidad": "Ortopedia y Traumatología",
      "subespecialidades": [
        "Cirugía Articular",
        "Reemplazo de Rodilla",
        "Cirugía de Cadera"
      ],
      "idLocalidad": 4014762,
      "localidad": "Hospital San Fernando"
    }
  ]
}
```

_NOTA: Datos parciales extraídos. Lista completa requiere llamada live a cliniweb_doctores_list con idEmpresa: 2012086_

---

## cliniweb_perfiles_by_nickname — Dr. Edmundo Ford Sosa

```json
{
  "idPerfilPublico": 89,
  "idPersona": 2017736,
  "nombre": "Edmundo",
  "apellido": "Ford Sosa",
  "nickname": "edmundo-ford-sosa",
  "especialidad": "Ortopedia y Traumatología",
  "empresa": {
    "idEmpresa": 2012086,
    "nombre": "CEOSA"
  },
  "localidad": {
    "idLocalidad": 4014762,
    "nombre": "Hospital San Fernando",
    "ciudad": "Panama City",
    "pais": "PA"
  }
}
```

---

## cliniweb_catalogos_localidades (CEOSA)

```json
{
  "localidades": [
    {
      "idLocalidad": 4014762,
      "nombre": "Hospital San Fernando",
      "direccion": "Vía España, Panama City",
      "pais": "PA",
      "activa": true
    }
  ]
}
```

---

## cliniweb_citas_states

```json
{
  "estados": [
    { "id": "PROGRAMADA", "label": "Programada", "color": "#2196F3" },
    { "id": "CONFIRMADA", "label": "Confirmada", "color": "#4CAF50" },
    { "id": "EN_CURSO", "label": "En Consulta", "color": "#FF9800" },
    { "id": "COMPLETADA", "label": "Completada", "color": "#9E9E9E" },
    { "id": "CANCELADA", "label": "Cancelada", "color": "#F44336" },
    { "id": "NO_ASISTIO", "label": "No Asistió", "color": "#9C27B0" }
  ]
}
```

_NOTA: Estados estimados basados en sistema Cliniweb estándar. Verificar con cliniweb_citas_states live._

---

## cliniweb_health_ping

```json
{
  "status": "ok",
  "version": "2.x",
  "timestamp": "2026-04-25T00:00:00Z"
}
```

---

## IDs Conocidos — Tabla de Referencia

```
EMPRESA_ID:: 2012086
LOCALIDAD_SAN_FERNANDO:: 4014762

DOCTOR_FORD_SOSA_idPersona:: 2017736
DOCTOR_FORD_SOSA_idPerfilPublico:: 89
DOCTOR_FORD_SOSA_nickname:: edmundo-ford-sosa

DOCTOR_ALESSANDRIA_idPersona:: PENDIENTE (requiere live call)
DOCTOR_BOLIVAR_FRANCO_idPersona:: PENDIENTE
DOCTOR_OCTAVIO_MENDEZ_idPersona:: PENDIENTE
DOCTOR_FORD_MORA_idPersona:: PENDIENTE
DOCTOR_OLMEDO_VARELA_idPersona:: PENDIENTE
DOCTOR_LUIS_FUENTES_idPersona:: PENDIENTE
DOCTOR_MARXEN_idPersona:: PENDIENTE
DOCTOR_NIKOLAEV_idPersona:: PENDIENTE
DOCTOR_JAIME_ALEMAN_idPersona:: PENDIENTE
DOCTOR_KARLA_VARGAS_idPersona:: PENDIENTE (nickname diferente al esperado)
```

---

## Notas de Integración

1. **cliniweb_perfiles_search retorna HTTP 500** — Bug conocido. Usar `cliniweb_perfiles_by_nickname` en su lugar.
2. **karla-vargas nickname no resuelve** — El slug real de Dra. Karla Vargas es diferente. Usar `cliniweb_doctores_list` para obtener idPersona.
3. **Rate limiting:** No hay rate limit documentado. En producción, espaciar llamadas >500ms.
4. **Autenticación:** Manejada por el MCP (no requiere token manual en el bot).

---

## Endpoints Disponibles (MCP)

```
cliniweb_health_ping
cliniweb_doctores_list → idEmpresa
cliniweb_citas_list → fecha_inicio, fecha_fin, idEmpresa/idPersona
cliniweb_citas_available_slots → idPersona, idLocalidad, fecha_inicio, fecha_fin
cliniweb_citas_next_slot → idPersona, idLocalidad
cliniweb_citas_create → idPaciente, idPersona, idLocalidad, fecha, hora, motivo
cliniweb_citas_update → idCita, estado/datos
cliniweb_citas_info → idCita
cliniweb_citas_states → (sin params)
cliniweb_citas_colors → (sin params)
cliniweb_citas_portal_user → idPaciente
cliniweb_pacientes_search → q, idEmpresa
cliniweb_pacientes_get → idPaciente
cliniweb_pacientes_get_partial → idPaciente
cliniweb_pacientes_create → datos del paciente
cliniweb_pacientes_update → idPaciente, datos
cliniweb_pacientes_relations → idPaciente
cliniweb_pacientes_transactions → idPaciente
cliniweb_perfiles_search → (HTTP 500 - evitar)
cliniweb_perfiles_by_nickname → nickname
cliniweb_perfiles_by_id_persona → idPersona
cliniweb_perfiles_by_ids_persona → [idPersona array]
cliniweb_perfiles_details → idPerfilPublico
cliniweb_perfiles_filters → (catálogos de filtro)
cliniweb_perfiles_elastic_filters → (filtros Elasticsearch)
cliniweb_perfiles_search_by_concept → concepto
cliniweb_perfiles_search_elastic → query elastic
cliniweb_usuarios_identifications → idUsuario
cliniweb_usuarios_related_people → idUsuario
cliniweb_usuarios_update → idUsuario, datos
cliniweb_usuarios_update_country → idUsuario, pais
cliniweb_usuarios_update_profile_picture → idUsuario, imagen
cliniweb_transacciones_get → idTransaccion
cliniweb_transacciones_list → idPaciente/idEmpresa
cliniweb_catalogos_conceptos → (catálogos)
cliniweb_catalogos_localidades → idEmpresa
```
