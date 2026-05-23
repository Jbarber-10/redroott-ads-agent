# HISTORIAL DE DECISIONES — Redroott Ads Agent

Memoria del agente. Registro cronológico de:
- **Decisiones estratégicas tomadas** (por Ignacio o el agente)
- **Postmortems de tests creativos** (qué validó, qué no, por qué)
- **Aprendizajes** que cambian las reglas para próximas ejecuciones

El agente debe LEER este archivo al inicio de cada reporte para no repetir errores y recordar el contexto histórico.

El agente debe ESCRIBIR aquí cada vez que:
1. Toma una acción importante (pausa, escalado de budget, variación)
2. Ignacio responde "OK" o "NO" a una propuesta vía Telegram/email
3. Un test creativo se valida o falla

Formato de cada entrada:

```
## [FECHA — DD/MM/AAAA] — [TIPO: DECISIÓN / POSTMORTEM / APRENDIZAJE]

### Contexto
[Qué pasaba en la cuenta]

### Decisión / acción
[Lo que se hizo o se decidió]

### Razón
[Regla aplicada o lógica usada]

### Resultado (completar después)
[Qué pasó, días después]

### Aprendizaje
[Una línea: qué guardo para el futuro]
```

---

## Entradas

---

## 22/05/2026 — DECISIÓN — VS Minoxidil (esperar 24h más)

### Contexto
Ad "Redroot VS Minoxidil" llegó a $92.637 spend acumulado con 2 compras, CPA implícito $46.319. El CPA está sobre línea roja ($32.296) pero el ad tiene solo 2 compras (no llega al umbral de ≥5 compras que define pausa automática por CPA alto). Adset está en aprendizaje (<50 conversiones), candado 2 impide pausar el adset.

### Decisión / acción
Ignacio decide esperar 24h más antes de pausar. Pre-aprobación dada para el próximo reporte:
1. Si suma ≥5 compras totales → re-aplicar regla normal "CPA > $32.296 con ≥5 compras = pausar"
2. Si sigue con 2-4 compras Y CPA acumulado > $40.000 → pausar (pre-aprobada, no requiere OK adicional)
3. Si convierte a CPA aceptable → re-evaluar normal

### Razón
Ignacio quiere darle 1 día más al ad porque el CBO le estaba asignando 30% del budget (señal de que Meta detecta receptividad de audiencia). Posibilidad de que la siguiente data confirme rentabilidad.

### Resultado
[Pendiente — completar en reporte de mañana 23/05]

### Aprendizaje
Cuando un ad tiene baja conversión pero el CBO le da spend desproporcionado, vale la pena darle 1 día más antes de pausar. Documentar el experimento para futuros casos similares.

---

[Las próximas entradas las agrega el agente automáticamente]

---

## 23/05/2026 — DECISIÓN — VS Minoxidil PAUSADO (resultado de pre-aprobación 22/05)

### Contexto
VS Minoxidil tenía pre-aprobación de Ignacio (entrada 22/05): si al siguiente run seguía con 2-4 compras Y CPA > $40K → pausar. El ad aparece como PAUSED en el MCP al check de 02:03 AM del 23/05.

### Decisión / acción
El ad "Redroot VS Minoxidil" (120248102150650750) fue pausado. Ayer (22/05) gastó $27.020 CLP adicionales con 0 compras, llevando el acumulado a ~$92.637+ sin llegar a la rentabilidad. La pausa ya está ejecutada (por Ignacio manualmente o por el agente anterior).

### Razón
Pre-aprobación del HISTORIAL 22/05: condición 2 → "Si sigue con 2-4 compras Y CPA acumulado >$40K → pausar". Con $92.637 acumulado y solo 2 compras históricas, CPA implícito ~$46.318 (>$40K). Regla cumplida.

### Resultado
PAUSADO. Se libera el presupuesto del CBO para redistribuir en ads con mejor performance.

### Aprendizaje
El ad VS Minoxidil nunca superó 2 compras con más de $90K de gasto. El concepto comparativo vs minoxidil puede valer la pena retestear con un visual y hook completamente diferentes.

---

## 23/05/2026 — DECISIÓN — Labels EMOJIS Copia en línea roja (requiere OK Ignacio)

