# Exemple de README
Això és un [enllaç](https://google.com) i això són **negretes** i *cursiva* i ara ve una llista:

* hola
* que
* tal

Potser vols una llista numerada:

1. tot
2. bé
3. gràcies

## Un títol de nivell 2

I un troç de codi

    apt-get install virus

O aixó també és un troç de codi:

```python
a = 2 + 3
```
També pots integrar-ho `a=2` al paràgraf.

---

# Desplegament del nostre entorn virtual
## Instal·lacio de pip

Començarem instal·lant el paquet pip. Aquest s'empelara per instal·lar al nostre entron virtual que crearem a cotinuació.

```

apt install pip

```



## Creacio del nostre entorn virtual
**Els seguents comandaments seran executats en python.**
1. Comencem creant el nostre entron vitual on treballarem. Per poder fer aixo executarem el comandament:

```

python3 -m venv .venv

```

2. A continuacio activarem l'entorn virtual.Per poder fer aixo executarem el comandament:
```

source .venv/bin/activate

```
3. Un cop executada aquesta comanda podrem observar si tenim l'entorn activar per el nostre promt.


**(.venv) tarda@PC-AULA:~/Documents/ASIX_M04/UF3/Progecte/jmirinformatica 1asixdaw-m0**


### Instal·lacio de tots els programes requerits
Si desitgem instal·lar tots els programes d'alun altre entorn virtual, pordem emplear el programa instal·lat anteriorment ( **pip**) 

per aixó executarem la seguent comanda

```

pip install -r requeriments.txt 

```

En aquest cas estem instal·lant tos els programes indicats al arxiu requirements.txt (Aquesta es una de grans util·litats de **pip**)

Un cop fet aixó haurem instal·lat **flask** 

## Flask

La funcionalitat de **flask** en el nostre cas, sera per crer servidors locals on provorem que l'aplicacio que hem creat s'executa i funciona correctament.

Per crear aquest servidor de provers, accionarem la seguent comanda.
```
flask run --debug
```

En cas que s'hagi accionat correctament, ja podrem accedir al servidor. Per fer aixó , accedirem a l'**IP** que ens indiqui **flask** en el moment d'accionar el programa. 
En el nostre cas serà **http://127.0.0.1:5000**


Ens sortira una imatge semblant a la seguent
![Captura de pantalla de 2024-05-03 19-01-47](https://github.com/dcanomASIX1/ProgecteM04_Flask-rss/assets/165805335/5e204b54-7864-4648-ba31-49ede341f8fd)


Si deitges veure mes informacio sobre **FLASK** pots visitar el seguent enllaç https://flask-es.readthedocs.io/

# Iniciar l'aplicatiu
1. Comencem aciconant l'entorn vitual .venv
2. Accionemt **FLASK**

# Mode remot o local
<<<<<<< HEAD

# Bootstrap
Framework,clase de libreria predefinida, que permite la enmaquetacion mediante
Permite trabajar con:
- CSS
- html
- javascript

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
Sirve para añdir bordes a las etiquetas 
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


per mes informacio visitar https://www.w3schools.com/bootstrap5/bootstrap_navbar.php
## Tables

classs .table en la  etiqueta ".table"

https://getbootstrap.com/docs/5.3/content/tables/

.Table-stripped --> colorea la tabla

.table-hover --> añade indicaciones al marcar con el raton sobre la tabla

.table-bordered --> Añade bordes a las tablas 