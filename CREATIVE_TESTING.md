# CREATIVE TESTING — Redroott Meta Ads

Cuándo testear concepto vs hook vs visual. Cuántos creativos por semana. Cómo identificar ganadores vs perdedores rápido. Cómo no quemar plata en tests mal armados.

Destilado de Sam Piliero (The Moonlighter), Davie Fogarty, Mark Goldhamer, Aazar Ali Shad + frameworks de testing en producción 2026.

---

## 1. Filosofía del testing creativo en 2026

### El M4 method (Mark Goldhamer)

Cuatro niveles de variación, de mayor a menor impacto. Cuando algo funciona, vas iterando hacia abajo. Cuando algo no funciona, subes un nivel.

| Nivel | Variás | Impacto en performance | Velocidad de iteración |
|---|---|---|---|
| 1. CONCEPT | Mensaje completo, ángulo de venta | 🔥🔥🔥🔥 ALTO | Lento (1-2 semanas) |
| 2. HOOK | Primeros 3 segundos / primer line | 🔥🔥🔥 ALTO | Medio (3-5 días) |
| 3. VISUAL | Foto, escena, personaje | 🔥🔥 MEDIO | Rápido (1-3 días) |
| 4. COPY | Body text, CTA, headline | 🔥 BAJO | Muy rápido (horas) |

**Regla práctica:** si un concepto no funciona, NO sigas testeando hooks/visuals/copy de ese concepto. Subí al nivel 1 y cambiá el concepto entero.

### Two truths sobre creative testing

1. **Más volumen ≠ más ganadores.** Producir 50 ads/mes basura no te va mejor que 8 ads/mes pensados.
2. **El ad ganador parece igual al perdedor antes de testearlo.** No lo puedes predecir mirando. Solo medilo.

---

## 2. Cuántos creativos producir (por Tier de spend)

| Tier | Spend diario sostenido | Creativos nuevos/semana | Cadencia |
|---|---|---|---|
| Tier 1 | < $155.000 | 2-3 | cada 3 días |
| **Tier 2 (Redroott actual)** | **$155-250K** | **5-7** | **cada 2-3 días** |
| Tier 3 | $250-400K | 8-12 | cada 2 días |
| Tier 4 | $400-700K | 15-20 | diario |
| Tier 5 | > $700K | 25+ | diario, batches grandes |

### Por qué este número y no más/menos

**Si producís más de la cuenta del tier:**
- Fragmentás el aprendizaje
- Ningún ad recibe spend suficiente para validarse (necesitas mínimo 5 compras para confirmar)
- Quemás créditos Higgsfield sin ganar performance

**Si producís menos:**
- El ganador actual entra en fatiga sin reemplazo listo
- Le das ventaja a competidores que sí refrescan
- Una cuenta sin pipeline creativo muere en 14-21 días

### El "Inventory rule"

Tu pipeline creativo debe tener SIEMPRE:
- **2 ads listos para subir mañana** (procesados, aprobados)
- **3-5 ads en producción** (Estratega armó briefs, Creativo está iterando)
- **5-10 conceptos en backlog** (ideas no ejecutadas todavía)

Si tu inventory está por debajo de eso → freno todo y dedico tiempo a llenarlo.

---

## 3. Mezcla 70/30 (la regla del playbook)

### En fase de exploración (todavía buscando mensaje ganador)

- **70% variaciones de ganadores** parciales (mejor concepto que tienes hoy)
- **30% conceptos nuevos** (puertas distintas, ángulos no testeados)

### En fase de explotación (mensaje validado, escalando)

- **80% variaciones de ganadores**
- **20% conceptos nuevos** (para tener pipeline contra fatiga)

### Para Redroott hoy

Mensaje validado (la cap LED 660nm), 3 puertas con ROAS sólido (Vergüenza 51x, Dinero tirado 8x, Resignación 8.78x). Estamos en explotación. **Mezcla: 80/20**.

Cada batch de 6 ads/semana queda así:
- 5 ads variando ganadores actuales (Labels EMOJIS, Deja de tapar, Oferta 43%)
- 1 ad concepto nuevo (ej. video largo storytelling, otro avatar, etc)

---

## 4. Las 3 puertas validadas de Redroott (no las pierdas de vista)

