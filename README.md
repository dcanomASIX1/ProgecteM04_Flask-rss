# Despliegue de nuestro entorno virtual
## Instalación de pip


Empezaremos instalando el paquete pip. Este se empelará para instalar a nuestro entrono virtual que crearemos a cotinuación.

```

apt install pip

```



## Creación de nuestro entorno virtual
**Los siguientes comandos serán ejecutados en python.**
1. Empezamos creando nuestro entron vitual donde trabajaremos. Para poder hacer esto ejecutaremos el mando:

```

python3 -m venv .venv

```

2. A continuación activaremos el entorno virtual.Para poder hacer esto ejecutaremos el mando:dament:
```

source .venv/bin/activate

```
3. Una vez ejecutado este pedido podremos observar si tenemos el entorno activado por nuestro promt.


**(.venv) tarda@PC-AULA:~/Documents/ASIX_M04/UF3/Progecte/jmirinformatica 1asixdaw-m0**


### Instalación de todos los programas requeridos
Si deseamos instalar todos los programas de otro entorno virtual, podemos emplear el programa instalado anteriormente ( **pip**)

por eso ejecutaremos el siguiente pedido

```

pip install -r requeriments.txt 

```

En este caso estamos instalando todos los programas indicados en el archivo requirements.txt (Esta es una de grandes utilidades de **pip**)

Una vez hecho esto habremos instalado **flask**

## Flask
La funcionalidad de **flask** en nuestro caso, será para crear servidores locales donde probaremos que la aplicación que hemos creado se ejecuta y funciona correctamente.

Para crear este servidor de proverso, accionaremos el siguiente pedido.
```
flask run --debug
```
En caso de que se haya accionado correctamente, ya podremos acceder al servidor. Para ello, accederemos al **IP** que nos indique **flask** en el momento de accionar el programa.
En nuestro caso será **http://127.0.0.1:5000**


