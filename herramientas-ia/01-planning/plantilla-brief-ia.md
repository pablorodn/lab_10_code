# Plantilla Technical Brief

---

## 1. Título de la tarea

`[Una frase que diga exactamente qué se va a construir o refactorizar, con intención arquitectónica clara]`

**Ejemplo:** Extraer lógica de cálculo de descuentos a un servicio desacoplado y testeable.

---

## 2. Contexto

**Sistema actual:**  
`[Qué existe hoy, cómo está organizado, en qué lenguaje, framework o arquitectura corre]`

**Problema:**  
`[Qué falla, qué riesgo tiene, por qué no puede seguir así]`

**Objetivo:**  
`[Qué debe quedar resuelto cuando esto esté listo. No el "qué hacer", sino el "para qué"]`

---

## 3. Requerimientos técnicos

| Campo | Valor |
|---|---|
| Lenguaje | `[ ]` |
| Framework / Runtime | `[ ]` |
| Arquitectura esperada | `[ ]` (ej: servicio stateless, patrón strategy, módulo independiente) |
| Inputs | `[ ]` (tipos, formato, de dónde vienen) |
| Outputs | `[ ]` (tipos, formato, a dónde van) |
| Integraciones | `[ ]` (qué otros módulos o servicios debe tocar o ignorar) |

---

## 4. Constraints

- **Qué NO debe hacer la IA:** `[ ]`  
- **Archivos que no debe modificar:** `[ ]`  
- **Librerías permitidas:** `[ ]`  
- **Librerías prohibidas:** `[ ]`  
- **Estándares de código que debe respetar:** `[ ]` (ej: sin any en TypeScript, sin floats en lógica financiera)  
- **Testing requerido:** `[ ]` (ej: unitarios con Jest, sin mocks innecesarios)  
- **Compatibilidad:** `[ ]` (versiones, entornos, OS si aplica)

---

## 5. Definition of Done

- [ ] `[Test o criterio verificable 1]`
- [ ] `[Test o criterio verificable 2]`
- [ ] `[Test o criterio verificable 3]`
- [ ] Linter pasa sin errores ni warnings
- [ ] No se modificaron archivos fuera del alcance del brief
- [ ] `[Cobertura mínima de tests, si aplica]`
- [ ] `[Documentación generada o actualizada, si aplica]`

---

## Cómo usar esta plantilla

1. **Copiar y completar** antes de abrir cualquier conversación con la IA.
2. **Pegar el brief completo** y pedirle que lo critique antes de escribir código:  
   > *"Este es mi Technical Brief. Antes de escribir código, critica el brief: ¿qué falta?, ¿qué está ambiguo?, ¿qué restricción añadirías?"*
3. **Iterar el brief** si la crítica revela huecos. Un brief con huecos genera código con suposiciones.
4. **Pedir el plan primero:**  
   > *"Basado en el brief anterior, genera un plan de implementación paso a paso. NO escribas código aún. Lista los archivos que crearás, los que modificarás y por qué, y la lógica de cada uno en lenguaje natural."*
5. **Negociar el plan** antes de ejecutar. Ahí es cuando se detectan problemas estructurales, no después de tener 300 líneas de código que corregir.

---

*Semana 1 — 10x Builders: Code*
