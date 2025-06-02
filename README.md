# pgf-es - Una traducción al español del manual de pgf/TikZ

## Notas de traducción.

Esta es una traducción no oficial de manual de TikZ, por lo mismo puede (y 
probablemente haya) errores de traducción. Haré todo lo posible por que eso no
sea así. También, por motivos de tropicalización, es posible que algunos
términos o frases no estén traducidos de manera literal.

En específico, algunos términos de programación no los traduciré. El motivo es
que, usualmente, este tipo palabras es más común escuchar (o ver) el anglicismo
que su término original. Otro motivo es que, dado que no soy un traductor 
profesional, no tengo ni idea de cual sería la mejor forma de traducir estos
términos. Así que consideré que es mejor dejar las palabras tal cuales como
están.

Es un proyecto personal, por lo que el resultado está en proceso y puede que
nunca esté acabado (esperemos que no).

# pgf – Un Formato Gráfico Portable para TeX

![Test suite](https://github.com/pgf-tikz/pgf/actions/workflows/check.yml/badge.svg?branch=master)

PGF es un paquete de macros de TeX para generar gráficos. Es independiente de la
plataforma y el formato y funciona con los drivers de backend de TeX más 
importantes, incluyendo `pdftex` y `dvips`. Además, viene con una capa de
sintaxis user-friendly llamada Ti*k*Z.

Puedes consultar el directorio `doc/generic/pgf` para más información. También
puedes  consultar el archivo `doc/generic/pgf/pgfmanual.pdf` (también disponible
en inglés, desde https://pgf-tikz.github.io/pgf/pgfmanual.pdf) para un manual.
Esta documentación también explica la instalación. Finalmente, puedes mirar el
archivo `doc/generic/pgf/license/LICENSE` para los detalles de la licencia.

Por favor, visite el repositorio oficial en https://github.com/pgf-tikz/pgf o la
lista de correo en https://tug.org/mailman/listinfo/pgf-tikz para enviar
reportes de errores, solicitar nuevas características, etc.

También tenemos un chat en la red de Matrix en
[#pgf-tikz:matrix.org](https://matrix.to/#/#pgf-tikz:matrix.org)
([versión de solo lectura](https://view.matrix.org/room/!NuxCISwYQJuyWwNsEI:matrix.org/)).

## Instalación

En general deberías simplemente usar la versión de PGF que está incluida en tu
distribución de TeX. Consulte su documentación para saber como instalar
paquetes.

Si te sientes aventurero también puedes instalar la última versión de desarrollo
en TeX Live desde nuestro repositorio de tlcontrib.
```console
$ tlmgr repository add http://pgf-tikz.github.io/pgf/tlnet pgf-development
$ tlmgr pinning add pgf-development "*"
$ tlmgr update --self --all
$ tlmgr install pgf --reinstall
```

## Desarrollo
Actualmente, PGF solo cuenta con un conjunto de pruebas muy rudimentario para
detectar regresiones, por lo que, por ahora, buscamos errores compilando el
manual para cada commit. Para compilar el manual localmente, puedes copiar el repositorio de PGF en tu árbol de texmf (no recomendado) o usar la opción
usertree de TeX Live. Para usar la opción usertree en GNU/Linux, siga estos
pasos:
```console
$ git clone https://github.com/pgf-tikz/pgf
$ tlmgr init-usertree --usertree pgf
$ export TEXMFHOME=$(readlink -f pgf)
$ cd pgf
$ l3build doc -q -H
```
Recomendamos compilar al menos la versión para LuaTeX, como se muestra en el
ejemplo anterior, ya que ofrece la cobertura más amplia de las funciones de PGF.
Para probar la función de animaciones, debes compilar la versión para dvisvgm.