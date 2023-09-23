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

```r
# BORRA TODAS LAS VARIABLES DE MEMORIA
rm(list=ls(all=TRUE))

# Limpia consola
cat("\014")

### 1. CARGAR DATOS
# 1.1 Creamos una variable, le asignamos la ruta del dataset
path <- "C:/Users/Core i5/Desktop/Fundamentos de Data Science/TRABAJO PARCIAL/hotel_bookings.csv"

# 1.2 Leemos nuestro dataset
hotel_booking_demand <- read.csv(path, header = TRUE, stringsAsFactors = FALSE, sep = ',')
```
- **Resultado**: La carga de datos se ha realizado con éxito, y ahora tenemos el conjunto de datos almacenado en la variable "hotel_booking_demand" para llevar a cabo nuestro análisis exploratorio.

```r
> ### 1. CARGAR DATOS
> # 1.1 Creamos una variable, le asignamos la ruta del dataset
> path <- "C:/Users/Core i5/Desktop/Fundamentos de Data Science/TRABAJO PARCIAL/hotel_bookings.csv"
> # 1.2 Leemos nuestro dataset
> hotel_booking_demand <- read.csv(path, header = TRUE, stringsAsFactors = FALSE, sep = ',')
```
##### Inspeccionar Datos
- **Acciones**: Se realizó una inspección inicial de los datos para comprender su estructura y contenido. Para tener una vista previa de las primeras filas en nuestro documento se utilizó la función “head(hotel_booking_demand)”, también, se utilizó la función “tail(hotel_booking_demand) “ para observar las últimas filas del documento, esto con la finalidad de observar datos distintos a las filas iniciales. Por otro lado, se identificaron los nombres de todas las columnas en el conjunto de datos con la función “names(hotel_booking_demand)” junto a las dimensiones del dataset, ello con la ayuda de la función “dim(hotel_booking_demand)” que incluyen el número de filas y columnas. Adicionalmente, utilizamos “str(hotel_booking_demand)” para examinar la estructura del conjunto de datos y con la función “summary(hotel_booking_demand)”, obtuvimos estadísticas resumidas de las columnas numéricas y una visión general de las columnas categóricas, finalmente, hemos utilizado la función” unique()” para identificar valores únicos en varias columnas clave del conjunto de datos.

```r
### 2. INSPECCIONAR DATOS
# 2.1 Vizualizamos
# 2.1.1 Las primeras filas
head(hotel_booking_demand)

# 2.1.2 Las ultimas filas
tail(hotel_booking_demand)

# 2.1.3 Nombre de las columnas
names(hotel_booking_demand)

# 2.2 Dimensiones del dataset
dim(hotel_booking_demand)

# 2.3 Estructura
str(hotel_booking_demand)

# 2.4 Descripcion general
summary(hotel_booking_demand)

# 2.5 Identificamos los valores de las columnas
unique(hotel_booking_demand$hotel)
unique(hotel_booking_demand$is_canceled)
unique(hotel_booking_demand$lead_time)
unique(hotel_booking_demand$arrival_date_year)
unique(hotel_booking_demand$arrival_date_month)
unique(hotel_booking_demand$arrival_date_week_number)
unique(hotel_booking_demand$arrival_date_day_of_month)
unique(hotel_booking_demand$stays_in_weekend_nights)
unique(hotel_booking_demand$stays_in_week_nights)
unique(hotel_booking_demand$adults)
unique(hotel_booking_demand$children)
unique(hotel_booking_demand$babies)
unique(hotel_booking_demand$meal)
unique(hotel_booking_demand$country)
unique(hotel_booking_demand$market_segment)
unique(hotel_booking_demand$distribution_channel)
unique(hotel_booking_demand$is_repeated_guest)
unique(hotel_booking_demand$previous_cancellations)
unique(hotel_booking_demand$previous_bookings_not_canceled)
unique(hotel_booking_demand$reserved_room_type)
unique(hotel_booking_demand$assigned_room_type)
unique(hotel_booking_demand$booking_changes)
unique(hotel_booking_demand$deposit_type)
unique(hotel_booking_demand$agent)
unique(hotel_booking_demand$company)
unique(hotel_booking_demand$customer_type)
unique(hotel_booking_demand$adr)
unique(hotel_booking_demand$required_car_parking_spaces)
unique(hotel_booking_demand$total_of_special_requests)
unique(hotel_booking_demand$reservation_status)
unique(hotel_booking_demand$reservation_status_date)
```
- **Resultado**: Se visualizaron las primeras filas del conjunto de datos, lo que permitió obtener una vista previa de las observaciones iniciales y sus atributos, como el tipo de hotel, la cancelación de reservas, el tiempo de anticipación y otros. Además, se presentaron las últimas filas para analizar las observaciones más recientes y buscar tendencias o patrones en los datos finales. Cabe mencionar que se imprimieron los nombres de todas las columnas, lo que es fundamental para identificar y referirse a las variables de interés. Asimismo, se imprimieron las dimensiones del dataset que consta de 119,390 observaciones y 32 columnas. Algunos resultados fundamentales fueron la descripción a detalle de la estructura del dataset, especificando la presencia de variables categóricas y numéricas, así como, el resumen de estadísticas para las variables numéricas y una visión general de las variables categóricas. Por último, se identificaron valores únicos en columnas clave, como el tipo de hotel, la cancelación de reservas, el año y mes de llegada.

