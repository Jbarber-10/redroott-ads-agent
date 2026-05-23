# DIAGNOSIS TREE — Árbol de decisión Redroott Meta Ads

Cuando algo en la cuenta empieza a fallar, NO actuar por instinto. Seguir el árbol de diagnóstico abajo. Cada decisión está ordenada por costo (de menor a mayor) y por probabilidad (causas más comunes primero).

Destilado de operadores experimentados (Andrew Foxwell, Sam Piliero, Nick Theriot) + post-mortems de cuentas reales.

---

## Cómo usar este documento

Cuando notes una anomalía en la cuenta:
1. Identificá el **síntoma principal** (CPA sube, ROAS baja, etc.)
2. Andá al árbol correspondiente
3. Hacé las preguntas en orden — NO saltarse pasos
4. Tomá la acción del primer nodo donde la respuesta indica un problema
5. Si nada matchea, escalá a Ignacio con todo el detalle del árbol recorrido

---

## ÁRBOL 1 — CPA está subiendo (síntoma más común)

### Pregunta 1: ¿Cuánto subió?

- **Subió < 15% vs últimos 7d** → No es alarma, probablemente ruido estadístico. Si tu base es chica (50 compras/semana), ±15% es normal. **No actúes.** Esperá 3 días más.
- **Subió 15-30%** → Posible problema. Continuá a Pregunta 2.
- **Subió >30%** → Algo cambió. Continuá a Pregunta 2 con urgencia.

### Pregunta 2: ¿Pasó en TODOS los ads o solo en algunos?

- **Solo 1-2 ads están malos, el resto bien** → Problema de creativo individual. **Acción:** evaluar pausa según reglas de `RULES_META.md` para esos ads.
- **TODO la cuenta CPA subió uniforme** → Problema sistémico. Continuá a Pregunta 3.

### Pregunta 3: ¿Cuándo empezó exactamente?

Buscá la fecha del corte:

- **Coincide con un cambio que hiciste** (subiste budget, cambiaste audience, pausaste ads ganadores, agregaste creativos) → **Causa probable: tu cambio.** Acción: revertir si es posible, o esperar 5-7 días para que Meta re-aprenda.
- **Coincide con un día de la semana / mes específico** (sábado, fin de mes) → **Estacionalidad normal.** Revisar histórico de mismo día semanas pasadas.
- **Coincide con un evento externo** (feriado CL, evento país, noticia grande) → **Distracción de audiencia.** Esperar 2-3 días.
- **No coincide con nada visible** → Continuá a Pregunta 4.

### Pregunta 4: ¿Subió el CPM también?

- **CPM subió ≥20%** → **Causa: audiencia saturada / competencia subió bids.** Acción: revisar frecuencia (Árbol 4) + agregar creativos nuevos urgente.
- **CPM estable, pero CTR cayó** → **Causa: fatiga creativa.** Acción: refrescar ads, ver Árbol 4.
- **CPM y CTR estables, pero conversiones bajaron** → **Causa: problema POST-CLICK.** Ir al Árbol 7 (problema de landing/checkout).

---

## ÁRBOL 2 — ROAS está bajando pero CPA estable

### Pregunta 1: ¿El AOV bajó?

- **Sí, AOV bajó** → **Causa: cambio de mix de productos vendidos.** No es problema de ads, es de oferta. Acción: revisar qué productos están vendiendo más.
- **No, AOV estable** → Continuá Pregunta 2.

### Pregunta 2: ¿Los purchases reportados por Meta cuadran con Shopify/Klaviyo?

- **Meta reporta MÁS purchases que Shopify** → **Atribución view-through inflada / píxel duplicando eventos.** Acción: cruzar manualmente. Si la diferencia es >15%, modo degradado.
- **Meta reporta MENOS purchases que Shopify** → **Píxel perdiendo conversiones.** Acción: revisar healthcheck del píxel en Events Manager. Probable problema técnico.
- **Match razonable (delta <10%)** → Continuá Pregunta 3.

