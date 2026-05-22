# Reglas de decisión — Meta Ads Redroott

Reglas alineadas con `Meta_Ads_Deep_Class_Redroott.pdf` (Parte 2 — Playbook Operativo) y `Redroott_CPA_Analysis.pdf`. Esto es lo que Ignacio ya validó. NO inventar reglas nuevas sin su OK.

---

## Tus números (data real)

| Métrica | Valor |
|---|---|
| AOV promedio | $85.882 CLP |
| COGS promedio | $46.104 CLP (53.7%) |
| Margen contribución / venta | $32.296 CLP |
| **CPA línea roja (breakeven)** | **$32.296 CLP** |
| CPA target sostenido (15% margen) | $19.414 CLP |
| CPA KPI para escalamiento | $25.000 CLP |
| CPA actual blended | $16.628 CLP |
| OPEX fijo mensual | $544.000 CLP |
| **Presupuesto diario configurado** | **$245.000 CLP** (CBO campaña "Redroott Oficial", confirmado 2026-05-21) |
| **Spend promedio últimos 7d** | **$172.893 CLP/día** (rampa: $123K → $224K en 14-20 mayo) |
| **Hard Deck (piso de presupuesto)** | **$60.000 CLP/día** |
| **Ad Account ID Redroott** | `1579671306460559` (act_1579671306460559) |
| **Campaña CBO principal** | "Redroott Oficial" — ID `120247346595660750` (única campaña activa) |
| **Bid Strategy** | Highest Volume |
| **Píxel ID** | `26801597616136298` |

**🔴 LÍNEA ROJA ABSOLUTA: $32.296 CLP.** Pasa de ahí y cada venta pierde plata por sí sola. Nunca bidear por encima.

---

## Reglas Kill / Keep (tal cual el playbook)

| Estado del ad | CPA | Acción |
|---|---|---|
| 🟢 GANADOR | < $19.000 | No tocar. Pedir variaciones. |
| 🟢 RENTABLE | $19.000 – $25.000 | Dejar correr. No priorizar variaciones. |
| 🟠 ZONA DE RIESGO | $25.000 – $32.000 | Si lleva 7+ días así → pausar. |
| 🔴 PERDIENDO PLATA | > $32.000 | **Pausar inmediatamente.** |
| ⚪ DATA INSUFICIENTE | gasto < $25.000 y 0 ventas | Dejar correr. |
| ⚫ MUERTO | gasto > $50.000 y 0 ventas | Pausar con confianza. |

---

## SOP Diario (lo que el Analista ejecuta cada mañana)

**Cada mañana a las 10:00 CL:**

1. Abrir Meta Ads MCP, traer métricas del día anterior.
2. Para cada ad, aplicar tabla Kill/Keep arriba.
3. **Escalado:** Si CPA del día anterior < $25.000 → **considerar subir budget +20%** (recomendar a Ignacio).
4. **De-escalado:** Si CPA del día anterior > $25.000 → **no tocar budget**.
5. **Regla de 3 días:** Si 3 días consecutivos con CPA > $25.000 → **bajar budget −20%**. Antes de los 3 días → esperar.
6. **Hard Deck:** Nunca bajar del piso $60.000/día. Si tocamos el piso → enfocar en creativos nuevos y funnel, no recortar más.
7. **Una variable a la vez:** NO subir budget el mismo día que se suben ads nuevos. Si hoy se suben creativos, hoy no se mueve budget.
8. **Wave surfing:** Inicio de mes y domingos → ser más agresivo con budget si la data lo justifica.

**Cada viernes (zoom-out semanal):**

- Revisar CPA promedio últimos 7 días.
- Evaluar qué ads matar, mantener y variar.
- Decidir si la cuenta está lista para subir nivel de spend.

---

## Ritmo de producción de creativos (por nivel de spend)

