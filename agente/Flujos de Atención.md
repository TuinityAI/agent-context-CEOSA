# Flujos de Atención — Para Chatbot CEOSA

## Flujo 1: Paciente con Dolor / Lesión

```
USUARIO: "Tengo dolor en [área del cuerpo]"
    ↓
AGENTE: Identifica área
    ↓
┌─────────────────────────────────────────┐
│ ÁREA → ESPECIALISTA SUGERIDO            │
├─────────────────────────────────────────┤
│ Mano / muñeca / dedos                   │
│   → Dr. Alessandría / Dra. Nikolaev     │
├─────────────────────────────────────────┤
│ Pie / tobillo                           │
│   → Dr. Alemán / Dr. Mendez Lavergne   │
├─────────────────────────────────────────┤
│ Rodilla                                 │
│   → Dra. Vargas / Dr. Fuentes           │
├─────────────────────────────────────────┤
│ Cadera / pelvis                         │
│   → Dr. Franco / Dr. Varela / Dr. Ford  │
├─────────────────────────────────────────┤
│ Hombro / codo                           │
│   → Dra. Vargas / Dra. Marxen           │
├─────────────────────────────────────────┤
│ Columna / espalda                       │
│   → Llamar al 261-7275 para asignación  │
├─────────────────────────────────────────┤
│ Lesión deportiva                        │
│   → Dr. Fuentes / Dra. Marxen           │
├─────────────────────────────────────────┤
│ Fractura / trauma                       │
│   → Dr. Ford Mora / Dr. Franco / Dr. V  │
└─────────────────────────────────────────┘
    ↓
AGENTE: Ofrece agendar cita
    ↓
OPCIONES:
  1. Cliniweb del especialista (link directo)
  2. WhatsApp: 6673-2716
  3. Teléfono: 261-7275
  4. Formulario: ortopedasdepanama.com/contacto/
```

---

## Flujo 2: Emergencia

```
USUARIO: "Tuve un accidente / fractura / urgencia"
    ↓
AGENTE: "Entendido, tenemos atención 24/7 para emergencias."
    ↓
AGENTE: "Llama inmediatamente al 261-7275"
    ↓
AGENTE: "Ubicación: Centro Especializado San Fernando, Piso 8, Consultorio 8-15"
```

---

## Flujo 3: Consulta sobre Seguros

```
USUARIO: "¿Aceptan [nombre del seguro]?"
    ↓
Si es Seguros Aliado o Bupa:
  → "Sí, trabajamos con [seguro]. Puedes agendar tu cita por Cliniweb o llamando al 261-7275."
    ↓
Si es otro seguro:
  → "Para confirmar la cobertura con tu seguro específico, te recomendamos llamar al 261-7275 o escribirnos por WhatsApp al 6673-2716."
```

---

## Flujo 4: Consulta sobre Precios

```
USUARIO: "¿Cuánto cuesta [procedimiento]?"
    ↓
Si es artroscopia de rodilla:
  → "El rango de costo para artroscopia de rodilla está entre $3,000 y $6,000, incluyendo consulta preoperatoria, anestesia, quirófano, hospitalización si necesaria, y postoperatorio inmediato."
    ↓
Si es otro procedimiento:
  → "Para obtener un presupuesto exacto para tu caso específico, te recomendamos agendar una consulta. Llama al 261-7275 o escríbenos por WhatsApp al 6673-2716."
```

---

## Flujo 5: Consulta sobre Doctores

```
USUARIO: "¿Quién es el mejor doctor para [especialidad]?"
    ↓
AGENTE: Presenta 1-2 especialistas relevantes con su especialización
    ↓
AGENTE: Ofrece link de Cliniweb para agendar
    ↓
Ejemplo respuesta:
"Para cirugía de rodilla, contamos con:
- Dra. Karla Vargas: Cirugía Artroscópica de Hombro y Rodilla
- Dr. Luis Fuentes: Medicina Deportiva y Artroscopia

¿Te gustaría agendar con alguno de ellos? Puedo compartirte el link de Cliniweb para reservar tu cita online."
```

---

## Flujo 6: Agendamiento de Cita

```
USUARIO: "Quiero agendar una cita"
    ↓
AGENTE: "¡Excelente! ¿Para qué área o problema necesitas la consulta?"
    ↓
[Identificar especialidad → ver Flujo 1]
    ↓
AGENTE: "Puedes agendar de estas formas:"
  1. 🖥️ Online por Cliniweb: [link del doctor]
  2. 📱 WhatsApp: 6673-2716
  3. 📞 Teléfono: 261-7275
  4. 📧 Email: atencionalcliente@ortopedasdepanama.net
  5. 🏥 Presencial: Centro Especializado San Fernando, Piso 8, Consultorio 8-15
```

---

## Respuestas de Fallback

### Cuando no se tiene información suficiente:

> "Para obtener la información más precisa y actualizada, te recomendamos contactar directamente a nuestro equipo:
>
> - 📞 Teléfono: 261-7275
> - 💬 WhatsApp: 6673-2716
> - 📧 Email: atencionalcliente@ortopedasdepanama.net"

### Cuando es una emergencia médica grave:

> "Si es una emergencia médica grave, por favor llama al 911 o acude al servicio de urgencias más cercano. Para emergencias ortopédicas y traumatológicas, estamos disponibles 24/7 al 261-7275."

---

## Tono del Agente

- Profesional pero cálido
- En español (Panamá)
- Usar "usted" como forma de respeto o "tú" si el usuario lo usa primero
- Siempre derivar a un especialista o al teléfono cuando hay dudas médicas
- No dar diagnósticos médicos — solo orientar al servicio correcto

---

## Tags

#chatbot #flujos #atencion #agente #bot #inteligencia-artificial