```r
> ### 2. INSPECCIONAR DATOS
> # 2.1 Vizualizamos
> # 2.1.1 Las primeras filas
> head(hotel_booking_demand)
         hotel is_canceled lead_time arrival_date_year arrival_date_month arrival_date_week_number
1 Resort Hotel           0       342              2015               July                       27
2 Resort Hotel           0       737              2015               July                       27
3 Resort Hotel           0         7              2015               July                       27
4 Resort Hotel           0        13              2015               July                       27
5 Resort Hotel           0        14              2015               July                       27
6 Resort Hotel           0        14              2015               July                       27
  arrival_date_day_of_month stays_in_weekend_nights stays_in_week_nights adults children babies meal
1                         1                       0                    0      2        0      0   BB
2                         1                       0                    0      2        0      0   BB
3                         1                       0                    1      1        0      0   BB
4                         1                       0                    1      1        0      0   BB
5                         1                       0                    2      2        0      0   BB
6                         1                       0                    2      2        0      0   BB
  country market_segment distribution_channel is_repeated_guest previous_cancellations
1     PRT         Direct               Direct                 0                      0
2     PRT         Direct               Direct                 0                      0
3     GBR         Direct               Direct                 0                      0
4     GBR      Corporate            Corporate                 0                      0
5     GBR      Online TA                TA/TO                 0                      0
6     GBR      Online TA                TA/TO                 0                      0
  previous_bookings_not_canceled reserved_room_type assigned_room_type booking_changes deposit_type agent
1                              0                  C                  C               3   No Deposit  NULL
2                              0                  C                  C               4   No Deposit  NULL
3                              0                  A                  C               0   No Deposit  NULL
4                              0                  A                  A               0   No Deposit   304
5                              0                  A                  A               0   No Deposit   240
6                              0                  A                  A               0   No Deposit   240
  company days_in_waiting_list customer_type adr required_car_parking_spaces total_of_special_requests
1    NULL                    0     Transient   0                           0                         0
2    NULL                    0     Transient   0                           0                         0
3    NULL                    0     Transient  75                           0                         0
4    NULL                    0     Transient  75                           0                         0
5    NULL                    0     Transient  98                           0                         1
6    NULL                    0     Transient  98                           0                         1
  reservation_status reservation_status_date
1          Check-Out              2015-07-01
2          Check-Out              2015-07-01
3          Check-Out              2015-07-02
4          Check-Out              2015-07-02
5          Check-Out              2015-07-03
6          Check-Out              2015-07-03
> # 2.1.2 Las ultimas filas
> tail(hotel_booking_demand)
            hotel is_canceled lead_time arrival_date_year arrival_date_month arrival_date_week_number
119385 City Hotel           0        21              2017             August                       35
119386 City Hotel           0        23              2017             August                       35
119387 City Hotel           0       102              2017             August                       35
119388 City Hotel           0        34              2017             August                       35
119389 City Hotel           0       109              2017             August                       35
119390 City Hotel           0       205              2017             August                       35
       arrival_date_day_of_month stays_in_weekend_nights stays_in_week_nights adults children babies meal
119385                        30                       2                    5      2        0      0   BB
119386                        30                       2                    5      2        0      0   BB
119387                        31                       2                    5      3        0      0   BB
119388                        31                       2                    5      2        0      0   BB
119389                        31                       2                    5      2        0      0   BB
119390                        29                       2                    7      2        0      0   HB
       country market_segment distribution_channel is_repeated_guest previous_cancellations
119385     BEL  Offline TA/TO                TA/TO                 0                      0
119386     BEL  Offline TA/TO                TA/TO                 0                      0
119387     FRA      Online TA                TA/TO                 0                      0
119388     DEU      Online TA                TA/TO                 0                      0
119389     GBR      Online TA                TA/TO                 0                      0
119390     DEU      Online TA                TA/TO                 0                      0
       previous_bookings_not_canceled reserved_room_type assigned_room_type booking_changes deposit_type
119385                              0                  A                  A               0   No Deposit
119386                              0                  A                  A               0   No Deposit
119387                              0                  E                  E               0   No Deposit
119388                              0                  D                  D               0   No Deposit
119389                              0                  A                  A               0   No Deposit
119390                              0                  A                  A               0   No Deposit
       agent company days_in_waiting_list customer_type    adr required_car_parking_spaces
119385   394    NULL                    0     Transient  96.14                           0
119386   394    NULL                    0     Transient  96.14                           0
119387     9    NULL                    0     Transient 225.43                           0
119388     9    NULL                    0     Transient 157.71                           0
119389    89    NULL                    0     Transient 104.40                           0
119390     9    NULL                    0     Transient 151.20                           0
       total_of_special_requests reservation_status reservation_status_date
119385                         2          Check-Out              2017-09-06
119386                         0          Check-Out              2017-09-06
119387                         2          Check-Out              2017-09-07
119388                         4          Check-Out              2017-09-07
119389                         0          Check-Out              2017-09-07
119390                         2          Check-Out              2017-09-07
> # 2.1.3 Nombre de las columnas
> names(hotel_booking_demand)
 [1] "hotel"                          "is_canceled"                    "lead_time"                     
 [4] "arrival_date_year"              "arrival_date_month"             "arrival_date_week_number"      
 [7] "arrival_date_day_of_month"      "stays_in_weekend_nights"        "stays_in_week_nights"          
[10] "adults"                         "children"                       "babies"                        
[13] "meal"                           "country"                        "market_segment"                
[16] "distribution_channel"           "is_repeated_guest"              "previous_cancellations"        
[19] "previous_bookings_not_canceled" "reserved_room_type"             "assigned_room_type"            
[22] "booking_changes"                "deposit_type"                   "agent"                         
[25] "company"                        "days_in_waiting_list"           "customer_type"                 
[28] "adr"                            "required_car_parking_spaces"    "total_of_special_requests"     
[31] "reservation_status"             "reservation_status_date"       
> # 2.2 Dimensiones del dataset
> dim(hotel_booking_demand)
[1] 119390     32
> # 2.3 Estructura
> str(hotel_booking_demand)
'data.frame':	119390 obs. of  32 variables:
 $ hotel                         : chr  "Resort Hotel" "Resort Hotel" "Resort Hotel" "Resort Hotel" ...
 $ is_canceled                   : int  0 0 0 0 0 0 0 0 1 1 ...
 $ lead_time                     : int  342 737 7 13 14 14 0 9 85 75 ...
 $ arrival_date_year             : int  2015 2015 2015 2015 2015 2015 2015 2015 2015 2015 ...
 $ arrival_date_month            : chr  "July" "July" "July" "July" ...
 $ arrival_date_week_number      : int  27 27 27 27 27 27 27 27 27 27 ...
 $ arrival_date_day_of_month     : int  1 1 1 1 1 1 1 1 1 1 ...
 $ stays_in_weekend_nights       : int  0 0 0 0 0 0 0 0 0 0 ...
 $ stays_in_week_nights          : int  0 0 1 1 2 2 2 2 3 3 ...
 $ adults                        : int  2 2 1 1 2 2 2 2 2 2 ...
 $ children                      : int  0 0 0 0 0 0 0 0 0 0 ...
 $ babies                        : int  0 0 0 0 0 0 0 0 0 0 ...
 $ meal                          : chr  "BB" "BB" "BB" "BB" ...
 $ country                       : chr  "PRT" "PRT" "GBR" "GBR" ...
 $ market_segment                : chr  "Direct" "Direct" "Direct" "Corporate" ...
 $ distribution_channel          : chr  "Direct" "Direct" "Direct" "Corporate" ...
 $ is_repeated_guest             : int  0 0 0 0 0 0 0 0 0 0 ...
 $ previous_cancellations        : int  0 0 0 0 0 0 0 0 0 0 ...
 $ previous_bookings_not_canceled: int  0 0 0 0 0 0 0 0 0 0 ...
 $ reserved_room_type            : chr  "C" "C" "A" "A" ...
 $ assigned_room_type            : chr  "C" "C" "C" "A" ...
 $ booking_changes               : int  3 4 0 0 0 0 0 0 0 0 ...
 $ deposit_type                  : chr  "No Deposit" "No Deposit" "No Deposit" "No Deposit" ...
 $ agent                         : chr  "NULL" "NULL" "NULL" "304" ...
 $ company                       : chr  "NULL" "NULL" "NULL" "NULL" ...
 $ days_in_waiting_list          : int  0 0 0 0 0 0 0 0 0 0 ...
 $ customer_type                 : chr  "Transient" "Transient" "Transient" "Transient" ...
 $ adr                           : num  0 0 75 75 98 ...
 $ required_car_parking_spaces   : int  0 0 0 0 0 0 0 0 0 0 ...
 $ total_of_special_requests     : int  0 0 0 0 1 1 0 1 1 0 ...
 $ reservation_status            : chr  "Check-Out" "Check-Out" "Check-Out" "Check-Out" ...
 $ reservation_status_date       : chr  "2015-07-01" "2015-07-01" "2015-07-02" "2015-07-02" ...
> # 2.4 Descripcion general
> summary(hotel_booking_demand)
    hotel            is_canceled       lead_time   arrival_date_year arrival_date_month
 Length:119390      Min.   :0.0000   Min.   :  0   Min.   :2015      Length:119390     
 Class :character   1st Qu.:0.0000   1st Qu.: 18   1st Qu.:2016      Class :character  
 Mode  :character   Median :0.0000   Median : 69   Median :2016      Mode  :character  
                    Mean   :0.3704   Mean   :104   Mean   :2016                        
                    3rd Qu.:1.0000   3rd Qu.:160   3rd Qu.:2017                        
                    Max.   :1.0000   Max.   :737   Max.   :2017                        
                                                                                       
 arrival_date_week_number arrival_date_day_of_month stays_in_weekend_nights stays_in_week_nights
 Min.   : 1.00            Min.   : 1.0              Min.   : 0.0000         Min.   : 0.0        
 1st Qu.:16.00            1st Qu.: 8.0              1st Qu.: 0.0000         1st Qu.: 1.0        
 Median :28.00            Median :16.0              Median : 1.0000         Median : 2.0        
 Mean   :27.17            Mean   :15.8              Mean   : 0.9276         Mean   : 2.5        
 3rd Qu.:38.00            3rd Qu.:23.0              3rd Qu.: 2.0000         3rd Qu.: 3.0        
 Max.   :53.00            Max.   :31.0              Max.   :19.0000         Max.   :50.0        
                                                                                                
     adults          children           babies              meal             country         
 Min.   : 0.000   Min.   : 0.0000   Min.   : 0.000000   Length:119390      Length:119390     
 1st Qu.: 2.000   1st Qu.: 0.0000   1st Qu.: 0.000000   Class :character   Class :character  
 Median : 2.000   Median : 0.0000   Median : 0.000000   Mode  :character   Mode  :character  
 Mean   : 1.856   Mean   : 0.1039   Mean   : 0.007949                                        
 3rd Qu.: 2.000   3rd Qu.: 0.0000   3rd Qu.: 0.000000                                        
 Max.   :55.000   Max.   :10.0000   Max.   :10.000000                                        
                  NA's   :4                                                                  
 market_segment     distribution_channel is_repeated_guest previous_cancellations
 Length:119390      Length:119390        Min.   :0.00000   Min.   : 0.00000      
 Class :character   Class :character     1st Qu.:0.00000   1st Qu.: 0.00000      
 Mode  :character   Mode  :character     Median :0.00000   Median : 0.00000      
                                         Mean   :0.03191   Mean   : 0.08712      
                                         3rd Qu.:0.00000   3rd Qu.: 0.00000      
                                         Max.   :1.00000   Max.   :26.00000      
                                                                                 
 previous_bookings_not_canceled reserved_room_type assigned_room_type booking_changes  
 Min.   : 0.0000                Length:119390      Length:119390      Min.   : 0.0000  
 1st Qu.: 0.0000                Class :character   Class :character   1st Qu.: 0.0000  
 Median : 0.0000                Mode  :character   Mode  :character   Median : 0.0000  
 Mean   : 0.1371                                                      Mean   : 0.2211  
 3rd Qu.: 0.0000                                                      3rd Qu.: 0.0000  
 Max.   :72.0000                                                      Max.   :21.0000  
                                                                                       
 deposit_type          agent             company          days_in_waiting_list customer_type     
 Length:119390      Length:119390      Length:119390      Min.   :  0.000      Length:119390     
 Class :character   Class :character   Class :character   1st Qu.:  0.000      Class :character  
 Mode  :character   Mode  :character   Mode  :character   Median :  0.000      Mode  :character  
                                                          Mean   :  2.321                        
                                                          3rd Qu.:  0.000                        
                                                          Max.   :391.000                        
                                                                                                 
      adr          required_car_parking_spaces total_of_special_requests reservation_status
 Min.   :  -6.38   Min.   :0.00000             Min.   :0.0000            Length:119390     
 1st Qu.:  69.29   1st Qu.:0.00000             1st Qu.:0.0000            Class :character  
 Median :  94.58   Median :0.00000             Median :0.0000            Mode  :character  
 Mean   : 101.83   Mean   :0.06252             Mean   :0.5714                              
 3rd Qu.: 126.00   3rd Qu.:0.00000             3rd Qu.:1.0000                              
 Max.   :5400.00   Max.   :8.00000             Max.   :5.0000                              
                                                                                           
 reservation_status_date
 Length:119390          
 Class :character       
 Mode  :character       
                        
                        
                        
                        
> # 2.5 Identificamos los valores de las columnas
> unique(hotel_booking_demand$hotel)
[1] "Resort Hotel" "City Hotel"  
> unique(hotel_booking_demand$is_canceled)
[1] 0 1
> unique(hotel_booking_demand$lead_time)
  [1] 342 737   7  13  14   0   9  85  75  23  35  68  18  37  12  72 127  78  48  60  77  99 118  95  96
 [26]  69  45  40  15  36  43  70  16 107  47 113  90  50  93  76   3   1  10   5  17  51  71  63  62 101
 [51]   2  81 368 364 324  79  21 109 102   4  98  92  26  73 115  86  52  29  30  33  32   8 100  44  80
 [76]  97  64  39  34  27  82  94 110 111  84  66 104  28 258 112  65  67  55  88  54 292  83 105 280 394
[101]  24 103 366 249  22  91  11 108 106  31  87  41 304 117  59  53  58 116  42 321  38  56  49 317   6
[126]  57  19  25 315 123  46  89  61 312 299 130  74 298 119  20 286 136 129 124 327 131 460 140 114 139
[151] 122 137 126 120 128 135 150 143 151 132 125 157 147 138 156 164 346 159 160 161 333 381 149 154 297
[176] 163 314 155 323 340 356 142 328 144 336 248 302 175 344 382 146 170 166 338 167 310 148 165 172 171
[201] 145 121 178 305 173 152 354 347 158 185 349 183 352 177 200 192 361 207 174 330 134 350 334 283 153
[226] 197 133 241 193 235 194 261 260 216 169 209 238 215 141 189 187 223 284 214 202 211 168 230 203 188
[251] 232 709 219 162 196 190 259 228 176 250 201 186 199 180 206 205 224 222 182 210 275 212 229 218 208
[276] 191 181 179 246 255 226 288 253 252 262 236 256 234 254 468 213 237 198 195 239 263 265 274 217 220
[301] 307 221 233 257 227 276 225 264 311 277 204 290 266 270 294 319 282 251 322 291 269 240 271 184 231
[326] 268 247 273 300 301 267 244 306 293 309 272 242 295 285 243 308 398 303 245 424 279 331 281 339 434
[351] 357 325 329 278 332 343 345 360 348 367 353 373 374 406 400 326 379 399 316 341 320 385 355 363 358
[376] 296 422 390 335 370 376 375 397 289 542 403 383 384 359 393 337 362 365 435 386 378 313 351 287 471
[401] 462 411 450 318 372 371 454 532 445 389 388 407 443 437 451 391 405 412 419 420 426 433 440 429 418
[426] 447 461 605 457 475 464 482 626 489 496 503 510 517 524 531 538 545 552 559 566 573 580 587 594 601
[451] 608 615 622 629 396 410 395 423 408 409 448 465 387 414 476 479 467 490 493 478 504 507 458 518 521
[476] 377 444 380 463
> unique(hotel_booking_demand$arrival_date_year)
[1] 2015 2016 2017
> unique(hotel_booking_demand$arrival_date_month)
 [1] "July"      "August"    "September" "October"   "November"  "December"  "January"   "February" 
 [9] "March"     "April"     "May"       "June"     
> unique(hotel_booking_demand$arrival_date_week_number)
 [1] 27 28 29 30 31 32 33 34 35 36 37 38 39 40 41 42 43 44 45 46 47 48 49 50 51 52 53  1  2  3  4  5  6  7
[35]  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26
> unique(hotel_booking_demand$arrival_date_day_of_month)
 [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31
> unique(hotel_booking_demand$stays_in_weekend_nights)
 [1]  0  1  2  4  3  6 13  8  5  7 12  9 16 18 19 10 14
> unique(hotel_booking_demand$stays_in_week_nights)
 [1]  0  1  2  3  4  5 10 11  8  6  7 15  9 12 33 20 14 16 21 13 30 19 24 40 22 42 50 25 17 32 26 18 34 35
[35] 41
> unique(hotel_booking_demand$adults)
 [1]  2  1  3  4 40 26 50 27 55  0 20  6  5 10
> unique(hotel_booking_demand$children)
[1]  0  1  2 10  3 NA
> unique(hotel_booking_demand$babies)
[1]  0  1  2 10  9
> unique(hotel_booking_demand$meal)
[1] "BB"        "FB"        "HB"        "SC"        "Undefined"
> unique(hotel_booking_demand$country)
  [1] "PRT"  "GBR"  "USA"  "ESP"  "IRL"  "FRA"  "NULL" "ROU"  "NOR"  "OMN"  "ARG"  "POL"  "DEU"  "BEL" 
 [15] "CHE"  "CN"   "GRC"  "ITA"  "NLD"  "DNK"  "RUS"  "SWE"  "AUS"  "EST"  "CZE"  "BRA"  "FIN"  "MOZ" 
 [29] "BWA"  "LUX"  "SVN"  "ALB"  "IND"  "CHN"  "MEX"  "MAR"  "UKR"  "SMR"  "LVA"  "PRI"  "SRB"  "CHL" 
 [43] "AUT"  "BLR"  "LTU"  "TUR"  "ZAF"  "AGO"  "ISR"  "CYM"  "ZMB"  "CPV"  "ZWE"  "DZA"  "KOR"  "CRI" 
 [57] "HUN"  "ARE"  "TUN"  "JAM"  "HRV"  "HKG"  "IRN"  "GEO"  "AND"  "GIB"  "URY"  "JEY"  "CAF"  "CYP" 
 [71] "COL"  "GGY"  "KWT"  "NGA"  "MDV"  "VEN"  "SVK"  "FJI"  "KAZ"  "PAK"  "IDN"  "LBN"  "PHL"  "SEN" 
 [85] "SYC"  "AZE"  "BHR"  "NZL"  "THA"  "DOM"  "MKD"  "MYS"  "ARM"  "JPN"  "LKA"  "CUB"  "CMR"  "BIH" 
 [99] "MUS"  "COM"  "SUR"  "UGA"  "BGR"  "CIV"  "JOR"  "SYR"  "SGP"  "BDI"  "SAU"  "VNM"  "PLW"  "QAT" 
[113] "EGY"  "PER"  "MLT"  "MWI"  "ECU"  "MDG"  "ISL"  "UZB"  "NPL"  "BHS"  "MAC"  "TGO"  "TWN"  "DJI" 
[127] "STP"  "KNA"  "ETH"  "IRQ"  "HND"  "RWA"  "KHM"  "MCO"  "BGD"  "IMN"  "TJK"  "NIC"  "BEN"  "VGB" 
[141] "TZA"  "GAB"  "GHA"  "TMP"  "GLP"  "KEN"  "LIE"  "GNB"  "MNE"  "UMI"  "MYT"  "FRO"  "MMR"  "PAN" 
[155] "BFA"  "LBY"  "MLI"  "NAM"  "BOL"  "PRY"  "BRB"  "ABW"  "AIA"  "SLV"  "DMA"  "PYF"  "GUY"  "LCA" 
[169] "ATA"  "GTM"  "ASM"  "MRT"  "NCL"  "KIR"  "SDN"  "ATF"  "SLE"  "LAO" 
> unique(hotel_booking_demand$market_segment)
[1] "Direct"        "Corporate"     "Online TA"     "Offline TA/TO" "Complementary" "Groups"       
[7] "Undefined"     "Aviation"     
> unique(hotel_booking_demand$distribution_channel)
[1] "Direct"    "Corporate" "TA/TO"     "Undefined" "GDS"      
> unique(hotel_booking_demand$is_repeated_guest)
[1] 0 1
> unique(hotel_booking_demand$previous_cancellations)
 [1]  0  1  2  3 26 25 14  4 24 19  5 21  6 13 11
> unique(hotel_booking_demand$previous_bookings_not_canceled)
 [1]  0  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 20 21 22 23 24 25 27 28 29 30 19 26 31 32 33
[35] 34 35 36 37 38 39 40 41 42 43 44 45 46 47 48 49 50 51 52 53 54 55 56 57 58 59 60 61 62 63 64 65 66 67
[69] 68 69 70 71 72
> unique(hotel_booking_demand$reserved_room_type)
 [1] "C" "A" "D" "E" "G" "F" "H" "L" "P" "B"
> unique(hotel_booking_demand$assigned_room_type)
 [1] "C" "A" "D" "E" "G" "F" "I" "B" "H" "P" "L" "K"
> unique(hotel_booking_demand$booking_changes)
 [1]  3  4  0  1  2  5 17  6  8  7 10 16  9 13 12 20 14 15 11 21 18
> unique(hotel_booking_demand$deposit_type)
[1] "No Deposit" "Refundable" "Non Refund"
> unique(hotel_booking_demand$agent)
  [1] "NULL" "304"  "240"  "303"  "15"   "241"  "8"    "250"  "115"  "5"    "175"  "134"  "156"  "243" 
 [15] "242"  "3"    "105"  "40"   "147"  "306"  "184"  "96"   "2"    "127"  "95"   "146"  "9"    "177" 
 [29] "6"    "143"  "244"  "149"  "167"  "300"  "171"  "305"  "67"   "196"  "152"  "142"  "261"  "104" 
 [43] "36"   "26"   "29"   "258"  "110"  "71"   "181"  "88"   "251"  "275"  "69"   "248"  "208"  "256" 
 [57] "314"  "126"  "281"  "273"  "253"  "185"  "330"  "334"  "328"  "326"  "321"  "324"  "313"  "38"  
 [71] "155"  "68"   "335"  "308"  "332"  "94"   "348"  "310"  "339"  "375"  "66"   "327"  "387"  "298" 
 [85] "91"   "245"  "385"  "257"  "393"  "168"  "405"  "249"  "315"  "75"   "128"  "307"  "11"   "436" 
 [99] "1"    "201"  "183"  "223"  "368"  "336"  "291"  "464"  "411"  "481"  "10"   "154"  "468"  "410" 
[113] "390"  "440"  "495"  "492"  "493"  "434"  "57"   "531"  "420"  "483"  "526"  "472"  "429"  "16"  
[127] "446"  "34"   "78"   "139"  "252"  "270"  "47"   "114"  "301"  "193"  "182"  "135"  "350"  "195" 
[141] "352"  "355"  "159"  "363"  "384"  "360"  "331"  "367"  "64"   "406"  "163"  "414"  "333"  "427" 
[155] "431"  "430"  "426"  "438"  "433"  "418"  "441"  "282"  "432"  "72"   "450"  "180"  "454"  "455" 
[169] "59"   "451"  "254"  "358"  "469"  "165"  "467"  "510"  "337"  "476"  "502"  "527"  "479"  "508" 
[183] "535"  "302"  "497"  "187"  "13"   "7"    "27"   "14"   "22"   "17"   "28"   "42"   "20"   "19"  
[197] "45"   "37"   "61"   "39"   "21"   "24"   "41"   "50"   "30"   "54"   "52"   "12"   "44"   "31"  
[211] "83"   "32"   "63"   "60"   "55"   "56"   "89"   "87"   "118"  "86"   "85"   "210"  "214"  "129" 
[225] "179"  "138"  "174"  "170"  "153"  "93"   "151"  "119"  "35"   "173"  "58"   "53"   "133"  "79"  
[239] "235"  "192"  "191"  "236"  "162"  "215"  "157"  "287"  "132"  "234"  "98"   "77"   "103"  "107" 
[253] "262"  "220"  "121"  "205"  "378"  "23"   "296"  "290"  "229"  "33"   "286"  "276"  "425"  "484" 
[267] "323"  "403"  "219"  "394"  "509"  "111"  "423"  "4"    "70"   "82"   "81"   "74"   "92"   "99"  
[281] "90"   "112"  "117"  "106"  "148"  "158"  "144"  "211"  "213"  "216"  "232"  "150"  "267"  "227" 
[295] "247"  "278"  "280"  "285"  "289"  "269"  "295"  "265"  "288"  "122"  "294"  "325"  "341"  "344" 
[309] "346"  "359"  "283"  "364"  "370"  "371"  "25"   "141"  "391"  "397"  "416"  "404"  "299"  "197" 
[323] "73"   "354"  "444"  "408"  "461"  "388"  "453"  "459"  "474"  "475"  "480"  "449" 
> unique(hotel_booking_demand$company)
  [1] "NULL" "110"  "113"  "270"  "178"  "240"  "154"  "144"  "307"  "268"  "59"   "204"  "312"  "318" 
 [15] "94"   "174"  "274"  "195"  "223"  "317"  "281"  "118"  "53"   "286"  "12"   "47"   "324"  "342" 
 [29] "373"  "371"  "383"  "86"   "82"   "218"  "88"   "31"   "397"  "392"  "405"  "331"  "367"  "20"  
 [43] "83"   "416"  "51"   "395"  "102"  "34"   "84"   "360"  "394"  "457"  "382"  "461"  "478"  "386" 
 [57] "112"  "486"  "421"  "9"    "308"  "135"  "224"  "504"  "269"  "356"  "498"  "390"  "513"  "203" 
 [71] "263"  "477"  "521"  "169"  "515"  "445"  "337"  "251"  "428"  "292"  "388"  "130"  "250"  "355" 
 [85] "254"  "543"  "531"  "528"  "62"   "120"  "42"   "81"   "116"  "530"  "103"  "39"   "16"   "92"  
 [99] "61"   "501"  "165"  "291"  "290"  "43"   "325"  "192"  "108"  "200"  "465"  "287"  "297"  "490" 
[113] "482"  "207"  "282"  "437"  "225"  "329"  "272"  "28"   "77"   "338"  "72"   "246"  "319"  "146" 
[127] "159"  "380"  "323"  "511"  "407"  "278"  "80"   "403"  "399"  "14"   "137"  "343"  "346"  "347" 
[141] "349"  "289"  "351"  "353"  "54"   "99"   "358"  "361"  "362"  "366"  "372"  "365"  "277"  "109" 
[155] "377"  "379"  "22"   "378"  "330"  "364"  "401"  "232"  "255"  "384"  "167"  "212"  "514"  "391" 
[169] "400"  "376"  "402"  "396"  "302"  "398"  "6"    "370"  "369"  "409"  "168"  "104"  "408"  "413" 
[183] "148"  "10"   "333"  "419"  "415"  "424"  "425"  "423"  "422"  "435"  "439"  "442"  "448"  "443" 
[197] "454"  "444"  "52"   "459"  "458"  "456"  "460"  "447"  "470"  "466"  "484"  "184"  "485"  "32"  
[211] "487"  "491"  "494"  "193"  "516"  "496"  "499"  "29"   "78"   "520"  "507"  "506"  "512"  "126" 
[225] "64"   "242"  "518"  "523"  "539"  "534"  "436"  "525"  "541"  "40"   "455"  "410"  "45"   "38"  
[239] "49"   "48"   "67"   "68"   "65"   "91"   "37"   "8"    "179"  "209"  "219"  "221"  "227"  "153" 
[253] "186"  "253"  "202"  "216"  "275"  "233"  "280"  "309"  "321"  "93"   "316"  "85"   "107"  "350" 
[267] "279"  "334"  "348"  "150"  "73"   "385"  "418"  "197"  "450"  "452"  "115"  "46"   "76"   "96"  
[281] "100"  "105"  "101"  "122"  "11"   "139"  "142"  "127"  "143"  "140"  "149"  "163"  "160"  "180" 
[295] "238"  "183"  "222"  "185"  "217"  "215"  "213"  "237"  "230"  "234"  "35"   "245"  "158"  "258" 
[309] "259"  "260"  "411"  "257"  "271"  "18"   "106"  "210"  "273"  "71"   "284"  "301"  "305"  "293" 
[323] "264"  "311"  "304"  "313"  "288"  "320"  "314"  "332"  "341"  "352"  "243"  "368"  "393"  "132" 
[337] "220"  "412"  "420"  "426"  "417"  "429"  "433"  "446"  "357"  "479"  "483"  "489"  "229"  "481" 
[351] "497"  "451"  "492" 
> unique(hotel_booking_demand$customer_type)
[1] "Transient"       "Contract"        "Transient-Party" "Group"          
> unique(hotel_booking_demand$adr)
   [1]   0.00  75.00  98.00 107.00 103.00  82.00 105.50 123.00 145.00  97.00 154.77  94.71  97.50  88.20
  [15] 107.42 153.00  97.29  84.67  99.67  94.95  63.60  79.50  94.00  87.30  62.00  63.86 108.30  65.50
  [29] 108.80 137.00 117.81 110.70  58.95  82.88  82.35 119.35  67.58  56.01 147.00 117.90 135.00 133.00
  [43] 136.33 110.50 110.30  73.80  91.50 114.50  90.90 122.00  85.86  55.68 124.00 111.15 134.73  92.45
  [57] 108.73 131.00 117.00 196.54  99.30  90.95  92.67  71.55  96.49  85.80  96.30 163.00 172.00 139.00
  [71]  67.24 116.50 149.00 105.00 113.00  85.10  89.00  80.10 101.00 167.00 225.00  85.59 164.20 114.00
  [85]  98.40 175.00 124.45  74.07 134.10 171.32 210.00 117.80 117.63 185.00  71.00  47.25 151.00 120.60
  [99] 157.10  91.37  73.00  93.60  83.50 185.50 109.80 195.00 193.00 150.00 126.65 146.00  61.00 104.72
 [113]  66.42  77.96 112.00  89.68 155.00 130.10 100.10 105.08  65.42  75.46 119.25 118.13 120.00 197.00
 [127] 165.00 149.40 106.84 161.00 134.43 144.43 152.00 125.54 133.83 159.75 112.20 110.60 105.90  95.27
 [141] 108.83 153.96  90.67 126.67 144.40  99.50 139.40  89.97 144.90 100.00 104.68 166.00 111.25 213.75
 [155] 178.00 113.90 129.29 169.00  93.00 132.29 117.22 164.57 105.71 126.00 148.30 125.22 130.00 133.16
 [169]  78.84  90.71 120.20 128.00 130.05 103.80 196.00 175.71 119.70 100.86  64.00 110.00 132.80 144.20
 [183] 107.20 163.80  98.50 130.50 184.60 181.22 100.20 134.25  83.09 134.00   8.00 136.20 101.80 127.00
 [197] 161.50 230.67  65.70 180.00 168.57 107.67  96.90  73.41 109.90 187.50 132.44 106.90 131.86 216.13
 [211] 190.33  98.75 148.23 123.20 198.00 103.50 135.60 184.00 151.33 121.33 150.20  75.44 160.00 127.25
 [225] 164.00 144.50 155.50 107.60 133.75  84.80 125.00 132.30  92.00 194.90 118.50 192.00 128.27 126.30
 [239] 154.00 136.00 116.33 147.67 168.30 137.75 132.60 157.00 132.50  98.02 173.00 249.00 186.50  95.00
 [253] 241.50 177.00 153.73 115.00 127.03 128.25 124.50 154.50 110.53 158.50 131.37 117.71 117.84 116.85
 [267] 129.16 214.00 135.20 179.10 111.65 104.00 133.17 141.33 121.01 240.64 167.50 152.43 148.34 172.93
 [281] 192.50 111.20 141.60 200.00 207.00 163.33 151.86  95.57 112.05 103.18 119.75 167.69 178.40 194.00
 [295] 101.46 217.05 112.50 233.00 222.67 149.70 161.25 159.20 163.29 121.98 118.00 158.77 142.03 240.00
 [309] 176.00 131.63 233.05  90.12 114.25  88.55  95.02 209.00 174.01 124.20 162.00 133.20 167.20 183.45
 [323] 159.60 219.43 102.72 114.85 138.80 115.50 108.54 165.40 188.00 186.00 141.65  99.24 108.06 148.63
 [337] 250.33 146.67 280.74 137.80 125.89 126.71 154.80 219.50 111.92  57.60 157.80 170.33 118.06 202.00
 [351] 252.00 211.00 237.00 188.29 177.14 222.14 127.82 194.14 144.53 193.13 210.78 174.70 135.53 144.00
 [365] 162.50 209.60 195.50 163.50 180.28 174.76 159.00 104.55 144.76 205.00 220.55 162.14  77.54 221.00
 [379] 230.50 241.00 187.80 171.90 148.25 183.00 242.60 168.71 268.00 149.20 217.20 239.30 181.50 181.90
 [393] 267.00 226.00 191.00 277.50 133.50 154.38 121.39 250.00 208.00 181.00 157.59 211.75 246.00 200.71
 [407] 276.43 228.00 138.00 165.69 127.31 211.50 210.33 145.40 101.25 179.38 277.00 106.40 254.00 147.60
 [421] 129.00 147.07 164.65 190.00 185.57 162.30 274.93 156.73 200.70 142.26 129.41 157.08 258.33 133.21
 [435] 173.50 184.45 158.00 114.14 168.80 178.33 255.00  87.91 187.20 243.00 222.20 178.20 203.00 266.40
 [449] 236.00 271.00 232.00 223.00 178.67 167.25 195.80 229.00 266.00 262.00 182.50 234.00 242.50 158.40
 [463] 131.20 248.00 209.20 299.33 156.45 145.75 198.71 218.00 101.65 188.71 181.94 150.53 223.99 175.79
 [477] 165.11 209.40 225.90 131.10 187.00  87.90 213.00 172.55 179.00 229.67 121.50 176.64 179.86 239.50
 [491] 186.25 220.40 163.23 222.07 176.80 163.35 213.50 176.75 123.04 260.71 222.00 174.71 118.70 129.55
 [505] 179.83 160.43 146.30 161.26 195.45 162.29 221.43 177.57 218.50 151.89 151.95 191.67 201.00 259.00
 [519] 164.40 199.00 155.77 131.70 206.00 201.50 138.79 113.47 231.60 261.40 199.40 150.83 129.27 133.76
 [533] 197.70 219.33 200.80 130.20 189.67 186.13 158.38 206.60 137.70 129.15 192.20 202.77 111.27 157.67
 [547] 112.34 172.60 120.27 118.29  75.53  90.39 155.86 120.38 180.55 127.67 114.13 113.70 166.50 101.16
 [561] 130.60 109.83 141.67  98.63 166.14 150.71  97.74 189.86 123.11 104.80 142.50  77.50 140.40 173.25
 [575] 122.86 130.90 129.33 115.20  71.72 106.80  71.69 112.33 113.43 161.29 167.86 103.07  92.86  80.55
 [589] 120.33 130.33  96.33 117.83 122.60 101.44 120.50 126.29  87.75 113.55 134.67 137.67 111.00 119.00
 [603] 109.00  93.12 101.03 120.71  82.72 110.71 114.19  86.95 154.25  57.00 131.40  90.40  80.00 109.50
 [617]  91.46  62.48 124.10 143.00 116.80 151.25 168.00 151.88 143.50 171.00 156.00 139.50 154.14 107.50
 [631] 124.80 111.50  83.70  91.77 208.14 103.85  66.15  99.80 111.96 139.18  83.15  77.60  64.29 117.29
 [645]  75.96  84.47 101.53  97.54  76.50  68.50  86.69 124.40  77.70  59.00 115.40 108.00  87.05  70.98
 [659]  82.44  57.54 120.43 106.25  70.48  85.00  48.88  73.50 101.50 118.20  50.15 112.42 138.50  57.50
 [673]  77.11  97.99  51.75 141.50  36.00  59.13  66.60  58.05  95.86  68.45 131.14  72.25  53.10 127.75
 [687] 110.75  91.00 122.75 138.60  70.20  93.21  58.50 132.00 212.83 120.08  77.20 160.80  76.67 100.50
 [701] 103.51  68.40  55.79  99.00 122.14  90.14  68.88  74.53  71.66  74.00  79.00  65.00  55.00  86.00
 [715]  83.00  77.75 150.25  85.50  71.20  81.50 106.20  84.71  59.20 109.71  90.43  80.63  45.90  81.60
 [729]  81.20  87.33  75.10  69.83 102.93  65.10  96.26 124.74 138.29 125.71 116.00  95.40 100.93  74.93
 [743]  58.98  58.93 103.22  42.50  55.64  26.00  90.00  72.00  59.02  89.14  53.69 114.48  73.98  65.64
 [757]  75.43  77.73 140.63 108.65  75.65 108.85  56.98  74.80  87.86  75.50  97.20  76.30  74.70  55.43
 [771]  48.54  83.80  43.93 108.50 136.50  96.50  89.06  72.14  90.49  53.68  80.08  73.35  82.80 128.42
 [785]  55.09  93.86  69.13  88.40  94.50  78.60  85.08  93.43  36.13  66.29  90.74  38.25 106.31  74.20
 [799]  93.20  83.67  42.23  68.53  86.10  63.14  74.60  60.50  69.50  55.44  44.50 108.09  68.00  78.10
 [813]  70.50  66.80  39.24  48.78  54.40  56.59  59.03 148.12  81.45  81.75  48.80 106.00  90.10  55.50
 [827]  55.80  67.50  13.00  64.33  79.83 100.33  71.93  52.73  58.57  48.00  62.43  44.27  87.00  48.30
 [841]  56.00  66.00  74.40  74.23  77.00  69.93  57.43  36.74  63.08  47.00  50.40  76.00  78.00  59.40
 [855]  60.90  67.25  63.90  36.05  42.30  67.00  58.00  38.07  40.07  59.29  74.14  40.96  44.80  47.33
 [869]  83.05  87.43  68.16 136.71  51.30  92.60  63.66  68.43  60.40  78.20  41.25  40.05 107.43  57.67
 [883]  63.47  60.30  61.50  88.00  56.95  54.50  54.72  83.60  65.45  71.67  37.00  52.20  43.12  62.80
 [897]  96.67  43.30  66.30  49.01  41.60  48.74  68.86  40.00  73.67  50.00  73.66  45.00  41.37  53.37
 [911]  48.57  77.43 123.56  62.47  42.00 104.67 113.33  72.80  54.02  63.33  83.33  78.80  55.73  71.50
 [925]  70.40  73.68  76.35  49.20 102.50  61.35   4.00  79.22  46.50  37.60  56.40  56.52  58.24  69.85
 [939]  92.71  53.00  61.28  74.28  73.38  64.50  43.00  33.30  70.00  57.83  68.57  54.77  45.56  50.05
 [953]  86.50  67.92  55.14  81.34  40.50  39.00  40.23  76.80  58.40  79.63  37.56  36.90  67.56  67.15
 [967]  88.67  60.00  34.65  41.98  45.55  66.43 112.29  61.60  81.00  70.31  38.92 119.43  52.51  49.80
 [981]  96.00  54.00  42.05  52.00  34.56  63.82  48.60  43.20  72.50  77.40  63.76  69.76  65.19  35.10
 [995]  41.10  56.02  41.45  47.45  47.12  45.66
 [ reached getOption("max.print") -- omitted 7879 entries ]
> unique(hotel_booking_demand$required_car_parking_spaces)
[1] 0 1 2 8 3
> unique(hotel_booking_demand$total_of_special_requests)
[1] 0 1 3 2 4 5
> unique(hotel_booking_demand$reservation_status)
[1] "Check-Out" "Canceled"  "No-Show"  
> unique(hotel_booking_demand$reservation_status_date)
  [1] "2015-07-01" "2015-07-02" "2015-07-03" "2015-05-06" "2015-04-22" "2015-06-23" "2015-07-05"
  [8] "2015-07-06" "2015-07-07" "2015-07-08" "2015-05-11" "2015-07-15" "2015-07-16" "2015-05-29"
 [15] "2015-05-19" "2015-06-19" "2015-05-23" "2015-05-18" "2015-07-09" "2015-06-02" "2015-07-13"
 [22] "2015-07-04" "2015-06-29" "2015-06-16" "2015-06-18" "2015-06-12" "2015-06-09" "2015-05-26"
 [29] "2015-07-11" "2015-07-12" "2015-07-17" "2015-04-15" "2015-05-13" "2015-07-10" "2015-05-20"
 [36] "2015-05-12" "2015-07-14" "2015-06-17" "2015-05-01" "2015-03-30" "2015-07-19" "2015-06-03"
 [43] "2015-06-26" "2015-05-14" "2015-07-20" "2015-05-07" "2015-05-28" "2015-04-13" "2015-03-25"
 [50] "2015-07-21" "2015-06-27" "2015-07-18" "2015-07-23" "2015-06-08" "2015-06-22" "2015-06-24"
 [57] "2015-03-05" "2015-06-01" "2015-04-24" "2015-07-22" "2015-05-27" "2015-04-06" "2015-04-11"
 [64] "2015-07-25" "2015-07-28" "2015-07-29" "2015-06-25" "2015-07-24" "2015-06-05" "2015-06-30"
 [71] "2015-06-13" "2015-06-11" "2015-07-30" "2015-07-27" "2015-04-29" "2015-06-04" "2015-07-26"
 [78] "2015-08-01" "2015-08-02" "2015-06-15" "2015-04-23" "2015-07-31" "2015-05-25" "2015-08-03"
 [85] "2015-04-17" "2015-08-04" "2015-08-06" "2015-05-15" "2015-05-09" "2015-03-17" "2015-05-22"
 [92] "2015-08-07" "2015-04-04" "2015-08-05" "2015-08-08" "2015-08-10" "2015-05-04" "2015-06-06"
 [99] "2015-08-09" "2015-08-15" "2015-08-11" "2015-03-28" "2015-08-14" "2015-08-12" "2015-08-16"
[106] "2015-05-16" "2015-08-21" "2015-08-13" "2015-08-17" "2015-04-20" "2015-08-18" "2015-08-23"
[113] "2015-08-22" "2015-08-19" "2015-08-20" "2015-08-29" "2015-03-31" "2015-05-30" "2015-08-25"
[120] "2015-04-14" "2015-08-24" "2015-03-24" "2015-05-21" "2015-08-28" "2015-08-26" "2015-08-27"
[127] "2015-08-30" "2015-08-31" "2015-09-06" "2015-09-03" "2015-09-04" "2015-09-02" "2015-09-01"
[134] "2015-09-05" "2015-06-20" "2015-09-07" "2015-09-10" "2015-09-11" "2015-09-08" "2015-09-09"
[141] "2015-09-13" "2015-09-15" "2015-04-10" "2015-01-02" "2014-11-18" "2015-09-12" "2015-09-17"
[148] "2015-09-14" "2015-04-07" "2015-09-19" "2015-09-16" "2015-09-20" "2015-01-18" "2015-10-23"
[155] "2015-01-22" "2015-01-01" "2015-09-22" "2015-09-24" "2015-09-18" "2015-09-21" "2015-09-30"
[162] "2015-09-25" "2015-09-27" "2015-09-28" "2015-10-12" "2015-09-29" "2015-09-23" "2015-10-01"
[169] "2015-09-26" "2015-04-18" "2015-10-02" "2015-10-04" "2015-10-08" "2015-10-03" "2015-10-07"
[176] "2015-10-09" "2015-10-11" "2015-10-05" "2015-10-06" "2015-10-10" "2015-10-14" "2015-10-15"
[183] "2015-10-18" "2015-10-13" "2015-10-20" "2015-10-19" "2015-10-31" "2015-10-16" "2015-10-21"
[190] "2015-10-22" "2015-10-17" "2015-10-24" "2015-10-25" "2015-10-28" "2015-10-27" "2015-10-26"
[197] "2015-10-30" "2015-11-05" "2015-10-29" "2015-11-03" "2015-11-07" "2015-11-04" "2015-11-01"
[204] "2015-11-02" "2015-11-17" "2015-11-06" "2015-11-10" "2015-11-08" "2015-11-09" "2015-11-15"
[211] "2015-11-16" "2015-11-11" "2015-11-12" "2015-11-14" "2015-11-13" "2015-11-18" "2015-11-22"
[218] "2015-11-19" "2015-11-21" "2015-11-20" "2015-11-24" "2015-11-25" "2015-11-23" "2015-11-28"
[225] "2015-11-26" "2015-11-27" "2015-11-29" "2015-12-04" "2015-12-01" "2015-12-06" "2015-12-08"
[232] "2015-12-02" "2015-12-03" "2015-12-31" "2015-12-05" "2015-12-10" "2015-12-17" "2015-11-30"
[239] "2015-12-12" "2015-12-07" "2016-01-05" "2015-12-11" "2015-12-13" "2015-12-15" "2015-12-16"
[246] "2015-12-19" "2015-12-18" "2015-12-26" "2015-12-27" "2015-12-22" "2015-12-23" "2015-12-24"
[253] "2015-12-29" "2015-12-28" "2015-12-20" "2015-12-30" "2016-01-02" "2016-01-01" "2015-12-25"
[260] "2016-01-03" "2016-01-04" "2016-01-11" "2016-01-07" "2015-12-21" "2016-01-09" "2016-01-10"
[267] "2016-01-08" "2016-01-06" "2016-01-12" "2016-01-13" "2016-01-23" "2016-02-09" "2016-01-15"
[274] "2016-01-16" "2016-01-17" "2016-01-19" "2016-01-18" "2016-01-21" "2016-01-24" "2016-01-22"
[281] "2016-01-29" "2016-01-27" "2016-01-25" "2016-03-08" "2016-01-26" "2016-01-20" "2016-01-30"
[288] "2016-02-01" "2016-02-02" "2016-02-08" "2016-02-07" "2016-01-28" "2016-02-05" "2016-02-03"
[295] "2016-02-13" "2016-02-10" "2016-02-04" "2016-02-12" "2016-02-11" "2016-02-16" "2016-02-14"
[302] "2016-02-15" "2016-02-20" "2016-02-06" "2016-01-14" "2016-02-17" "2016-02-21" "2016-02-24"
[309] "2016-02-25" "2016-02-19" "2016-02-18" "2016-02-26" "2016-02-23" "2016-03-05" "2016-02-22"
[316] "2016-02-27" "2016-03-03" "2016-03-24" "2016-03-04" "2016-02-29" "2016-03-01" "2016-03-02"
[323] "2016-03-30" "2016-03-07" "2016-03-14" "2016-03-21" "2016-03-09" "2016-03-12" "2016-03-22"
[330] "2016-03-10" "2016-03-11" "2016-03-20" "2016-03-15" "2016-03-17" "2016-03-16" "2016-03-19"
[337] "2016-03-27" "2016-03-18" "2016-03-26" "2016-03-31" "2016-03-28" "2016-03-29" "2016-04-01"
[344] "2016-03-23" "2016-04-02" "2016-03-25" "2016-03-13" "2016-04-04" "2016-04-03" "2016-04-05"
[351] "2016-04-08" "2016-04-06" "2016-04-09" "2016-04-12" "2016-04-16" "2016-04-17" "2016-04-27"
[358] "2016-04-14" "2016-04-18" "2016-04-21" "2016-04-19" "2016-04-20" "2016-04-10" "2016-04-13"
[365] "2016-04-11" "2016-04-07" "2016-04-15" "2016-04-22" "2016-04-23" "2016-04-26" "2016-04-28"
[372] "2016-04-24" "2016-04-25" "2016-04-29" "2016-04-30" "2016-05-01" "2016-05-10" "2016-05-02"
[379] "2016-05-07" "2016-05-08" "2016-05-12" "2016-05-04" "2016-05-06" "2016-05-03" "2016-05-09"
[386] "2016-05-05" "2016-05-13" "2016-05-14" "2016-05-18" "2016-05-19" "2016-05-15" "2016-05-16"
[393] "2016-05-11" "2016-05-21" "2016-05-22" "2016-05-20" "2016-05-24" "2016-05-25" "2016-05-26"
[400] "2016-05-23" "2016-05-27" "2016-05-17" "2016-05-29" "2016-05-28" "2016-05-30" "2016-05-31"
[407] "2016-06-01" "2016-06-03" "2016-06-08" "2016-06-02" "2016-06-05" "2016-06-06" "2016-06-13"
[414] "2016-06-07" "2016-06-10" "2016-06-11" "2016-06-16" "2016-06-12" "2016-06-14" "2016-06-17"
[421] "2016-06-04" "2016-06-18" "2016-06-21" "2016-06-09" "2016-06-24" "2016-06-20" "2016-06-25"
[428] "2016-06-22" "2016-06-26" "2016-06-23" "2016-07-01" "2016-06-15" "2016-06-28" "2016-07-02"
[435] "2016-06-19" "2016-06-27" "2016-07-04" "2016-06-30" "2016-07-05" "2016-07-08" "2016-07-09"
[442] "2016-07-07" "2016-07-12" "2016-06-29" "2016-07-10" "2016-07-15" "2016-07-03" "2016-07-16"
[449] "2016-07-14" "2016-07-18" "2016-07-13" "2016-07-06" "2016-07-20" "2016-07-21" "2016-07-23"
[456] "2016-07-19" "2016-07-11" "2016-07-28" "2016-07-17" "2016-07-25" "2016-07-22" "2016-07-29"
[463] "2016-08-03" "2016-08-02" "2016-08-04" "2016-08-08" "2016-08-10" "2016-08-01" "2016-08-06"
[470] "2016-03-06" "2016-08-05" "2016-07-26" "2016-08-07" "2016-07-30" "2016-07-24" "2016-08-12"
[477] "2016-07-27" "2016-08-13" "2016-08-18" "2016-08-16" "2016-08-15" "2016-08-17" "2016-08-11"
[484] "2016-07-31" "2016-08-19" "2016-09-01" "2016-08-23" "2016-08-26" "2016-08-20" "2016-08-21"
[491] "2016-09-04" "2016-08-22" "2016-08-27" "2016-08-25" "2016-08-09" "2016-09-05" "2016-08-24"
[498] "2016-09-10" "2016-08-29" "2016-09-09" "2016-08-30" "2016-09-13" "2016-08-31" "2016-09-14"
[505] "2016-09-12" "2016-09-15" "2016-08-14" "2016-09-02" "2016-09-08" "2016-09-19" "2016-09-16"
[512] "2016-09-07" "2016-09-21" "2016-09-06" "2016-09-22" "2016-09-17" "2016-09-20" "2016-09-03"
[519] "2016-09-26" "2016-09-23" "2016-09-18" "2016-09-29" "2016-10-02" "2016-10-01" "2016-09-27"
[526] "2016-09-25" "2016-10-05" "2016-09-11" "2016-09-30" "2016-10-09" "2016-10-03" "2016-10-06"
[533] "2016-10-11" "2016-09-24" "2016-10-13" "2016-09-28" "2016-10-08" "2016-10-07" "2016-10-16"
[540] "2016-08-28" "2016-10-17" "2016-10-18" "2016-10-10" "2016-10-04" "2016-10-15" "2016-10-19"
[547] "2016-10-21" "2016-10-12" "2016-10-24" "2016-10-26" "2016-10-23" "2016-10-20" "2016-10-25"
[554] "2016-10-27" "2016-10-28" "2016-10-30" "2016-10-29" "2016-11-01" "2016-11-04" "2016-10-14"
[561] "2016-11-07" "2016-11-03" "2016-11-10" "2016-11-14" "2016-11-02" "2016-10-31" "2016-11-11"
[568] "2016-11-08" "2016-11-05" "2016-11-25" "2016-11-09" "2016-11-20" "2016-11-21" "2016-10-22"
[575] "2016-11-22" "2016-11-16" "2016-11-23" "2016-11-17" "2016-11-06" "2016-11-15" "2016-11-13"
[582] "2016-11-12" "2016-11-27" "2016-11-19" "2016-11-30" "2016-11-18" "2016-12-02" "2016-12-04"
[589] "2016-11-29" "2016-12-07" "2016-11-28" "2016-12-03" "2016-12-06" "2016-11-24" "2016-12-08"
[596] "2016-12-05" "2016-12-10" "2016-12-13" "2016-12-14" "2016-12-16" "2016-12-15" "2016-12-17"
[603] "2016-12-19" "2016-12-21" "2016-12-20" "2016-12-22" "2016-12-23" "2016-12-24" "2016-12-01"
[610] "2016-12-27" "2016-12-29" "2016-12-30" "2016-12-12" "2017-01-02" "2016-12-11" "2017-01-03"
[617] "2017-01-04" "2017-01-01" "2016-12-26" "2017-01-06" "2016-12-28" "2016-12-18" "2017-01-10"
[624] "2017-01-11" "2017-01-07" "2017-01-12" "2017-01-16" "2017-01-14" "2017-01-13" "2017-01-05"
[631] "2017-01-17" "2017-01-20" "2016-12-09" "2017-01-26" "2016-12-31" "2017-01-23" "2017-01-27"
[638] "2017-01-28" "2017-01-19" "2017-01-25" "2017-01-24" "2017-01-29" "2017-01-18" "2016-12-25"
[645] "2017-01-15" "2017-01-21" "2017-02-01" "2017-02-02" "2017-01-31" "2017-02-03" "2017-02-04"
[652] "2017-02-06" "2017-02-07" "2017-02-08" "2017-01-30" "2017-02-09" "2017-01-09" "2017-02-11"
[659] "2017-02-10" "2017-02-12" "2017-02-13" "2017-02-14" "2017-02-16" "2017-02-17" "2017-02-18"
[666] "2017-02-19" "2017-02-20" "2017-02-15" "2017-02-21" "2017-02-22" "2017-02-26" "2017-02-23"
[673] "2017-02-24" "2017-02-25" "2017-02-28" "2017-03-05" "2017-02-27" "2017-03-03" "2017-03-06"
[680] "2017-03-02" "2017-03-08" "2017-03-09" "2017-03-10" "2017-03-07" "2017-03-12" "2017-03-13"
[687] "2017-03-14" "2017-03-01" "2017-03-18" "2017-03-17" "2017-03-24" "2017-03-22" "2017-03-26"
[694] "2017-03-27" "2017-03-11" "2017-03-28" "2017-03-29" "2017-03-30" "2017-03-31" "2017-03-19"
[701] "2017-01-22" "2017-04-02" "2017-03-20" "2017-04-03" "2017-01-08" "2017-03-23" "2017-04-05"
[708] "2017-02-05" "2017-04-04" "2017-03-15" "2017-04-07" "2017-03-25" "2017-04-08" "2017-04-06"
[715] "2017-03-21" "2017-04-10" "2017-04-01" "2017-04-11" "2017-04-13" "2017-04-15" "2017-04-12"
[722] "2017-03-04" "2017-04-19" "2017-04-22" "2017-04-20" "2017-05-02" "2017-04-09" "2017-04-23"
[729] "2017-04-24" "2017-04-16" "2017-04-28" "2017-04-18" "2017-04-26" "2017-04-25" "2017-04-17"
[736] "2017-04-21" "2017-05-03" "2017-05-04" "2017-03-16" "2017-05-05" "2017-04-29" "2017-04-14"
[743] "2017-05-08" "2017-04-27" "2017-05-11" "2017-05-01" "2017-05-10" "2017-05-13" "2017-05-06"
[750] "2017-05-14" "2017-05-16" "2017-04-30" "2017-05-15" "2017-05-07" "2017-05-09" "2017-05-17"
[757] "2017-05-21" "2017-05-12" "2017-05-22" "2017-05-24" "2017-05-23" "2017-05-25" "2017-05-26"
[764] "2017-05-28" "2017-05-27" "2017-05-29" "2017-05-19" "2017-05-31" "2017-05-20" "2017-06-01"
[771] "2017-05-30" "2017-06-02" "2016-11-26" "2017-06-04" "2017-06-05" "2017-06-06" "2017-06-07"
[778] "2017-05-18" "2017-06-09" "2017-06-10" "2017-06-11" "2017-06-12" "2017-06-14" "2017-06-08"
[785] "2017-06-16" "2017-06-13" "2017-06-03" "2017-06-24" "2017-06-20" "2017-06-19" "2017-06-21"
[792] "2017-06-26" "2017-06-27" "2017-06-22" "2017-06-28" "2017-06-15" "2017-06-29" "2017-06-30"
[799] "2017-06-18" "2017-07-04" "2017-07-08" "2017-07-05" "2017-07-03" "2017-07-07" "2017-07-01"
[806] "2017-07-06" "2017-07-11" "2017-07-12" "2017-06-23" "2017-07-13" "2017-07-02" "2017-07-10"
[813] "2017-07-14" "2017-07-15" "2017-07-16" "2017-07-18" "2017-07-17" "2017-07-19" "2017-07-20"
[820] "2017-07-21" "2017-06-25" "2017-06-17" "2017-07-24" "2017-07-26" "2017-07-09" "2017-07-27"
[827] "2017-07-28" "2017-07-31" "2017-07-29" "2017-07-22" "2017-08-02" "2017-08-01" "2017-08-03"
[834] "2017-08-04" "2017-07-25" "2017-07-23" "2017-08-09" "2017-08-10" "2017-07-30" "2017-08-07"
[841] "2017-08-13" "2017-08-05" "2017-08-14" "2017-08-08" "2017-08-16" "2017-08-17" "2017-08-15"
[848] "2017-08-18" "2017-08-20" "2017-08-22" "2017-08-06" "2017-08-25" "2017-08-26" "2017-08-23"
[855] "2017-08-11" "2017-08-27" "2017-08-21" "2017-08-29" "2017-08-31" "2017-08-12" "2017-08-19"
[862] "2016-01-31" "2017-09-01" "2017-08-28" "2015-04-03" "2015-01-21" "2015-01-28" "2015-01-29"
[869] "2015-01-30" "2015-02-02" "2015-02-05" "2015-02-06" "2015-02-09" "2015-02-10" "2015-02-11"
[876] "2015-02-12" "2015-02-19" "2015-02-20" "2015-02-23" "2015-02-24" "2015-02-25" "2015-02-26"
[883] "2015-02-27" "2015-03-03" "2015-03-04" "2015-03-06" "2015-03-09" "2015-03-11" "2015-03-12"
[890] "2015-03-18" "2015-04-02" "2015-06-14" "2015-04-08" "2015-04-16" "2015-04-25" "2015-04-28"
[897] "2015-05-08" "2017-09-06" "2016-02-28" "2015-12-09" "2015-12-14" "2017-09-09" "2017-09-02"
[904] "2017-08-24" "2017-08-30" "2017-09-03" "2017-09-04" "2017-09-05" "2017-09-07" "2017-09-08"
[911] "2017-09-10" "2017-09-12" "2017-09-14" "2015-04-30" "2015-04-21" "2015-04-05" "2015-03-13"
[918] "2015-05-05" "2015-03-29" "2015-06-10" "2015-04-27" "2014-10-17" "2015-01-20" "2015-02-17"
[925] "2015-03-10" "2015-03-23"
```
##### Pre-Procesar Datos
###### Identificación de datos faltantes (NA)
- **Acciones**: En primer lugar, se creó una copia del conjunto de datos original, denominada "hotel_booking_data", con el propósito de preservar la integridad del conjunto de datos original y evitar cualquier modificación inadvertida. A continuación, se llevó a cabo un análisis exhaustivo de los datos faltantes en el conjunto de datos. Se procedió a identificar los datos faltantes por columna, lo que proporcionó una visión detallada de la magnitud del problema en cada atributo. En particular, se centró la atención en la columna "children" para examinar las filas que contenían datos faltantes y comprender mejor su distribución mediante un resumen estadístico. Se determinó que el valor más frecuente en esta columna.

