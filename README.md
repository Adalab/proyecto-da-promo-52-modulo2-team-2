# Introduccion

 Sistema para analizar los artistas mas populares en los géneros de nicho de musica flamenco pop, reggae, ska y kpop entre los años 2013 a 2017 (veintena de los millennials).
 Nos contrata una productora de grandes festivales solicitando que precisan analizar los artistas mas populares en los géneros y años mencionados, ya que estos años eran los primeros en los que 
 que este sector de clientes ha acudido a grandes festivales.Nos lo solicitan a raíz de un estudio interno que les ha arrojado que en este momento tienen edad en la que cuentan con mayores 
 ingresos y pueden permitirse este tipo de eventos. Para la empresa es un target interesante de atraer.
 Desean desarrollar una gira de grandes eventos para atraerlos en masa. 

 Este proyecto implementa un sistema basico de consultas, que permite analizar la evolucón de los géneros músicales en el período e identificar cuales son los artistas y canciones mas populares en 
 los diferentes generos durante el rango de años definido.

## Como arrancar el proyecto
El proyecto inicia con un [notebook](PROYECTO_MOD2_SPOTIFY.ipynb) desde la fase de extraccion de datos 

Comienza con una función que incluye un bucle for para la extracción de datos en ambas plataformas.



### Fase de extraccion de datos

**Extraccion de datos de las Apis Spotify y Last.fm
Para acceder a la extracción de datos son necesarias credenciales de las Apis.

Ejemplo introducción credenciales:

```python
auth_manager = SpotifyClientCredentials(client_id=CLIENT_ID, client_secret=CLIENT_SECRET)
sp = spotipy.Spotify(auth_manager=auth_manager)

```python
API_KEY = ' # INTRODUCE con tu clave de API válida de Last.fm'  
BASE_URL = ' # URL base de la API de Last.fm'  
```

- **Antes de la fase de inserción de datos visualizamos la información extraída a través de un DataFrame.
  
### Fase de insercion de datos

- **Guardar la informacion recopilada en una base de datos
- **Crear el modelo de proyecto de la base de datos
- **Insertar datos
- **Limpiar los datos

   ##### ** ```En MYSQL Workbench``` 
  
   - **Crear la base de datos con sus tablas y relaciones
   - **Hemos limpiado la columna de la fecha, dejando solo el año.
   - **Se han eliminado columnas innecesarias.
   - ** 


### Fase de analisis de la informacion recopilada
- **Analisis de los resultados
- **Presentacion
  

## Estructura de Datos
- **Archivos**:Csv
- **Base de datos**:MYSQL Workbench

## Ejemplo de Uso
El sistema permite extraer artistas de distintos años y generos
- Extraer caracteristicas de los artistas en distintas plataformas
- Crear una base de datos en la que se pueda almacenar los datos extraidos
- Analizar los resultados de los datos
