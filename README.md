# Instalación o uso de la extensión Quarto: "memoriatfeq"

## Instalación de la extensión

Para instalar la extensión Quarto: "memoriatfeq" en el terminal (de RStudio o del sistema operativo) escribir:

```sh
quarto use template calote/memoriatfeq
```

## Uso de la extensión en una carpeta o proyecto RStudio

Desde el proyecto Quarto o directorio del documento, ejecutar el siguiente comando desde el terminal:

```sh
quarto install extension calote/memoriatfeq
```


## Requisitos para usar la extensión

Se debe tener instalada alguna distribución de "TeX" en nuestro ordenador: "TinyTeX", ...

Si no se tiene ninguna instalada, se recomienda instalar "TinyTeX".

- **Método 1**: desde la consola de R ejecutar las siguientes instrucciones:

```r
install.packages("tinytex")
tinytex::install_tinytex()
```


- **Método 2**: desde el terminal (de RStudio o sistema operativo) ejecutar el siguiente comando:

```sh
quarto install tinytex
```

# Uso de la extensión (plantilla o template) Quarto: "memoriatfeq"

## Previsualización rápida

Para mostrar una previsualización del contenido del TFE, ejecute en la consola la siguiente función:

``` r
quarto::quarto_preview(file = "index.qmd")
```

**Nota:** si quiere que se muestre en la previsualización en el formato "html", adelantar en el fichero "`_quarto.yml`", la llamada a `memoriatfeq-html: default`.

Si se quiere previsualizar en el formato "pdf", colocar en el fichero "`_quarto.yml`", la llamada a `memoriatfeq-html: default` al final.

Para detener la previsualización ejecute:

``` r
quarto::quarto_preview_stop()
```

## Configuración de los capítulos-apéndices

En el fichero "`_quarto.yml`" se indican los ficheros que componen el trabajo fin de estudios (TFE) del siguiente modo:

``` yml
  chapters:
    - index.qmd        # Prólolgo, ...
    - capitulo01.qmd   # Introducción
    - capitulo02.qmd   # Desarrollo
    - capitulo03.qmd   # Aplicación
  appendices:
    - x_apendice01.qmd
    - x_referencias.qmd
```

Se pueden

-   **añadir** nuevos capítulos o apéndices,

-   se pueden **borrar** los que no se vayan a utilizar

-   y también se pueden **comentar** (utilizando el símbolo "`#`" delante del guión) para cuando se genere la salida ("pdf" o "html") únicamente se usen los ficheros-capítulos que están sin comentar. Podría ser interesante comentar todos los capítulos salvo: "index.qmd", "x_referencias.qmd" y el capítulo en el que estemos trabajando, por ejemplo: "capitulo01.qmd".

``` yml
  chapters:
    - index.qmd        # Prólolgo, ...
    - capitulo01.qmd   # Introducción
    #- capitulo02.qmd   # Desarrollo
    #- capitulo03.qmd   # Aplicación
  appendices:
    #- x_apendice01.qmd
    - x_referencias.qmd
```



En el fichero "`_quarto.yml`" se puede utilizar una estructura más compleja, como puede verse a continuación:

``` yml
  chapters:
    - index.qmd
    - intro.qmd
    - summary.qmd
    - part: dice.qmd
      chapters:
        - basics.qmd
        - packages.qmd
    - part: "Dice 2"
      chapters:
        - basics2.qmd
        - packages2.qmd
  appendices:
    - tools.qmd
    - resources.qmd
    - references.qmd
```