| Puerta | Hook ejemplo | ROAS | Cuándo usarla |
|---|---|---|---|
| **1. Vergüenza/Inseguridad** | "¿Sigues tapándote las entradas con el peinado?" | 51× | Por defecto. Es la mejor. La mayoría de variaciones desde acá. |
| **2. Dinero tirado** | "Ojalá alguien me hubiera mostrado esto antes de gastar en shampoos que no sirven." | 8× | Cuando el avatar es 40+ con historia de tratamientos fallidos. |
| **3. Resignación por edad** | "¿Pensaste que a esta edad ya no se podía recuperar el pelo?" | 8.78× | Para audiencia 45+. Delta emocional: resignación → esperanza → urgencia. |

**Cuándo explorar una 4ª puerta:**

- Solo cuando llevás 2+ meses con las 3 ya optimizadas a tope.
- Tratar la 4ª como PROTOTIPO (budget la mitad, criterio de validación más bajo: si llega a CPA <$25K → validada).
- Posibles 4ª puertas para Redroott:
  - Miedo a Turquía / cirugía
  - Comparativa vs cirugía capilar
  - Storytelling de un cliente real
  - Curiosidad ("Esto cambió mi vida y costó X menos que…")

---

## 5. Anatomía de un test bien armado

### Setup técnico

| Elemento | Recomendado |
|---|---|
| Campaign | La existente "Redroott Oficial" CBO (no crear campaign nueva) |
| Ad set destino | **Adset nuevo dedicado al test** (no mezclar con ad sets en escalado) |
| Minimum daily spend del adset | $17.000 los primeros 7 días (regla del playbook) |
| Targeting | Mismo que adset ganador (no querés que la variable de test sea audiencia) |
| Bid strategy | Lowest cost (heredado de CBO) |
| Estado al subir | PAUSED (siempre) |

### Cantidad por test

- **3-5 ads dentro del adset de testing** (no más, no menos)
- Cada ad debe ser una variación clara del otro, no copias ligeramente distintas
- Ejemplo bueno: 3 hooks distintos sobre mismo visual. Ejemplo malo: mismo hook con tipo de letra ligeramente distinta.

### Criterio de validación (por ad individual)

Después de **$25.000 gastado** en el ad:

| Resultado | Decisión |
|---|---|
| ≥3 compras, CPA <$19.414 | **GANADOR** → mover a adset de escalado |
| ≥3 compras, CPA $19-25K | **RENTABLE** → dejar correr en testing, no priorizar |
| 1-2 compras, CPA $25-32K | **AMBIGUO** → 1 día más antes de decidir |
| 0 compras o CPA >$32K | **PERDEDOR** → pausar y aprender qué no funcionó |

### Tiempo de validación

- Mínimo: 3 días con spend
- Máximo: 7 días
- Después de 7 días sin definirse → cualquier interpretación es ruido. Pausar.

---

## 6. Variaciones inteligentes (sin reinventar la rueda)

### Si tu visual es ganador pero hook se quemó (nivel 2 del M4)

Mantener: foto/escena/personaje
Variar: las primeras 5-7 palabras del copy / primeros 3 segundos del video

Ejemplos para "Labels beneficios gorro EMOJIS" (visual ganador):

| Hook actual | Hook variación |
|---|---|
| Implicit (no hook escrito, labels hablan) | "Los 3 datos que las clínicas capilares no quieren que sepas" |
| | "Lo que el shampoo nunca te va a hacer" |
| | "Si ya gastaste en mesoterapia, esto te va a doler" |

### Si tu hook es ganador pero visual se quemó (nivel 3 del M4)

Mantener: el copy (primary text + headline)
Variar: la imagen / video / personaje

Ejemplos para "Deja de tapar las entradas" (hook ganador):

- Variación A: hombre 35 en auto (actual)
- Variación B: hombre 40 en baño (nueva escena)
- Variación C: split-screen antes/después
- Variación D: foto cenital de coronilla con entradas marcadas (más viscerál)

### Si concepto entero está fatigado (nivel 1 del M4)

No salvar el ad. Cambiar a otra puerta de entrada validada o probar 4ª.

---

## 7. Velocidad post-lanzamiento — qué hacer las primeras 72h

### Hora 0-6 después de subir

- Verificá que efectivamente recibe entrega (impressions > 0)
- Si no tiene impressions a las 6h → revisar policy / quality assessment
- No tocar nada más

### Hora 6-24

- Mirar CTR. Si es <0.8% → señal temprana mala, pero esperar más data.
- Mirar CPC. Si es >$2.000 → audiencia equivocada o creativo malo.
- No actuar todavía.

### Día 2-3

