# Chatbot Intents — CEOSA

## Definición

Un **intent** es la intención del usuario al enviar un mensaje. El chatbot debe identificar el intent y responder apropiadamente.

---

## Categoría 1: AGENDAR CITA

### intent_agendar_cita_general

**Frases de Entrenamiento:**

- "Quiero agendar una cita"
- "Necesito una consulta"
- "¿Cómo hago una cita?"
- "Quiero ver a un doctor"
- "¿Puedo hacer una cita?"
- "Quiero reservar una consulta"
- "Necesito ver a un ortopeda"
- "I want to make an appointment"
- "Schedule appointment"

**Respuesta:**

```
"¡Claro! Puedes agendar tu cita de las siguientes formas:

🖥️ Online (Cliniweb): app.cliniweb.com/es/perfil/[doctor]
📱 WhatsApp: 6673-2716
📞 Teléfono: 261-7275
📧 Email: atencionalcliente@ortopedasdepanama.net
🏥 Presencial: Centro Especializado San Fernando, Piso 8, Consultorio 8-15

¿Para qué especialidad o área del cuerpo necesitas la consulta? Así te puedo indicar el doctor más adecuado."
```

---

### intent_agendar_cita_doctor_especifico

**Frases de Entrenamiento:**

- "Quiero cita con el Dr. Ford"
- "¿Cómo cito con Karla Vargas?"
- "Necesito ver a Luis Fuentes"
- "Quiero una cita con la doctora Marxen"

**Respuesta:** Dar link de Cliniweb del doctor específico

---

### intent_agendar_cita_especialidad

**Frases de Entrenamiento:**

- "Quiero cita con el especialista de rodilla"
- "Necesito el doctor de pie"
- "¿Quién atiende cadera?"
- "Necesito un traumatólogo"

**Acción:** Identificar especialidad → buscar doctor en tabla de routing → dar link Cliniweb

---

## Categoría 2: INFORMACIÓN DE DOLOR / SÍNTOMAS

### intent_dolor_rodilla

**Frases de Entrenamiento:**

- "Tengo dolor en la rodilla"
- "Me duele la rodilla"
- "Lesión en la rodilla"
- "Me caí y me lastimé la rodilla"
- "Creo que me rompí la rodilla"
- "Tengo la rodilla inflamada"
- "Dolor al doblar la rodilla"

**Respuesta:**

```
"Para problemas de rodilla, contamos con especialistas en artroscopia y cirugía de rodilla:

🦵 Dra. Karla Vargas — Artroscopia de Hombro y Rodilla
🦵 Dr. Luis Fuentes — Medicina Deportiva y Artroscopia

¿Deseas agendar una consulta? Puedo darte el link de Cliniweb para reservar tu cita online, o puedes llamar al 261-7275."
```

---

### intent_dolor_cadera

**Frases de Entrenamiento:**

- "Me duele la cadera"
- "Dolor en la cadera"
- "Tengo problema en la cadera"
- "Fractura de cadera"
- "Artrosis de cadera"

**Doctores a sugerir:** Dr. Ford Sosa, Dr. Franco, Dr. Varela

---

### intent_dolor_pie_tobillo

**Frases de Entrenamiento:**

- "Me duele el pie"
- "Dolor en el tobillo"
- "Lesión en el tobillo"
- "Me torcí el tobillo"
- "Juanete"
- "Espolón calcáneo"
- "Pie plano"

**Doctores a sugerir:** Dr. Alemán, Dr. Mendez Lavergne

---

### intent_dolor_hombro

**Frases de Entrenamiento:**

- "Me duele el hombro"
- "Dolor en el hombro"
- "Lesión de hombro"
- "Manguito rotador"
- "Hombro congelado"
- "Me disloqé el hombro"

**Doctores a sugerir:** Dra. Vargas, Dra. Marxen

---

### intent_dolor_mano_muneca

**Frases de Entrenamiento:**

- "Me duele la mano"
- "Dolor en la muñeca"
- "Túnel carpiano"
- "Dedo en gatillo"
- "Fractura en la mano"
- "Lesión en los dedos"

**Doctores a sugerir:** Dr. Alessandría, Dra. Nikolaev

---

### intent_dolor_espalda_columna

**Frases de Entrenamiento:**

- "Me duele la espalda"
- "Dolor lumbar"
- "Hernia de disco"
- "Ciática"
- "Dolor en la columna"

**Respuesta:** Derivar al 261-7275 para asignación específica de especialista en columna

---

### intent_lesion_deportiva

**Frases de Entrenamiento:**