### Contexto
Check 02:03 AM. "Labels beneficios gorro EMOJIS - Copia" (120248102435420750) en adset "Scale 2v 1n 21 de Mayo" tuvo ayer (22/05): spend $77.763, 2 compras, CPA $38.882. Está sobre línea roja ($32.296). El CBO le asignó ayer el 36% del spend total de la cuenta ($77.763 de $215.256).

### Decisión / acción
NO se pausó automáticamente (el auto-pause estricto del AGENTE_1 requiere CPA >$32.296 con ≥5 compras, o gasto >$50K con 0 ventas; esta situación es gasto >$50K con 2 ventas). Se eleva a Ignacio como "PAUSA URGENTE RECOMENDADA". Según SCALING_PLAYBOOK sección 9: "Ad con CPA > $32K, 2-4 compras, gasto > $50K → PAUSAR".

### Razón
La regla automática del AGENTE_1 no se activa con 2 compras (requiere ≥5). Pero SCALING_PLAYBOOK sección 9 es clara: la combinación CPA>$32K + 2-4 compras + gasto>$50K → PAUSAR. Se requiere OK de Ignacio para actuar.

### Resultado
Pendiente — aguardando respuesta de Ignacio.

### Aprendizaje
El concepto "Labels EMOJIS Copia" en el adset del 21 de mayo no está replicando el éxito del ad original. El original (120247636242890750) tiene CPA $14.964 en su propio adset. La copia en adset distinto puede estar captando audiencia de menor calidad.

---

## 23/05/2026 — APRENDIZAJE — Frecuencia 7d en 2.95 (zona de fatiga)

### Contexto
La cuenta entera tiene frecuencia promedio 7d de 2.95. RULES_META.md dice: "Frecuencia entre 2.5 y 3.5 → lanzar reemplazo ahora (la fatiga viene)". SCALING_PLAYBOOK sección 2: "Adset ganador, frecuencia >2.5 → Variación de creativos (no escalar)".

### Decisión / acción
Alerta reportada a Ignacio. Se requiere urgentemente pipeline de creativos nuevos. La ganadora "Labels EMOJIS" original (freq 1.17) está bien, pero la cuenta aggregate llega a 2.95 por el peso de ads históricos. El Estratega debe priorizar variaciones del ganador.

### Razón
RULES_META.md: regla de variación condición 2 — "Frecuencia entre 2.5 y 3.5 → lanzar reemplazo ahora".

### Resultado
Pendiente — depende de acción del Estratega.

### Aprendizaje
La frecuencia 7d de la cuenta puede estar siendo inflada por adsets pausados recientes que ya habían llegado a frecuencias altas. Vigilar frecuencia POR ADSET activo, no solo la cuenta.

---

## 23/05/2026 — APRENDIZAJE — Shopify confirma más pedidos que Meta reporta (buen signo)

### Contexto
AYER (22/05): Meta reportó 6 purchases. Los emails de Shopify confirman 7 pedidos reales (#1109 al #1115). Klaviyo registered 5 "Placed Order" (2 guest checkouts no capturados). CPA real Shopify = $215.256 / 7 = $30.751 (bajo línea roja). CPA Meta = $35.876 (sobre línea roja).

### Decisión / acción
Se usó el CPA real de Shopify ($30.751) como referencia más precisa. Delta Meta vs Klaviyo = 16.7% (bordeline >15%), pero se interpretó como gap de guest checkout NO como inflación de Meta, dado que Shopify > Meta.

### Razón
AGENTE_1_ANALISTA_META.md: "Atribución conservadora: asumir 100% Meta (peor caso). Real ~70-85%." En este caso Meta está UNDER-reporting vs Shopify. Klaviyo miss es por guest checkouts esperado. No hay inflación de Meta.

### Resultado
En días donde Shopify muestre más compras que Meta, el CPA real es mejor de lo que Meta indica.

### Aprendizaje
Verificar emails de Shopify como triangulación adicional al cruce Meta/Klaviyo. La discrepancia Shopify>Meta>Klaviyo es la SALUDABLE (Meta conservador, Klaviyo con gap de guest). La MALA sería Meta>Shopify>Klaviyo.
