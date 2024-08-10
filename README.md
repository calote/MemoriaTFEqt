
## Introducción

Este proyecto está diseñado para facilitar la redacción de un Trabajo de Fin de Grado (TFG) utilizando **Quarto**, una herramienta poderosa para la creación de documentos técnicos y científicos. Quarto permite integrar texto, código y resultados en un solo documento, lo que lo convierte en una opción ideal para estudiantes que desean presentar sus investigaciones de manera clara y profesional.

Recomendamos el uso de **RStudio** como entorno de desarrollo integrado (IDE) para trabajar con Quarto. RStudio ofrece una interfaz amigable y una serie de funcionalidades que simplifican la edición, ejecución y visualización de documentos Quarto. Con este proyecto, los estudiantes podrán centrarse en el contenido de su TFG, mientras que Quarto y RStudio se encargan de la presentación y el formato.


# Instalación o uso de la extensión Quarto: "MemoriaTFEqt"

## Instalación de la extensión

Para instalar la extensión Quarto: "MemoriaTFEqt", escribir en el terminal de RStudio o del sistema operativo:

```sh
quarto use template calote/MemoriaTFEqt
```

Responda: "Y" a la pregunta de confiar en el "author" e indique un nombre de subdirectorio, por ejemplo: "mitfg".

Cambie el nombre al fichero: "MemoriaTFEqt.Rproj", para que coincida con el del subdirectorio creado, por ejemplo: "mitfg.Rproj". A continuación, podrá abrir el proyecto RStudio asociado al hacer doble clic en el fichero "mitfg.Rproj".

Abra el fichero "_quarto.yml" para personalizar los datos para que coincidan con los de su trabajo fin de grado (TFG).

Edite los ficheros quarto de su TFG: "index.qmd", "capitulo01.Rmd", etc, y obtenga una previsualización de su trabajo ("preview") o una construcción ("render") en formato: "pdf" y "html", los cuales se encontrarán en la subcarpeta: "`_tfg`" de su proyecto.

- Para construir o "render", en la pestaña "Build" de RStudio haga clic en el botón "Render Project".

- Para previsualizar o "preview", escribir en la consola de R: `quarto::quarto_preview(file = "index.qmd")` (instale previamente el paquete R "quarto" o `install.packages("quarto")`). 


## Uso de la extensión en una carpeta o proyecto RStudio

Desde el proyecto Quarto o directorio del documento, ejecutar el siguiente comando desde el terminal:

```sh
quarto install extension calote/MemoriaTFEqt
```

Cree el fichero "`_quarto.yml`" y añada los elementos básicos consultando el fichero "`_quarto.yml`" de este repositorio.




## Requisitos para usar la extensión

1. Instalar R (<https://www.r-project.org>) y RStudio Desktop (<https://posit.co/products/open-source/rstudio/>).

2. RStudio instala "Quarto" en nuestro ordenador. Pero se puede instalar desde la página oficial: <https://quarto.org/docs/download/>.

3. Se debe tener instalada alguna distribución de "TeX" en nuestro ordenador: "TinyTeX", ...

Si no se tiene ninguna instalada, se recomienda instalar "TinyTeX". A continuación se indican 2 métodos alternativos para instalarlo en su ordenador.

- **Método 1**: desde la consola de R ejecutar las siguientes instrucciones:

```r
install.packages("tinytex")
tinytex::install_tinytex()
```


- **Método 2**: desde el terminal (de RStudio o sistema operativo) ejecutar el siguiente comando:

```sh
quarto install tinytex
```

# Uso de la extensión (plantilla o template) Quarto: "MemoriaTFEqt"

## Previsualización rápida

Para mostrar una previsualización del contenido del TFE, ejecute en la consola la siguiente función:

``` r
quarto::quarto_preview(file = "index.qmd")
```

**Nota:** si quiere que se muestre en la previsualización en el formato "html", adelantar en el fichero "`_quarto.yml`", la llamada a `MemoriaTFEqt-html: default`.

Si se quiere previsualizar en el formato "pdf", colocar en el fichero "`_quarto.yml`", la llamada a `MemoriaTFEqt-html: default` al final.

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


# Cómo citar este proyecto

```bibtex
@misc{Luque2023,
  author = {Luque-Calvo, P.L.},
  title = {Extensión Quarto: MemoriaTFEqt},
  year = {2023},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/calote/MemoriaTFEqt}}
}
```
