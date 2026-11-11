# proyecto-integrador-grupo-1
# Proyecto integrador — Grupo 1: Análisis de casos de dengue en Antioquia durante 2025

## Integrantes

SEBASTIAN RINCON RODRIGUEZ
MARIA CAMILA VALLEJOS BASENTOS

## El conjunto de datos

El proyecto utiliza el conjunto de datos `salud_dengue_antioquia_2025.csv`, compuesto por 2.859 registros y 18 columnas.

Los datos son sintéticos y representan casos notificados de dengue durante 2025 en diez municipios de Antioquia.

Cada fila representa un caso notificado al sistema de vigilancia en salud pública.

Las variables incluyen información demográfica, ubicación geográfica, características clínicas, clasificación del dengue y condiciones ambientales.

### Decisión que apoya

El análisis busca apoyar a una secretaría de salud en la identificación de municipios y periodos que requieren mayor atención en las campañas de prevención, control del mosquito transmisor y atención oportuna de pacientes.

### Principales variables

| Variable | Tipo | Descripción |
|---|---|---|
| fecha_notificacion | Fecha | Fecha de notificación del caso |
| semana_epidemiologica | Numérica | Semana de notificación |
| municipio | Categórica | Municipio de residencia |
| subregion | Categórica | Subregión de Antioquia |
| zona | Categórica | Zona urbana o rural |
| sexo | Categórica | Sexo del paciente |
| edad | Numérica | Edad en años |
| regimen_salud | Categórica | Régimen de afiliación |
| dias_sintomas_a_consulta | Numérica | Días hasta la consulta |
| clasificacion | Categórica | Gravedad del dengue |
| plaquetas_miles | Numérica | Recuento de plaquetas |
| hospitalizado | Categórica | Indica si fue hospitalizado |
| dias_hospitalizacion | Numérica | Días de hospitalización |
| condicion_final | Categórica | Estado final del paciente |
| temperatura_media_semana | Numérica | Temperatura semanal |
| precipitacion_semana_mm | Numérica | Lluvia acumulada semanal |

## Preguntas de análisis

1. ¿Cómo evolucionan los casos de dengue semana a semana y qué relación tienen con las lluvias?
2. ¿Qué municipios y subregiones concentran más casos y cómo se relacionan con la temperatura?
3. ¿Cómo cambian los niveles de plaquetas según la clasificación del dengue?
4. ¿Los pacientes que tardan más en consultar presentan casos más graves y quiénes tardan más según la zona y el régimen de salud?

## Calidad de los datos y limpieza

Se identificaron valores faltantes, datos atípicos y registros que requerían revisión.

Entre los principales hallazgos de calidad se encontraron:

- 2.260 valores faltantes en días de hospitalización, correspondientes a pacientes no hospitalizados. Se conservaron porque representan una situación de no aplicación.
- 1.946 valores faltantes en ocupación (68,07 %). Se eliminó esta columna por su elevada proporción de datos faltantes.
- 420 valores faltantes en plaquetas (14,69 %).
- 183 valores faltantes en régimen de salud (6,40 %).
- 156 valores faltantes en días de síntomas hasta la consulta (5,46 %).
- 108 valores faltantes en precipitación (3,78 %).
- 98 valores faltantes en edad (3,43 %).

También se detectaron edades superiores a 110 años y demoras de consulta superiores a 30 días, que fueron identificadas para su revisión.

La limpieza permitió conservar 2.859 filas y trabajar con 17 columnas.

**Nota:** los valores faltantes restantes y las decisiones de imputación se documentan en el notebook.

## Hallazgos

### 1. Evolución semanal y lluvias

La semana epidemiológica 21 presentó el mayor número de casos, con 119 notificaciones.

La correlación entre la precipitación de la semana anterior y los casos actuales fue de 0,451, mientras que la correlación con la lluvia de la misma semana fue de 0,361.

### 2. Municipios y temperatura

Medellín presentó 595 casos, seguido de Apartadó con 542 y Caucasia con 461.

Urabá fue la subregión con más notificaciones, con 998 casos.

La correlación entre temperatura promedio y cantidad de casos por municipio fue de 0,657.

### 3. Plaquetas y clasificación

El promedio de plaquetas fue:

- Dengue sin signos de alarma: 144,02 miles/µL.
- Dengue con signos de alarma: 80,26 miles/µL.
- Dengue grave: 33,10 miles/µL.

Se observó una disminución de los niveles de plaquetas a medida que aumenta la gravedad de la clasificación.

### 4. Demora en la consulta

Los pacientes con dengue grave tardaron en promedio 5,16 días en consultar, frente a 3,51 días de los pacientes sin signos de alarma.

Los pacientes rurales tardaron 4,91 días y los urbanos 3,29 días.

Los pacientes no asegurados presentaron la mayor demora promedio, con 5,42 días.

## Visualizaciones

### Casos de dengue por municipio

![Casos por municipio](visualizaciones/Cantidad_de_casos_de_dengue_por_municipio.png)

### Relación entre temperatura y casos

![Temperatura y casos](visualizaciones/Relacion_entre_temperatura_y_casos_de_dengue.png)

### Plaquetas según clasificación

![Plaquetas por clasificación](visualizaciones/Niveles_de_plaquetas_segun_clasificacion_del_dengue.png)

### Demora en la consulta según gravedad

![Demora en consulta](visualizaciones/Demora_en_consulta_segun_gravedad_del_dengue.png)

## Conclusiones generales

El análisis permitió identificar diferencias temporales, territoriales y clínicas en los casos de dengue registrados durante 2025.

Se recomienda fortalecer las campañas de prevención en los municipios con mayor cantidad de notificaciones, prestar atención a los periodos posteriores a las lluvias y mejorar el acceso oportuno a los servicios de salud en las zonas rurales y para la población no asegurada.

Los resultados representan asociaciones descriptivas sobre datos sintéticos y no permiten establecer relaciones causales ni tasas reales de incidencia.


**Archivo de datos:** `data/salud_dengue_antioquia_2025.csv`