```r
### 3. PRE-PROCESAR DATOS
# 3.1 Creamos una copia para no alterar el dataset original
hotel_booking_data <- hotel_booking_demand

# 3.2 Identificación de datos faltantes (NA)
# 3.2.1 Datos faltantes en total
total_missing_data <- sum(is.na(hotel_booking_data))
cat("Total de datos faltantes:", total_missing_data,"\n")

# 3.2.2 Datos faltantes por columna
missing_data_per_column <- colSums(is.na(hotel_booking_data))
print(missing_data_per_column)

# 3.2.3 Fila de los datos faltantes
unique(hotel_booking_data$children)
hotel_booking_data[is.na(hotel_booking_data$children), ]
summary(hotel_booking_data$children)

# 3.3 Completamos los datos faltante
# 3.3.1 Calculamos la moda y reemplazamos
children_data <- hotel_booking_data$children
children_data_table <- table(children_data)
frequency <- as.numeric(names(children_data_table[children_data_table == max(children_data_table)]))
cat("La moda en la columna 'children' es:", frequency, "\n")
barplot(children_data_table, 
        main = "Distribución de los valores de la columna 'children'",
        xlab = "Número de niños",
        ylab = "Frecuencia",
        col = "blue",
        border = "black")

hotel_booking_data$children[is.na(hotel_booking_data$children)] <- frequency
```
- **Resultado**: Se detectaron un total de 4 datos faltantes en el conjunto de datos, siendo la columna "children" la única afectada con estos valores ausentes. Cuatro filas específicas relacionadas con reservas en "City Hotel" presentaron estos datos faltantes, con variaciones en atributos como la fecha de llegada y la duración de la estadía. Previo a la corrección de datos, se reveló que la columna "children" tenía una distribución que abarcaba desde 0 hasta 10, con un valor de moda igual a 0. Para solucionar este problema, se imputaron los 4 valores faltantes con la moda (0), garantizando así la integridad de la información en la columna "children". Además, se proporcionó una visualización gráfica de la distribución de valores antes y después de la corrección, destacando 0 como el valor predominante tras el proceso de completación de datos faltantes.

