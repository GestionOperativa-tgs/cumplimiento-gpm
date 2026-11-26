# cumplimiento-gpm
Cumplimiento de Planes desde Dashboard

## Vista anual por agrupación

Pestaña **Vista anual**. Tiene botones por agrupación de temas y, dentro de cada agrupación, botones por tema. Muestra el despliegue del año en una fila por plan y equipo.

- **Agrupaciones:** se definen en la constante `AGRUPACIONES` al principio del script. Los temas se comparan con la columna Tema de la hoja de planes, sin distinguir mayúsculas, acentos ni plurales. Si un tema no está en ninguna agrupación, aparece en "Otros temas".
- **Marcas en cada mes:**
  - ✓ Cumplido, en el mes de la Fecha Fin de la OM cerrada.
  - › Mes en que estaba programado, cuando se cumplió en un mes posterior.
  - R Mes programado original de una OM reprogramada.
  - ↻ Mes al que se reprogramó, según la Fecha Fin de la OM abierta. "!" indica que esa nueva fecha ya pasó o que no hay nueva fecha.
  - ✕ Vencido sin cerrar.
  - • Por vencer.
  - – Excedente sobre la frecuencia (no cuenta).
- Las reprogramaciones que pasan al año siguiente se muestran en la última columna.
- El Resumen incluye un panel de cumplimiento por agrupación que lleva a esta vista.