- Revisar CPA. Si llegó a $25-50K gastado:
  - Sin compras → posible mal creativo, evaluar pausar
  - 1-2 compras a CPA aceptable → seguir
  - 3+ compras a CPA <$25K → ya es validable

### Día 4-7

- Decisión definitiva (ganador / rentable / ambiguo / perdedor)
- Si es ganador → mover a escalado
- Si es perdedor → pausar y documentar aprendizaje

### Después del día 7

- Si validó como ganador → 2-3 variaciones de él en pipeline
- Si validó como perdedor → no quemar más plata, escribir el postmortem

---

## 8. Postmortems — aprender de cada test (incluso de los fracasos)

Después de cada test (ganador o perdedor), escribir 5-10 líneas:

```
TEST: [nombre del ad]
SUBIDO: [fecha]
RESULTADO: [GANADOR / RENTABLE / PERDEDOR]
CPA FINAL: $X (vs target $19.414)
SPEND TOTAL: $X
COMPRAS: X

HIPÓTESIS INICIAL: "[lo que pensábamos que iba a funcionar]"
QUÉ APRENDIMOS: [insight clave]
CÓMO APLICAR EN FUTUROS TESTS: [acción]
```

Acumular esto en `HISTORIAL_DECISIONES.md` te da un dataset propio que mejora la calidad del próximo brief.

---

## 9. Anti-patrones de testing (NO hacer)

| Anti-patrón | Por qué falla |
|---|---|
| Subir 10 ads de golpe en 1 día | Fragmentás aprendizaje, ninguno recibe spend suficiente |
| Pausar un ad a las 24h sin data | Estás juzgando ruido, no señal |
| Variar 3 cosas a la vez en un test | No vas a poder atribuir qué movió la aguja |
| Testear conceptos que ya sabés que no funcionan ("para confirmar") | Quemás plata en algo predecible |
| Usar el mismo prompt Higgsfield para 5 variaciones | Salen 5 imágenes casi iguales — no es variación real |
| Testear con audiencias chicas (<500K) | Frecuencia rápida, mala lectura |
| "Test" sin criterio de éxito definido | Si no escribiste el KPI antes, todo se justifica post-hoc |

---

## 10. Aprendizajes específicos para Redroott (data real acumulada)

### Lo que sabemos que funciona

- **Formato Labels** (estático con beneficios + emojis) → motor de la cuenta
- **Hook "Deja de tapar las entradas"** → ROAS sólido con baja frecuencia
- **Foto producto con LEDs visibles** → engagement alto vs producto apagado
- **Avatar hombre 35-45** → mejor performance demográfica

### Lo que sabemos que NO funciona

- **Marca visible en la cap** → cuesta más CPA + sensación de "es un ad"
- **Beanie / sin visera** → genera confusión sobre qué es el producto
- **Promesas exageradas en el copy** (es-CL es escéptico a "milagros")
- **Videos largos sin hook fuerte en primeros 3 seg** → CTR cae rápido

### Lo que no hemos testeado todavía (oportunidades)

- **Video UGC con voiceover real chileno** (no sintético)
- **Comparativa side-by-side con minoxidil** (el ad actual de comparativa anda alto)
- **Audiencia mujeres postparto** (Puerta 1 con avatar mujer)
- **Hook con cifras / estudios** ("3 de cada 5 hombres recuperan pelo con 660nm")
- **Storytelling de un cliente real** (testimonio largo formato 15-20s)

### Aprendizajes acumulados (se completa con HISTORIAL_DECISIONES.md)

[Acumular acá cada test importante, sus aprendizajes, lo que validó/invalidó]

---

## 11. Cheat sheet — Decisión rápida

```
¿Subir cuántos ads esta semana?
→ Tier 2 = 5-7 ads (5 variaciones + 1 concepto nuevo + 1 wildcard)

¿Variar visual o hook?
→ Si CTR cae con CPM estable: VARIAR HOOK
→ Si CPM sube con CTR estable: VARIAR VISUAL
→ Si ambos caen: VARIAR CONCEPTO (nivel 1)

¿Pausar el ad nuevo?
→ Spend < $25K sin compras: NO, dejar correr
→ Spend $25-50K sin compras: 1 día más
→ Spend > $50K sin compras: SÍ, pausar
→ CPA > $32K con ≥5 compras: SÍ, pausar

¿Promover un ad a "escalado"?
→ CPA < $19.414 con ≥3 compras en 3 días: SÍ, mover a adset ganador
→ Cualquier otra cosa: dejar en testing hasta confirmar
```
