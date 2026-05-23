# SCALING PLAYBOOK — Redroott Meta Ads

Cuándo subir presupuesto, cuántos ads producir por semana, cuándo ir agresivo y cuándo ir cauto. Destilado de los mejores operadores DTC (Nick Theriot, Davie Fogarty, Charlie Lawrance, Sam Piliero, Mark Builds Brands) + data post-iOS14.5 / era Advantage+.

Aplicar SIEMPRE en combinación con `RULES_META.md` (números de Redroott). Este doc cubre el "cómo decidir", `RULES_META.md` cubre el "los umbrales exactos".

---

## 1. Los 5 principios universales (no negociables)

### Principio 1 — Money loves speed, pero ad accounts hate change

Acelera la velocidad de creativos. Frena la velocidad de cambios estructurales.

- **Subir budget:** máximo 1 cambio cada 72h por ad set, +20% por cambio (regla universal).
- **Subir creativos:** lo más rápido que la calidad permita. 3-6 ads nuevos/semana es estándar para Tier 2.
- **Cambiar audiencia:** mínimo 7 días entre cambios. Cada cambio resetea aprendizaje.

### Principio 2 — Nunca tocar un ad set en fase de aprendizaje

Meta penaliza fuertemente las interrupciones en learning phase. Mínimo 50 conversiones acumuladas antes de tocar.

Si pausas un ad dentro de un adset en aprendizaje, NO resetea aprendizaje del adset (solo el ad). Si pausas, cambias budget, o cambias audience del adset → SÍ resetea.

### Principio 3 — Una variable a la vez

NO subir budget el mismo día que se suben ads nuevos. NO cambiar audiencia el día que se subió budget. Cada variable se mueve sola para poder atribuir.

### Principio 4 — Asume nothing, mide todo

CPA blended de cuenta vs CPA por ad activo son cosas distintas. CPA hoy vs CPA 7d son cosas distintas. Antes de cualquier acción, mira la métrica relevante en la ventana relevante.

### Principio 5 — Entropía es real

Todo ad muere. Todo ganador entra en fatiga. El sistema NO sobrevive sin pipeline de creativos nuevos. Si dejas de inyectar energía, todo se desmorona en 14-21 días.

---

## 2. Cuándo subir presupuesto (escalamiento vertical)

### Las 4 condiciones de "luz verde" para escalar

Todas deben cumplirse al MISMO TIEMPO:

| Condición | Umbral Redroott |
|---|---|
| 1. CPA promedio **3 días consecutivos** | < $19.414 |
| 2. Volumen del adset | ≥ 3 compras/día |
| 3. Frecuencia | < 2.5 |
| 4. CTR | ≥ 1.2% |

Si solo 3 de 4 se cumplen → NO subir. Esperar 1 día más.

### Cómo subir presupuesto

**Vertical (mismo adset, más budget):**
- +20% por incremento
- Mínimo 72h entre incrementos
- Tope: +50% acumulado por semana por adset

**Horizontal (duplicar adset ganador):**
- Duplicar adset 1:1 con misma audience + creativos
- Empezar el duplicado al 50% del budget del original
- Dejar correr 7 días en paralelo
- Si el duplicado también funciona → tienes 2 motores, no 1

**Cuándo elegir vertical vs horizontal:**

| Situación | Estrategia |
|---|---|
| Adset ganador, frecuencia baja (<2.0), CPM estable | Vertical (sube budget) |
| Adset ganador, frecuencia 2.0–2.5, CPM subiendo | Horizontal (duplicar) |
| Adset ganador, frecuencia >2.5 | Variación de creativos (no escalar) |
| Cuenta entera por debajo del CPA target | Vertical en TODOS los ganadores |

### Señales de que un escalado no está funcionando

Después de subir budget +20%, esperás 3 días y mirás:

- CPA sube >20% vs antes del escalado → **volver al budget anterior**
- Frecuencia salta de <2.0 a >2.5 → **dejar el budget actual, no subir más**
- CTR cae >15% → **fatiga creativa, antes de subir más budget, refrescar creatives**
- Volumen aumenta proporcionalmente al budget pero CPA estable → **continuar subiendo cada 72h**

---

## 3. Cuándo bajar presupuesto

### Regla de 3 días consecutivos sobre $25K CPA

Si durante 3 días seguidos el CPA del adset queda en zona de riesgo ($25K–$32K) → **bajar budget −20%** y dejar correr 72h más.

Si después de bajar:
- CPA mejora → quedarte en el budget bajo
- CPA sigue malo → bajar otro −20% O pausar ads malos del adset (no el adset entero si está en aprendizaje)

### Nunca bajar el budget de un adset a $0

Bajar a $0 es equivalente a pausar el adset (rompe el aprendizaje). Mejor:
- Bajar al Hard Deck ($60.000 daily)
- O pausar ads individuales dentro del adset (preservar el aprendizaje)

