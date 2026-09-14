# Dashboard de Producción
Power BI dashboard for monitoring production performance through key indicators such as units produced, rejected units, quality, productivity, and productive and non-productive hours. Allows analysis by operator, location, and month to support operational follow-up and decision-making.

# Dashboard de Producción

## 1. Descripción

Dashboard desarrollado en Power BI para analizar el desempeño de la producción a partir de indicadores de calidad, productividad, horas trabajadas y piezas producidas.

El reporte permite consultar los resultados por operador y periodo, así como comparar las horas productivas y no productivas por ubicación.

## 2. Objetivo

Facilitar el seguimiento de la producción mediante indicadores que permitan identificar el volumen de piezas producidas, piezas rechazadas, nivel de calidad, productividad y distribución de las horas productivas y no productivas.

## 3. Fuente y estructura de los datos

El dashboard utiliza una única tabla denominada `Producción`, por lo que no fue necesario construir un modelo de datos con múltiples tablas o relaciones.

La tabla contiene información relacionada con órdenes de producción, operadores, ubicaciones, productos, tiempos de operación y resultados de producción.

### Principales campos

- No. Orden
- Operador
- Ubicación
- Producto
- Obstáculos
- Fecha inicio
- Hora inicio
- Fecha fin
- Hora fin
- Total Horas
- Piezas producidas
- Piezas rechazadas

## 4. Limpieza y preparación de datos

La limpieza de datos se realizó antes de construir las visualizaciones, verificando que los campos fueran consistentes y que los valores pudieran utilizarse correctamente en los cálculos.

### 4.1 Revisión de tipos de datos

Se verificaron los tipos de datos de cada columna de acuerdo con su contenido:

- Fechas → tipo fecha.
- Horas → tipo hora.
- Total Horas → tipo numérico.
- Piezas producidas → tipo numérico.
- Piezas rechazadas → tipo numérico.
- Operador, ubicación, producto y obstáculos → tipo texto.

Asignar correctamente los tipos de datos permite evitar errores en cálculos, filtros y visualizaciones.

### 4.2 Revisión de valores nulos y vacíos

Se revisaron los valores `null`, vacíos y celdas sin información para determinar si representaban un dato faltante o una condición válida del proceso.

En el campo `Obstáculos`, un valor vacío representa que no se registró un obstáculo y se utiliza como criterio para identificar horas productivas. Por esta razón, estos valores no deben eliminarse automáticamente.

Antes de reemplazar o eliminar valores nulos se debe analizar:

- Qué significa el campo dentro del proceso.
- Si el valor vacío representa una condición válida.
- Si existen registros con información en el mismo campo.
- Si el dato faltante afecta algún cálculo o indicador.
- Si reemplazarlo por otro valor podría modificar el significado original.

La regla de limpieza debe definirse de acuerdo con el significado del dato y no únicamente por la existencia de valores nulos.

### 4.3 Validación de valores

Se revisaron los campos utilizados en los indicadores para identificar valores inconsistentes, formatos diferentes o registros que pudieran afectar los resultados.

La validación debe considerar especialmente:

- Valores numéricos negativos o fuera de rango.
- Fechas u horas con formatos incorrectos.
- Diferencias de escritura en categorías como operador, ubicación o producto.
- Registros duplicados.
- Campos obligatorios sin información.
- Valores que no correspondan con la lógica del proceso.

## 5. Modelo de datos

El dashboard utiliza una sola tabla (`Producción`), por lo que no se requirió establecer relaciones entre tablas.

<img width="416" height="405" alt="image" src="https://github.com/user-attachments/assets/141726cf-bb82-4613-b0cd-55bbafa0f2c5" />

La información se encuentra estructurada en registros de producción y es utilizada directamente para generar los indicadores y visualizaciones del reporte.

## 6. Medidas

Las medidas DAX utilizadas para calcular los principales indicadores se documentan de forma independiente.

Entre los indicadores calculados se encuentran:

- Piezas buenas producidas.
- Total de piezas rechazadas.
- Total de piezas producidas.
- Total de horas productivas.
- Horas no productivas.
- Porcentaje de calidad.
- Porcentaje de productividad.

## 7. Diseño del dashboard

El dashboard incorpora filtros, tarjetas, gráficos y medidores para facilitar el seguimiento de los principales indicadores de producción.

### Filtros

- Operador.
- Mes.

### Tarjetas

- Piezas buenas producidas.
- Total de piezas rechazadas.
- Total de piezas producidas.
- Total de horas productivas.

### Gráfico de barras agrupadas

Permite comparar las horas productivas y no productivas por ubicación.

- Eje Y: Ubicación.
- Eje X: Horas.
- Series: Total de horas productivas y horas no productivas.

### Gráfico de áreas

Muestra la evolución mensual de las piezas buenas producidas.

- Eje X: Mes.
- Eje Y: Piezas buenas producidas.

### Medidores

Se utilizan dos medidores para mostrar indicadores porcentuales:

- % de calidad.
- % de productividad.

### Tabla de detalle

Permite consultar la información individual de cada registro de producción:

- No. Orden.
- Operador.
- Ubicación.
- Producto.
- Obstáculos.
- Fecha inicio.
- Hora inicio.
- Fecha fin.
- Hora fin.
- Total Horas.
- Piezas producidas.
- Piezas rechazadas.

## 8. Preguntas que responde el dashboard

El dashboard está diseñado para responder preguntas relacionadas con el desempeño de la producción:

- ¿Cuántas piezas buenas se produjeron?
- ¿Cuántas piezas fueron rechazadas?
- ¿Cuál es el total de piezas producidas?
- ¿Cuál es el porcentaje de calidad?
- ¿Cuál es el porcentaje de productividad?
- ¿Cuántas horas fueron productivas?
- ¿Cuántas horas fueron no productivas?
- ¿Cómo se distribuyen las horas productivas y no productivas entre las ubicaciones?
- ¿Cómo cambia la producción de piezas buenas a lo largo de los meses?
- ¿Cómo varían los resultados según el operador?

  # Vista previa
  <img width="762" height="423" alt="image" src="https://github.com/user-attachments/assets/c20c3558-8485-4e81-a8e1-784ccf6391dc" />
