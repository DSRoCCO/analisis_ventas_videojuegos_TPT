# Proyecto Integrado: Análisis de Ventas de Videojuegos

Este proyecto tiene como objetivo identificar patrones que determinan el éxito de un videojuego, permitiendo detectar proyectos prometedores y planificar campañas publicitarias.

## Descripción del Proyecto

Trabajas para la tienda online **Ice**, que vende videojuegos en todo el mundo. Contamos con datos históricos de ventas, reseñas de usuarios y expertos, géneros, plataformas y clasificaciones ESRB, recopilados hasta 2016. 

Imaginamos que estamos en diciembre de 2016 y planeamos una campaña publicitaria para 2017. Nuestro enfoque principal es adquirir experiencia en el manejo de datos y establecer un modelo para predecir ventas futuras.

### Descripción de los Datos

El dataset incluye las siguientes columnas:

- **Name:** Nombre del juego.
- **Platform:** Plataforma (ej., Xbox, PlayStation, PC).
- **Year_of_Release:** Año de lanzamiento.
- **Genre:** Género del juego.
- **NA_sales:** Ventas en Norteamérica (millones de USD).
- **EU_sales:** Ventas en Europa (millones de USD).
- **JP_sales:** Ventas en Japón (millones de USD).
- **Other_sales:** Ventas en otras regiones (millones de USD).
- **Critic_Score:** Puntuación de críticos (máximo de 100).
- **User_Score:** Puntuación de usuarios (máximo de 10).
- **Rating:** Clasificación ESRB.

Los datos de 2016 pueden estar incompletos.

### Clasificaciones ESRB

- **E (Everyone):** Contenido apto para todas las edades.
- **E10+ (Everyone 10+):** Contenido apto para mayores de 10 años.
- **EC (Early Childhood):** Contenido apto para niños en edad preescolar.
- **K-A (Kids to Adults):** Clasificación obsoleta, ahora reemplazada por **E**.
- **M (Mature):** Contenido apto para mayores de 17 años.
- **RP (Rating Pending):** Clasificación en espera.
- **T (Teen):** Contenido apto para mayores de 13 años.
- **NaN:** Valores faltantes o no disponibles.

---

## Procesamiento de Datos

1. **Manejo de Valores Faltantes:**
   - Los valores "tbd" en la columna `User_Score` se reemplazaron con `NaN`.
   - Los datos antes del año 2000 se excluyeron, dejando 6,826 registros para el análisis inicial.

2. **Imputación de Valores:**
   - Se realizaron imputaciones para las columnas `Critic_Score` y `User_Score`.
   - La columna `Rating` no mostró relaciones significativas con otras variables, por lo que se dejó sin cambios.

3. **Cálculo de Ventas Totales:**
   - Se creó una columna `Total_Sales` sumando las ventas en todas las regiones.

4. **Selección de Datos Relevantes:**
   - Se trabajó con datos de 2000 a 2014 para maximizar la calidad y cantidad de información.

---

## Análisis y Resultados

### Relación entre Variables
- **User_Score vs. Ventas:** Relación significativa observada para plataformas específicas como `DC`, con un **R²** de hasta 73% al incluir `Critic_Score`.
- **Critic_Score y User_Score:** Relación moderada, con un **R²** de 58%.

### Tendencias por Plataforma
- Las plataformas más populares (ej., PS2, Wii, X360) alcanzan su pico de ventas entre los 3 y 5 años posteriores a su lanzamiento.
- La **PC** es la única plataforma con ventas constantes debido a su capacidad de actualización y versatilidad.

### Géneros Más Rentables
- **Más vendidos:** Action, Sports y Shooter.
- **Mayor rentabilidad promedio:** Shooter, Misc y Platform.

### Análisis Regional
- Norteamérica es el mayor mercado, con géneros como Action y plataformas como X360 liderando las ventas.

### Comparaciones Estadísticas
- **XOne vs. PC:** Evidencia significativa de diferencias en las medias (rechazo de hipótesis nula).
- **Action vs. Sports:** No hay diferencias significativas en las medias (no se rechaza la hipótesis nula).

---

## Conclusiones

1. **Duración de Vida de las Plataformas:** Las plataformas generalmente no permanecen populares más de 10 años, excepto la PC.
2. **Relación entre Puntuaciones y Ventas:** No hay correlaciones significativas entre puntuaciones de usuarios/críticos y ventas totales.
3. **Géneros Rentables:** Shooter es el género más efectivo en términos de ventas totales.
4. **Manejo de Datos Faltantes:** Imputaciones realizadas con éxito para mejorar la calidad del análisis.
5. **Análisis Estadístico:** Evidencia significativa para algunas comparaciones (plataformas y géneros).
6. **Planificación de Campañas:** Datos entre 2000 y 2014 son clave para predecir tendencias futuras.

---

## Próximos Pasos

- Optimizar imputaciones considerando plataformas específicas.
- Explorar más relaciones entre puntuaciones, ventas y géneros.
- Desarrollar un modelo predictivo para estimar ventas futuras.
