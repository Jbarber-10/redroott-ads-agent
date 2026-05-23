# Redroott — Sistema de Agentes IA para Meta Ads (24/7)

Sistema de 4 agentes IA encadenados que gestionan los anuncios de Meta Ads de **Redroott** (tienda Shopify chilena de cap LED para crecimiento capilar) de forma autónoma 24/7.

## Arquitectura

```
ANALISTA (Agente 1) → cola de variaciones
    ↓
ESTRATEGA (Agente 2) → briefs ultra-específicos
    ↓
CREATIVO (Agente 3) → assets Higgsfield
    ↓
EJECUTOR (Agente 4) → sube borradores PAUSED a Meta
    ↓
Ignacio publica manualmente desde Meta Ads Manager
```

## Estructura del repo

### Agentes (los 4 roles del sistema)
| Archivo | Propósito |
|---|---|
| `AGENTE_1_ANALISTA_META.md` | Lee Meta, decide pausar/escalar/variar (full auto + 4 candados) |
| `AGENTE_2_ESTRATEGA.md` | Genera briefs ultra-específicos para variaciones |
| `AGENTE_3_CREATIVO.md` | Produce assets vía Higgsfield (Nano Banana 2 / Kling 3.0) |
| `AGENTE_4_EJECUTOR.md` | Sube ads como borradores PAUSED a Meta |

### Reglas y estrategia
| Archivo | Propósito |
|---|---|
| `00_INDICE_REDROOTT.md` | Mapa de qué archivo leer para qué tarea |
| `RULES_META.md` | Reglas básicas de decisión (CPA, ROAS, tiers, escalado/kill) con números reales Redroott |
| `SCALING_PLAYBOOK.md` | Cuándo subir budget, cuántos ads/semana, vertical vs horizontal, wave surfing |
| `DIAGNOSIS_TREE.md` | 10 árboles de diagnóstico para problemas (CPA sube, ROAS baja, ad muere, etc) |
| `CREATIVE_TESTING.md` | M4 method, mezcla 70/30, anatomía de test bien armado, postmortems |
| `HISTORIAL_DECISIONES.md` | Memoria del agente: decisiones pasadas + postmortems + aprendizajes |
| `ROUTINES_SETUP.md` | Cómo programar las Routines en claude.ai |

### Assets
| Carpeta | Contenido |
|---|---|
| `refs/cap/` | Foto oficial del producto (cap 3/4 con LEDs) |
| `refs/cap-internals/` | Interior LEDs en patrón + vista exploded |
| `refs/cap-real-use/` | Foto real del producto en uso (no IA) |
| `refs/style-anchors/` | Estáticos ganadores actuales para imitar estilo (a poblar) |

## Datos clave Redroott

- **Cuenta Meta:** `act_1579671306460559` "Redroott Oficial"
- **Píxel:** `26801597616136298`
- **Campaña CBO:** `120247346595660750`
- **AOV:** $85.882 CLP | **CPA target:** $19.414 | **Línea roja:** $32.296

## Regla inmutable

> TODOS los ads se suben en estado **PAUSED**. Ignacio publica manualmente desde Meta Ads Manager.

## Cómo usar este repo en claude.ai

1. Crear un **Agente Remoto** en claude.ai app
2. En "Seleccionar un repositorio" → conectar este repo
3. Conectores requeridos: **Meta Ads**, **Higgsfield**, **Klaviyo**
4. En "Instrucciones" pegar el prompt correspondiente al agente (ver `ROUTINES_SETUP.md`)
5. Activar Routine cuando esté listo

## Replicabilidad

Este sistema es replicable a cualquier tienda Shopify cambiando:
- Datos de cuenta Meta + Shopify
- Carpeta `refs/` con fotos del producto nuevo
- Customer Research específica de la marca
- Reglas económicas (`RULES_META.md`)
