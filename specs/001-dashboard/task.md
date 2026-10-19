# Tareas: Dashboard de rendimiento de influencer

## Estructura y datos

- [x] Definir el conjunto de datos de demostración para productos, plataformas y campañas.
- [x] Marcar los datos de demostración para que no se confundan con datos reales.
- [x] Preparar la estructura HTML semántica de cabecera, navegación, contenido principal y secciones.
- [x] Añadir controles de periodo, plataforma y producto, indicando si son estáticos o funcionales.
- [x] Aplicar formatos de moneda, cantidades, periodos y estados sin datos.

## Bloque superior: KPI

- [x] Crear el patrón visual reutilizable para tarjetas KPI.
- [x] Mostrar ventas atribuidas y comisiones generadas.
- [x] Mostrar alcance o impresiones, conversiones y tasa de engagement.
- [x] Mostrar periodo, unidad y comparación anterior solo cuando haya datos comparables.
- [x] Verificar los importes de comisión por producto: A 7,50 €, B 18 € y C 12 €.

## Bloque intermedio: drivers

- [x] Mostrar las etapas del embudo de alcance, clics y conversiones.
- [x] Comparar alcance, interacciones, conversiones y comisiones por plataforma.
- [x] Comparar conversiones y comisiones por producto.
- [x] Mostrar actividad publicada por plataforma cuando esté disponible.
- [x] Desglosar interacciones en me gusta, comentarios, compartidos y guardados cuando estén disponibles.
- [x] Aplicar las fórmulas de engagement, conversión y CTR definidas en la especificación.

## Bloque inferior: detalle operacional

- [x] Crear la tabla de productos con precio, ventas, conversiones, comisiones y retorno disponible.
- [x] Crear la tabla de plataformas con alcance, interacciones, engagement, conversiones y comisiones.
- [x] Crear la tabla de campañas con fechas, plataforma, producto, costes y resultados disponibles.
- [x] Añadir listados de productos, plataformas y campañas con mejor rendimiento.
- [x] Añadir oportunidades de mejora basadas en datos disponibles.
- [x] Mostrar alertas solo cuando existan datos comparables suficientes.
- [x] Distinguir claramente ROAS de ROI y no calcularlos sin costes válidos.

## Diseño responsive

- [x] Diseñar primero la disposición móvil para KPI, drivers, tablas y controles.
- [x] Adaptar las cuadrículas y tablas a tablet mediante breakpoints de Tailwind.
- [x] Adaptar la disposición a escritorio sin alterar la jerarquía de los bloques.
- [x] Comprobar las vistas de 320–639 px, 640–1023 px y 1024 px o más.
- [x] Corregir desbordamientos horizontales y asegurar legibilidad y acceso a los contenidos.

## Revisión de aceptación

- [x] Confirmar estructura semántica y encabezados de tabla claros.
- [x] Comprobar cálculos y tratamiento de datos faltantes o denominadores en cero.
- [x] Confirmar que MRR, churn, permanencia, NPS y CSAT no muestran valores inventados.
- [x] Confirmar que la implementación usa solo HTML y Tailwind CSS v4.
- [x] Verificar que no se usa React, Vue, CSS personalizado, Tailwind v3 ni `cdn.tailwindcss.com`.
- [x] Confirmar que los controles no aparentan filtrar cuando no tienen filtrado implementado.

## Verificación final

Completada el 19 de octubre de 2026, siguiendo el orden de la lista. Datos de referencia: [datos.md](datos.md). Criterios de aceptación verificados: [spec.md](spec.md#criterios-de-aceptación).

- HTML: `html-validate:recommended`, sin errores.
- Navegador: Chromium con Playwright en 320, 390, 640, 768, 1024 y 1440 px; sin desbordamiento horizontal, imagen cargada y sin errores de ejecución. Capturas revisadas de móvil, tablet y escritorio. Encabezados de tablet ajustados y comprobados nuevamente a 768 px.
- Accesibilidad automática: axe, reglas WCAG 2 A/AA y 2.1 A/AA, sin incidencias en 320, 768 y 1440 px. No sustituye una auditoría manual completa con tecnologías de asistencia.
- Interacción: enlace de salto, navegación interna y apertura/cierre de los desplegables mediante teclado; tres filtros deshabilitados y etiquetados.
- Datos: reconciliación de seis campañas, tres productos, tres plataformas y ocho métricas visibles; comprobados el coste cero y los estados sin datos.
- Tecnología: HTML y Tailwind CSS v4; sin JavaScript de aplicación, CSS propio ni frameworks adicionales. Herramientas de verificación instaladas en `/tmp/nexo-check`, fuera del proyecto.

La página es estática, no conecta cuentas reales ni aplica filtros. Tailwind, la tipografía y la imagen se cargan desde servicios externos y requieren conexión a internet.