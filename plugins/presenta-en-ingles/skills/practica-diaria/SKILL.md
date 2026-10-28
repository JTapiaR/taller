---
name: practica-diaria
description: Genera una ficha breve de práctica diaria en inglés para la presentación de resultados anuales. Pensada para ejecutarse desde una tarea programada, sin interacción.
argument-hint: "[tema opcional]"
---

# Práctica diaria

Esta skill se ejecuta normalmente desde una **tarea programada**, sin nadie al otro lado. Por eso:

- **No hagas preguntas** ni esperes respuesta. Genera la ficha completa de una vez.
- No modifiques archivos ni ejecutes comandos, salvo leer el banco de frases.

Tema opcional del día: $ARGUMENTS

## Qué hacer

1. Lee el banco de frases en `../coach-presentacion/frases.md` (relativo a esta carpeta).
2. Usa la fecha de hoy para variar el contenido: elige secciones distintas del banco según el día de la semana (lunes: apertura y highlights; martes: cifras; miércoles: objetivos y retos; jueves: perspectivas y transiciones; viernes: gestión de preguntas; fin de semana: cierre y repaso mixto). Si hay tema opcional, prioriza las frases relacionadas con él.
3. Genera la ficha con este formato exacto, en Markdown:

```
# Práctica diaria — [fecha]

## 5 frases del día
1. **[frase en inglés]** — [traducción al español]
   Pista: [palabra difícil o cómo usarla]
...

## Cifras en voz alta
Lee en voz alta: [3 cifras inventadas pero realistas: moneda, porcentaje, fecha/trimestre]
Solución: [cómo se dice cada una]

## Pregunta difícil del día
"[pregunta en inglés]"
Piensa tu respuesta en 30 segundos. Respuesta modelo: [3–4 frases en inglés]

## Mini-reto
[Un ejercicio de 2 minutos, p. ej. grabarse diciendo la apertura con dos frases del día]
```

Mantén la ficha corta: que se lea en menos de 5 minutos.