### Hard Deck para Redroott

$60.000/día es tu piso. Si la cuenta entera está bajando, NO bajes del piso. Mejor:
1. Pausar ads malos
2. Subir creativos nuevos
3. Invertir el tiempo en mejorar landing/funnel

---

## 4. Cuántos ads nuevos producir por semana (por Tier de spend)

| Tier | Spend diario sostenido (avg 7d) | Ads nuevos/semana | Cadencia |
|---|---|---|---|
| Tier 1 | < $155.000 | 2-3 | cada 3 días |
| **Tier 2 (Redroott actual)** | **$155K–$250K** | **5-7** | **cada 2-3 días** |
| Tier 3 | $250K–$400K | 8-12 | cada 2 días |
| Tier 4 | $400K–$700K | 15-20 | diario |
| Tier 5 | > $700K | 25+ | diario, batches grandes |

### Mezcla 70/30 dentro de cada semana

- **70% variaciones de ganadores** (hook nuevo + visual viejo / visual nuevo + hook viejo / mismo concepto + personaje nuevo)
- **30% conceptos nuevos** (nueva puerta de entrada, nuevo ángulo, nuevo formato)

Si llevas 4+ semanas con mensaje validado → cambiar a 80/20 (más explotación, menos exploración).

### Por qué este número y no más

- Subir 10 ads en Tier 2 ($175K/día) → fragmentas aprendizaje, ningún ad recibe spend suficiente para validarse.
- Subir 3 ads en Tier 2 → demasiado lento, no compensas la fatiga del ganador actual.
- El sweet spot es lo que el CBO puede distribuir + lo que tu economía soporta para "matar rápido los perdedores".

### Cálculo de cuántos ads puede "comer" tu CBO

Regla práctica:
```
N_ads_max_simultáneos = budget_diario / (CPA_target × 1.3)
```

Para Redroott con CBO $245K y CPA target $19.414:
```
245.000 / (19.414 × 1.3) = 245.000 / 25.238 = ~9.7 ads
```

Esto significa que **simultáneamente** puedes tener hasta ~10 ads ACTIVOS antes de fragmentar. Hoy tenés 6 — todavía hay headroom.

---

## 5. Estructura de cuenta para escalar (consenso de los top)

### Una sola CBO de prospecting principal

**Consenso de Nick Theriot, Charlie Lawrance, Sam Piliero, Mark Goldhamer:**

> "No uso testing campaign separada. No uso scaling campaign separada. Uso una campaña por objetivo de negocio."

Tu cuenta (Redroott) ya está así: 1 sola campaña CBO. Mantenerlo.

### 3-5 ad sets dentro de la CBO

Meta recomienda 3-5 ad sets por CBO. Hoy tenés 4. Está en el rango óptimo.

Cada ad set debe atacar un **ángulo distinto** (no audiencias distintas, ángulos distintos):
- Adset por puerta de entrada (Vergüenza / Dinero tirado / Resignación)
- Adset por formato (UGC video / Static / Advertorial)
- Adset por avatar (hombre 30s / hombre 45s / mujer postparto)

**NO** usar ad sets para "audiencias hot/warm/cold separadas" en prospecting — eso ya no funciona post-iOS14.5. Confía en Meta para distribuir.

### Las 3 swim lanes (división de cuenta)

```
1. CBO Prospecting principal (90% del budget)
2. Retargeting (5% del budget, si querés)
3. Retention / Existing customers (5%, para upsells)
```

Para Redroott hoy: SOLO swim lane #1. Las otras 2 son optimización para más adelante.

---

## 6. Cuándo cambiar de Tier (decisión clave)

### Subir de Tier 2 → Tier 3

Cumplir TODAS estas condiciones:

1. **Spend promedio 7d ≥ 90% del daily budget** durante 7 días seguidos (cuenta consolidada en su tier actual)
2. **CPA blended 7d ≤ target** ($19.414 para Redroott)
3. **Pipeline creativo con ≥ 5 ads nuevos esperando subida**
4. **Mínimo 2 ad sets distintos con CPA validado** (no dependés de 1 solo motor)
5. **Suficiente cash flow para sostener el aumento** (cash conversion cycle considerado)

**Cómo subir de tier:**
- Aumentar daily budget +20% por semana
- Aumentar producción de creativos al ritmo del nuevo tier
- Monitorear delivery: si la cuenta no consume el aumento de budget → no es momento

### Bajar de Tier (cuando obligado)

Razones legítimas para bajar:
- Cash flow problemas reales
- Producto out of stock (no quemar plata mientras no podés despachar)
- Plataforma rota (píxel caído, etc) — degradación temporal

