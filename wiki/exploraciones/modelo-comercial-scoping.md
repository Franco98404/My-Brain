---
tipo: exploracion
tags: [comercial, eurekant, scoping, modelo-negocio, precio-fijo]
creado: 2026-06-07
actualizado: 2026-06-07
fuentes: [conversacion-modelo-comercial-2026-06-07]
---

# Modelo Comercial — Scoping y Precio Fijo

Exploración del rediseño del modelo de ventas de [[eurekant]], específicamente cómo resolver el ciclo de "necesito SRS para dar precio fijo, pero el cliente no paga antes de saber el precio".

## El problema (el bucle)

- Para dar precio fijo se necesita un SRS completo.
- El SRS completo requiere entre 2hs (proyecto simple) y 20+hs (proyecto complejo) de trabajo.
- El cliente no quiere pagar antes de conocer el precio total ni antes de confiar en Eurekant.
- Los competidores no cobran por el Scoping → cobrar por él genera fricción adicional.

## Diagnóstico

El problema tiene dos causas simultáneas:

1. **Confianza** — el cliente no conoce Eurekant todavía.
2. **Modelo** — la estructura de "pagar por el SRS antes de saber el precio final" es contraria a cómo funciona el mercado LatAm de SMBs/startups.

Los clientes que se fueron no rechazaron el precio final (el proyecto les cerraba), sino el Scoping previo.

## Modelo descartado: Scoping pago ($200 / $500)

Intentado con $200 → algunos clientes rechazaron por falta de confianza.
Analizado con $500 + deducible del total → descartado porque ningún competidor cobra por esto y el mercado no lo acepta en frío.

**Conclusión del LLM Council (2026-06-07):** el problema no es el precio del Scoping sino que es un peaje de acceso antes de establecer confianza. Subir el precio amplifica el problema, no lo resuelve.

## Modelo adoptado: Scoping gratis + SRS durante el proyecto

### Funnel completo

1. **Llamada comercial** — gratis. Presentación, entender el negocio.
2. **Reunión técnica con PM** — 1 reunión, máximo 2hs, gratis. Objetivo: clasificar el proyecto en simple/intermedio/complejo y tener suficiente info para estimar.
3. **Informe Preliminar** — generado con el skill `eurekant-preliminary-report`. Incluye estimación rough por complejidad y roadmap orientativo. Se envía al cliente. *Filtra aquí: si el rango no les cierra, se van sin costo para Eurekant.*
4. **Si aceptan el rango → firman el Contrato de Desarrollo** con:
   - Precio estimado con rango explícito (ej: "entre $17.000 y $22.000")
   - Buffer del 20-30% incorporado
   - Cláusula de scope change: funcionalidades no contempladas en el estimado → adendum con costo adicional
5. **SRS completo** — se redacta en la primera semana del proyecto, ya con el primer pago cobrado.

### Protección sin SRS previo

La protección ante scope creep es contractual, no documental:

- Estimado con rango explícito (no precio puntual)
- Cláusula de adendum en el contrato
- SRS completo generado en semana 1 y aprobado por el cliente como baseline

## Escala de complejidad y pisos de precio

| Complejidad | Reuniones técnicas | Estimado rough |
|---|---|---|
| Simple | 1-2hs en total | Desde USD 11.500 / 2 meses |
| Intermedio | 2-3 reuniones | Desde USD 17.000 / 3 meses |
| Complejo | 4+ reuniones | Desde USD 22.500 / 4 meses |

## Insight clave del LLM Council

> "El Informe Preliminar es el activo desaprovechado. Hoy termina en un apretón de manos. Debería terminar con un camino concreto hacia el siguiente paso — el contrato de desarrollo."

Acción pendiente: rediseñar el cierre del Informe Preliminar para que incluya una oferta concreta y nombrada del siguiente paso, con precio y descripción exacta de qué recibe el cliente.

## Ver también

- [[estructura-comercial-eurekant]] — pipeline comercial en ClickUp
- [[eurekant]] — empresa
- [[tooling-eurekant]] — skill eurekant-preliminary-report
