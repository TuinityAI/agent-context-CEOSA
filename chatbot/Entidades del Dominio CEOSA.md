# Entidades del Dominio — CEOSA Chatbot

## Definición

Una **entidad** es un valor específico extraíble de un mensaje de usuario. El chatbot identifica entidades para personalizar la respuesta.

---

## Entidad: DOCTOR

### Valores y Sinónimos

| Valor Canónico              | Sinónimos / Variaciones               |
| --------------------------- | ------------------------------------- |
| Dr. Edmundo Ford Sosa       | Ford Sosa, Dr. Ford, Edmundo Ford     |
| Dr. Alessandro Alessandría  | Alessandría, Alessandro, Alessandria  |
| Dr. Jaime Alemán            | Alemán, Dr. Aleman, Jaime Aleman      |
| Dr. Luis Fuentes            | Fuentes, Dr. Luis, Luis Fuentes       |
| Dr. Bolívar Franco          | Franco, Bolivar, Dr. Franco           |
| Dra. Jolieanne Marxen       | Marxen, Jolieanne, Jolie, Dra. Marxen |
| Dr. Edmundo Ford Mora       | Ford Mora, edfordmd                   |
| Dra. Marisol Nikolaev       | Nikolaev, Marisol, Dra. Nikolaev      |
| Dr. Octavio Mendez Lavergne | Mendez, Octavio, octomendezmd         |
| Dra. Karla Vargas           | Vargas, Karla, Dra. Vargas            |
| Dr. Olmedo Varela           | Varela, Olmedo, Dr. Varela            |

---

## Entidad: ÁREA_CORPORAL

| Valor Canónico | Sinónimos                                    |
| -------------- | -------------------------------------------- |
| RODILLA        | rodilla, rótula, menisco, ligamentos rodilla |
| CADERA         | cadera, articulación cadera, fémur           |
| PIE            | pie, dedo del pie, metatarso, talón          |
| TOBILLO        | tobillo, maléolo                             |
| HOMBRO         | hombro, manguito rotador, glenohumeral       |
| CODO           | codo, epicóndilo, olécranon                  |
| MANO           | mano, dedos, nudillos                        |
| MUÑECA         | muñeca, carpo, cúbito radio distal           |
| COLUMNA        | columna, espalda, lumbar, cervical, hernia   |
| PELVIS         | pelvis, ilion, acetábulo, isquion            |

---

## Entidad: PROCEDIMIENTO

| Valor Canónico    | Sinónimos                                                   |
| ----------------- | ----------------------------------------------------------- |
| ARTROSCOPIA       | artroscopia, artroscopía, arthroscopy, endoscopia articular |
| REEMPLAZO_RODILLA | reemplazo rodilla, prótesis rodilla, artroplastia rodilla   |
| REEMPLAZO_CADERA  | reemplazo cadera, prótesis cadera, artroplastia cadera      |
| LCA               | LCA, ligamento cruzado, ACL, ligamento cruzado anterior     |
| MENISCO           | menisco, meniscectomía, reparación meniscal                 |
| FRACTURA          | fractura, hueso roto, quebrarse un hueso                    |
| TRAUMA            | trauma, accidente, trauma ortopédico                        |
| CIRUGIA_MANO      | cirugía mano, tunel carpiano, tendones mano                 |
| CIRUGIA_PIE       | cirugía pie, juanete, hallux valgus                         |

---

## Entidad: ASEGURADORA

| Valor Canónico | Sinónimos                                |
| -------------- | ---------------------------------------- |
| SEGUROS_ALIADO | Aliado, Seguros Aliado                   |
| BUPA           | Bupa, BUPA, Bupa Global                  |
| BLUE_CROSS     | Blue Cross, Blue Cross Blue Shield, BCBS |
| SAGICOR        | Sagicor                                  |
| MAPFRE         | Mapfre, MAPFRE                           |
| CIGNA          | Cigna                                    |
| AXA            | AXA                                      |

---

## Entidad: CANAL_CONTACTO

| Valor Canónico | Valor real                                                  |
| -------------- | ----------------------------------------------------------- |
| TELEFONO       | 261-7275 / +507 261-7275                                    |
| WHATSAPP       | 6673-2716                                                   |
| EMAIL          | atencionalcliente@ortopedasdepanama.net                     |
| CLINIWEB       | https://app.cliniweb.com/es/perfil/[handle]                 |
| PRESENCIAL     | Centro Especializado San Fernando, Piso 8, Consultorio 8-15 |

---

## Entidad: URGENCIA

| Nivel       | Indicadores                                                | Respuesta                   |
| ----------- | ---------------------------------------------------------- | --------------------------- |
| EMERGENCIA  | accidente, fractura abierta, urgente, ahora, 911, sangrado | Dar 261-7275 directo + 24/7 |
| URGENTE     | dolor severo, no puedo caminar, lesión reciente            | Agendar cita urgente        |
| NORMAL      | dolor crónico, seguimiento, chequeo                        | Agendar cita normal         |
| INFORMACION | preguntar, quiero saber, información                       | Responder informativo       |

---

## Entidad: ESPECIALIDAD_MEDICA

| Especialidad       | Doctores Asignados                       |
| ------------------ | ---------------------------------------- |
| RODILLA            | Dra. Vargas, Dr. Fuentes                 |
| CADERA             | Dr. Ford Sosa, Dr. Franco, Dr. Varela    |
| PIE_TOBILLO        | Dr. Alemán, Dr. Mendez                   |
| HOMBRO_CODO        | Dra. Vargas, Dra. Marxen                 |
| MANO_MUNECA        | Dr. Alessandría, Dra. Nikolaev           |
| COLUMNA            | → 261-7275 para asignación               |
| MEDICINA_DEPORTIVA | Dr. Fuentes, Dra. Marxen                 |
| TRAUMA             | Dr. Ford Mora, Dr. Franco, Dr. Varela    |
| REEMPLAZOS         | Dr. Ford Sosa, Dr. Ford Mora, Dr. Varela |

---

## Entidad: IDIOMA_PREFERIDO

| Idioma    | Detección             |
| --------- | --------------------- |
| ESPAÑOL   | mensaje en español    |
| INGLÉS    | message in English    |
| FRANCÉS   | message en français   |
| PORTUGUÉS | mensagem em português |

_Nota: Doctors Ford Mora (EN/FR/PT) y Varela (EN/PT) atienden en múltiples idiomas_

---

## Tags

#chatbot #entidades #NER #NLP #extraccion #doctor #especialidad #seguro
