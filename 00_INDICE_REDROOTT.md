# Índice maestro — Redroott (Agente Ads)

Este documento le dice al agente QUÉ archivo leer para QUÉ pregunta. Es el primer archivo que debe consultar siempre.

## Datos básicos de la tienda

- **Nombre:** Redroott
- **País / moneda:** Chile / CLP
- **Idioma copy:** es-CL (tú chileno educado, sin modismos brutos, sin "wn"/"po"/"cachai" exagerados)
- **Producto principal:** Cap LED baseball-style 660nm + 830nm, visera corta curva, knit negro, USB. (Es una cap CON visera. NUNCA describirla como "beanie", "soft", "rigid shell", "helmet", ni mencionar la marca "Redroott" en la foto/descripción del producto en sí.)
- **Dominio público:** redroott.com (es-CL, CLP) — NO confundir con reviveroott.com (en, USD).
- **Envío:** 7–12 días hábiles a todo Chile. Gratis sobre $29.000. NUNCA escribir "2–5" ni "3–5 días".
- **Promesa principal:** crecimiento de pelo / detener caída con terapia de luz roja diaria 10 min, protocolo 120 días.

## Mapa de qué leer para qué tarea

### Si necesitas entender al cliente / qué duele / cómo habla
1. `Customer Research/pain_points_synthesis.md` ← dolores priorizados
2. `Customer Research/language_swipe_file.md` ← frases textuales del cliente
3. `Customer Research/objection_map.md` ← objeciones + respuestas
4. `Customer Research/voice_of_customer_RAW.md` ← citas crudas
5. `Advertorial/Redroott_Avatar_Sheet.pdf` ← avatar consolidado
6. `Advertorial/Redroott_5_Creencias_Necesarias.pdf` ← qué tiene que creer el cliente para comprar

### Si necesitas escribir copy o hooks para anuncios
1. `UGC Script Framework/01_PRINCIPIOS.md`
2. `UGC Script Framework/02_FORMATOS.md`
3. `UGC Script Framework/03_BLOQUES_DIRECCION.md`
4. `UGC Script Framework/20_SCRIPTS_META_ADS.md` ← scripts de referencia ya validados
5. `Customer Research/language_swipe_file.md` ← para escribir como ellos hablan

### Si necesitas diseñar visuales / fotos / videos UGC
1. `UGC Script Framework/05_CAMERA_Y_BROLL.md`
2. `UGC Script Framework/07_BRAND_VARIABLES_REDROOTT.md` ← variables visuales aprobadas
3. `UGC Script Framework/09_CAPTIONS.md`
4. `Higgsfield Workflow/00_README.md`
5. `personajes UGC/` ← banco de personajes aprobados (cada uno tiene su prompt)

### Si necesitas decidir qué pausar / escalar / variar en Meta
1. `RULES_META.md` ← reglas de decisión con tus números reales (FUENTE PRIMARIA)
2. `SCALING_PLAYBOOK.md` ← cuándo subir budget, cuántos ads por semana, escalado vertical/horizontal, wave surfing (DESTILADO de Nick Theriot, Davie Fogarty, Charlie Lawrance, Sam Piliero)
3. `DIAGNOSIS_TREE.md` ← árbol de decisión para 10 escenarios de problema (CPA subiendo, ROAS bajando, ad ganador muriendo, etc)
4. `CREATIVE_TESTING.md` ← M4 method, mezcla 70/30, postmortems, anatomía de tests bien armados
5. `Meta_Ads_Deep_Class_Redroott.pdf` (opcional) ← playbook completo Mark Builds Brands (referencia profunda)
6. `HISTORIAL_DECISIONES.md` ← registro de decisiones pasadas + postmortems de tests (memoria del agente)

### Si necesitas generar un personaje UGC nuevo o un diario de progreso completo
1. `Descargas Redroott/SISTEMA_REDROOTT_DOCUMENTO_MAESTRO.md` ← Sistema completo de 9 fotos + 5 videos del diario 120 días (prompts exactos, modelo, aspect ratio, orden de referencias)
2. `Higgsfield Workflow/00_README.md`
3. `personajes UGC/` (local) ← personajes ya aprobados como base

### Si necesitas saber qué evitar / qué falla
1. `UGC Script Framework/06_FAILURE_MODES.md`
2. `MEMORY (raíz del project)` — feedback histórico de Ignacio

## Reglas absolutas (no negociables)

1. **NUNCA publicar ads en estado ACTIVO automáticamente.** Siempre subir como `PAUSED` (borrador). Ignacio publica desde Meta manualmente.
2. **NUNCA cambiar budget de un ad set sin que Ignacio lo apruebe en chat.** El analista RECOMIENDA, no ejecuta cambios de budget.
3. **Idioma: español de Chile.** Nunca portugués, nunca inglés en el ad final (sí en prompts internos de Higgsfield).
4. **La cap NO lleva marca visible** en ningún render/foto.
5. **Visera SIEMPRE presente** en cualquier render del producto. Es una baseball cap, no un beanie.
6. **Envío 7–12 días hábiles.** Nunca prometer otra cosa.
7. **Caption UGC fijo:** TikTok Sans 900, blanco, stroke 1px negro, sin fondo. Emoji color nativo.
8. **Si dudas, pregunta a Ignacio antes de actuar.** Mejor pausar que hacer cagada.

## Flujo de trabajo (resumen)

```
ANALISTA META (cada 6h)
  → lee Meta Ads MCP
  → compara contra RULES_META.md
  → escribe DECISIONES_PENDIENTES.md
  → notifica a Ignacio

ESTRATEGA DE VARIACIONES (1x/día)
  → lee DECISIONES_PENDIENTES.md
  → cruza con winning ads + hook bank
  → escribe BRIEFS_NUEVOS.md

CREATIVO (on-demand)
  → lee BRIEFS_NUEVOS.md
  → genera prompts Higgsfield
  → crea imagen/video vía MCP Higgsfield
  → guarda en assets/ + actualiza COLA_SUBIDA.md

EJECUTOR META (on-demand, con tu OK)
  → lee COLA_SUBIDA.md
  → sube creativo + copy a Meta como ad PAUSED (borrador)
  → Ignacio publica manualmente desde Meta
  → registra en HISTORIAL_ADS.md
```