### Pregunta 3: ¿Subió la tasa de devolución?

- **Sí** → No es problema de Meta, es de producto/expectativa. Revisar reviews recientes.
- **No** → Inexplicable con datos disponibles. Escalar a Ignacio.

---

## ÁRBOL 3 — Spend bajó pero el budget está igual

### Pregunta 1: ¿La cuenta perdió delivery?

- **Sí, antes gastaba 95% del budget, ahora gasta 60%** → Continuá Pregunta 2.
- **Solo bajó momentáneamente (ej. 1 día)** → Esperar. Probable ruido del algoritmo o competencia puntual.

### Pregunta 2: ¿Qué pasó las últimas 48h?

- **Pausaste muchos ads** → Lógico, hay menos creatives donde gastar. Acción: subir creativos nuevos.
- **Bajaste el budget** → Lógico, esperar 72h después del cambio.
- **No cambiaste nada** → Continuá Pregunta 3.

### Pregunta 3: ¿La frecuencia subió de >2.5 antes de la caída?

- **Sí** → **Causa: audiencia agotada.** Meta deja de entregar porque ya impactó a todos los que pudo. Acción: refrescar creativos + revisar audience size.
- **No** → Continuá Pregunta 4.

### Pregunta 4: ¿Hay rechazo de ads por policy?

- **Sí** (revisar Quality Assessment de cada ad) → **Causa: rechazo silencioso por policy.** Acción: revisar / apelar ads rechazados.
- **No** → Continuá Pregunta 5.

### Pregunta 5: ¿Pasó algo en tu account (account spending limit, billing)?

- **Sí** → Resolver billing issues.
- **No** → Inexplicable. Escalar a Ignacio. Posible bug de Meta (suele resolverse solo en 24-48h).

---

## ÁRBOL 4 — Frecuencia subiendo (>2.5)

### Pregunta 1: ¿Cuánto subió y cuán rápido?

- **Subió gradual** (0.3-0.5 por semana) → Normal en cuentas en fase de explotación. Acción: empezar a refrescar 20% de los creativos en pipeline.
- **Subió brusco** (de 1.8 a 3.5 en 3 días) → Anormal. Continuá Pregunta 2.

### Pregunta 2: ¿Estás corriendo audiencias chicas?

- **Sí (audiencia <500K)** → **Causa: audiencia pequeña agotándose.** Acción: expandir audience size (eliminar interest stacking) o moverse a Advantage+ que abre target.
- **No, audiencias grandes** (1M+) → Continuá Pregunta 3.

### Pregunta 3: ¿Los ads ganadores llevan mucho tiempo corriendo?

- **Sí, los top 2 ads llevan 14+ días** → **Causa: dependencia de pocos ads.** Acción urgente: variar los ganadores Y subir 2-3 conceptos nuevos.
- **No** → Continuá Pregunta 4.

### Pregunta 4: ¿La cuenta tiene >3 adsets activos?

- **Sí** → Posible overlap entre adsets (mismo usuario impactado por varios). Acción: revisar Audience Overlap en Audience Insights.
- **No** → Acción: agregar adsets con ángulos distintos para distribuir frecuencia.

---

## ÁRBOL 5 — Un ad ganador empezó a perder

### Pregunta 1: ¿Cuántos días lleva ganando?

- **<7 días** → Demasiado pronto para fatigue. Continuá Pregunta 2.
- **7-14 días** → Zona típica de inicio de fatiga. Continuá Pregunta 2.
- **>14 días** → Fatiga muy probable. **Acción inmediata: pedir variación.**

### Pregunta 2: ¿La frecuencia del ad llegó a 2.5+?

- **Sí** → Fatiga confirmada. **Acción:** Variar (mismo concepto, visual nuevo o hook nuevo).
- **No** → Continuá Pregunta 3.