- "Me lesioné jugando fútbol"
- "Lesión deportiva"
- "Me lastimé en el gimnasio"
- "Lesión de ligamento"
- "Desgarro muscular"
- "LCA"
- "Menisco roto"

**Doctores a sugerir:** Dr. Fuentes, Dra. Marxen

---

### intent_fractura_trauma

**Frases de Entrenamiento:**

- "Me fracturé"
- "Tengo una fractura"
- "Accidente de carro"
- "Me caí y me partí algo"
- "Fractura abierta"
- "Necesito cirugía de urgencia"

**Respuesta:** Enfatizar atención 24/7, dar 261-7275 directo

---

## Categoría 3: EMERGENCIAS

### intent_emergencia

**Frases de Entrenamiento:**

- "Es una emergencia"
- "Tuve un accidente"
- "Me fracturé ahora"
- "Necesito atención urgente"
- "Estoy en urgencias"
- "Emergency"

**Respuesta:**

```
"Para emergencias ortopédicas, contamos con atención 24/7.

🚨 Llama AHORA al: 261-7275

📍 Dirección: Centro Especializado San Fernando, Piso 8, Consultorio 8-15

Para emergencias médicas graves que requieran sala de urgencias, llama al 911."
```

---

## Categoría 4: INFORMACIÓN DE SEGUROS

### intent_consulta_seguro

**Frases de Entrenamiento:**

- "¿Aceptan mi seguro?"
- "¿Trabajan con [nombre seguro]?"
- "¿Tienen convenio con Bupa?"
- "¿Aceptan Aliado?"
- "¿Cubren mi póliza?"

**Lógica:**

- Aliado → ✅ Confirmar
- Bupa → ✅ Confirmar (Dra. Marxen)
- Otros → Derivar al 261-7275

---

## Categoría 5: PRECIOS

### intent_precio_procedimiento

**Frases de Entrenamiento:**

- "¿Cuánto cuesta la artroscopia?"
- "¿Qué precio tiene la cirugía de rodilla?"
- "¿Cuánto cobra el doctor?"
- "Precio de reemplazo de rodilla"
- "¿Cuánto sale la consulta?"

**Lógica:**

- Artroscopia de rodilla → $3,000-$6,000 (confirmar)
- Otros → "Para un presupuesto exacto, agenda una consulta al 261-7275"

---

## Categoría 6: INFORMACIÓN INSTITUCIONAL

### intent_donde_estan

**Frases de Entrenamiento:**

- "¿Dónde están ubicados?"
- "¿Cuál es la dirección?"
- "¿Cómo llego?"
- "Location"
- "¿Están en Panama City?"

**Respuesta:** Dar dirección + Maps link

---

### intent_horarios

**Frases de Entrenamiento:**

- "¿Cuál es el horario?"
- "¿Atienden los sábados?"
- "¿Cuándo abren?"
- "Hours of operation"

**Respuesta:** Horarios de CEOSA (L-V 8:30-6:30 para Ford Mora, confirmar CEOSA general)

---

### intent_informacion_doctor

**Frases de Entrenamiento:**

- "¿Quién es el mejor doctor para rodilla?"
- "¿Qué doctores tienen?"
- "¿Qué especialidades tienen?"
- "Tell me about your doctors"

---

### intent_saludo

**Frases de Entrenamiento:**

- "Hola"
- "Buenos días"
- "Hello"
- "Hi"

**Respuesta:**

```
"¡Hola! Bienvenido al Centro de Especialidades Ortopédicas (CEOSA),
el primer grupo ortopédico fundado en Panamá.

¿En qué puedo ayudarte hoy?
- 📅 Agendar una cita
- 👨‍⚕️ Información sobre nuestros especialistas
- 💊 Consultar sobre un dolor o lesión
- 📍 Información de ubicación y contacto"
```

---

### intent_despedida

**Frases de Entrenamiento:**

- "Gracias"
- "Adiós"
- "Hasta luego"
- "Bye"

**Respuesta:**

```
"¡Con gusto! Recuerda que estamos disponibles para cualquier consulta
en el 261-7275 o WhatsApp al 6673-2716. ¡Que te mejores pronto! 🙏"
```

---

## Categoría 7: FALLBACK

### intent_fuera_de_scope

**Cuando no se identifica ningún intent válido:**

**Respuesta:**

```
"Entiendo tu consulta. Para darte la información más precisa,
te recomendamos contactar directamente a nuestro equipo:

📞 Teléfono: 261-7275
💬 WhatsApp: 6673-2716
📧 Email: atencionalcliente@ortopedasdepanama.net"
```

---

## Tags

#chatbot #intents #NLP #clasificacion #flujos #CEOSA #agente