```r
> ### 3. PRE-PROCESAR DATOS
> # 3.1 Creamos una copia para no alterar el dataset original
> hotel_booking_data <- hotel_booking_demand
> # 3.2 Identificación de datos faltantes (NA)
> # 3.2.1 Datos faltantes en total
> total_missing_data <- sum(is.na(hotel_booking_data))
> cat("Total de datos faltantes:", total_missing_data,"\n")
Total de datos faltantes: 4 
> # 3.2.2 Datos faltantes por columna
> missing_data_per_column <- colSums(is.na(hotel_booking_data))
> print(missing_data_per_column)
                         hotel                    is_canceled                      lead_time 
                             0                              0                              0 
             arrival_date_year             arrival_date_month       arrival_date_week_number 
                             0                              0                              0 
     arrival_date_day_of_month        stays_in_weekend_nights           stays_in_week_nights 
                             0                              0                              0 
                        adults                       children                         babies 
                             0                              4                              0 
                          meal                        country                 market_segment 
                             0                              0                              0 
          distribution_channel              is_repeated_guest         previous_cancellations 
                             0                              0                              0 
previous_bookings_not_canceled             reserved_room_type             assigned_room_type 
                             0                              0                              0 
               booking_changes                   deposit_type                          agent 
                             0                              0                              0 
                       company           days_in_waiting_list                  customer_type 
                             0                              0                              0 
                           adr    required_car_parking_spaces      total_of_special_requests 
                             0                              0                              0 
            reservation_status        reservation_status_date 
                             0                              0 
> # 3.2.3 Fila de los datos faltantes
> unique(hotel_booking_data$children)
[1]  0  1  2 10  3 NA
> hotel_booking_data[is.na(hotel_booking_data$children), ]
           hotel is_canceled lead_time arrival_date_year arrival_date_month arrival_date_week_number
40601 City Hotel           1         2              2015             August                       32
40668 City Hotel           1         1              2015             August                       32
40680 City Hotel           1         1              2015             August                       32
41161 City Hotel           1         8              2015             August                       33
      arrival_date_day_of_month stays_in_weekend_nights stays_in_week_nights adults children babies meal
40601                         3                       1                    0      2       NA      0   BB
40668                         5                       0                    2      2       NA      0   BB
40680                         5                       0                    2      3       NA      0   BB
41161                        13                       2                    5      2       NA      0   BB
      country market_segment distribution_channel is_repeated_guest previous_cancellations
40601     PRT      Undefined            Undefined                 0                      0
40668     PRT         Direct            Undefined                 0                      0
40680     PRT      Undefined            Undefined                 0                      0
41161     PRT      Online TA            Undefined                 0                      0
      previous_bookings_not_canceled reserved_room_type assigned_room_type booking_changes deposit_type
40601                              0                  B                  B               0   No Deposit
40668                              0                  B                  B               0   No Deposit
40680                              0                  B                  B               0   No Deposit
41161                              0                  B                  B               0   No Deposit
      agent company days_in_waiting_list   customer_type  adr required_car_parking_spaces
40601  NULL    NULL                    0 Transient-Party 12.0                           0
40668    14    NULL                    0 Transient-Party 12.0                           0
40680  NULL    NULL                    0 Transient-Party 18.0                           0
41161     9    NULL                    0 Transient-Party 76.5                           0
      total_of_special_requests reservation_status reservation_status_date
40601                         1           Canceled              2015-08-01
40668                         1           Canceled              2015-08-04
40680                         2           Canceled              2015-08-04
41161                         1           Canceled              2015-08-09
> summary(hotel_booking_data$children)
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max.    NA's 
 0.0000  0.0000  0.0000  0.1039  0.0000 10.0000       4 
> # 3.3 Completamos los datos faltante
> # 3.3.1 Calculamos la moda y reemplazamos
> children_data <- hotel_booking_data$children
> children_data_table <- table(children_data)
> frequency <- as.numeric(names(children_data_table[children_data_table == max(children_data_table)]))
> cat("La moda en la columna 'children' es:", frequency, "\n")
La moda en la columna 'children' es: 0 
> barplot(children_data_table, 
+         main = "Distribución de los valores de la columna 'children'",
+         xlab = "Número de niños",
+         ylab = "Frecuencia",
+         col = "blue",
+         border = "black")
> hotel_booking_data$children[is.na(hotel_booking_data$children)] <- frequency
```
###### Identificación de datos atípicos (Outliers)
- **Acciones**: Se realizaron evaluaciones exhaustivas de datos atípicos en diversas columnas del conjunto de datos, incluyendo "lead_time," "stays_in_weekend_nights," "stays_in_week_nights," "adults," "children," "babies," "is_repeated_guest," "previous_cancellations," "previous_bookings_not_canceled," "booking_changes," "days_in_waiting_list," "adr," "required_car_parking_spaces," y "total_of_special_requests." Para abordar estos valores atípicos, se diseñó una función especializada llamada "transformar_outliers," que calcula los cuartiles y el Rango Intercuartílico (IQR) para cada columna, estableciendo límites superior e inferior para identificar y ajustar los valores atípicos. Se destacan medidas adicionales en las columnas "children," "babies," y "required_car_parking_spaces," donde se aplicaron limitaciones específicas para garantizar que los valores permanezcan dentro de rangos particulares (de 0 a 10 en "children" y "babies," y de 0 a 8 en "required_car_parking_spaces")