### Pregunta 3: ¿El CPM del ad subió >20% en los últimos 3 días?

- **Sí** → Su audiencia se está agotando. Continuá Pregunta 4.
- **No** → Continuá Pregunta 4.

### Pregunta 4: ¿El CTR cayó >15% en los últimos 3 días?

- **Sí** → Confirmed fatiga. Variar.
- **No** → Posible ruido. Esperar 3 días más antes de actuar.

---

## ÁRBOL 6 — Un ad nuevo no arranca (sin spend o sin conversiones)

### Pregunta 1: ¿Tiene impressions?

- **No, 0 impressions con > 24h activo** → **Probable rechazo por policy** (silencioso). Acción: revisar Quality Assessment del ad.
- **Sí, tiene impressions pero 0 conversiones** → Continuá Pregunta 2.

### Pregunta 2: ¿Cuánto gastó?

- **<$15.000** → **Data insuficiente.** Dejar correr.
- **$15.000-$25.000, 0 conversiones, CTR <1%** → Mal creativo. Acción: pausar a $25.000 si no levantó.
- **$15.000-$25.000, 0 conversiones, CTR 1-2%** → Algo está atrayendo pero no convierte. Continuá Pregunta 3.
- **>$50.000 sin conversiones** → **MUERTO.** Acción: pausar (regla del playbook).

### Pregunta 3: ¿El CTR es bueno pero no convierte? (atrae pero no cierra)

Causas posibles, en orden de probabilidad:

1. **Hook ≠ landing**: el ad promete algo, la landing dice otra cosa. Acción: revisar coherencia ad → landing.
2. **Landing rota** (forms, checkout, mobile) → revisar manualmente desde el celular.
3. **Precio o oferta no encaja con audiencia**: ad atrae a personas que no son tu cliente. Acción: refinar copy del ad o audiencia.
4. **Píxel mal configurado**: ad genera ventas pero Meta no las atribuye. Acción: cruzar con Shopify/Klaviyo.

---

## ÁRBOL 7 — Problema POST-CLICK (la landing/checkout)

### Pregunta 1: ¿La conversion rate del site cayó?

- **Sí** → Continuá Pregunta 2.
- **No, CR estable** → No es problema post-click. Volver a Árboles 1-4.

### Pregunta 2: ¿Qué cambió en la landing últimamente?

- Cambió copy → revisar si afecta CTA o claridad
- Cambió precio → posible objection ahora
- Cambió foto/video → ¿se ve mal en mobile?
- Cambió checkout flow → testear manualmente
- Apareció error 500/timeout → revisar logs de Shopify

### Pregunta 3: ¿La velocidad de carga subió?

- Mobile load time > 3s → optimizar imágenes / código
- Time to interactive > 5s → revisar scripts third-party (Klaviyo, FB Pixel, etc.)

### Pregunta 4: ¿El checkout funciona desde mobile?

Probar manualmente desde tu teléfono ahora mismo. Si hay error → ese es el problema #1.

---

## ÁRBOL 8 — La cuenta entera empezó a fallar

Cuando NADA funciona y todo se cae al mismo tiempo:

### Pregunta 1: ¿El píxel está disparando eventos?

- **No** → **Píxel caído.** Causa más común de cuenta entera fallando. Acción inmediata: revisar Events Manager → Test Events.
- **Sí, dispara** → Continuá Pregunta 2.

### Pregunta 2: ¿Hubo update de iOS / Chrome / safari reciente?

- **Sí** → Posible degradación de tracking. Wait & see 7 días.
- **No** → Continuá Pregunta 3.

### Pregunta 3: ¿Hay un evento país / mundial grande?

- **Sí** (elecciones, paro nacional, evento deportivo) → Audience distraída. Esperar.
- **No** → Continuá Pregunta 4.

### Pregunta 4: ¿Empezó después de cambios estructurales tuyos?

