---
name: ingerir-anuncio
description: Convierte el texto bruto de un anuncio inmobiliario en un Markdown en anuncios/. Usar cuando el usuario pega un anuncio, pide ingerirlo, o pide crear el archivo de una vivienda a partir del contenido del portal.
---

# Ingerir anuncio

## Antes de escribir

Leer:

- `docs/contexto.md`
- `docs/criterios-vivienda.md`
- `docs/localidades.md`
- `docs/plantilla-anuncio.md`

El formato del archivo es el de `docs/plantilla-anuncio.md`. No añadir bloques distintos.

No modificar `docs/criterios-vivienda.md` ni `docs/localidades.md`. No copiar al anuncio la línea, la estación ni la prioridad del maestro.

## Valoración

La valoración la da el usuario: `me_gusta` o `me_gusta_pero`, motivos, y pegas o dudas.

Organizarla en la plantilla sin cambiarla, sin quitar pegas y sin añadir motivos que el usuario no haya dicho. No deducirla de los criterios. Si falta, preguntar antes de crear el archivo.

## Datos

Extraer solo lo que el anuncio dice de forma explícita. Si no aparece, escribir `no indicado`. Escribir `no` solo cuando el anuncio lo dice de forma explícita.

No convertir afirmaciones ambiguas del anunciante en datos objetivos.

- "amplia terraza" → no inventar los m² de terraza.
- "cerca de la estación" → no inventar una distancia.
- "zona tranquila" → conservarlo como descripción del anunciante, no como hecho objetivo.
- "luminoso" → no convertirlo automáticamente en una característica objetiva.

`Localidad` es el nombre del maestro si el anuncio encaja con una fila. `Ubicación` es el texto de zona, barrio o calle del anuncio, no el eje del maestro.

`Terraza` y `Balcón` son `sí`, `no` o `no indicado`. Los m² solo si el anuncio da un número en m². `10mt` no es m². No escribir una frase larga en la celda.

`Planta` se copia como está escrita. No deducir que es la última planta a partir del número. Si el anuncio dice ático y la planta no lo contradice, se puede añadir a la celda.

`Ascensor` queda en `no indicado` si el anuncio no lo menciona.

`Estado de la vivienda` es la conservación que declara el anuncio, no la valoración.

`Año`, `Orientación` y `Calefacción` solo si el anuncio los indica. «50 a 70 años» de antigüedad no es un año.

`Actualización` es el día y el mes del anuncio, tal como aparecen. No inventar el año. No convertir «hace 3 días» en una fecha.

`Precio`, `Precio por m²` y `URL` se copian tal como aparecen. No calcular €/m².

Si la ficha y el comentario no coinciden, la celda usa el dato de la ficha. La diferencia va en `Discrepancias`, debajo de la tabla, con las dos frases y sin elegir cuál es cierta. Si la ficha no da número de planta y el comentario sí, la celda usa esa planta y `Discrepancias` dice que la ficha no trae número. Si no hay diferencia, no añadir `Discrepancias`.

## Localidad

Identificar la localidad contra `docs/localidades.md`. Si no encaja o es ambigua, preguntar. No añadir filas al maestro.

| Localidad | Carpeta |
| --- | --- |
| La Garriga | la-garriga |
| Cardedeu | cardedeu |
| Sant Celoni | sant-celoni |
| Llinars del Vallès | llinars-del-valles |
| Les Franqueses | les-franqueses |
| Granollers | granollers |
| Montgat | montgat |
| El Masnou | el-masnou |
| Canet de Mar | canet-de-mar |
| Arenys de Mar | arenys-de-mar |
| Centelles | centelles |
| Horta | horta |
| Sant Andreu | sant-andreu |
| Nou Barris | nou-barris |

«Les Franqueses del Vallès» corresponde a Les Franqueses. Un barrio de una localidad del maestro usa esa localidad. Un barrio de Barcelona que no esté en el maestro: preguntar.

## Archivo

Ruta: `anuncios/<carpeta>/<id>.md`.

El `<id>` es el del portal si aparece en la URL. En `https://www.idealista.com/inmueble/12345678/` el id es `12345678`. En `https://www.fotocasa.es/es/comprar/vivienda/.../190639090/d` el id es `190639090`. Un código para llamar o la referencia de la agencia no es el id. Si no hay URL, preguntar. No inventarlo.

## Contenido original

Copiar el texto relevante con los títulos del anuncio. No resumirlo ni reescribirlo. No añadir apartados vacíos. No copiar botones del portal: hipoteca, ver mapa, idiomas o ver etiqueta. Si el mismo texto está en catalán y en castellano, guardar solo uno.
