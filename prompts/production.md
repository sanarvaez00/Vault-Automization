Objetivo mensual: generar 15 productos/borradores en total por mes, con la misma proporción que usa el research (65% finanzas personales + IA, 35% nichos emergentes/trending detectados).

Antes de generar nada, lee el archivo vault-data.json (en C:\Users\sanar\vault-agents) y revisa los campos:
- products_month (formato "YYYY-MM")
- products_finance_count
- products_niche_count

Si products_month no existe o no coincide con el mes actual, reinicia products_finance_count a 0, products_niche_count a 0, y actualiza products_month al mes actual.

Metas del mes: products_finance_count debe llegar a 10 (65% de 15), products_niche_count debe llegar a 5 (35% de 15).

En esta corrida:
- Si products_finance_count < 10: genera UN producto nuevo basado en el nicho actual de finanzas personales + IA (lee la entrada más reciente de "Research semanal" en Notion, sección "Nicho actual", para inspirarte).
- Si products_niche_count < 5: genera UN producto nuevo basado en un nicho emergente/trending detectado (lee la misma entrada de research, sección "Nichos emergentes fuera del tema").
- Si ambos contadores ya llegaron a su meta (15 productos ya generados este mes), no generes ningún producto en esta corrida — solo verifica que products_month siga correcto y termina sin más cambios.

Cada producto es UN borrador de: una nueva idea de capítulo, variante de plantilla, o descripción de producto que aproveche la tendencia detectada. Etiqueta cada borrador con su categoría ("Finanzas + IA" o "Nicho emergente").

Cada producto debe redactarse en DOS versiones, ambas enfocadas en la clientela y sus necesidades reales (no en la tendencia en abstracto):
- **Versión en español** (para "Finanzas Automáticas"): tono humorístico, humano y cercano — como si un amigo con conocimiento explicara el tema, no un corporativo.
- **Versión en inglés** (para "Money on Autopilot"): tono profesional, claro y directo — orientado a resultados y credibilidad.
No son traducciones literales una de la otra: cada una debe sonar nativa a su tono y audiencia, aunque cubran la misma idea de producto.

Guarda los borradores nuevos en la página "Borradores pendientes de aprobación" en Notion (workspace "Sistema de Finanzas Automáticas / Money on Autopilot"). Si la página no existe, créala. Inserta los borradores nuevos al INICIO del contenido existente (insert_content con position start, o replace_content reconstruyendo todo con lo nuevo arriba) — nunca borres los borradores anteriores. Encabeza cada borrador con fecha (## Borrador: YYYY-MM-DD) y su categoría, y dentro de cada uno incluye ambas versiones claramente separadas (### Versión ES (humorística) / ### Versión EN (profesional)). No publiques nada en Gumroad ni en ningún otro lado — solo deja los borradores listos para que yo los revise.

IMPORTANTE: usa saltos de línea reales en el markdown que envíes a Notion, no la secuencia de escape "\n" como texto literal.

Al terminar, actualiza vault-data.json: incrementa products_finance_count y/o products_niche_count según lo que hayas generado en esta corrida (solo súmales 1 por cada producto generado de esa categoría), y asegúrate de que products_month quede en el mes actual. No toques los demás campos (revenue, ebooks, niches, messages_pending, research_status, last_updated).

Si no generaste ningún producto (porque ya se alcanzó la meta de 15 este mes), no hagas commit ni push — no hay cambios que subir.

Si sí generaste al menos un producto, ejecuta en la terminal desde esta carpeta:
1. git add vault-data.json
2. git commit -m "chore: actualizar contador de productos [fecha de hoy]"
3. git push

Ejecuta todo esto sin pedir confirmación.