```r
# 3.3 Identificación de datos atípicos (Outliers)
# 3.3.1 Datos atipicos por columna
boxplot.stats(hotel_booking_data$lead_time)
length(boxplot.stats(hotel_booking_data$lead_time)$out)

boxplot.stats(hotel_booking_data$stays_in_weekend_nights)
length(boxplot.stats(hotel_booking_data$stays_in_weekend_nights)$out)

boxplot.stats(hotel_booking_data$stays_in_week_nights)
length(boxplot.stats(hotel_booking_data$stays_in_week_nights)$out)

boxplot.stats(hotel_booking_data$adults)
length(boxplot.stats(hotel_booking_data$adults)$out)

boxplot.stats(hotel_booking_data$children)
length(boxplot.stats(hotel_booking_data$children)$out)

boxplot.stats(hotel_booking_data$babies)
length(boxplot.stats(hotel_booking_data$babies)$out)

boxplot.stats(hotel_booking_data$is_repeated_guest)
length(boxplot.stats(hotel_booking_data$is_repeated_guest)$out)

boxplot.stats(hotel_booking_data$previous_cancellations)
length(boxplot.stats(hotel_booking_data$previous_cancellations)$out)

boxplot.stats(hotel_booking_data$previous_bookings_not_canceled)
length(boxplot.stats(hotel_booking_data$previous_bookings_not_canceled)$out)

boxplot.stats(hotel_booking_data$booking_changes)
length(boxplot.stats(hotel_booking_data$booking_changes)$out)

boxplot.stats(hotel_booking_data$days_in_waiting_list)
length(boxplot.stats(hotel_booking_data$days_in_waiting_list)$out)

boxplot.stats(hotel_booking_data$adr)
length(boxplot.stats(hotel_booking_data$adr)$out)

boxplot.stats(hotel_booking_data$required_car_parking_spaces)
length(boxplot.stats(hotel_booking_data$required_car_parking_spaces)$out)

boxplot.stats(hotel_booking_data$total_of_special_requests)
length(boxplot.stats(hotel_booking_data$total_of_special_requests)$out)

# 3.4 Transformamos los datos atipicos (outliers)
transformar_outliers <- function(data, columna) {
  # 3.4.1 Calculamos los cuartiles e IQR
  Q1 <- quantile(data[[columna]], 0.25)
  Q3 <- quantile(data[[columna]], 0.75)
  IQR <- Q3 - Q1
  
  # 3.4.2 Calcula los límites superior e inferior
  limite_superior <- Q3 + 1.5 * IQR
  limite_inferior <- Q1 - 1.5 * IQR

  data[[columna]][data[[columna]] > limite_superior] <- limite_superior
  data[[columna]][data[[columna]] < limite_inferior] <- limite_inferior
  
  return(data)
}

hotel_booking_data <- transformar_outliers(hotel_booking_data, 'lead_time')
hotel_booking_data <- transformar_outliers(hotel_booking_data, 'stays_in_weekend_nights')
hotel_booking_data <- transformar_outliers(hotel_booking_data, 'stays_in_week_nights')
hotel_booking_data <- transformar_outliers(hotel_booking_data, 'adults')
hotel_booking_data$children <- pmin(pmax(hotel_booking_data$children, 0), 10)
hotel_booking_data$babies <- pmin(pmax(hotel_booking_data$babies, 0), 10)
hotel_booking_data <- transformar_outliers(hotel_booking_data, 'is_repeated_guest')
hotel_booking_data <- transformar_outliers(hotel_booking_data, 'previous_cancellations')
hotel_booking_data <- transformar_outliers(hotel_booking_data, 'previous_bookings_not_canceled')
hotel_booking_data <- transformar_outliers(hotel_booking_data, 'booking_changes')
hotel_booking_data <- transformar_outliers(hotel_booking_data, 'days_in_waiting_list')
hotel_booking_data <- transformar_outliers(hotel_booking_data, 'adr')
hotel_booking_data$required_car_parking_spaces <- pmin(pmax(hotel_booking_data$required_car_parking_spaces, 0), 8)
hotel_booking_data <- transformar_outliers(hotel_booking_data, 'total_of_special_requests')
```
- **Resultado**: Se observó que la columna "lead_time" contenía un total de 3,005 valores atípicos, mientras que la columna "stays_in_weekend_nights" presentaba 265 valores atípicos y la columna "stays_in_week_nights" tenía 167 valores atípicos. En contraste, las columnas "adults," "is_repeated_guest," "previous_cancellations," "previous_bookings_not_canceled," y "booking_changes" no mostraban valores atípicos notables. Para las columnas "children" y "babies," se aplicaron restricciones para mantener los valores dentro del rango de 0 a 10, garantizando así la consistencia de los datos. Además, la columna "required_car_parking_spaces" se transformó para limitar los valores dentro del rango de 0 a 8. Se llevaron a cabo ajustes en las columnas "days_in_waiting_list" y "adr" para abordar valores atípicos.

