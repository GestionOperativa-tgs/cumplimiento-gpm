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

## Planes sin OM en el año

En la Vista anual hay un selector **"Planes sin OM en el año"**. Abarca los casos "Sin OM en el dashboard" y "Sin OM en el año" (tienen OM, pero de otros años).

- **Incluir:** comportamiento original.
- **Ocultar del cálculo y la vista:** esos planes no se cuentan en ninguna vista (planes, equipos, llamados esperados, pestañas). Siguen apareciendo en Control de datos.
- **Ver solo estos:** la grilla muestra solo esos planes, por agrupación, sector y tema, para revisarlos en SAP. El CSV trae la columna Situación.

La elección queda guardada en el navegador. Esos planes no tienen llamados vencidos, así que no modifican el % de cumplimiento a la fecha.

## Relevamiento de planes (nov-2026)

La constante `RELEVAMIENTO` (al principio del script) carga el relevamiento "Observaciones de Planes", plan por plan. Prevalece sobre la bajada de SAP y solo se aplica al año `RELEV_ANIO` (2026).

- **Eliminar del tablero:** planes no activos o con un error a corregir. No se muestran ni cuentan, y sus OM salen también del backlog.
- **Acomodar la frecuencia para 2027:** quedan fuera de 2026. Se reincorporan en 2027, después de ajustar la frecuencia en SAP.
- **Realizado:** cuenta como cumplido aunque la OM falte en la bajada, esté NEJE o figure en la lista de anuladas. Se marca en el mes de la fecha de realización.
- **Pendiente / Traer a diciembre:** se programa como llamado pendiente en diciembre. Con el corte Hoy no figura como vencido; con el corte Cierre de diciembre, sí.
- **Dar de alta equipo en SAP y lanzar plan:** se lista en Control de datos y no cambia el cálculo.
- Si el relevamiento trae N° de OM, el ajuste es por equipo: esa OM representa al equipo y las otras OM del mismo plan y ubicación técnica en el año quedan reemplazadas. Sin N° de OM, el ajuste es por plan, y si no hay OM en la bajada se agrega un llamado "s/OM".
- Lo confirmado por el relevamiento no se toma como excedente sobre la frecuencia.
- En la Vista anual las marcas ajustadas llevan un asterisco (*), y el detalle se ve al pasar el mouse. En Control de datos hay un panel con cada fila del relevamiento y la OM con que quedó en el tablero.
