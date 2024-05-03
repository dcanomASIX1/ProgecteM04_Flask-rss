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


# Iniciar l'aplicatiu
1. Comencem aciconant l'entorn vitual .venv
2. Accionemt **FLASK**

# Mode remot o local