- Pausaste muchos ads → re-encender los que no eran lo suficientemente malos para pausar
- Cambiaste objetivo de campaña → revertir
- Cambiaste píxel → revertir y validar

Si nada matchea → **escalar a Ignacio con TODA la información** (timeline de cambios, métricas antes/después, hipótesis).

---

## ÁRBOL 9 — Klaviyo y Meta no cuadran

### Pregunta 1: ¿Qué tan grande es la diferencia?

- **<5%** → Normal. View-through attribution + delay normal.
- **5-15%** → Vigilar. Cruzar 2-3 días seguidos.
- **>15%** → Continuá Pregunta 2.

### Pregunta 2: ¿En qué dirección?

- **Meta reporta MÁS que Klaviyo** → Atribución inflada. Causas:
  - View-through attribution (gente que vio el ad pero compró sin clic)
  - Píxel disparando duplicados
  - Customers que compran sin email tracking
- **Meta reporta MENOS que Klaviyo** → Píxel perdiendo eventos. Causas:
  - Ad blockers / iOS14.5
  - Píxel mal instalado
  - Eventos no llegando vía CAPI

### Pregunta 3: ¿Cuánto tiempo lleva la discrepancia?

- **1 día aislado** → Ruido. Ignorar.
- **3+ días seguidos** → Hay un patrón. **Modo degradado: agente solo recomienda, NO ejecuta acciones**. Escalar a Ignacio para investigar.

---

## ÁRBOL 10 — Cuándo escalar el problema a Ignacio (en vez de actuar)

Siempre escalar (en vez de actuar) si:

1. La data parece imposible (CPA $0, 1000 compras de un ad nuevo, etc)
2. Más del 50% de los ads de la cuenta están en línea roja simultáneamente
3. Las pausas que ya hiciste hoy NO mejoraron el CPA blended
4. Klaviyo y Meta tienen discrepancia >15% por 3+ días
5. Cualquier acción que propongas tomar gastaría más de $50.000 CLP/día
6. Identificás un problema fuera de Meta Ads (landing rota, checkout, producto)
7. Tu hipótesis principal contradice las reglas del playbook
8. Notás algo extraño que no está en ningún árbol arriba

**Cómo escalar bien:**

Email + Telegram a Ignacio con:
- **Asunto:** "⚠️ ESCALADO — [resumen 1 línea]"
- **Síntoma observado:** datos exactos
- **Árbol(es) recorridos:** qué preguntas hiciste, qué respuestas dieron
- **Hipótesis:** qué creés que pasa
- **Acción que propondrías:** explicada
- **Por qué no actuás solo:** la regla que te lo impide o la incertidumbre
- **Decisiones que necesitás de Ignacio:** lista clara

---

## Anti-patrones (cosas que NO hacer cuando algo falla)

| Anti-patrón | Por qué no |
|---|---|
| Pausar todo y empezar de cero | Pierdes 6+ semanas de aprendizaje del píxel |
| Cambiar 5 cosas el mismo día | No vas a poder atribuir qué arregló qué |
| Tocar ad sets en aprendizaje | Reseteas y empeoras el problema |
| Subir budget para "salir del bache" | Subir budget en mal momento empeora todo |
| Cambiar bid strategy a "lowest cost cap" en pánico | Te quedas sin entrega |
| Crear campaña nueva paralela "para ver" | Fragmentas el aprendizaje |
| Re-activar ads que pausaste hace 2 días | Si pausaste por algo, dejalos pausados al menos 7 días |

---

## Reglas de oro de diagnóstico

1. **Si la data es rara, NO actúes.** Investigá primero.
2. **Si dudas, espera 24h.** La paciencia gana CPAs.
3. **Cuenta no se rompe en 1 día, no se arregla en 1 día.** Cambios sostenidos.
4. **Pausar es reversible. Subir budget descontrolado, no.** Default conservador.
5. **La regla más útil: "¿qué cambió que antes funcionaba?".** Empezar siempre ahí.