Razones MALAS para bajar:
- "Mal día/semana" (no es razón)
- Pánico por un CPA alto puntual

---

## 7. Wave surfing (técnica avanzada)

Aprovechar momentos donde la audiencia está "en modo compra" para ir más agresivo.

### Días favorables (presupuesto +30% temporal)
- Domingo (gente con tiempo de scroll)
- 25-1 del mes (post pago de sueldo CL)
- Black Friday / Cyber Monday
- Días lluviosos en Santiago (más tiempo en casa)

### Días desfavorables (mantener o bajar -10%)
- Sábado en la tarde (gente afuera)
- Día de partido importante (futbol nacional / internacional)
- Final de mes (15-31 antes del 1) — gente sin plata

**Cómo aplicar:** la noche anterior, subir +30% el budget. Al final del día siguiente, evaluar si mantener o volver al budget normal.

---

## 8. Diagnóstico "estamos escalando bien?"

### Las 4 métricas semanales que importan

| Métrica | Saludable |
|---|---|
| Spend semanal | Creciendo +10-20% W/W si estás en fase de escalado |
| CPA blended semanal | Estable o bajando (no más del target) |
| ROAS semanal | Estable o subiendo |
| Frecuencia promedio cuenta | Estable, no subiendo más de 0.3/semana |

### Las 3 señales tempranas de problemas

1. **CTR cayendo W/W** → primero síntoma de fatiga
2. **CPM subiendo W/W** sin que cambies audience → audiencia agotada
3. **Time to first purchase del adset** subiendo (de 2h a 12h promedio) → tracking caído o audiencia equivocada

---

## 9. Decisiones binarias frecuentes

### "¿Pauso o le doy 1 día más?"

| Situación | Decisión |
|---|---|
| Ad con CPA > $32K, ≥5 compras | PAUSAR (regla dura) |
| Ad con CPA > $32K, 2-4 compras, gasto > $50K | PAUSAR |
| Ad con CPA > $32K, 2-4 compras, gasto < $50K | 1 DÍA MÁS |
| Ad con CPA $25-32K, 7+ días consecutivos así | PAUSAR |
| Ad con CPA $25-32K, 3-6 días | 1 DÍA MÁS |
| Ad sin compras, gasto < $25K | 1 DÍA MÁS (data insuficiente) |
| Ad sin compras, gasto $25-50K | 1 DÍA MÁS (último chance) |
| Ad sin compras, gasto > $50K | PAUSAR (muerto) |

### "¿Subo budget o no?"

| Situación | Decisión |
|---|---|
| Cumple las 4 condiciones de escalado | SUBIR +20% |
| Cumple 3 de 4 (CTR bajo del 1.2% pero el resto OK) | NO SUBIR, esperar |
| Cumple 3 de 4 (frecuencia >2.5) | NO SUBIR, pedir variación primero |
| Cumple 4 condiciones pero ya subiste +20% hace <72h | ESPERAR (regla de 72h) |
| Cumple 4 condiciones y llevas +50% acumulado en la semana | NO SUBIR (tope semanal) |

### "¿Subo más ads o todavía no?"

| Spend semanal vs target | Decisión |
|---|---|
| Spend del tier actual al 90%+ | SUBIR MÁS ADS (saturación cerca) |
| Spend al 70-89% | RITMO NORMAL (lo del tier) |
| Spend < 70% | NO SUBIR MÁS, primero arreglar delivery (creativos viejos no convierten) |

---

## 10. Resumen accionable para el Agente Analista

Cuando hagas el reporte diario, después de las métricas, **DEBE incluir esta sección "Recomendaciones estratégicas" con análisis estructurado:**

### Plantilla obligatoria

```
🎯 RECOMENDACIONES ESTRATÉGICAS (priorizadas por impacto)

1. [Acción concreta — "Subir budget del adset X +20%"]
   Razón (cita regla): [ej. cumple 4/4 condiciones del SCALING_PLAYBOOK.md sección 2]
   Impacto esperado: [ej. +$30K spend/día con CPA proyectado $X]
   Riesgo si NO se hace: [ej. el ganador entra en fatiga sin alternativa]

2. [...]

3. [...]

⚠️ Tier check:
- Tier actual: [Tier X]
- Para subir a Tier siguiente faltan: [condiciones]

📈 Ritmo de creativos:
- Ads nuevos esta semana: [X]
- Recomendado para tu tier: [Y]
- Gap: [-/+ Z ads]

❓ Preguntas para Ignacio (a enviar por Telegram):
- [Pregunta concreta tipo "¿avanzo con variación de X?"]
- [Pregunta tipo "¿OK pausar ad Y mañana si sigue mal?"]
```

Estas preguntas se mandan por Telegram al final del resumen, formuladas para que Ignacio responda "sí" o "no" rápido desde el teléfono.
