# CC216-TP-2023-2-CC51
## Contenido
- Objetivo
- Participantes
- Descripción del Dataset
- Conclusiones
- Referencias Bibliográfica
## Objetivo
El objetivo del trabajo en el marco del curso de Fundamentos de Data Science es realizar un análisis exploratorio de un conjunto de datos utilizando RStudio y R como herramientas. El conjunto de datos proporcionado se llama "Hotel booking demand" y presenta datos faltantes y datos atípicos, lo que lo hace interesante para su estudio. El propósito principal de este trabajo es desarrollar habilidades fundamentales en el campo del Data Science, como la manipulación de datos, la visualización y la obtención de inferencias a partir de un conjunto de datos complejo. Se busca responder a preguntas clave sobre el comportamiento de las reservas de hoteles, considerando factores como el tipo de hotel, la temporada de reservas, la demanda en diferentes momentos del año, la presencia de niños y bebés, y otros aspectos relevantes.
## Participantes
|**Apellidos y Nombres**| **Código**| **Carrera**|
| ------------ | ------------ | ------------ |
| Alvarez Orellana, Iam Anthony Marcelo| U202118258| Ciencias de la Computación|
| Zuñiga Lovera, Angel Ruben| U202111299| Ciencias de la Computación|
| Escobedo Ccahuana Arlington Edwin| U20211C618| Ciencias de la Computación|
## Descripción del Dataset
### Caso de Análisis
Los datos proporcionados en este caso de análisis provienen de un artículo titulado "Hotel booking demand datasets" escrito por Nuno Antonio, Ana de Almeida y Luis Nunes, afiliados al Instituto Universitario de Lisboa (ISCTE-IUL), Instituto de Telecomunicaciones (IT) en Lisboa, Centro de Informática y Sistemas de la Universidad de Coímbra (CISUC) y Centro de Investigación de la Información, Tecnologías y Arquitectura (ISTAR-IUL) en Lisboa, Portugal. El artículo fue recibido el 5 de octubre de 2018, aceptado el 26 de noviembre de 2018 y está disponible en línea desde el 29 de noviembre de 2018.
El artículo describe dos conjuntos de datos con demanda hotelera. Uno de los hoteles es un resort (H1) y el otro es un hotel urbano (H2). Ambos conjuntos de datos comparten la misma estructura y contienen un total de 40,060 observaciones para H1 y 79,330 observaciones para H2. Cada observación representa una reserva de hotel. Los datos abarcan reservas con fechas de llegada entre el 1 de julio de 2015 y el 31 de agosto de 2017, incluyendo reservas que se materializaron y reservas que fueron canceladas (Antonio, Almeida., & Nunes, 2019). Estos conjuntos de datos ofrecen una oportunidad única para llevar a cabo un análisis que beneficie a diversas partes interesadas.
Por ejemplo, para los propietarios y gerentes de hoteles, el análisis de estos datos puede ayudarles a entender las tendencias de reserva específicas de su tipo de alojamiento (resort o urbano) y a tomar decisiones informadas sobre precios, promociones y gestión de recursos. Para las agencias de viajes y plataformas de reservas en línea, esta información puede ser valiosa para ajustar sus estrategias de marketing y publicidad, lo que a su vez puede aumentar la visibilidad y las reservas de los hoteles en sus plataformas.
### Conjunto de Datos (Data Set)
Para obtener una visión detallada y precisa de la información contenida en nuestro dataset, hemos organizado los datos en una tabla. La siguiente tabla nos permitirá reconocer cuales son nuestras variables, el tipo de dato y una breve descripción de estas.
|**Variables**| **Tipo de Dato**| **Descripción**|
| ------------ | ------------ | ------------ |
| hotel| chr| Indica el tipo de hotel|
| is_canceled| int| Indica si la reserva fue cancelada|
| lead_time| int| Representa la cantidad de días que transcurrieron entre la fecha de reserva y la fecha de llegada|
| arrival_date_year| int| Indica el año de llegada de los huéspedes|
| arrival_date_month| chr| Indica el mes de llegada de los huéspedes|
| arrival_date_week_number| int| Indica el número de semana del año en la que llegaron los huéspedes|
| arrival_date_day_of_month| int| Indica el día del mes en el que llegaron los huéspedes|
| stays_in_weekend_nights| int| Representa la cantidad de noches que los huéspedes se quedaron durante el fin de semana|
| stays_in_week_nights| int| Representa la cantidad de noches que los huéspedes se quedaron durante la semana|
| adults| int| Indica la cantidad de adultos en la reserva|
| children| int| Indica la cantidad de niños en la reserva|
| babies| int| Indica la cantidad de bebés en la reserva|
| meal| chr| Indica el tipo de comida incluida en la reserva|
| country| chr| Indica el país de origen de los huéspedes|
| market_segment| chr| Describe el segmento de mercado al que pertenece la reserva|
| distribution_channel| chr| Describe el canal de distribución utilizado para la reserva|
| is_repeated_guest| int| Indica si el huésped es un cliente repetido |
| previous_cancellations| int| Indica la cantidad de cancelaciones previas por parte del cliente|
| previous_bookings_not_canceled| int| Indica la cantidad de reservas previas no canceladas por el cliente|
| reserved_room_type| chr| Indica el tipo de habitación reservada|
| assigned_room_type| chr| Indica el tipo de habitación asignada|
| booking_changes| int| Representa la cantidad de cambios realizados en la reserva|
| deposit_type| chr| Indica el tipo de depósito realizado para la reserva|
| agent| chr| Indica el agente de viajes asociado a la reserva|
| company| chr| Indica la compañía asociada a la reserva|
| days_in_waiting_list| int| Representa la cantidad de días en lista de espera|
| customer_type| chr| Describe el tipo de cliente|
| adr| num| Representa la tarifa diaria promedio|
| required_car_parking_spaces| int| Indica la cantidad de espacios de estacionamiento requeridos por el cliente|
| total_of_special_requests| int| Representa la cantidad total de solicitudes especiales realizadas por el cliente|
| reservation_status| chr| Indica el estado de la reserva|
| reservation_status_date| chr| Contiene la fecha en la que se registró el estado de la reserva|
### Análisis Exploratorio de Datos
Una vez que hemos completado la fase de organización y preparación de nuestra tabla, el siguiente paso que realizamos es llevar a cabo un análisis exhaustivo que nos permita obtener una visión más clara de la información que contiene nuestro dataset. A continuación, detallaremos las acciones específicas que hemos llevado a cabo en este proceso y presentaremos los resultados clave obtenidos.
##### Cargar DatosCargar Datos
- **Acciones**: Se realizó el proceso de carga de los datos desde el archivo CSV llamado "hotel_bookings”. Para mantener un entorno limpio, primero se han eliminado todas las variables previas de la memoria y se ha limpiado la consola para comenzar en blanco. La variable “path” tiene asignada la ruta de nuestro archivo CSV, esto nos permite tener un acceso claro y directo a nuestro dataset. Además, utilizamos la función “read.csv” para leer en “path”, se configuró la función con la opción “header = TRUE”, para indicar que la primera del archivo CSV contiene los nombres de las columnas, “stringsAsFactors = FALSE” para que las cadenas de caracteres no se conviertan en tipos de dato factor y “sep = ‘,’” para los delimitadores que separan cada campo en el archivo.
- **Resultado**: La carga de datos se ha realizado con éxito, y ahora tenemos el conjunto de datos almacenado en la variable "hotel_booking_demand" para llevar a cabo nuestro análisis exploratorio.
##### Inspeccionar Datos
- **Acciones**: Se realizó una inspección inicial de los datos para comprender su estructura y contenido. Para tener una vista previa de las primeras filas en nuestro documento se utilizó la función “head(hotel_booking_demand)”, también, se utilizó la función “tail(hotel_booking_demand) “ para observar las últimas filas del documento, esto con la finalidad de observar datos distintos a las filas iniciales. Por otro lado, se identificaron los nombres de todas las columnas en el conjunto de datos con la función “names(hotel_booking_demand)” junto a las dimensiones del dataset, ello con la ayuda de la función “dim(hotel_booking_demand)” que incluyen el número de filas y columnas. Adicionalmente, utilizamos “str(hotel_booking_demand)” para examinar la estructura del conjunto de datos y con la función “summary(hotel_booking_demand)”, obtuvimos estadísticas resumidas de las columnas numéricas y una visión general de las columnas categóricas, finalmente, hemos utilizado la función” unique()” para identificar valores únicos en varias columnas clave del conjunto de datos.
- **Resultado**: Se visualizaron las primeras filas del conjunto de datos, lo que permitió obtener una vista previa de las observaciones iniciales y sus atributos, como el tipo de hotel, la cancelación de reservas, el tiempo de anticipación y otros. Además, se presentaron las últimas filas para analizar las observaciones más recientes y buscar tendencias o patrones en los datos finales. Cabe mencionar que se imprimieron los nombres de todas las columnas, lo que es fundamental para identificar y referirse a las variables de interés. Asimismo, se imprimieron las dimensiones del dataset que consta de 119,390 observaciones y 32 columnas. Algunos resultados fundamentales fueron la descripción a detalle de la estructura del dataset, especificando la presencia de variables categóricas y numéricas, así como, el resumen de estadísticas para las variables numéricas y una visión general de las variables categóricas. Por último, se identificaron valores únicos en columnas clave, como el tipo de hotel, la cancelación de reservas, el año y mes de llegada.
##### Pre-Procesar Datos
###### Identificación de datos faltantes (NA)
- **Acciones**: En primer lugar, se creó una copia del conjunto de datos original, denominada "hotel_booking_data", con el propósito de preservar la integridad del conjunto de datos original y evitar cualquier modificación inadvertida. A continuación, se llevó a cabo un análisis exhaustivo de los datos faltantes en el conjunto de datos. Se procedió a identificar los datos faltantes por columna, lo que proporcionó una visión detallada de la magnitud del problema en cada atributo. En particular, se centró la atención en la columna "children" para examinar las filas que contenían datos faltantes y comprender mejor su distribución mediante un resumen estadístico. Se determinó que el valor más frecuente en esta columna.
- **Resultado**: Se detectaron un total de 4 datos faltantes en el conjunto de datos, siendo la columna "children" la única afectada con estos valores ausentes. Cuatro filas específicas relacionadas con reservas en "City Hotel" presentaron estos datos faltantes, con variaciones en atributos como la fecha de llegada y la duración de la estadía. Previo a la corrección de datos, se reveló que la columna "children" tenía una distribución que abarcaba desde 0 hasta 10, con un valor de moda igual a 0. Para solucionar este problema, se imputaron los 4 valores faltantes con la moda (0), garantizando así la integridad de la información en la columna "children". Además, se proporcionó una visualización gráfica de la distribución de valores antes y después de la corrección, destacando 0 como el valor predominante tras el proceso de completación de datos faltantes.
###### Identificación de datos atípicos (Outliers)
- **Acciones**: Se realizaron evaluaciones exhaustivas de datos atípicos en diversas columnas del conjunto de datos, incluyendo "lead_time," "stays_in_weekend_nights," "stays_in_week_nights," "adults," "children," "babies," "is_repeated_guest," "previous_cancellations," "previous_bookings_not_canceled," "booking_changes," "days_in_waiting_list," "adr," "required_car_parking_spaces," y "total_of_special_requests." Para abordar estos valores atípicos, se diseñó una función especializada llamada "transformar_outliers," que calcula los cuartiles y el Rango Intercuartílico (IQR) para cada columna, estableciendo límites superior e inferior para identificar y ajustar los valores atípicos. Se destacan medidas adicionales en las columnas "children," "babies," y "required_car_parking_spaces," donde se aplicaron limitaciones específicas para garantizar que los valores permanezcan dentro de rangos particulares (de 0 a 10 en "children" y "babies," y de 0 a 8 en "required_car_parking_spaces")
- **Resultado**: Se observó que la columna "lead_time" contenía un total de 3,005 valores atípicos, mientras que la columna "stays_in_weekend_nights" presentaba 265 valores atípicos y la columna "stays_in_week_nights" tenía 167 valores atípicos. En contraste, las columnas "adults," "is_repeated_guest," "previous_cancellations," "previous_bookings_not_canceled," y "booking_changes" no mostraban valores atípicos notables. Para las columnas "children" y "babies," se aplicaron restricciones para mantener los valores dentro del rango de 0 a 10, garantizando así la consistencia de los datos. Además, la columna "required_car_parking_spaces" se transformó para limitar los valores dentro del rango de 0 a 8. Se llevaron a cabo ajustes en las columnas "days_in_waiting_list" y "adr" para abordar valores atípicos.
##### Visualizar Datos
###### ¿Cuántas reservas se realizan por tipo de hotel? o ¿Qué tipo de hotel prefiere la gente?
- **Variables en uso**: hotel.

