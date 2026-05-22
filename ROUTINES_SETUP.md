# ROUTINES SETUP — Redroott (claude.ai Max)

Documento operativo: cómo crear las 4 Tasks/Routines en claude.ai que activan el sistema 24/7.

## Cómo acceder a Tasks en claude.ai

1. Abrí claude.ai en navegador (logueado con tu cuenta Max)
2. Buscá en sidebar izquierdo el ícono de reloj 🕐 o el menú "Tasks" / "Scheduled tasks"
3. Si no aparece: Settings → Features → activá "Scheduled Tasks" (en Max viene on por default)

## Cómo configurar cada Task

| Campo común | Valor |
|---|---|
| **Project** | Agente Ads — Redroott (siempre el mismo) |
| **Timezone** | Santiago / America/Santiago (UTC-4 en horario invierno chileno, -3 en verano) |
| **Status inicial** | **PAUSED** (toggle off hasta que Ignacio diga "activar Routine X") |

---

## ROUTINE 1 — Analista Reporte Diario

**Name:** `Redroott — Analista Reporte Diario`
**Schedule:** Diario, **09:00 CL** (cron: `0 9 * * *`)
**Status:** PAUSED hasta activar

**Prompt:**

```
Actúa como Analista Meta de Redroott. Hacé el reporte diario completo siguiendo AGENTE_1_ANALISTA_META.md.

Modo: FULL AUTO con los 4 candados activos.

Pasos obligatorios:
1. Traer data FRESH del MCP para act_1579671306460559 (no usar cache)
2. Snapshot inicial: comparar estructura actual vs la guardada en el archivo del Analista. Reportar cambios.
3. Traer 3 ventanas: HOY parcial / AYER completo / ÚLTIMOS 7 DÍAS desglose por día
4. Reportar HOY arriba de AYER
5. Separar CPA blended 7d (incluye ads pausados) de CPA 7d solo ads activos hoy (operativo real)
6. Aplicar reglas Kill/Keep + Escalado de RULES_META.md
7. Cruzar Meta vs Klaviyo (metric RaGzV7) del día de ayer
8. Si discrepancia Klaviyo >15% → modo degradado (no ejecutar acciones)
9. Tier check: spend promedio 7d → tier actual + alerta si cambió de tier
10. Ejecutar acciones permitidas dentro de candados:
    - Máx 3 pausas/día
    - No tocar adsets en aprendizaje (<50 conversiones)
    - Máx ±20% budget/día por adset
11. Actualizar/crear archivo DECISIONES_PENDIENTES.md con la cola de variaciones para el Estratega
12. Notificar cada acción ejecutada con cómo revertir

Idioma: tú chileno educado, sin "wn/po/cachai".
Brutalmente honesto en las notas del Analista.
```

---

## ROUTINE 2 — Analista Check de 6h

**Name:** `Redroott — Analista Check 6h`
**Schedule:** Cada 6h en **15:00, 21:00, 03:00 CL** (cron: `0 3,15,21 * * *`)
**Status:** PAUSED hasta activar

**Prompt:**

```
Actúa como Analista Meta de Redroott. Hacé un CHECK DE 6H siguiendo AGENTE_1_ANALISTA_META.md sección "CHECK DE 6H".

Modo: FULL AUTO con los 4 candados activos. Análisis LIGERO, no reporte completo.

Pasos:
1. Traer data fresh: spend hoy acumulado, CPA últimas 6h, eventos píxel últimas 6h
2. Comparar Meta vs Klaviyo últimas 6h (sanity check)
3. Aplicar reglas Kill SOLO en casos críticos:
   - Línea roja flagrante (>$10K gastado en 6h con CPA >$32.296 o sin compras)
   - Fatiga aguda (freq subió de <3.0 a >4.0 en 24h)
   - Píxel caído (Meta 0 eventos + Klaviyo sí tiene Placed Orders)
   - Spend descontrolado (>35% del daily budget en primeras 6h)
4. Si no hay alertas Y no hubo acciones → mensaje de 1 línea: "✅ Check 6h HH:MM — todo en verde"
5. Si hubo acciones o alertas → reporte completo del check de 6h

NO hacer reporte diario completo. NO hacer cruce Klaviyo exhaustivo.
Solo cazar problemas urgentes entre los reportes diarios.
```

---

## ROUTINE 3 — Estratega Procesamiento Cola

**Name:** `Redroott — Estratega Procesa Cola`
**Schedule:** Lunes a viernes, **10:00 CL** (cron: `0 10 * * 1-5`)
**Status:** PAUSED hasta activar

**Prompt:**

```
Actúa como Estratega de Redroott siguiendo AGENTE_2_ESTRATEGA.md.

Procesá la cola de variaciones que dejó el Analista esta mañana (revisar DECISIONES_PENDIENTES.md y/o la sección "🎨 COLA DE VARIACIONES" del último reporte del Analista en este Project).

Pasos:
1. Leer 00_INDICE_REDROOTT.md y RULES_META.md
2. Leer cola del Analista
3. Para cada item priorizado, generar UN brief ULTRA-ESPECÍFICO siguiendo el formato de 10 secciones del archivo del Estratega
4. Limitar al tier de producción actual (Tier 2 → máximo 3 briefs por procesamiento)
5. Si hay más items en cola que el tier permite, dejar excedentes en "cola siguiente"
6. Validar mezcla 70/30 (variaciones de ganadores / conceptos nuevos)
7. Hooks en es-CL (tú chileno educado) usando language_swipe_file
8. Para personajes: priorizar reuso del banco existente. Si no hay personaje adecuado, especificar prompt completo de Soul 2 para personaje nuevo
9. Para producto: SIEMPRE referenciar la foto oficial de la cap como ref obligatoria (cap-3-4-leds-on-white.jpg)
10. Adjuntar style anchor relevante si la variación pide replicar un formato ganador (Labels EMOJIS, Deja de tapar, etc)
11. Copy completo de cada ad (primary text, headline, description, CTA, URL) listo para el Ejecutor
12. Config Meta sugerida: adset destino o "CREAR ADSET NUEVO: [nombre]"
13. Hipótesis y KPI por brief

Output final: actualizar BRIEFS_NUEVOS.md con todos los briefs del día.

Si NO hay cola del Analista (porque hoy no hubo recomendaciones de variación) → mensaje: "Sin cola pendiente, no genero briefs hoy."
```

