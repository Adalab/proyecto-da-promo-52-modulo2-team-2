# Introduccion
 Sistema para analizar los artistas mas populares en los generos de musica flamenco pop,reggae,ska y kpop entre los años 2013 a 2017(veintena de los millenial).Nos contrata una productora de grandes festivales que precisan analizar los artistas mas populares en los generos y años mencionados ya que estos años eran los primeros que este sector de clientes ha acudido a grandes festivales y desean desarrollar una gira de grandes festivales con estos generos para atraerlos en masa, en este momento que tienen edad en la que cuentan con mayores ingresos y pueden permitirse este tipo de eventos y para la empresa es un target interesante de atraer.

Este proyecto implementa un sistema basico de consultas, que permite identificar cuales artistas son mas populares en los diferentes generos y rango de años

## Como arrancar el proyecto
El proyecto inicia con un [notebook](PROYECTO_MOD2_SPOTIFY.ipynb) desde la fase de extraccion de datos 
```python
for track in tracks_info['tracks']:
            track_data.append({
                'genre': genre,
                'name': track['name'],
                'artists_name': ', '.join([artist['name'] for artist in track['artists']]),  # Si hay varios artistas
                'album_name': track['album']['name'],
                'album_release_date': track['album']['release_date'],
                'duration_ms': track['duration_ms'],
                'popularity': track['popularity'],
                'track_number': track['track_number'],
                'uri': track['uri']
            })


### Fase de extraccion de datos
Extraccion de datos de las Apis Spotify y Last.fm
```python
auth_manager = SpotifyClientCredentials(client_id=CLIENT_ID, client_secret=CLIENT_SECRET)
sp = spotipy.Spotify(auth_manager=auth_manager)

```python
API_KEY = 'd97c59010214fb89dd7e101407646224'  # Reemplaza con tu clave de API válida de Last.fm
BASE_URL = 'http://ws.audioscrobbler.com/2.0/'  # URL base de la API de Last.fm
```

### Fase de insercion de datos
- **Guardar la informacion recopilada en una base de datos
- **Crear el modelo de proyecto de la base de datos
_ **Crear la base de datos con sus tablas y relaciones
_ **Insertar datos
_ **Limpiar los datos

```En MYSQL Workbench``` Hemos limpiado la columna año, de tener día, mes y año, a solo años, en cada género

UPDATE flamencopop
SET año = LEFT(año, 4);
SELECT año FROM flamencopop;

UPDATE ska
SET año = LEFT(año, 4);
SELECT año FROM ska;

UPDATE reggae
SET año = LEFT(año, 4);
SELECT año FROM reggae;

UPDATE kpop
SET año = LEFT(año, 4);
SELECT año FROM kpop;

### Fase de analisis de la informacion recopilada
- **Analisis de los resultados
_ **Presentacion
  

## Estructura de Datos
- **Archivos**:Csv
- **Base de datos**:MYSQL Workbench

## Ejemplo de Uso
El sistema permite extraer artistas de distintos años y generos
- Extraer caracteristicas de los artistas en distintas plataformas
- Crear una base de datos en la que se pueda almacenar los datos extraidos
- Analizar los resultados de los datos