En primer lugar, convierte la columna `hotel` en un factor para tratar las categorías de hoteles como niveles discretos. Luego, se calcula una tabla de frecuencia que muestra cuántas reservas hay para cada tipo de hotel. Esta información se almacena en un marco de datos llamado `reservas_df`, cuyas columnas se etiquetan como `Tipo_de_Hotel` y `Numero_de_Reservas` para mayor claridad. A continuación, se genera un gráfico de barras que representa el número de reservas por tipo de hotel, con detalles de formato como colores y límites del eje y. Además, se identifica el tipo de hotel más preferido y se imprime en la consola junto con el resumen de las reservas por tipo de hotel. En resumen, este código procesa y visualiza datos de reservas de hoteles, identificando el tipo de hotel más preferido en función de las reservas acumuladas.
###### ¿Está aumentando la demanda con el tiempo?
- **Variables en uso**: arrival_date_month.

En primer lugar, se convierte la columna `arrival_date_month` en un factor con niveles que corresponden a los nombres de los meses para asegurar una representación adecuada en los gráficos. Luego, se calcula una tabla de frecuencia llamada `reservas_por_mes`, que resume cuántas reservas se realizaron en cada mes, brindando una visión de la demanda a lo largo del tiempo. Esta información se organiza en un marco de datos llamado `reservas_mes_df` con columnas etiquetadas como `Mes` y `Numero_de_Reservas` para facilitar su manipulación. A continuación, se crea un gráfico de líneas que muestra la evolución del número de reservas a lo largo del año, utilizando el eje x para representar los meses y el eje y para mostrar el número de reservas en un tono azul. Finalmente, se imprimen los valores de la tabla de frecuencia `reservas_por_mes` en la consola, proporcionando una visión detallada de las reservas realizadas en cada mes.
###### ¿Cuándo se producen las temporadas de reservas: alta, media y baja?
- **Variables en uso**: arrival_date_month, is_canceled. 