---

## ROUTINE 4 — Creativo + Ejecutor encadenados

**Name:** `Redroott — Creativo Produce + Ejecutor Sube`
**Schedule:** Lunes a viernes, **11:00 CL** (cron: `0 11 * * 1-5`)
**Status:** PAUSED hasta activar

**Prompt:**

```
Sos un agente encadenado: primero Creativo, después Ejecutor.

═══════ FASE 1: CREATIVO ═══════
Actúa como Creativo siguiendo AGENTE_3_CREATIVO.md.

Procesá los briefs pendientes (de BRIEFS_NUEVOS.md, los que dejó el Estratega esta mañana).

Para cada brief:
1. Validar que está completo (10 secciones)
2. Usar refs/cap/01_cap-3-4-leds-on-white.jpg (o la apropiada según el brief) como media_reference OBLIGATORIA cuando la cap aparezca
3. Adjuntar style anchor si el brief lo indica (de refs/style-anchors/)
4. Ejecutar el prompt Higgsfield exacto del brief
5. Aplicar los 8 checks no-negociables (visera, sin marca, LEDs grilla, etc)
6. Iterar máximo 5 veces si falla un check
7. Si tras 5 reintentos no logra texto legible → guardar imagen LIMPIA y marcar "labels pendientes (montar manual)"
8. Registrar asset en COLA_SUBIDA.md con copy completo, config Meta, hipótesis, KPI

Tope de la sesión: 3 briefs (tier 2). Si hay más, dejar pendientes.

═══════ FASE 2: EJECUTOR ═══════
Actúa como Ejecutor siguiendo AGENTE_4_EJECUTOR.md.

Procesá COLA_SUBIDA.md (los items "✅ Listo para Ejecutor" — saltar los "labels pendientes").

Para cada item:
1. Validar asset binario + copy completo + config Meta
2. Si el brief dice "CREAR ADSET NUEVO": crear adset en PAUSED clonando targeting del adset ganador actual (CPA más bajo últimos 7d con ≥3 compras), con minimum spend $17.000 × 7 días
3. Subir AD nuevo en estado PAUSED (obligatorio) con:
   - Image hash o video ID del Creativo
   - Copy exacto del brief
   - URL con UTM parameters
   - Píxel 26801597616136298
   - Optimization: PURCHASE
4. Verificar que se subió correctamente (re-leer del MCP)
5. Registrar en HISTORIAL_ADS.md
6. Reportar enlaces directos a Ads Manager para que Ignacio revise y publique manualmente

REGLA INMUTABLE: TODO ad se sube en PAUSED. SIN EXCEPCIÓN.

═══════ OUTPUT FINAL ═══════
Reporte combinado:
- Fase 1 (Creativo): X assets producidos, Y iteraciones totales
- Fase 2 (Ejecutor): Z ads subidos como borradores
- Enlaces directos a cada borrador en Meta
- Items bloqueados y por qué
- Cola pendiente para mañana
```

---

## Orden de activación recomendado

Cuando estés listo para activar, recomendado prender 1 Routine cada 2-3 días:

1. **Día 1:** Activá R1 (Reporte diario 09:00). Lee el reporte de mañana, revisá criterio.
2. **Día 3:** Si el reporte diario es bueno → activá R2 (Checks de 6h).
3. **Día 5:** Si los checks 6h no causan ruido → activá R3 (Estratega 10:00).
4. **Día 7:** Si los briefs del Estratega son buenos → activá R4 (Creativo + Ejecutor 11:00).
5. **Día 14:** Si todo funciona → bajar candados (más autonomía).

Si en cualquier paso algo sale mal, pausás esa Routine y nos sentamos a ajustar el archivo del agente.

---

## Cómo pausar una Routine si algo sale mal

1. claude.ai → Tasks → buscar la Routine
2. Toggle off
3. Todas las próximas ejecuciones quedan canceladas hasta que la vuelvas a activar
4. Las acciones ya ejecutadas en Meta (si las hubo) NO se revierten automáticamente — eso lo hacés vos manualmente en Meta Ads Manager

---

## Verificación post-activación

Después de cada activación, en las primeras 24h:
- ¿La Routine corrió en el horario esperado?
- ¿El output tiene sentido?
- ¿Las acciones ejecutadas (si las hubo) son correctas?
- ¿Se actualizaron los archivos del Project como espera (DECISIONES_PENDIENTES, BRIEFS_NUEVOS, COLA_SUBIDA, HISTORIAL_ADS)?

Si algo no cuadra → toggle off → me cuentas qué pasó → ajustamos el archivo del agente correspondiente → re-subir → re-activar.
