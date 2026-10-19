# Especificación: Dashboard de rendimiento de influencer

## Objetivo

Definir un dashboard de reporte que consolide el rendimiento de una influencer en varias plataformas sociales y permita supervisar ventas, comisiones, conversiones y engagement para tomar decisiones sobre productos, plataformas y campañas.

## Contexto del negocio

La influencer está empezando a colaborar con marcas y promociona tres productos mediante enlaces o anuncios en distintas redes sociales. Recibe una comisión del 15 % por cada venta atribuida a su promoción.

| Producto | Precio de venta | Comisión por venta |
| --- | ---: | ---: |
| Producto A | 50 € | 7,50 € |
| Producto B | 120 € | 18 € |
| Producto C | 80 € | 12 € |

Las plataformas consideradas incluyen Instagram, TikTok y YouTube. La estructura debe poder presentar otras plataformas sin cambiar el significado de las métricas.

## Requisitos funcionales

### Bloque superior: indicadores principales

- Mostrar al menos tres KPI de negocio, con nombre, valor y periodo de referencia.
- Incluir como mínimo ventas atribuidas, comisiones generadas, alcance o impresiones, conversiones y tasa de engagement.
- Presentar importes en euros y cantidades con formato legible.
- Comparar con un periodo anterior solo cuando existan datos comparables; en caso contrario, indicar que no hay comparación disponible.

### Bloque intermedio: drivers del resultado

- Mostrar el embudo de rendimiento con alcance, clics y conversiones cuando esos datos estén disponibles.
- Comparar alcance, interacciones, conversiones y comisiones por plataforma.
- Comparar conversiones y comisiones por producto.
- Mostrar actividad publicada por plataforma, como posts, stories, reels y videos, cuando haya datos.
- Desglosar interacciones en me gusta, comentarios, compartidos y guardados cuando haya datos.

### Bloque inferior: detalle operacional

- Incluir una tabla de productos con nombre, precio, ventas atribuidas, conversiones, comisiones y retorno cuando se conozcan los costes.
- Incluir una tabla de plataformas con alcance, interacciones, tasa de engagement, conversiones y comisiones.
- Incluir una tabla de campañas con fechas, plataforma, producto promocionado, costes disponibles, resultados y rendimiento.
- Incluir listados de productos, plataformas y campañas con mejor rendimiento, además de oportunidades de mejora basadas en las métricas disponibles.
- Mostrar alertas de cambios relevantes en conversión o rendimiento solo cuando exista una base comparable para detectarlos.
- Ofrecer controles de selección por periodo, plataforma y producto. Si la versión es estática y no puede aplicar filtros, los controles deben identificarse como no interactivos y no aparentar filtrar resultados.

## Definiciones y reglas de cálculo

- **Comisión por venta:** precio del producto × 0,15.
- **Comisiones generadas:** suma de las comisiones de las ventas atribuidas a cada producto.
- **Tasa de engagement:** interacciones totales ÷ alcance × 100. Las interacciones totales son la suma de me gusta, comentarios, compartidos y guardados disponibles.
- **Tasa de conversión:** conversiones ÷ alcance × 100, de acuerdo con la definición solicitada para este dashboard.
- **CTR:** clics ÷ impresiones × 100, únicamente cuando se disponga de ambas cantidades.
- **ROAS (retorno sobre gasto publicitario):** ingresos atribuidos ÷ costes publicitarios. Se debe distinguir de ROI.
- **ROI:** (ingresos atribuidos − costes publicitarios) ÷ costes publicitarios × 100.
- Si faltan datos necesarios o el denominador es cero, mostrar “Sin datos” o “No aplicable”; no inventar valores ni dividir por cero.
- MRR, churn, permanencia, NPS y CSAT no forman parte de las métricas calculables con la información del negocio disponible. Solo se mostrarán si se incorporan datos adecuados; de lo contrario, se omitirán o se marcarán como no disponibles.

## Requisitos de contenido y datos

- Los datos reales de plataformas, campañas, costes, clics, ventas y satisfacción no están incluidos en el proyecto actual.
- Cualquier dato de ejemplo debe identificarse de forma visible como demostración y no debe confundirse con resultados reales.
- Los datos deben asociar cada conversión con producto, plataforma y campaña cuando esa atribución esté disponible.
- El periodo seleccionado debe ser visible y consistente entre KPI, gráficos o comparaciones y tablas.

## Requisitos de interfaz y tecnología

- La interfaz debe separar visualmente los bloques de KPI, drivers y detalle operacional, con jerarquía clara y patrones consistentes para elementos equivalentes.
- La estructura debe usar HTML semántico, incluyendo landmarks como `header`, `nav`, `main` y `section`, y tablas HTML para datos tabulares.
- La implementación se limita a HTML y Tailwind CSS v4. No se deben usar React, Vue, otros frameworks CSS ni hojas de estilo personalizadas.
- No se debe usar `cdn.tailwindcss.com` ni configuración o sintaxis de Tailwind CSS v3. Si se utiliza CDN, debe ser la distribución de navegador de Tailwind CSS v4 que ya carga el proyecto.
- El diseño debe ser mobile-first y adaptar los mismos contenidos a móvil, tablet y escritorio mediante breakpoints de Tailwind.
- La interfaz debe mantener legibilidad, orden y controles utilizables en pantallas estrechas, sin desbordamiento horizontal de la página.

## Criterios de aceptación

- [x] **CA-01.** El dashboard presenta tres bloques distinguibles: KPI en la parte superior, drivers en la parte intermedia y detalle operacional en la parte inferior.
- [x] **CA-02.** El bloque superior muestra al menos tres KPI e incluye ventas atribuidas y comisiones; cada KPI indica su periodo y unidad cuando corresponda.
- [x] **CA-03.** El bloque intermedio incluye conversión por etapas, comparación por plataforma y comparación por producto cuando existan datos para esas vistas.
- [x] **CA-04.** El bloque inferior incluye tablas de productos, plataformas y campañas con las columnas indicadas en los requisitos funcionales.
- [x] **CA-05.** Los importes de comisión corresponden al 15 % del precio: 7,50 € para A, 18 € para B y 12 € para C.
- [x] **CA-06.** Las tasas de engagement, conversión, CTR, ROAS y ROI respetan las fórmulas definidas y no presentan resultados engañosos cuando faltan datos o el denominador es cero.
- [x] **CA-07.** Los datos demostrativos están identificados claramente; ningún dato de ejemplo se presenta como dato real de la influencer.
- [x] **CA-08.** Las métricas para las que no hay fuentes disponibles, como MRR, churn, NPS o CSAT, no se rellenan con valores inventados.
- [x] **CA-09.** El HTML mantiene una jerarquía semántica válida y las tablas tienen encabezados que identifican sus columnas.
- [x] **CA-10.** La vista funciona sin desbordamiento horizontal y conserva el acceso a los contenidos principales en móvil (320–639 px), tablet (640–1023 px) y escritorio (1024 px o más).
- [x] **CA-11.** Los estilos se implementan con utilidades de Tailwind CSS v4; no aparecen dependencias de React, Vue, otro framework CSS, CSS personalizado, `cdn.tailwindcss.com` ni instrucciones de Tailwind CSS v3.
- [x] **CA-12.** Los controles de periodo, plataforma y producto no afirman filtrar datos si no tienen comportamiento de filtrado implementado.

Verificados el 19 de octubre de 2026. Evidencias y alcance de la revisión: [task.md](task.md#verificación-final).