Primero, se utiliza la función `aggregate()` para agrupar y contar el número de reservas por mes de llegada. Luego, se reorganiza el resultado en orden descendente, priorizando los meses con más cancelaciones. A continuación, se asigna a `temporada_alta` el primer mes en el conjunto de datos, representando la temporada con el mayor número de reservas. Para determinar la temporada media, se calcula el mes en el centro del conjunto de datos, asegurando un índice entero mediante redondeo hacia arriba. Por último, `temporada_baja` se obtiene del último mes en la lista, indicando la temporada con el menor número de reservas. Los resultados se presentan en la consola de RStudio para su visualización.
###### ¿Cuándo es menor la demanda de reservas?
- **Variables en uso**: hotel, arrival_date_month.

Primero, utiliza la función `aggregate()` para calcular cuántas reservas se hicieron en cada mes, agrupando los datos por el mes de llegada. El resultado se almacena en un objeto llamado `reservas_por_mes`, que contiene los nombres de los meses y la cantidad de reservas correspondiente. Luego, se determina el mes con la menor demanda de reservas al encontrar el valor mínimo en la columna de recuento. El nombre de ese mes se guarda en la variable `mes_menor_demanda`. Finalmente, se imprime en la consola un mensaje que identifica el mes con la menor cantidad de reservas.
###### ¿Cuántas reservas incluyen niños y/o bebes?
- **Variables en uso**: children, babies.