Nos saldrá una imagen parecida a la siguiente
![Captura de pantalla de 2024-05-03 19-01-47](https://github.com/dcanomASIX1/ProgecteM04_Flask-rss/assets/165805335/5e204b54-7864-4648-ba31-49ede341f8fd)


Si deseas ver más información sobre **FLASK** puedes visitar el siguiente enlace https://flask-es.readthedocs.io/

### Jinja2
És el motor que emplea flask para hacer de "traductor" entre el app.py( El archivo principal de python ) y el HTML.
Este emplea variables las quales de declaran de la siguiente forma --> {{ variable }}
Ademas se pueden emplear otras estructuras de programacion como: if o for

-**if**
```

    {% if (edat >= 18) %}
        <h3>{{nom}} és major d'edat</h3>
    {% else %}
        <h3>{{nom}} és menor d'edat</h3>
    {% endif %}

```
-**for**
```
    {% for i in range(edat) %}
        <p>No té {{i}} anys</p>
    {% endfor %}

```
#### Traspaso de variables en jinja
Las variables en un principio se obtendran del archivo app.py. Cada funcion, es activada al buscar la ruta indicada en su app.route. Dentro de cada funcion, se declararan las variables de la misma y de donde se obtienen, existen varias opciones como podrian ser : obtenerlas de un formulario anterior o que fuesen predeterminadas, etc.
A continuacion, se emplea el metodo return. En este se indica la plantilla que sera renderizada, ademas de las variables que portara la plantilla renderizada i la variable de la funcion respectivamente.

**ej**

```

@app.route("/demo4") ---> Ruta mediante la qual la función se activa
def demo4(): ---> Nombre de la función
    nom = request.args.get('nom', default = "Desconegut/a", type = str) --->variable nom de la función
    edat = request.args.get('edat', default = 0, type = int) ---> --->variable edat de la función
    return render_template("exemples/demo/edat.html", nom = nom, edat = edat) ---> indicamos la plantilla que renderizamos, además de la variable de la plantilla y la variable de la funcion a la que hace referencia respectivamente


```

finalmente tendiramos la plantilla correspondiente con sus variables . 
En este caso seria:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Edat</title>
</head>
<body>
    <h1>Pàgina de {{nom}}</h1>
    {% if (edat >= 18) %}
        <h3>{{nom}} és major d'edat</h3>
    {% else %}
        <h3>{{nom}} és menor d'edat</h3>
    {% endif %}

    {% for i in range(edat) %}
        <p>No té {{i}} anys</p>
    {% endfor %}
    
    <p>Té {{edat}} anys!!!</p>

</body>
</html>


```

# Pasos a seguir para iniciar el aplicativo

1. Empezamos aciconando el entorno vitual .venv
2. Accionem **FLASK**
# Mode remot o local
Para cambiar entre el modo local(Empleando el RSS descargado) o el modo remoto (accedemos al RSS desdde la URL). Ejecutamos las siguientes funciones del archivo app.py
```
@app.route('/lavanguardia/<seccio>')
def lavanguardia(seccio):
    rss = get_rss_lavanguardia(seccio)
    return render_template("lavanguardia.html", rss = rss)

def get_rss_lavanguardia(seccio):
    # MODE REMOT: versió on descarrega l'XML de la web
    # xml = f"https://www.lavanguardia.com/rss/{seccio}.xml"
    
    # MODE LOCAL: versió que fa servir l'XML descarregat
    xml = f"./rss/lavanguardia/{seccio}.xml"
    
    rss = feedparser.parse(xml)
    return rss

```

La primera sera  llamada  al clicar en la pagina deseada cogiendo el archivo RSS mediante la funcion **get_rss_lavanguardia(seccio)**. Al llamar a esta segunda función, esta sera la que coja al archivo RSS. Dependiendo del que este comentado escogera uno o el otro.

Cabe recalcar dos cosas
1. No se puedem emplear los dos metodos a la vez, **se debe tener siemre almenos 1 metodo comentado**
2. No todos los enlaces a RSS son iguales pueden variar dependiendo del diario asi que ten cuidado a la hora de indicarlos

# Bootstrap
Framework,clase de libreria predefinida, que permite la enmaquetacion mediante
Permite trabajar con:
- CSS
- html
- javascript
A continuacio veremos varias de sus utilidades, además de como aplicarlo
## Como aplicarlo
1. Cargamos CSS de bootstrap en el heading
2. Al finalizar el html añadimos el java script de bootstrap
**ej de estructura base**
```
<!doctype html>
<html lang="ca">

<head>
    <!-- Meta tags necessaris -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- CSS del framework bootstrap -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet"
        integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">

    <title>Estructura inicial</title>
</head>

<body>

    <p>Pàgina amb bootstrap, tot i que no vegis res especial</p>

    <!-- JavaScript del framework bootstrap -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"
        integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz"
        crossorigin="anonymous"></script>
</body>

</html>

```

## Containers de bootstrap
- Containers responsives
    hay dos tipos
    1. Normal(Te ocupa margenes y te lo centra)
    2. Fluid (Ocupa el 100% de la pantalla)


El container te deja un margen dependiendo del tamaño de la pantaña, este varia dependiendo del tamaño de la pantalla, para mas informacion visitar el enlace.
https://getbootstrap.com/docs/5.3/layout/containers/
**ej.**
```
    <div class="container-lg">
        <h1>container-lg!</h1>
        <p>I aquest és un container normal</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Vitae impedit rerum consequuntur, non dicta
            perferendis harum laborum quae fugiat. Sequi explicabo labore ad blanditiis, error consequatur assumenda a
            delectus porro.</p>
    </div>
```


## Viewport meta
Elemento del header que adapta los containers al tamaño de la pantalla
```
<meta name="viewport" content="width=device-width, initial-scale=1">
```

## Control de colores
las etiquetas para el control de colores son : **.text-<'escrivim la clase desitjada'>**
**ej**
```
<div class="container bg-secondary text-bg-secondary">
```
Si deseas cambiar las clases predefinidas puesdes modificar el archivo SAS

en caso de queres modivicar el fondo añadimos un background **bg-<'nombredecolor'>**

**ej**
```
<div class="container bg-secondary text-bg-secondary">
```

para mas informacion visitar 
 https://getbootstrap.com/docs/5.3/utilities/colors/

 ## Padding Y Margin
 clases margin = m
 clases padding = p
añadimos la letra al final de la clase con un guion y el numero deseado 
p-2

 **ej**

 ```
 <div class="container bg-secondary text-bg-secondary mt-5 p-2">
 
 ```

 La letra acompañante en este caso la **T** , indica la dirreccion donde se genera, en este caso seria un **margin top**

 sertian

 t --> arriba
 b --> abajo
 s --> izquierda
 e --> derecha

 los numeros van del 1-5 siendo el 5 el mas elevado

 ## Text
Subclases especiales predefinidas del H1 al H6
.small --> PAra texto pequeño
.mark --> PAra marcar texto
.Text-center --ZPAra centrar el texto

y muchos mas existentes

para mas informacion visitar:
https://getbootstrap.com/docs/5.3/content/typography/

 ## Borders
Sirve para ñadir bordes a las etiquetas 
```

<span class="border"></span>
<span class="border-top"></span>
<span class="border-end"></span>
<span class="border-bottom"></span>
<span class="border-start"></span>
```
**ej**

```
    <div class="container mt-5 p-2 border border-danger">
        <h1>container-sm</h1>
        <p>I aquest és un container normal</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Vitae impedit rerum consequuntur, non dicta
            perferendis harum laborum quae fugiat. Sequi explicabo labore ad blanditiis, error consequatur assumenda a
            delectus porro.</p>
    </div>
```


 ## Grid
12 columnas predefinidas 
- **Row** para las filas
Dentro de las columnas añadimos **col** para las columnas

Si se indican mas columnas de las existetnes las sobrantes iran en la proxima linea

**Ejemplo de aplicacion**

```

<div class="col-md-6 col-lg-4 col-xl-3 border">
    Banana
</div>

```
## Navbar
Conocidas como barras de navegacion
Etiquetas: div o nav (preferible emplear la etiqueta **nav**)
se empleara la clase bootstrap **.navbar**
.navbar-expand --> indica cuando se expande o colapsa 
.navbar-nav

**ej**

```

<nav class="navbar navbar-expand-sm bg-light">

  <div class="container-fluid">
    <!-- Links -->
    <ul class="navbar-nav">
      <li class="nav-item">
        <a class="nav-link" href="#">Link 1</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link 2</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link 3</a>
      </li>
    </ul>
  </div>

</nav>
```

en caso de logo se puede usar navbar-brand

ejemplo nav-bar simple
![image](https://github.com/dcanomASIX1/ProgecteM04_Flask-rss/assets/165805335/607b3026-d3af-4463-b6b7-a60aa5d4ce1c)



per mes informacio visitar https://www.w3schools.com/bootstrap5/bootstrap_navbar.php
## Tables

classs .table en la  etiqueta ".table"

https://getbootstrap.com/docs/5.3/content/tables/

.Table-stripped --> colorea la tabla

.table-hover --> añade indicaciones al marcar con el raton sobre la tabla

.table-bordered --> Añade bordes a las tablas 

![image](https://github.com/dcanomASIX1/ProgecteM04_Flask-rss/assets/165805335/0e55df77-1d88-4b1f-99a8-fa93f21c1197)

