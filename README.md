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

## Margen de cierre (mes en curso)

Con el corte **Hoy**, un llamado del mes en curso que todavía no se cerró se considera **pendiente**, no vencido, aunque su fecha ya haya pasado. El equipo de mantenimiento suele cerrar las OM cerca de fin de mes.

- Vencen los llamados programados hasta el último día del mes anterior.
- Con el corte **Cierre de mes**, vence todo lo programado hasta el último día de ese mes.
- El mismo criterio se aplica al backlog y al tablero de seguimiento (jostt).