```r
> # 3.3 Identificación de datos atípicos (Outliers)
> # 3.3.1 Datos atipicos por columna
> boxplot.stats(hotel_booking_data$lead_time)
$stats
[1]   0  18  69 160 373

$n
[1] 119390

$conf
[1] 68.35068 69.64932

$out
   [1] 737 394 460 381 382 709 468 468 468 468 468 468 468 468 468 468 398 424 434 374 406 406 406 406 406
  [26] 400 379 399 385 422 390 390 394 376 376 376 375 385 385 385 397 397 385 385 385 397 397 397 385 385
  [51] 397 397 397 397 397 385 385 385 385 385 397 397 397 385 385 397 397 385 385 397 397 385 385 385 542
  [76] 542 542 542 542 542 542 542 542 542 403 403 383 383 383 383 383 383 383 383 383 383 383 383 383 383
 [101] 383 383 383 383 383 383 383 383 383 383 383 383 383 383 383 383 383 383 383 383 383 383 383 383 383
 [126] 383 383 383 383 383 383 383 383 383 383 383 383 384 385 393 393 393 393 393 393 393 393 393 393 393
 [151] 393 393 393 393 393 393 393 393 393 393 393 393 393 393 393 393 393 435 375 382 386 386 385 385 385
 [176] 385 385 385 386 386 386 386 386 386 386 386 386 386 386 386 386 386 386 378 378 378 378 378 378 378
 [201] 378 378 378 378 378 378 378 378 378 378 378 471 471 471 471 471 471 462 462 462 462 462 462 462 462
 [226] 462 462 462 462 462 462 462 462 462 462 462 462 411 411 411 411 411 411 411 411 411 411 411 411 411
 [251] 411 411 411 411 411 411 411 411 450 411 411 411 390 381 378 454 399 468 468 468 468 468 468 468 468
 [276] 468 468 468 468 468 468 468 468 468 468 468 468 460 460 532 468 468 468 468 468 468 468 468 468 468
 [301] 468 468 468 468 468 468 468 383 386 383 406 422 445 542 542 542 542 445 445 542 542 542 542 542 542
 [326] 542 542 542 383 383 383 383 383 383 383 383 383 383 383 383 383 383 384 383 383 383 383 383 386 386
 [351] 386 386 386 386 386 386 386 386 386 386 390 386 386 389 389 386 386 386 386 386 386 386 386 386 386
 [376] 386 386 386 386 386 386 386 386 386 386 386 386 386 385 386 386 386 386 386 386 386 386 386 386 386
 [401] 386 386 386 388 388 388 388 388 388 388 388 388 388 388 388 388 388 388 388 388 388 388 388 379 379
 [426] 407 407 379 379 393 393 393 393 393 393 393 393 393 393 393 393 393 393 393 393 393 393 393 393 393
 [451] 393 393 393 393 393 393 393 393 393 443 443 443 443 443 443 443 443 443 443 443 443 443 443 443 443
 [476] 443 443 443 443 443 443 437 437 437 437 437 437 437 437 437 437 437 437 437 437 437 437 437 437 437
 [501] 437 437 437 437 437 437 437 437 437 437 437 451 451 451 451 451 451 451 451 451 451 451 451 451 451
 [526] 451 451 451 451 451 451 451 451 451 451 451 451 451 451 451 451 384 384 384 384 384 384 384 384 384
 [551] 384 384 384 384 384 384 384 384 384 384 384 384 384 384 379 379 379 379 379 379 379 379 379 379 379
 [576] 379 379 379 379 379 379 379 379 379 379 379 379 379 379 379 379 379 379 379 379 379 391 391 391 391
 [601] 391 391 391 391 391 391 391 391 391 391 391 391 391 391 391 391 391 391 391 386 386 386 386 386 386
 [626] 386 386 386 386 386 386 386 386 386 386 386 386 386 386 386 386 386 386 386 386 386 386 386 386 386
 [651] 386 391 391 391 391 391 391 391 391 391 391 391 391 391 391 391 391 391 391 391 391 391 391 391 391
 [676] 391 391 391 391 391 391 391 391 405 405 405 405 405 405 405 405 405 405 405 405 405 405 405 405 405
 [701] 405 405 405 405 405 405 398 398 398 398 398 398 398 398 398 398 398 398 398 398 398 398 398 398 398
 [726] 398 398 398 398 398 398 398 398 398 398 398 398 398 405 405 405 405 405 405 405 405 405 405 405 405
 [751] 405 405 405 405 405 405 405 405 405 405 405 405 405 405 405 405 405 405 405 405 412 412 412 412 412
 [776] 412 412 412 412 412 412 412 412 412 412 412 412 412 412 412 412 412 412 412 412 412 412 412 412 412
 [801] 412 412 419 419 419 419 419 419 419 419 419 419 419 419 419 419 419 419 419 419 419 419 419 419 419
 [826] 419 419 419 419 419 419 419 419 419 420 420 420 420 420 420 420 420 420 420 420 420 420 420 420 420
 [851] 420 420 420 420 420 420 420 420 420 420 420 420 420 420 426 426 426 426 426 426 426 426 426 426 426
 [876] 426 426 426 426 426 426 426 426 426 426 426 426 426 426 426 426 426 426 426 426 426 433 433 433 433
 [901] 433 433 433 433 433 433 433 433 433 433 433 433 433 433 433 433 433 433 433 433 433 433 433 433 433
 [926] 433 433 433 433 433 433 433 433 433 433 433 433 433 433 433 433 433 433 433 433 433 433 433 422 422
 [951] 422 422 422 422 422 422 422 422 422 422 422 422 422 440 440 440 440 440 440 440 440 440 440 440 440
 [976] 440 440 440 440 440 440 440 440 440 440 440 440 440 440 440 440 440 440 440 440 429 429 429 429 429
 [ reached getOption("max.print") -- omitted 2005 entries ]

> length(boxplot.stats(hotel_booking_data$lead_time)$out)
[1] 3005
> boxplot.stats(hotel_booking_data$stays_in_weekend_nights)
$stats
[1] 0 0 1 2 5

$n
[1] 119390

$conf
[1] 0.9908546 1.0091454

$out
  [1]  6  6 13  6  8  6  7  7  7  7  7  7  6  8  8  6  6  6  8  8  8  8 12 12  7  7  6  8  8  6  6  6  6
 [34]  6  6  6  6  6  6  6  6  6  6  6  6  9  6  6  6  9  9  8  6  6 16  8  8  8  6  8  8  7  6  6  6  6
 [67]  6  6  6  6  6  6  6  6  6  6  6  6  6  6  6  6  6  8  6  6  6  6  6  8  6  6 18 19  9  6  7  6  8
[100]  8  9  6  7  7  7  6  8  6  8 10  8  6  6  6  8  6  8  8  8  6  8  6  6  6  8 10  6  8  8  6  6 13
[133]  8 10 10  6  6  6  6 10  8  6 16  6  6  6  6  6  6  8  6  6  6  6  6  6  6  6  6  6  6  6  6  6 12
[166]  6  6  6  6  6  6  8  6  8  6 12 12  6  6  6  6  6  8  9  6  6  6  8  7  6  9  6  8  8  6  7  6  8
[199]  8  6  9  7  6  6  6  6  6  7  7 14  6  8  6  8  6  6  8  6  8  6  6  6  8  8  6  8 10 10  8  6  6
[232]  8  6  8  8  6  6  8  7  8  6  6  6  6  6  6  8  8  9  9  8  8  6  6 14  6  8  6  6 16  9  6  6 13
[265]  8

> length(boxplot.stats(hotel_booking_data$stays_in_weekend_nights)$out)
[1] 265
> boxplot.stats(hotel_booking_data$stays_in_week_nights)
$stats
[1] 0 1 2 3 6

$n
[1] 119390

$conf
[1] 1.990855 2.009145

$out
   [1] 10 11  8  8 10  7  7  7  7  7 10 10 15  7 10 10  7  7  7  7  7  8 10 10 10  7  7  7  7  7  9  7  7
  [34] 10  7  7  7  9 10 10 11  7 10  7 10 10  7  7  7  8  8  7  8  7  7  7 10  8 10  8  7  7  7  7 10 10
  [67] 10  8  8  7  9 10 10  8  8  8 10 10  8  8  8 10 10 12 10 10  7  8  8  7  7  7  7  7  7  7 10  7  7
 [100]  7  8  7  9  7  8  7  8  8 10 10  7  7  7  8  8  8 10  7  7  7 10 10  7 10 33  7  7 10 10  7  7  7
 [133]  7  8  8 10  7 12  7  8  8 10 10 10 20  7 10 11 10 10 10 10  7  7 10  7  7  7  7  7  7  8  8  7  8
 [166] 10  8 10  9  7 10 10  7  8  8  8  8  8  8  8  8  8  8  8  8 10  7  9  7  8 15  8  8 12  7  8  9  7
 [199] 11  7 14 15 16 16 16 16 16  8 11 11 11 11 11 11 11 10 10 10 10 10 10 10 10  9  9  9  8  8  8  7  7
 [232]  7  7  7  7  7  8 10  7 15 10  7 21 10 20 13  7  8  8 13 13  9  9  9  9  9  9  9  8  7  7 10  8 10
 [265]  7  8 20 20 10 10 10 20 20 30 30 15 19 19  8 10 10 15  7 10 10  7  7  7 20  7  7  7  7  7 10 20  7
 [298]  7 15 15 15 15 15 15 15 15 15 15 15 15 15 15 15 10 10  9 10 10  9  8  7  9  8  7  8  7  8 13  7 10
 [331] 11  7 10 10  7  7  7  7 10 10 10 10 10 24 10  7 10 10 10  8 10 10  7  7  7  7  7 10  7  8  8  8 10
 [364]  7  7  7  7  7  7  7  8  8  8  8  8  8  9  7  8  8  8  8  8  7  7 10  7  8 10  7  8  8 10 10 10 10
 [397] 10  7  8  8  9  7  7  8  7 10 10  7  7  7 10 10 10  7  7  8  9 10 10  8 10 10  7  8  9  8  9  7  7
 [430] 10 10  7 10 10 10  7  7 10 10  8 10 10 10 10 10 10  8  7  7  9  7  7  7  7  8  8  8  8  8 10  7 10
 [463] 10 11  7  8 10  7  7  7 10 10 10 10 10 11  7  9  7  7  7  7  8 10 10 10  8  7  8  8  8  8  8 10 10
 [496]  7  7  9 10  7  8 10 10  7  7  8 10 10 12  7  8  8  8  8 10  8  7  8  8  8  8  9  8  8  8  8  9  7
 [529] 10 14  9 10 12  7  7 10 10 10  7  9  7  7 10 10 10 10  7  7 10 10 10 10 10 10  7  8  8 10 10 10  8
 [562]  9  9  8  8 10  7  7  7  7 10 10 10  8  8  7  8  7 10  8  9  9  9 10 10  8  8  8  8 10  7 10 10  7
 [595]  8  8  8 10 10 10 10 10 10 10  7  7  7  8 10 10  8 10  7 10 10  8 10 10  7  7  7  7 10 10 10  8 10
 [628]  7 10 10 10 10  9 10 10  7  8 10 10 10  7  7  7  7  7  9 10 10 10  7  7 10 15 15  7  7  7  8  7 10
 [661] 10  7  7  7  8 11 21 21  7  8 10 13 20 12 12  8 14  7  7  7  7  7 11  8  9  8  8  8  8 10  7  8 10
 [694] 40 10 12 10  9  9  9 21 20 10  7 20  7 10 15  7 20 10 20  8 19 19 19 19 19 19 19 19 19 10 10 19 19
 [727] 19 19 19 19 19 19 19 19 19 19 19 22 15 10 10  7  7  7  7  7 14 14 14 14 14 14 14 14 14 14 14 14 14
 [760] 14 14 14 14 15 10  7 10  7  7  7  7  7 11  7  7  7 10  7  7  7  7  7  7  7  7  7  7  7  7  7  7  7
 [793] 10  7  9  9  9  9  9  9  9  9  8 10 12  8 10  8  8  8  7  7  7 10  7  7 10  7 10  7  7  8 10  7  8
 [826]  8 10 10 10 10  7 10 10 10 10 10 15 15  9 10 10  7 10 10  7  7 10 10  7  7  8  9 10 10 19  7  7  7
 [859]  7 10  7  7  7  7 10 10 10 15  7  8 10  8  8  8  8  7  7 10  7  7  7  7 10 10  7  7 10  8  7  7  8
 [892] 10  7  7  7 10 10 10  7  8  8  8 10  7  7  8 10  7  7  8  8  8 10  8  8  8 10 10  8  7  7  8 10  7
 [925]  7 10  7  7  7  9  8 10 11 11 10 10 10  7  9 10  7  7  7 11 10 10  8  7  8  9  8  9  9  7  7  8  7
 [958]  9  9  7  9 10 10 10 10  8  8  8  8  8 10  8  8  8  7  7  7  7  7  7 10  7  7 10  8  8  8  8  8  8
 [991]  8  7  9  7  7 10 10 10  9  7
 [ reached getOption("max.print") -- omitted 2354 entries ]

> length(boxplot.stats(hotel_booking_data$stays_in_week_nights)$out)
[1] 3354
> boxplot.stats(hotel_booking_data$adults)
$stats
[1] 2 2 2 2 2

$n
[1] 119390

$conf
[1] 2 2

$out
   [1]  1  1  1  1  3  3  3  3  3  3  1  3  3  1  3  3  1  1  4  1  1  1  3  3  1  3  3  1  1  1  1  3  1
  [34]  3  3  1  3  3  3  1  1  3  3  1  3  4  1  3  1  1  1  3  1  1  3  1  3  1  1  1  1  1  1  1  1  3
  [67]  3  3  1  1  1  1  1  1  3  3  3  1  3  3  3  1  3  1  3  3  1  3  3  1  1  3  1  1  1  1  3  1  3
 [100]  1  1  3  3  1  3  3  1  1  1  4  1  1  3  1  1  3  1  1  3  3  3  3  3  3  3  3  1  1  1  1  1  1
 [133]  3  3  1  3  3  3  3  1  1  3  3  1  3  3  3  3  3  1  1  1  1  3  3  1  1  1  3  1  1  3  1  3  1
 [166]  3  1  1  1  1  3  1 40  3  1  1  3  1 26  1  1  3  3  1 50  1  1  1  1  1  1  1  1  1  3  1  1  1
 [199]  3  1  1  1 26  1  1  1  1  1  1  1  1  1  1  1  1  1  3 26  3  1  1 27  1  1  1  3 27  3  1  1 26
 [232]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  3  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1 26  1
 [265] 55  1  1  1  1  0 20  6  5  1  1  1  1  1  1  3  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [298]  1  1  1  0  1  1 10 20  5  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  3  3  3  1  1  1  1  1  1
 [331]  1  1  1  1  1  1  1  1  1  3  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [364]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [397]  3  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  3  1  1  1  1  1  1  1  1  1  1  1  1
 [430]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [463]  1  1  1  1  1  1  1  1  3  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [496]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [529]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  0  1  3  1  1  1  1  1  1  1  1  3  1  1  3  1  1
 [562]  1  1  1  1  1  3  1  3  1  1  1  1  1  1  3  3  3  1  1  1  1  1  1  1  1  3  3  1  3  1  1  1  1
 [595]  1  1  1  1  3  1  1  1  1  1  1  1  1  1  1  3  0  1  1  1  1  1  1  3  0  3  3  3  1  1  1  1  1
 [628]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  3  1  1  1  1  1  1  3  1  3  3  1  1
 [661]  3  1  3  1  1  3  0  3  1  1  3  3  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [694]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [727]  1  1  1  1  1  1  1  1  3  1  1  1  1  1  3  3  3  3  3  1  1  3  3  1  3  3  3  1  3  3  1  1  1
 [760]  1  1  1  3  1  1  1  1  1  3  1  1  1  3  1  1  1  3  1  1  1  1  1  3  1  1  1  1  1  1  1  1  1
 [793]  1  1  1  3  1  1  1  1  1  1  1  1  1  1  1  3  3  1  1  1  1  1  3  1  1  1  1  1  1  1  1  1  1
 [826]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  3  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [859]  1  1  1  1  1  1  1  1  3  1  1  1  1  1  1  1  1  3  1  3  1  1  1  1  1  1  1  3  1  1  1  1  1
 [892]  1  3  1  1  1  1  1  1  1  1  1  3  1  1  1  1  1  1  1  1  1  3  3  1  1  1  1  1  3  1  1  1  1
 [925]  1  1  1  1  1  1  1  1  1  1  1  1  1  3  1  1  1  1  1  1  1  1  1  1  1  1  3  1  1  1  1  1  1
 [958]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  3  1  1  1  1  1  1  1  1  3  1  1  4  1  1  1
 [991]  1  1  1  3  1  1  1  1  1  1
 [ reached getOption("max.print") -- omitted 28710 entries ]

> length(boxplot.stats(hotel_booking_data$adults)$out)
[1] 29710
> boxplot.stats(hotel_booking_data$children)
$stats
[1] 0 0 0 0 0

$n
[1] 119390

$conf
[1] 0 0

$out
   [1]  1  2  2  2  1  1  2  2  1  2  1  2  2  2  2  2  1  2  1  2  1  2  2  2  2  1  2  1  1  1  1  1  2
  [34]  2  1  1 10  2  2  2  1  1  2  2  2  2  2  2  1  1  1  2  2  1  1  1  1  2  2  1  2  2  1  2  1  2
  [67]  2  2  2  2  1  2  1  1  1  2  1  1  2  2  2  2  2  1  1  2  2  1  1  1  2  2  2  1  1  1  1  2  2
 [100]  1  2  1  2  2  2  2  2  2  2  1  2  1  2  1  2  2  2  1  2  1  2  2  1  2  2  2  2  1  1  2  1  1
 [133]  2  1  1  1  2  1  1  2  2  1  2  2  1  1  1  1  2  2  1  1  2  1  2  2  1  2  1  1  1  1  1  1  1
 [166]  2  1  2  1  1  2  2  1  1  2  2  2  1  1  1  2  2  1  1  2  2  2  1  2  1  1  2  2  2  2  1  1  1
 [199]  2  2  2  1  2  2  2  2  2  1  2  2  2  2  2  2  2  2  1  1  1  1  1  2  2  2  2  2  2  1  1  2  1
 [232]  1  1  1  1  1  1  1  2  2  1  2  2  2  1  2  1  2  2  1  1  2  1  2  2  1  1  1  1  1  1  2  1  1
 [265]  1  1  1  1  1  2  1  1  1  2  1  2  2  1  2  1  2  2  1  1  2  2  2  2  1  2  2  1  2  2  1  2  1
 [298]  1  1  1  1  1  1  2  2  1  2  1  2  1  1  2  1  2  1  1  2  1  2  1  2  1  1  1  1  1  2  2  1  1
 [331]  2  2  1  2  2  2  2  2  2  1  2  2  1  1  2  1  1  1  1  1  2  2  2  2  2  2  2  2  2  1  1  2  1
 [364]  2  1  2  1  2  1  2  1  2  1  2  1  2  2  2  2  2  2  1  2  1  2  2  2  1  2  2  1  2  2  2  2  2
 [397]  1  2  2  2  1  2  2  2  1  2  1  1  2  1  1  2  2  2  1  1  2  2  2  1  1  1  2  1  2  2  2  1  2
 [430]  2  2  1  2  1  2  1  1  2  1  1  2  2  1  1  1  1  2  1  2  2  1  1  2  2  1  2  2  1  2  1  1  1
 [463]  2  2  1  2  2  1  2  1  2  2  2  1  1  1  2  1  1  3  2  1  1  2  2  1  2  1  1  2  1  1  2  1  2
 [496]  1  1  2  1  2  2  2  2  2  2  2  1  1  2  1  2  1  1  2  2  2  2  2  2  2  2  2  2  1  2  1  2  2
 [529]  2  1  2  2  2  2  2  2  1  1  2  1  1  2  2  2  1  1  1  1  2  2  1  1  2  1  2  1  1  2  2  2  2
 [562]  1  2  2  1  1  1  1  1  2  1  2  2  1  1  2  2  1  2  2  1  2  2  1  2  1  1  1  1  1  1  2  2  1
 [595]  2  2  1  2  1  2  2  1  1  2  1  2  1  1  2  2  1  1  1  1  2  2  2  2  2  2  1  1  2  1  1  2  1
 [628]  1  1  1  1  1  1  1  1  1  2  1  2  1  1  2  1  3  1  1  1  1  1  2  1  1  1  1  2  2  2  2  2  1
 [661]  2  2  1  2  1  1  1  2  1  2  1  1  1  1  2  2  2  2  2  2  2  2  1  1  2  2  2  2  2  1  2  1  1
 [694]  2  1  1  2  2  1  1  1  1  1  1  1  1  1  1  2  1  1  2  2  2  1  2  2  1  1  2  1  2  2  2  2  2
 [727]  2  2  1  2  2  2  2  1  2  2  2  1  1  1  2  2  1  2  2  1  2  2  2  2  2  2  2  2  1  2  2  1  1
 [760]  2  1  1  2  2  1  1  1  2  1  2  1  2  1  2  2  2  2  1  2  2  1  2  1  1  1  2  1  1  1  1  2  1
 [793]  1  2  1  2  1  2  2  1  2  2  1  1  2  2  1  2  1  1  1  2  1  1  1  2  2  2  1  2  2  2  2  1  1
 [826]  1  1  1  1  1  2  1  1  1  2  1  1  2  1  2  2  1  2  1  2  1  2  2  1  1  2  1  1  1  2  1  1  1
 [859]  2  2  2  2  2  2  1  1  1  1  2  2  2  2  1  2  2  2  2  2  2  2  2  2  2  2  2  1  2  2  2  2  2
 [892]  2  2  1  2  2  2  1  2  2  1  2  1  1  2  1  2  1  1  2  1  2  2  2  2  1  2  2  2  2  1  2  2  1
 [925]  1  2  1  1  2  2  1  1  2  1  1  2  2  2  2  1  1  1  1  1  1  1  2  1  1  1  1  2  1  1  1  2  2
 [958]  2  2  2  1  1  2  2  1  2  2  2  2  2  2  2  2  2  2  1  2  2  2  2  2  1  2  2  2  1  2  2  2  2
 [991]  2  2  2  1  2  2  2  2  2  1
 [ reached getOption("max.print") -- omitted 7590 entries ]

> length(boxplot.stats(hotel_booking_data$children)$out)
[1] 8590
> boxplot.stats(hotel_booking_data$babies)
$stats
[1] 0 0 0 0 0

$n
[1] 119390

$conf
[1] 0 0

$out
  [1]  1  1  1  1  2  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [34]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [67]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  2  1  1  1  1  1  1  1  1  1
[100]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  2  1  1  1  1  1  1  1  1
[133]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  2  1  1  1  1  1  1
[166]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  2  1  1
[199]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
[232]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
[265]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
[298]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
[331]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
[364]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  2
[397]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
[430]  1  1  1  1  2  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
[463]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  2  1  1
[496]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
[529]  1  1  1  1  1  1  1  1  1  2  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
[562]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1 10  1  1  1  1  1  1  1  1  1
[595]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
[628]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  9  1  1  1  1  1  1  1  1  1  1  1
[661]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  2  1  1  1
[694]  2  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
[727]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  2  1  1  1  1  1  1  1  1  1  1  1  1  1  1
[760]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  2  1  1  1  1
[793]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
[826]  1  1  1  1  1  2  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
[859]  1  1  2  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
[892]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1

> length(boxplot.stats(hotel_booking_data$babies)$out)
[1] 917
> boxplot.stats(hotel_booking_data$is_repeated_guest)
$stats
[1] 0 0 0 0 0

$n
[1] 119390

$conf
[1] 0 0

$out
   [1] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
  [51] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [101] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [151] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [201] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [251] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [301] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [351] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [401] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [451] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [501] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [551] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [601] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [651] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [701] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [751] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [801] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [851] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [901] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [951] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [ reached getOption("max.print") -- omitted 2810 entries ]

> length(boxplot.stats(hotel_booking_data$is_repeated_guest)$out)
[1] 3810
> boxplot.stats(hotel_booking_data$previous_cancellations)
$stats
[1] 0 0 0 0 0

$n
[1] 119390

$conf
[1] 0 0

$out
   [1]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  2  2  2
  [34]  2  2  2  2  2  2  2  2  2  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  2  3  1  1  1  1  1  1  1
  [67]  1  1  1  1  1  2  2  1  1  1  1  1  1  2  2  2  1  1  2  1  1  1  1  1  2  2  2  1  1  1  1  1  1
 [100]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [133]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [166]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [199]  2  2  1  1  1 26 26 26 26 26 26 26 26 26 26 26 26 26 26 26 26 26 26 26 26 26 26 26 26 26 26  1  1
 [232]  1  1  1  1  1  1  1  1  2  2  1  1  1  1  1  1  1  1  1  1  1  1 25 25 25 25 25 25 25 25 25 25 25
 [265] 25 25 25 25 25 25 25 25 25 25 25 25 25 25  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [298]  1  1  1  1  1  1  1  1  1 14 14 14 14 14 14 14 14 14 14 14 14 14 14  1  1  3  3  3  1  1  1  1  1
 [331]  1  1  1  1  1  1  2  3  4  4  4  4  2  1  1  1  1  2  2  1  1  1  1  1  1  1  1  1  1  1  1 24 24
 [364] 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24  1 19 19 19 19 19 19 19 19 19 19
 [397] 19 19 19 19 19 19 19 19 19  1  1  1  1  1  1  1  3  3  1  1  1  1  1  1  1  1  2  2  1  1  1  2  2
 [430]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [463]  1  1  1  1  1  1  1  1  1  2  2  2  1  1  2  2 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24
 [496] 24 24 24 24 24 24 24  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [529]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [562]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [595]  1  1  1  3  3  3  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [628]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [661]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [694]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [727]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [760]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [793]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [826]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [859]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [892]  1  1  1  1  1  1  1  1  1  1  2  2  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [925]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [958]  1  1  2  2  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [991]  1  1  1  1  1  1  1  1  1  1
 [ reached getOption("max.print") -- omitted 5484 entries ]

> length(boxplot.stats(hotel_booking_data$previous_cancellations)$out)
[1] 6484
> boxplot.stats(hotel_booking_data$previous_bookings_not_canceled)
$stats
[1] 0 0 0 0 0

$n
[1] 119390

$conf
[1] 0 0

$out
   [1]  1  2  3  1  1  1  2  3  1  2  1  2  3  1  1  2  3  1  1  2  3  1  2  1  1  1  2  1  2  1  1  3  4
  [34]  5  1  1  2  3  4  1  2  1  1  2  3  1  2  1  2  3  3  4  5  6  7  8  1  1  2  3  4  5  6  2  3  4
  [67]  5  1  1  2  3  4  5  6  7  8  9 10 11 12  1  2  3  4  1  2  1  2  3  4  5  6  7  8  1  1  2  3  4
 [100]  1  1  1  1  2  3  1  2  2  2  3  4  5  6  7  8  9 10 11 12 13  1  1  2  1  2  3  1  2  1  2  3  4
 [133]  5  1  1  1  2  3  4  5  1  1  2  3  4  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 18 20 21 22 23
 [166] 24 25 25 27 27 28 29 30  1  1  2  3  4  5  1  2  1  2  3  4  5  1  2  1  1  1  2  1  2  1  2  1  2
 [199]  1  1  1  1  2  1  1  1  1  1  1  2  3  4  5  6  1  2  3  4  1  1  2  1  2  1  1  1  2  3  4  2  1
 [232]  1  1  1  1  2  3  4  5  1  2  3  4  5  6  1  2  3  1  2  3  4  1  2  1  2  3  4  5  6  7  8  9  1
 [265]  1  1  1  2  1  2  3  4  1  2  1  2  3  4  5  1  2  3  1  2  3  1  2  2  3  4  5  6  1  1  1  2  1
 [298]  2  2  1  2  2  1  2  3  4  5  6  7  1  2  3  4  5  6  1  1  2  1  2  2  3  4  5  6  7  8  9 10 11
 [331] 12 13 14 14  1  2  3  4  5  6  3  3  4  5  6  7  8  8  9  1  1  2  3  4  5  6  1  3  4  5  6  7  8
 [364]  9 10 11  1  1  1  1  1  1  1  2  1  1  1  1  2  1  1  3  4  5  5  1  2  3  2  2  2  2  2  3  4  5
 [397]  6  1  1  1  2  1  2  3  4  5  1  1  1  2  1  1  2  1  1  2  3  1  2  3  4  1  2  3  1  1  2  2  1
 [430]  1  2  3  2  3  4  5  6  7  8  9 10  1  2  3  4  5  6  1  1  2  3  1  2  3  4  1  1  2  3  4  2  3
 [463]  1  2  3  4  1  2  3  1  1  2  3  1  2  2  3  1  2  3  1  2  1  1  1  2  3  4  1  1  1  1  1  2  1
 [496]  1  2  1  2  1  1  3  1  2  1  2  3  4  5  6  1  1  1  1  2  3  1  1  1  1  2  3  2  3  1  1  1  4
 [529]  1  2  3  3  3  3  4  5  6  7  8  9 10 10 11 11 12 13  1  1  2  3  3  5  1  1  2  3  1  2  3  1  4
 [562]  5  6  7  8  9  1  1  2  3  1  2  1  2  1  2  3  1  1  1  2  3  4  1  2  1  1  2  1  2  1  2  3  3
 [595]  4  1  1  1  1  2  3  4  5  6  7  8  8  9 10  1  1  2  1  1  1  1  2  3  4  5  6  7  8  9 10  1  1
 [628]  1  2  2  3  4  1  1  2  2  4  5  6  7  7  8  9 10 11 12 13  1  1  1  2  1  2  3  1  1  1  1  2  1
 [661]  1  1  1  2  3  4  5  6  7  8  9 10  1  1  2  1  2  3  4  1  2  3  4  5  5  6  7  1  2  3  1  2  3
 [694]  4  5  6  7  8  9 10 11 12  1  1  2  3  3  5  6  1  1  1  2  1  1  2  1  2  3  4  1  2  1  1  1  2
 [727]  1  2  1  1  1  1  2  3  4  5  1  1  1  1  1  1  1  1  1  1  1  1  2  3  4  5  6  1  1  1  1  1  1
 [760]  1  1  1  2  1  1  1  2  3  1  1  1  1  2  3  4  5  6  1  2  1  2  3  4  4  5  6  7  8  9  1  1  1
 [793]  1  1  2  3  3  1  1  1  1  2  3  4  5  1  1  1  1  2  3  1  2  3  4  5  5  1  1  1  1  1  1  1  1
 [826]  1  1  1  1  2  1  1  2  1  1  2  1  2  3  4  5  6  7  8  9 10 10  1  2  3  4  1  2  1  2  3  1  2
 [859]  3  4  5  1  2  3  4  5  6  7  8  1  1  1  2  3  4  5  6  1  2  1  1  1  1  2  3  4  5  1  1  1  2
 [892]  3  4  5  1  2  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26  1  1  1
 [925]  1  1  1  2  3  4  5  1  2  1  1  1  1  1  1  1  1  2  2  4  5  6  2  1  1  1  1  2  1  1  2  3  1
 [958]  1  1  2  1  2  1  2  3  4  5  6  7  1  2  2  4  5  1  1  1  2  3  1  2  1  1  1  1  2  1  1  2  1
 [991]  1  1  2  3  1  2  1  2  3  1
 [ reached getOption("max.print") -- omitted 2620 entries ]

> length(boxplot.stats(hotel_booking_data$previous_bookings_not_canceled)$out)
[1] 3620
> boxplot.stats(hotel_booking_data$booking_changes)
$stats
[1] 0 0 0 0 0

$n
[1] 119390

$conf
[1] 0 0

$out
   [1]  3  4  1  1  1  1  2  1  1  2  1  1  1  1  2  1  3  1  1  3  1  1  1  1  1  5  1  2  2  1  1  2  2
  [34]  1  1  1  1  1  1  2  1  1  1  1  1  1  2  1  2  1  2  2  1  2  1  1  1  1  1  1  1  1  1  1  1  1
  [67]  1  1  1  1  1  1  1  1  1  3  3  1  4  1  1  1  1  2  3  1  1  1  1  1  1  1  1  1  2  1  1  1  1
 [100]  1  1  1  1  5  1  1  1  1  1  1  1  2  1  1  1  1  1  1  1  1  1  2  1  4  3  1  1  1  1  1  1  1
 [133]  1  1  1  2  1  1  1  2  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  2  1  1  1  1  1
 [166]  1  1  2  1  2  1  1  1  1  3  1  1  1  1  4  1  2  1  1  1  1  1  1  2  1  1  1  1  1  2  1  1  1
 [199]  2  1  1  1  1  1  1  1  1  1  1  1  1  1  1  5  1  3  1  2  1  1  1  2  2  2  2  1  2  1  1  1  1
 [232]  1  2  1  1  1  1  1  1  2  2  1  1  1  1  1  1  3  2 17  1  1  1  1  1  1  1  1  1  1  2  2  1  2
 [265]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  2  3  1  1  4  4  1  1  1  1  3
 [298]  1  1  1  1  1  1  3  1  1  1  1  1  1  1  1  1  1  1  1  1  2  3  1  1  2  2  1  2  2  1  1  4  1
 [331]  1  1  1  2  1  1  1  1  2  1  1  3  1  1  1  2  1  2  1  1  1  1  1  1  1  1  1  1  1  2  1  1  1
 [364]  1  1  1  1  1  1  2  2  1  2  2  4  1  1  1  2  1  1  2  1  1  1  1  2  1  1  1  2  1  1  1  1  1
 [397]  1  1  1  1  1  1  2  2  1  2  6  1  2  2  1  1  3  1  1  1  2  1  1  1  1  1  2  2  2  3  1  2  1
 [430]  1  1  2  2  1  2  1  1  2  1  1  1  1  2  1  1  2  1  1  1  1  2  1  3  3  4  2  1  4  1  1  1  3
 [463]  2  1  4  1  3  3  1  2  2  1  3  1  4  1  1  1  2  2  1  1  1  1  4  1  1  1  1  1  1  1  1  1  1
 [496]  1  1  1  1  2  1  3  3  1  1  1  2  3  2  2  1  1  1  1  1  1  1  1  1  1  1  3  2  1  1  1  2  2
 [529]  4  1  1  2  2  1  2  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [562]  1  1  1  1  1  1  1  1  1  1  2  1  1  1  1  1  3  5  1  1  1  1  3  1  1  1  1  2  1  1  1  1  1
 [595]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  2  1  1  1  1  2  1  1  4  1  1  1  1  1  1  1
 [628]  1  2  1  2  1  1  1  1  1  1  1  1  2  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1
 [661]  1  1  1  1  1  2  1  1  1  1  1  1  1  2  2  1  1  1  4  1  2  2  2  1  2  1  1  1  2  1  2  1  1
 [694]  1  1  1  1  1  1  2  1  1  1  1  1  2  2  1  1  1  1  1  1  1  1  2  2  1  1  2  2  1  2  1  1  3
 [727]  2  2  2  1  3  1  1  1  1  1  2  1  1  1  1  1  1  2  1  1  1  1  1  1  1  1  1  1  4  1  4  6  1
 [760]  1  2  2  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  2  1  1  1  1  1  1  1  1  1  2  1  1
 [793]  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  2  1  1  1  1  1  1  1  1  1  1  1  2  2  1  1
 [826]  2  1  1  1  1  1  1  1  2  1  1  1  1  1  1  1  1  1  1  1  4  3  1  1  1  1  1  1  1  1  1  1  1
 [859]  1  3  1  1  2  2  2  1  2  1  1  1  2  1  1  1  1  1  1  3  1  1  2  1  1  1  1  2  2  1  1  1  1
 [892]  1  1  1  1  2  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  1  2  2  2  2  1  1  2  2  1  2  1
 [925]  1  2  2  1  1  1  1  1  1  1  1  1  1  3  2  1  2  1  1  2  1  3  3  4  1  2  4  4  5  2  2  2  2
 [958]  1  2  2  1  2  2  2  2  2  2  2  2  2  2  2  2  2  2  2  2  2  2  2  3  2  2  3  2  2  2  2  2  2
 [991]  1  2  3  1  4  1  1  1  1  1
 [ reached getOption("max.print") -- omitted 17076 entries ]

> length(boxplot.stats(hotel_booking_data$booking_changes)$out)
[1] 18076
> boxplot.stats(hotel_booking_data$days_in_waiting_list)
$stats
[1] 0 0 0 0 0

$n
[1] 119390

$conf
[1] 0 0

$out
   [1]  50  47  47  47  47  47  47  47  47  47  47  47  47  47  47  47  47  47  47  47  47  47  65  65  65
  [26]  65  65  65  65  65  65  65  65  65  65  65  65  65  65  65  65 122 122 122 122 122 122 122 122 122
  [51] 122 122 122 122 122 122 122 122 122 122 122 122 122 122 122 122 122 122 122 122 122 122 122 122 122
  [76] 122 122 122 122 122 122 122 122 122 122 122 122 122 122 122 122 122 122 122 122  75  75  75  75  75
 [101]  75  75  75  75  75  75  75  75  75  75  75  75  75  75 101 101 101 101 101 101 101 101 101 101 101
 [126] 101 101 101 101 101 150 150 150 150 125 125 125 125 125 125 125 125 125 125 125 125 125 125 125  14
 [151]  60  34  50  50 100  22 121  61  39   5   5   1   8  50  50  47  47  65  65  65  65  65  65  65  65
 [176]   1 107 125  43  52   2  75  11 101 101 150 150 150 150 150 150 150  22 122 142   2 116  13  44  97
 [201]   1  97   1  97  83   4  14   4   4 113 113 113 113 113  18  20 185 185 107  93 109  34   6   6  13
 [226]   8  60  60  37  60  60  43   6   6 105 100  34   1 154  14  14 154  14   5  14  64  64  64 121   8
 [251]  61  61  20  99  99  38  38  38  38  38  38  38  38  48  48  48  48  48  48  48  48  65  65  65  65
 [276]  65  65  65  33  33  33  33  33  33  33  33  33  33  33  33  33  33  33  33  33  33  33  33  33  33
 [301]  33  33  33  33  33  33  33  77  77  77  77  77  77  77  77  77  77  77  77  77  77  77  77  77  77
 [326]  77  21  21  21  21  21  21  21  21  21  21  21  21  21  21  21  21  21  21  21  21  21  80  21  80
 [351]  80  80  80  80  80  59  59  59  59  59  59  59  59  40  40  77  77  77  77  77  40  40  77  77  40
 [376]  77  77  77  77  77  40  77  77  77  77  40  40  77  77  77  40  58  58  58  58  89  58  58  58  58
 [401]  58  58  58  58  58  58  53  53  53  53  53  50  50  50  50  49  49  50  50  50  49  49  50  50  50
 [426]  49  49  50  50  50  49  49  50  50  50  50  50  50  50  50  49  49  49  49  50  50  50  50  50  50
 [451]  49  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58
 [476]  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58
 [501]  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58
 [526]  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58
 [551]  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58
 [576]  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58  58
 [601]  58  60  60  60  60  60  60  60  60  60  60  60  60  60  60  60  60  60  60  60  60  69  69  69  69
 [626]  69  69  69  69  69  69  69  69  69  69  69  69  69  69  69  87  87  87  87  87  87  87  87  87  87
 [651]  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87
 [676]  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87
 [701]  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  87  91  91  91  91  91
 [726]  91  91  91  91  91  91  91  91  91  91  91  91  91  91  91  91  91  91  91  91  69  57  57  57  57
 [751]  57  57  57  57  57  57  57  57  57  57  57  57  57  57  57  57  57  57  57  57  69  69  69  69  69
 [776]  69  69  69  69  69  69  69  69  69  69  69  99  99  99  99  99  99  99  99  99  99  99  99  99  99
 [801]  99 111 111 111 111 111 111 111 111 111 111 111 111 111 111 111 111 111 111 111 111  79  79  79  79
 [826]  79  79  79  79  79  79  79  79  79  79  79  79  79  79  79  79  98  98  98  98  98  98  98  98  98
 [851]  98  98  98  98  98  98  91  91  91  91  91  91  91  91  91  91  91  91  91  91  91  91  91  91  91
 [876]  91  91  91  91  91  91  85  85  85  85  85  85  85  85  85  85  85  85  85  85  85  63  63  63  63
 [901]  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63
 [926]  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63
 [951]  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63  63
 [976]  63  15  15  15  15  15  15   3   3   3   3   3   3   3   3   3   3   3   3   3   3   3   3   3   3
 [ reached getOption("max.print") -- omitted 2698 entries ]

> length(boxplot.stats(hotel_booking_data$days_in_waiting_list)$out)
[1] 3698
> boxplot.stats(hotel_booking_data$adr)
$stats
[1]  -6.380  69.290  94.575 126.000 211.030

$n
[1] 119390

$conf
[1] 94.31568 94.83432

$out
   [1] 225.00 213.75 230.67 216.13 249.00 241.50 214.00 214.00 240.64 217.05 233.00 222.67 240.00 233.05
  [15] 219.43 240.00 250.33 280.74 219.50 214.00 252.00 233.00 237.00 222.14 220.55 221.00 230.50 230.50
  [29] 241.00 242.60 268.00 217.20 239.30 267.00 226.00 277.50 221.00 250.00 211.75 246.00 252.00 276.43
  [43] 228.00 211.50 277.00 214.00 254.00 221.00 233.00 214.00 241.00 274.93 252.00 258.33 255.00 243.00
  [57] 222.20 243.00 266.40 236.00 271.00 232.00 223.00 229.00 266.00 262.00 234.00 242.50 248.00 299.33
  [71] 218.00 248.00 223.99 214.00 225.90 213.00 213.00 236.00 229.67 239.50 220.40 241.00 241.00 241.00
  [85] 222.07 229.00 213.50 236.00 248.00 260.71 222.00 221.43 218.50 259.00 229.00 233.00 231.60 261.40
  [99] 219.33 212.83 221.20 332.00 270.00 276.60 232.00 214.00 220.00 225.00 220.00 220.00 272.00 222.00
 [113] 219.00 219.00 224.00 260.00 238.63 225.80 235.00 231.43 237.33 280.00 215.33 212.14 236.67 212.00
 [127] 240.00 240.00 224.00 224.00 212.00 239.00 227.00 242.00 250.00 237.00 233.00 252.00 287.00 259.00
 [141] 212.00 227.00 247.00 252.00 240.00 240.00 240.00 216.00 212.00 226.00 259.00 224.43 240.00 223.00
 [155] 212.00 227.00 288.00 222.33 226.00 226.00 226.00 226.00 262.00 222.00 226.00 243.32 259.00 219.80
 [169] 241.00 222.00 292.00 259.00 266.50 253.57 241.00 240.00 232.00 259.00 212.14 256.50 212.00 252.00
 [183] 244.50 282.00 250.00 240.00 221.00 219.00 283.32 231.00 231.00 272.70 221.00 230.00 240.00 231.00
 [197] 246.00 241.00 236.00 259.00 233.00 221.00 299.00 245.67 248.75 248.89 298.00 289.00 262.00 251.00
 [211] 213.00 224.00 274.00 230.00 299.00 241.00 273.00 269.00 269.00 254.00 259.00 236.71 259.00 243.63
 [225] 231.00 219.00 243.63 369.00 262.00 278.60 246.50 271.00 216.00 234.00 222.50 218.00 240.00 240.00
 [239] 216.00 254.31 240.00 261.50 240.00 240.00 214.00 246.00 259.00 224.00 224.00 225.67 219.00 231.50
 [253] 226.50 231.50 251.00 241.00 256.00 216.00 259.00 291.00 241.00 249.00 219.00 225.67 221.00 219.00
 [267] 225.67 214.00 251.50 234.60 234.00 279.00 241.00 259.00 241.00 254.00 277.67 299.00 227.92 258.00
 [281] 247.67 269.00 263.00 235.57 309.00 289.90 241.00 230.00 216.00 248.16 261.00 214.99 217.14 236.67
 [295] 236.50 259.00 216.50 219.00 219.00 256.00 219.00 246.00 231.00 221.00 246.00 231.00 221.00 229.00
 [309] 219.00 217.33 230.00 219.00 314.50 266.50 258.00 212.00 216.50 286.79 219.00 281.00 239.00 219.00
 [323] 239.00 231.00 219.00 274.00 219.00 227.92 214.00 214.00 275.00 237.00 222.00 222.00 222.00 237.00
 [337] 247.33 237.00 256.75 222.00 288.00 222.00 251.86 238.16 226.14 212.00 259.00 234.00 274.00 227.00
 [351] 304.00 286.00 329.00 231.00 231.00 231.00 235.67 281.00 214.00 226.73 251.73 274.00 219.00 231.00
 [365] 249.00 229.00 271.00 322.00 241.00 287.00 224.00 239.00 239.10 219.00 248.00 220.49 269.00 229.00
 [379] 214.60 214.00 214.00 226.50 265.67 249.50 240.00 249.50 262.00 253.00 232.25 322.00 269.00 234.00
 [393] 221.00 240.00 243.80 213.80 241.75 247.57 221.00 246.67 246.67 231.80 231.80 223.29 216.00 234.00
 [407] 227.10 221.00 240.60 252.00 219.00 264.00 216.00 219.00 254.00 246.00 221.07 292.40 212.86 233.00
 [421] 217.00 246.02 340.00 384.00 250.00 302.11 250.00 382.00 275.00 229.40 275.00 243.00 223.00 213.00
 [435] 213.00 225.50 228.00 228.00 262.50 223.00 212.00 213.33 215.00 223.00 228.00 228.00 233.00 260.00
 [449] 212.00 238.00 273.00 261.00 248.00 248.00 311.00 212.00 248.00 258.00 228.00 288.00 228.00 222.00
 [463] 222.00 238.00 216.00 248.00 265.00 260.00 220.00 250.00 243.00 217.50 238.00 300.86 292.00 238.71
 [477] 243.71 232.00 259.86 242.00 223.57 219.14 241.00 264.00 247.00 241.00 265.00 274.67 270.00 239.00
 [491] 303.00 242.75 212.00 212.00 293.00 222.00 222.00 232.00 275.00 260.00 230.86 218.00 270.00 260.00
 [505] 219.50 272.00 230.30 215.00 219.00 293.33 253.25 311.00 217.71 240.00 233.10 289.60 214.00 240.00
 [519] 252.00 252.00 232.00 229.00 229.00 212.00 234.67 242.00 213.00 212.54 216.93 338.00 230.00 229.00
 [533] 302.00 243.16 342.29 274.45 244.00 216.25 234.56 219.50 290.67 290.67 260.00 255.00 226.00 255.00
 [547] 225.00 306.00 232.91 303.00 249.50 250.00 217.50 237.34 245.00 237.00 289.00 229.00 229.00 278.00
 [561] 289.50 317.00 353.00 257.00 315.00 244.00 265.00 244.00 212.00 220.00 212.00 212.00 230.00 248.00
 [575] 278.57 225.00 219.00 315.00 234.00 245.00 277.00 270.71 277.00 244.00 225.00 213.00 228.00 292.00
 [589] 237.00 305.00 237.00 299.00 224.00 224.00 232.00 232.00 245.00 262.00 292.00 224.00 213.33 215.33
 [603] 211.30 244.00 221.60 255.00 212.16 224.16 245.00 212.16 255.00 221.00 245.00 220.00 267.86 245.00
 [617] 221.00 220.00 266.50 292.00 222.00 212.14 222.00 292.00 257.00 249.00 229.50 279.50 310.00 245.00
 [631] 257.00 315.00 252.00 224.44 278.00 315.00 220.00 287.00 225.00 237.50 244.00 363.00 363.00 248.00
 [645] 220.00 246.00 225.00 305.00 219.29 244.00 242.10 229.33 266.60 266.60 257.00 252.00 311.70 294.86
 [659] 219.00 212.17 250.00 230.00 229.00 248.00 299.00 309.10 257.00 212.00 224.00 218.00 220.00 229.17
 [673] 266.30 228.57 227.80 230.00 230.00 230.00 218.00 218.18 231.00 301.43 258.27 215.71 242.25 315.71
 [687] 244.72 450.00 264.00 300.40 300.40 253.33 241.60 257.34 213.75 229.00 225.00 213.75 215.67 213.33
 [701] 266.00 282.29 230.00 250.00 270.00 269.50 212.50 212.50 230.00 283.60 223.75 378.00 244.00 358.75
 [715] 220.00 328.00 230.00 252.00 330.00 220.00 214.00 214.00 259.33 214.00 230.00 292.00 250.00 269.00
 [729] 298.00 378.00 230.00 310.00 262.00 230.00 230.00 231.00 220.00 239.00 323.00 252.00 297.00 269.00
 [743] 239.00 239.00 239.00 220.00 239.00 225.60 259.00 303.70 218.00 230.00 250.00 294.50 216.00 275.00
 [757] 240.00 378.00 240.00 220.00 220.00 317.00 262.00 298.00 248.33 212.00 220.00 252.00 230.00 262.00
 [771] 292.00 292.00 220.00 215.00 216.00 231.84 297.00 230.00 259.00 258.00 392.00 294.50 280.00 273.25
 [785] 230.00 222.00 230.00 230.00 270.00 264.29 250.00 231.60 230.00 252.00 250.00 259.43 262.00 229.52
 [799] 297.38 230.00 300.00 232.33 303.20 340.00 230.00 256.57 262.00 212.00 225.50 228.00 232.00 232.00
 [813] 230.00 225.33 261.00 230.00 437.00 249.00 219.60 230.00 225.00 230.00 264.00 230.00 388.00 215.00
 [827] 249.00 274.50 262.00 221.00 254.00 310.00 240.00 262.00 297.00 308.00 246.80 259.00 244.00 230.00
 [841] 224.33 230.00 230.00 273.00 245.00 224.00 231.43 270.00 230.00 310.00 230.00 249.00 230.00 229.00
 [855] 230.00 252.00 230.00 230.00 264.00 308.00 215.00 215.00 262.00 241.00 289.80 378.00 338.00 311.50
 [869] 212.00 318.00 240.00 289.80 247.00 217.60 222.00 217.60 222.00 290.00 260.00 238.57 270.00 290.00
 [883] 217.50 270.00 217.50 237.50 213.00 230.00 230.00 282.00 262.00 220.00 270.00 249.00 330.00 250.00
 [897] 265.00 257.60 257.60 250.00 231.60 227.22 234.00 212.00 238.00 250.00 218.00 340.00 214.84 248.00
 [911] 238.00 230.00 235.71 230.00 247.20 227.10 244.00 244.00 270.00 250.00 268.00 236.00 343.00 254.00
 [925] 230.00 289.60 255.45 255.45 234.62 260.00 270.00 340.00 270.00 244.00 297.00 378.00 295.50 242.00
 [939] 232.00 230.00 240.91 278.14 260.00 280.00 230.00 237.50 319.00 268.00 225.60 270.00 216.67 222.00
 [953] 225.71 238.57 230.00 252.00 240.00 255.00 220.00 239.14 229.43 216.67 250.00 260.00 270.00 249.00
 [967] 229.00 331.33 214.00 251.43 259.00 249.00 235.00 240.00 243.33 303.33 295.67 295.67 220.00 242.00
 [981] 342.17 262.38 284.86 251.43 340.86 251.00 299.43 294.29 293.86 245.30 290.00 290.00 242.00 229.00
 [995] 244.16 222.00 295.00 289.80 253.80 230.00
 [ reached getOption("max.print") -- omitted 2793 entries ]

> length(boxplot.stats(hotel_booking_data$adr)$out)
[1] 3793
> boxplot.stats(hotel_booking_data$required_car_parking_spaces)
$stats
[1] 0 0 0 0 0

$n
[1] 119390

$conf
[1] 0 0

$out
   [1] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
  [51] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [101] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [151] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [201] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [251] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [301] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [351] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [401] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [451] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1
 [501] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2
 [551] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [601] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [651] 2 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [701] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [751] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [801] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [851] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [901] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
 [951] 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 2 1 1 1 1 1 1 1 1 1 1 1 1
 [ reached getOption("max.print") -- omitted 6416 entries ]

> length(boxplot.stats(hotel_booking_data$required_car_parking_spaces)$out)
[1] 7416
> boxplot.stats(hotel_booking_data$total_of_special_requests)
$stats
[1] 0 0 0 1 2

$n
[1] 119390

$conf
[1] -0.004572704  0.004572704

$out
   [1] 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 4 3 4 3 4 3 3 4 3 3 3 3 3 3 3 3 3 3 3 3
  [51] 3 3 4 3 3 3 3 3 3 3 3 4 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 4 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3
 [101] 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 4 3 3 3 3 3 3 3 3 4 4 3 3 3 3 3 3
 [151] 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 5 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3
 [201] 3 3 3 3 4 4 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 4 5 3 3 3 3 3 4 4 3 3 4 3 4 3 3 3 3 3 4 3 3
 [251] 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 4 3 3 3 4 3 3 3 4 3 3 3 3 3 3 3 3 3 4 4 3 3 3 4 3 3 3 3 3 3 3 3
 [301] 3 3 5 3 3 4 4 3 3 3 3 3 4 4 4 4 4 4 4 4 5 5 4 4 4 3 3 3 3 4 4 4 4 4 4 4 4 4 4 4 3 3 3 3 3 3 3 3 3 4
 [351] 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 4 3 3 3 3 3 4 3 4 3 3 3 3 3 4 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3
 [401] 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 4 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 4 3 3 3 3 3 3 3 3 3 3
 [451] 3 3 3 3 3 3 4 4 3 3 3 3 3 3 3 3 3 3 4 3 3 3 3 4 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 4 3 4 4 3 3 3 3 3 3
 [501] 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 5 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 4 3 3 3 3 3 3
 [551] 3 3 3 4 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 4 3 5 3 3 3 3 3 3 3 5 3 3 3 3 3 3 3 3 3 3 3 3
 [601] 3 3 3 3 4 4 3 3 3 3 3 4 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 4 3 4 3 3 3 3 3 3 3 4 3 3 5 3 4
 [651] 4 4 4 4 5 3 3 3 3 3 4 3 3 3 3 3 3 3 3 3 3 3 3 3 4 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3
 [701] 3 3 3 4 4 4 4 3 3 3 3 3 3 3 3 4 3 3 3 3 3 3 3 3 3 3 5 3 3 3 3 3 3 4 3 3 3 4 3 3 3 3 3 3 3 3 3 3 3 4
 [751] 3 3 3 3 3 3 3 3 3 3 3 3 3 3 4 4 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 4 3 3 3 4 3 3 3 3 3 4 3 4 3 3 3 3 4 3
 [801] 3 3 3 3 3 3 3 3 3 3 3 3 3 4 4 4 3 3 3 3 3 4 3 4 4 3 3 4 3 3 3 3 3 3 3 3 3 3 3 3 3 3 4 3 3 3 3 3 3 3
 [851] 3 3 3 3 3 3 3 4 4 4 3 3 3 3 3 3 4 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3
 [901] 3 3 3 3 3 3 3 4 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 4 3 3 3 3 4 3 3 4 3 3 4 5 4 3 3 3 3 4 3 4 5 4 3 3 3 3
 [951] 3 4 3 3 3 4 3 3 3 3 4 3 3 4 3 3 4 3 3 3 3 3 3 3 4 4 4 4 3 4 4 4 4 3 3 3 3 3 3 3 3 4 3 3 4 4 4 4 3 3
 [ reached getOption("max.print") -- omitted 1877 entries ]

> length(boxplot.stats(hotel_booking_data$total_of_special_requests)$out)
[1] 2877
> # 3.4 Transformamos los datos atipicos (outliers)
> transformar_outliers <- function(data, columna) {
+   # 3.4.1 Calculamos los cuartiles e IQR
+   Q1 <- quantile(data[[columna]], 0.25)
+   Q3 <- quantile(data[[columna]], 0.75)
+   IQR <- Q3 - Q1
+   
+   # 3.4.2 Calcula los límites superior e inferior
+   limite_superior <- Q3 + 1.5 * IQR
+   limite_inferior <- Q1 - 1.5 * IQR
+ 
+   data[[columna]][data[[columna]] > limite_superior] <- limite_superior
+   data[[columna]][data[[columna]] < limite_inferior] <- limite_inferior
+   
+   return(data)
+ }
> hotel_booking_data <- transformar_outliers(hotel_booking_data, 'lead_time')
> hotel_booking_data <- transformar_outliers(hotel_booking_data, 'stays_in_weekend_nights')
> hotel_booking_data <- transformar_outliers(hotel_booking_data, 'stays_in_week_nights')
> hotel_booking_data <- transformar_outliers(hotel_booking_data, 'adults')
> hotel_booking_data$children <- pmin(pmax(hotel_booking_data$children, 0), 10)
> hotel_booking_data$babies <- pmin(pmax(hotel_booking_data$babies, 0), 10)
> hotel_booking_data <- transformar_outliers(hotel_booking_data, 'is_repeated_guest')
> hotel_booking_data <- transformar_outliers(hotel_booking_data, 'previous_cancellations')
> hotel_booking_data <- transformar_outliers(hotel_booking_data, 'previous_bookings_not_canceled')
> hotel_booking_data <- transformar_outliers(hotel_booking_data, 'booking_changes')
> hotel_booking_data <- transformar_outliers(hotel_booking_data, 'days_in_waiting_list')
> hotel_booking_data <- transformar_outliers(hotel_booking_data, 'adr')
> hotel_booking_data$required_car_parking_spaces <- pmin(pmax(hotel_booking_data$required_car_parking_spaces, 0), 8)
> hotel_booking_data <- transformar_outliers(hotel_booking_data, 'total_of_special_requests')
```
##### Visualizar Datos
###### ¿Cuántas reservas se realizan por tipo de hotel? o ¿Qué tipo de hotel prefiere la gente?
- **Variables en uso**: hotel.

