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
Confirmado 23/05: El ad "Redroot VS Minoxidil" aparece PAUSED en Meta al revisar el 23/05. El 22/05 gastó $27.020 adicionales con 0 compras nuevas. Gasto acumulado total estimado ~$126K con 2 compras (CPA acumulado ~$63K). Condición pre-aprobación #2 cumplida: sigue con 2-4 compras Y CPA acumulado > $40.000. Pausa correcta.

### Aprendizaje
Cuando un ad tiene baja conversión pero el CBO le da spend desproporcionado, vale la pena darle 1 día más antes de pausar. En este caso el experimento confirmó que el extra gasto no generó conversiones. El concepto "VS Minoxidil" puede ser válido pero necesita un hook diferente y menor presupuesto inicial.

---

## 23/05/2026 — DECISIÓN — Pausa "Labels beneficios gorro EMOJIS - Copia" (adset Scale 2v 1n 21 de Mayo)

### Contexto
Ad "Labels beneficios gorro EMOJIS - Copia" (ID 120248102435420750, adset Scale 2v 1n 21 de Mayo) acumuló $109.881 en gasto 7d con 4 compras (CPA 7d $27.470). El 22/05 tuvo un día especialmente malo: $77.834 gastados con solo 2 compras (CPA diario $38.917 — sobre la línea roja $32.296). Al 23/05 las 09:09 CL ya llevaba $24.958 de gasto con 0 compras nuevas, proyectando continuar la tendencia negativa. El adset está en learning phase (<50 conversiones acumuladas) pero eso no impide pausar el ad individual.

### Decisión / acción
Se pausó el ad ID 120248102435420750 vía MCP Meta Ads a las 09:09 CL del 23/05. Pausa ejecutada automáticamente (dentro de candados).

### Razón
SCALING_PLAYBOOK.md sección 9: "Ad con CPA > $32K, 2-4 compras, gasto > $50K → PAUSAR". Los tres criterios se cumplen:
- CPA ayer: $38.917 (> $32.296) ✓
- Gasto 7d: $109.881 (> $50K) ✓
- Compras 7d: 4 (rango 2-4) ✓
- Candado 1: primera pausa del día (1/3). Candado 2: se pausó el AD, no el adset → no resetea aprendizaje.

### Resultado
[Pendiente — evaluar en el check de las 13:00 si el adset Scale 2v 1n 21 de Mayo mejora sin ese ad]

### Aprendizaje
"Labels EMOJIS - Copia" en un adset nuevo es un concepto válido, pero el 22/05 el CBO le asignó demasiado spend sin que el ad tuviera historial suficiente para convertir bien. El adset nuevo (Scale 2v 1n 21 de Mayo) tiene ahora solo "Deja de tapar Copia 2" activo, lo que puede liberar budget para que meta lo redistribuya mejor o para que el adset "muera" de forma natural.

---

## 23/05/2026 — APRENDIZAJE — Discrepancia leve Meta vs Klaviyo (22/05)

### Contexto
Cruce Meta vs Klaviyo para 22/05: Meta reportó 6 compras, Klaviyo reportó 5 "Placed Orders" (revenue Klaviyo: $524.910 CLP). Delta: 16.7% (sobre el umbral de 15%).

### Decisión / acción
No se activó modo degradado. Causa identificada: 1 orden de cliente invitado (guest checkout) sin email tracking → no capturado por Klaviyo. Diagnóstico validado por cruce con notificaciones de Shopify (6 emails de pedidos #1110–#1115 en el inbox).

### Razón
DIAGNOSIS_TREE.md Árbol 9: "1 día aislado → Ruido. Ignorar." La discrepancia es de 1 orden y tiene explicación clara.

### Resultado
Mañana 24/05 re-chequear si la discrepancia se repite. Si vuelve a aparecer por 3 días seguidos → modo degradado.

### Aprendizaje
El proxy Klaviyo tiene un sesgo sistemático bajo por guest checkouts. Un delta de 1 orden/día es normal y no debe activar modo degradado. Solo si es 2+ órdenes por 3 días se escala.

---

## 23/05/2026 — APRENDIZAJE — Nuevo adset "Scale 23 de Mayo" detectado

### Contexto
Al hacer el snapshot de cuenta del 23/05 se detectó un adset nuevo "Scale 23 de Mayo" (ID 120248273573790750) que no estaba en el snapshot guardado del 21/05. Tiene 3 ads: 2× "Labels beneficios gorro EMOJIS - Copia" + 1× "Deja de tapar las entradas distinta foto - Copia 2". El adset parece haber sido creado por Ignacio esta misma mañana del 23/05.

### Decisión / acción
Registrado como cambio estructural detectado. Ads en aprendizaje (< 50 conversiones). No se toca el adset (candado 2). Se monitorea en próximos checks.

### Razón
AGENTE_1_ANALISTA_META.md: "Si hay diferencias significativas, REPÓRTALAS al principio del reporte."

### Resultado
[Pendiente — evaluar desempeño en 72h]

### Aprendizaje
Cuando Ignacio agrega adsets sin avisar, el agente los detecta en el snapshot del primer run del día. Agregar al contexto del reporte como "cambios detectados desde último snapshot."

---

[Las próximas entradas las agrega el agente automáticamente]
