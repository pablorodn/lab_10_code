# Protocolo de Review para Código Generado por IA

---

## Cómo usarlo

1. Abrir el código generado junto al brief y el plan aprobado.
2. Revisar cada sección. Marcar cada punto como:
   - **OK** — cumple, no hay observación.
   - **Riesgo bajo** — funciona pero podría mejorar.
   - **Corregir** — hay un problema concreto. Describir qué y por qué.
3. Si no encuentro nada malo: pedirle a la IA que revise su propio código usando este checklist. La IA tiende a ser complaciente, pero a veces ella misma detecta lo que yo pasé por alto.
4. No hacer commit hasta que no haya ningún punto en **Corregir**.

---

## Sección 1 — Alucinaciones de librerías o APIs

| # | Check | Estado | Observación |
|---|---|---|---|
| 1.1 | ¿Todos los imports están instalados en el proyecto? | | |
| 1.2 | ¿Las librerías referenciadas son reales y no deprecadas? | | |
| 1.3 | ¿Las funciones y métodos usados existen en la documentación oficial? | | |
| 1.4 | ¿La versión de las dependencias es compatible con el entorno? | | |

---

## Sección 2 — Lógica de negocio

| # | Check | Estado | Observación |
|---|---|---|---|
| 2.1 | ¿La lógica cumple exactamente lo que dice el brief, no una interpretación de él? | | |
| 2.2 | ¿Las condiciones son completas o hay ramas que nunca ejecutan? | | |
| 2.3 | ¿Se cubren los casos borde del dominio? | | |
| 2.4 | ¿El tipo de dato usado es el adecuado para la operación? | | |

**Entradas para probar el código:**
- Valores válidos en los límites del rango esperado
- Inputs nulos, vacíos o del tipo incorrecto
- Valores fuera del rango esperado
- Combinaciones que activen ramas poco frecuentes

---

## Sección 3 — Seguridad

| # | Check | Estado | Observación |
|---|---|---|---|
| 3.1 | ¿Hay credenciales, tokens o secrets hardcodeados? | | |
| 3.2 | ¿Hay riesgo de SQL Injection en queries construidas con strings? | | |
| 3.3 | ¿Hay riesgo de Command Injection si se ejecutan procesos del sistema? | | |
| 3.4 | ¿Se validan y sanitizan los inputs antes de procesarlos? | | |
| 3.5 | ¿Los logs exponen información sensible (emails, tokens, datos de usuarios)? | | |
| 3.6 | ¿Hay endpoints o funciones que deberían tener autenticación y no la tienen? | | |

---

## Sección 4 — Respeto del brief y el plan

| # | Check | Estado | Observación |
|---|---|---|---|
| 4.1 | ¿El código cumple las secciones del brief original? | | |
| 4.2 | ¿Respeta todos los constraints definidos (librerías, patrones, archivos)? | | |
| 4.3 | ¿Sigue la estructura del plan aprobado, en el mismo orden? | | |
| 4.4 | ¿Modificó algún archivo que el brief marcaba como intocable? | | |
| 4.5 | ¿Cambió alguna interfaz o contrato sin haber pedido permiso explícito para hacerlo? | | |
| 4.6 | ¿Ignoró algún requerimiento inicial por desbordamiento de contexto? | | |

---

## Sección 5 — Criterio propio del stack

| # | Check | Estado | Observación |
|---|---|---|---|
| 5.1 | ¿Los tests realmente ejecutan el código nuevo y no solo el viejo? | | |
| 5.2 | ¿El linter pasa sin errores ni warnings? | | |
| 5.3 | ¿Hay logs de debug que se colaron y no deberían estar en producción? | | |
| 5.4 | ¿Se agregaron dependencias que no eran necesarias? | | |
| 5.5 | ¿El código respeta la arquitectura y convenciones del proyecto? | | |

---

## Señales de diseño sólido (buenas noticias)

- La IA extendió el código agregando clases o módulos nuevos sin romper lo existente.
- Las nuevas reglas se agregan en archivos separados, no dentro de los originales.
- Hay bajo acoplamiento entre el módulo nuevo y los existentes.
- El código nuevo no duplica lógica que ya existía.

## Señales de diseño frágil (a corregir antes de continuar)

- La IA metió `if/else` improvisados dentro de un archivo que ya existía.
- Duplicó lógica en vez de reutilizar lo que había.
- Acopló la nueva funcionalidad directamente al módulo que se quería desacoplar.
- El código funciona para el caso que pedí, pero no va a aguantar el siguiente cambio.

---

## Prompt para pedirle a la IA que se autoevalúe

```
Revisa el código que generaste usando este protocolo de review. 
Para cada sección, marca cada punto como OK, Riesgo bajo o Corregir, 
y explica brevemente por qué. Sé específico, no genérico.
```

---

*Semana 1 — 10x Builders: Code*
