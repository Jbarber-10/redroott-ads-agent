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

## 23/05/2026 — DECISIÓN — Pausa Redroot VS Minoxidil (pre-aprobación activada)

### Contexto
Check intermedio 20:30 CL (manual). Al 22/05 el historial ya documentaba que Ignacio pre-aprobó pausar este ad si "sigue con 2-4 compras Y CPA acumulado > $40.000". Hoy 23/05 los datos confirman:
- Compras acumuladas: 2 (7d May 15-21: 2 compras sobre $72.265 + hoy $26.984 con 0 compras = 2 totales)
- Spend acumulado aproximado: ~$99.249 CLP
- CPA acumulado implícito: ~$49.624 CLP (supera el umbral de $40.000 pre-aprobado)

### Decisión / acción
✅ PAUSÉ el ad "Redroot VS Minoxidil" (ID: 120248102150650750).
Acción ejecutada vía Meta Ads MCP. Status cambiado de ACTIVE → PAUSED.

### Razón
Pre-aprobación de Ignacio documentada en HISTORIAL 22/05: condición 2 cumplida (2-4 compras Y CPA acumulado > $40.000). No requería OK adicional según las instrucciones de Ignacio.
Nota: el adset "Scale 2v 1n 21 de Mayo" sigue activo con los otros 2 ads (Labels EMOJIS - Copia y Deja de tapar Copia 2). No se interrumpió el aprendizaje del adset (pausa de ad individual no resetea).

### Revertir
Meta Ads Manager → Ads → buscar "Redroot VS Minoxidil" → clic en el toggle o botón Activate. Verificar que el adset esté activo también.

### Resultado
[Pendiente — observar si Labels EMOJIS y Deja de tapar Copia 2 absorben más spend ahora]

### Aprendizaje
La pre-aprobación específica por CPA acumulado (no por CPA diario ni por número de compras vs línea roja) es una herramienta útil para ads con pocos datos pero gasto creciente. Documentar para futuros casos similares.