En primer lugar, convierte la columna `hotel` en un factor para tratar las categorías de hoteles como niveles discretos. Luego, se calcula una tabla de frecuencia que muestra cuántas reservas hay para cada tipo de hotel. Esta información se almacena en un marco de datos llamado `reservas_df`, cuyas columnas se etiquetan como `Tipo_de_Hotel` y `Numero_de_Reservas` para mayor claridad. A continuación, se genera un gráfico de barras que representa el número de reservas por tipo de hotel, con detalles de formato como colores y límites del eje y. Además, se identifica el tipo de hotel más preferido y se imprime en la consola junto con el resumen de las reservas por tipo de hotel. En resumen, este código procesa y visualiza datos de reservas de hoteles, identificando el tipo de hotel más preferido en función de las reservas acumuladas.

```r
### 4.VISUALIZAR DATOS
# 4.1 ¿Cuántas reservas se realizan por tipo de hotel? o ¿Qué tipo de hotel prefiere la gente?
hotel_booking_data$hotel <- as.factor(hotel_booking_data$hotel)
reservas_por_tipo_hotel <- table(hotel_booking_data$hotel)

reservas_df <- as.data.frame(reservas_por_tipo_hotel)
names(reservas_df) <- c("Tipo_de_Hotel", "Numero_de_Reservas")

barplot(reservas_df$Numero_de_Reservas, 
        names.arg = reservas_df$Tipo_de_Hotel,
        main = "Número de Reservas por Tipo de Hotel",
        xlab = "Tipo de Hotel",
        ylab = "Número de Reservas",
        col = "blue",
        border = "black",
        ylim = c(0, max(reservas_df$Numero_de_Reservas) * 1.2))

hotel_preferido <- names(reservas_por_tipo_hotel)[which.max(reservas_por_tipo_hotel)]
print(reservas_df)
print(paste("El tipo de hotel preferido es:", hotel_preferido))
```
###### ¿Está aumentando la demanda con el tiempo?
- **Variables en uso**: arrival_date_month.