En primer lugar, se crea un nuevo conjunto de datos llamado `reservas_con_ninos_bebes` utilizando la función `subset()`, el cual contiene las reservas donde al menos un niño o bebé está involucrado, basándose en las columnas `children` o `babies`. Luego, se calcula la cantidad total de estas reservas utilizando `nrow()` y se almacena en la variable `cantidad_reservas_con_ninos_bebes`. Finalmente, se imprime un mensaje informativo en la consola, destacando el número de reservas que incluyen niños y/o bebés, lo que proporciona información útil para la planificación de servicios orientados a familias con niños pequeños que viajan.
###### ¿Es importante contar con espacios de estacionamiento?
- **Variables en uso**: required_car_parking_spaces.

En primer lugar, se crea un nuevo conjunto de datos llamado `reservas_con_estacionamiento`, que contiene las reservas que especifican la necesidad de al menos un espacio de estacionamiento. Luego, se determina el número total de reservas en el conjunto de datos original `hotel_booking_data`. A continuación, se calcula el porcentaje de reservas que requieren estacionamiento dividiendo el número de reservas con esta condición entre el total de reservas y multiplicando el resultado por 100. Finalmente, se imprime en la consola un mensaje que muestra este porcentaje, redondeado a una decimal, proporcionando información relevante sobre la proporción de reservas que dependen de espacios de estacionamiento para su alojamiento.
###### ¿En qué meses del año se producen más cancelaciones de reservas?
- **Variables en uso**: arrival_date_month, reservation_status.

En primer lugar, se crea un conjunto de datos llamado `reservas_canceladas` que incluye solo las reservas con estado `Canceled` (canceladas). Luego, se calcula una tabla de frecuencia denominada `cancelaciones_por_mes` que resume la cantidad de cancelaciones mensuales. Esta información se organiza en un marco de datos llamado `cancelaciones_mes_df` con columnas etiquetadas como `Mes` y `Numero_de_Cancelaciones` para una mayor claridad. Se genera un gráfico de barras que muestra el número de cancelaciones por mes, con etiquetas de ejes, colores y otros detalles de formato. Finalmente, se imprime en la consola la tabla de frecuencia `cancelaciones_por_mes`, lo que proporciona una visión detallada de las cancelaciones de reservas en cada mes. En conjunto, este código ofrece una representación visual y cuantitativa de las cancelaciones de reservas a lo largo del año, permitiendo la identificación de patrones y tendencias.
## Conclusiones
## Referencias Bibliográfica
- Antonio, N., Almeida, A., & Nunes, L. (2019). Hotel booking demand datasets. Science Direct, 22, 41 - 49. Recuperado de: https://www.sciencedirect.com/science/article/pii/S2352340918315191 [Consulta: 18/09/2023]