| Spend diario | Tier | Ads nuevos a subir |
|---|---|---|
| < $155.000 | Tier 1 | 2–3 ads cada 3 días |
| **$155.000 – $250.000 (ACTUAL — avg 7d $172K)** | **Tier 2** | **2–3 ads cada 2–3 días** |
| $250.000 – $400.000 | Tier 3 | 3–5 ads cada 2–3 días |
| $400.000 – $700.000 | Tier 4 | 5–8 ads cada 2 días |
| > $700.000 | Tier 5 | Revisar con Ignacio (escala enterprise) |

> ⚠️ La cuenta ya configuró $245.000 daily budget pero el spend promedio real 7d es $172.893 (70% de delivery). Cuando la delivery suba al 90%+ del budget configurado, se considera "consolidada en Tier 2" y se evalúa pasar a Tier 3 subiendo el daily budget.

**Mezcla:**
- **70% variaciones de ganadores** / 30% conceptos nuevos (hasta encontrar mensaje validado)
- Después de validar mensaje: 80% variaciones / 20% conceptos nuevos

**Operativa al subir ads nuevos:**
- Subir en un **adset nuevo** con **minimum spend de $17.000**
- Quitar el minimum después de **7 días**
- Texto siempre en **zona segura central** (no arriba ni abajo de la imagen)

---

## Mensaje de venta ganador (validado con data)

> "Lo que estás haciendo ahora para tu pelo NO funciona (taparte, shampoos, resignarte). Tus folículos se están cerrando cada día. Pero existe una solución simple, sin fármacos, respaldada por ciencia, que funciona en minutos al día."

### 3 Puertas de entrada probadas (con ROAS real)

| Puerta | Hook ejemplo | ROAS |
|---|---|---|
| **1. Vergüenza / Inseguridad** | "¿Sigues tapándote las entradas con el peinado?" | **51×** |
| **2. Dinero tirado** | "Ojalá alguien me hubiera mostrado esto antes de gastar en shampoos que no sirven." | **8×** |
| **3. Resignación por edad** | "¿Pensaste que a esta edad ya no se podía recuperar el pelo?" | **8.78×** |

Cuando el Estratega decida qué variar, **siempre apoyarse en estas 3 puertas** o validar una 4ª nueva.

---

## Reglas de variación (cuándo pedir creativos nuevos)

Pedir variación al Creativo si:

1. **Ad ganador (CPA < $19K) lleva ≥ 7 días corriendo** → renovar antes de fatiga.
2. **Frecuencia entre 2.5 y 3.5** → lanzar reemplazo ahora (la fatiga viene).
3. **Concept ganador, CTR cayendo** → variar hook, mantener concepto visual.
4. **Concept ganador, CTR sano** → variar visual (otra escena/personaje/ángulo).

### Tipos de variación (en orden de prioridad)

| Prioridad | Variación | Cuándo |
|---|---|---|
| 1 | Mismo hook + foto/escena distinta | Hook validado, visual quemado |
| 2 | Mismo visual + hook nuevo | Visual sano, hook quemado |
| 3 | Mismo concepto + personaje UGC distinto | Para escalar sin canibalizar |
| 4 | Mismo concepto + formato distinto (foto↔video) | Cuando un formato satura |
| 5 | Nuevo ángulo de dolor (otra de las 3 puertas) | Para abrir audiencia nueva |

---

## Lo que el Analista NUNCA hace solo

- Cambiar budget (solo **recomienda**, Ignacio aprueba en chat).
- Pausar ads (solo **recomienda**; el ejecutor puede pausar SOLO si CPA > $32K **y** Ignacio dijo OK previamente).
- Cambiar bid strategy, audiencia o copy de ads vivos.
- Subir un ad en estado ACTIVE. **TODO se sube en PAUSED (borrador).** Ignacio publica desde Meta.

---

## Notas de atribución

- **Atribución conservadora:** asumir 100% Meta (peor caso). Real ~70–85%.
- **Fase de aprendizaje:** < 50 conversiones a nivel ad set → no tocar nada.
- **Bid strategy default:** Lowest cost (sin cost cap) hasta 50+ conversiones. Después evaluar cost cap = $19.414.