En primer lugar, se convierte la columna `arrival_date_month` en un factor con niveles que corresponden a los nombres de los meses para asegurar una representación adecuada en los gráficos. Luego, se calcula una tabla de frecuencia llamada `reservas_por_mes`, que resume cuántas reservas se realizaron en cada mes, brindando una visión de la demanda a lo largo del tiempo. Esta información se organiza en un marco de datos llamado `reservas_mes_df` con columnas etiquetadas como `Mes` y `Numero_de_Reservas` para facilitar su manipulación. A continuación, se crea un gráfico de líneas que muestra la evolución del número de reservas a lo largo del año, utilizando el eje x para representar los meses y el eje y para mostrar el número de reservas en un tono azul. Finalmente, se imprimen los valores de la tabla de frecuencia `reservas_por_mes` en la consola, proporcionando una visión detallada de las reservas realizadas en cada mes.

```r
# 4.2 ¿Está aumentando la demanda con el tiempo?
hotel_booking_data$arrival_date_month <- factor(hotel_booking_data$arrival_date_month, 
                                                levels = c("January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"))

reservas_por_mes <- table(hotel_booking_data$arrival_date_month)

reservas_mes_df <- as.data.frame(reservas_por_mes)
names(reservas_mes_df) <- c("Mes", "Numero_de_Reservas")

plot(reservas_mes_df$Numero_de_Reservas, type = "o", col = "blue",
     xaxt = "n",
     main = "Demanda de Reservas a lo largo del Tiempo",
     xlab = "Mes",
     ylab = "Número de Reservas")
axis(1, at = 1:12, labels = reservas_mes_df$Mes)

print(reservas_por_mes)
```
###### ¿Cuándo se producen las temporadas de reservas: alta, media y baja?
- **Variables en uso**: arrival_date_month, is_canceled. 

Primero, se utiliza la función `aggregate()` para agrupar y contar el número de reservas por mes de llegada. Luego, se reorganiza el resultado en orden descendente, priorizando los meses con más cancelaciones. A continuación, se asigna a `temporada_alta` el primer mes en el conjunto de datos, representando la temporada con el mayor número de reservas. Para determinar la temporada media, se calcula el mes en el centro del conjunto de datos, asegurando un índice entero mediante redondeo hacia arriba. Por último, `temporada_baja` se obtiene del último mes en la lista, indicando la temporada con el menor número de reservas. Los resultados se presentan en la consola de RStudio para su visualización.

```r
# 4.3 ¿Cuándo se producen las temporadas de reservas: alta, media y baja?
reservas_por_mes <- aggregate(is_canceled ~ arrival_date_month, data = hotel_booking_data, FUN = length)
reservas_por_mes <- reservas_por_mes[order(reservas_por_mes$is_canceled, decreasing = TRUE), ]


temporada_alta <- head(reservas_por_mes$arrival_date_month, n = 1)
temporada_media <- reservas_por_mes$arrival_date_month[ceiling(length(reservas_por_mes$arrival_date_month)/2)]
temporada_baja <- tail(reservas_por_mes$arrival_date_month, n = 1)

meses <- month.name

temporada_alta_texto <- meses[temporada_alta]
temporada_media_texto <- meses[temporada_media]
temporada_baja_texto <- meses[temporada_baja]

cat("Temporada Alta:", temporada_alta_texto, "\n")
cat("Temporada Media:", temporada_media_texto, "\n")
cat("Temporada Baja:", temporada_baja_texto, "\n")
```
###### ¿Cuándo es menor la demanda de reservas?
- **Variables en uso**: hotel, arrival_date_month.

Primero, utiliza la función `aggregate()` para calcular cuántas reservas se hicieron en cada mes, agrupando los datos por el mes de llegada. El resultado se almacena en un objeto llamado `reservas_por_mes`, que contiene los nombres de los meses y la cantidad de reservas correspondiente. Luego, se determina el mes con la menor demanda de reservas al encontrar el valor mínimo en la columna de recuento. El nombre de ese mes se guarda en la variable `mes_menor_demanda`. Finalmente, se imprime en la consola un mensaje que identifica el mes con la menor cantidad de reservas.

```r
# 4.4 ¿Cuándo es menor la demanda de reservas?
reservas_por_mes <- aggregate(hotel_booking_data$hotel, 
                              by = list(Mes = hotel_booking_data$arrival_date_month), FUN = length)

mes_menor_demanda <- reservas_por_mes[which.min(reservas_por_mes$x), "Mes"]

print(paste("El mes con menor demanda de reservas es:", mes_menor_demanda))
```
###### ¿Cuántas reservas incluyen niños y/o bebes?
- **Variables en uso**: children, babies.

En primer lugar, se crea un nuevo conjunto de datos llamado `reservas_con_ninos_bebes` utilizando la función `subset()`, el cual contiene las reservas donde al menos un niño o bebé está involucrado, basándose en las columnas `children` o `babies`. Luego, se calcula la cantidad total de estas reservas utilizando `nrow()` y se almacena en la variable `cantidad_reservas_con_ninos_bebes`. Finalmente, se imprime un mensaje informativo en la consola, destacando el número de reservas que incluyen niños y/o bebés, lo que proporciona información útil para la planificación de servicios orientados a familias con niños pequeños que viajan.

```r
# 4.5 ¿Cuántas reservas incluyen niños y/o bebes?
reservas_con_ninos_bebes <- subset(hotel_booking_data, children > 0 | babies > 0)
cantidad_reservas_con_ninos_bebes <- nrow(reservas_con_ninos_bebes)

print(paste("El número de reservas que incluyen niños y/o bebés es:", cantidad_reservas_con_ninos_bebes))
```
###### ¿Es importante contar con espacios de estacionamiento?
- **Variables en uso**: required_car_parking_spaces.

En primer lugar, se crea un nuevo conjunto de datos llamado `reservas_con_estacionamiento`, que contiene las reservas que especifican la necesidad de al menos un espacio de estacionamiento. Luego, se determina el número total de reservas en el conjunto de datos original `hotel_booking_data`. A continuación, se calcula el porcentaje de reservas que requieren estacionamiento dividiendo el número de reservas con esta condición entre el total de reservas y multiplicando el resultado por 100. Finalmente, se imprime en la consola un mensaje que muestra este porcentaje, redondeado a una decimal, proporcionando información relevante sobre la proporción de reservas que dependen de espacios de estacionamiento para su alojamiento.

```r
# 4.6 ¿Es importante contar con espacios de estacionamiento?
reservas_con_estacionamiento <- subset(hotel_booking_data, required_car_parking_spaces > 0)
total_reservas <- nrow(hotel_booking_data)

porcentaje_estacionamiento <- (nrow(reservas_con_estacionamiento) / total_reservas) * 100

print(paste("Porcentaje de reservas con estacionamiento:", round(porcentaje_estacionamiento, 1), "%"))
```
###### ¿En qué meses del año se producen más cancelaciones de reservas?
- **Variables en uso**: arrival_date_month, reservation_status.

En primer lugar, se crea un conjunto de datos llamado `reservas_canceladas` que incluye solo las reservas con estado `Canceled` (canceladas). Luego, se calcula una tabla de frecuencia denominada `cancelaciones_por_mes` que resume la cantidad de cancelaciones mensuales. Esta información se organiza en un marco de datos llamado `cancelaciones_mes_df` con columnas etiquetadas como `Mes` y `Numero_de_Cancelaciones` para una mayor claridad. Se genera un gráfico de barras que muestra el número de cancelaciones por mes, con etiquetas de ejes, colores y otros detalles de formato. Finalmente, se imprime en la consola la tabla de frecuencia `cancelaciones_por_mes`, lo que proporciona una visión detallada de las cancelaciones de reservas en cada mes. En conjunto, este código ofrece una representación visual y cuantitativa de las cancelaciones de reservas a lo largo del año, permitiendo la identificación de patrones y tendencias.

```r
# 4.7 ¿En qué meses del año se producen más cancelaciones de reservas?
reservas_canceladas <- subset(hotel_booking_data, reservation_status == "Canceled")

cancelaciones_por_mes <- table(reservas_canceladas$arrival_date_month)

cancelaciones_mes_df <- as.data.frame(cancelaciones_por_mes)
names(cancelaciones_mes_df) <- c("Mes", "Numero_de_Cancelaciones")

barplot(cancelaciones_mes_df$Numero_de_Cancelaciones, 
        names.arg = cancelaciones_mes_df$Mes,
        main = "Cancelaciones de Reservas por Mes",
        xlab = "Mes",
        ylab = "Número de Cancelaciones",
        col = "blue",
        border = "black",
        ylim = c(0, max(cancelaciones_mes_df$Numero_de_Cancelaciones) * 1.2))

print(cancelaciones_por_mes)
```
## Conclusiones
## Referencias Bibliográfica
- Antonio, N., Almeida, A., & Nunes, L. (2019). Hotel booking demand datasets. Science Direct, 22, 41 - 49. Recuperado de: https://www.sciencedirect.com/science/article/pii/S2352340918315191 [Consulta: 18/09/2023]
