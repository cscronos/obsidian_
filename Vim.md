# [Hoja de trucos de Vim](https://vim.rtorr.com/)

## Global

-   :h[elp] keyword- ayuda abierta para palabra clave
-   :sav[eas] file- Guardar archivo como
-   :clo[se]- cerrar el panel actual
-   :ter[minal]- abrir una ventana de terminal
-   K- abrir la página del manual para Word debajo del cursor

**Sugerencia** Ejecute vimtutoren una terminal para aprender los primeros comandos de Vim.

## movimiento del cursor

-   h- mover el cursor a la izquierda
-   j- mover el cursor hacia abajo
-   k- mover el cursor hacia arriba
-   l- mover el cursor a la derecha
-   gj- mover el cursor hacia abajo (texto de varias líneas)
-   gk- mover el cursor hacia arriba (texto de varias líneas)
-   H- mover a la parte superior de la pantalla
-   M- mover al centro de la pantalla
-   L- mover a la parte inferior de la pantalla
-   w- saltar hacia adelante al comienzo de una palabra
-   W- saltar hacia adelante al comienzo de una palabra (las palabras pueden contener puntuación)
-   e- saltar hacia delante hasta el final de una palabra
-   E- saltar hacia adelante hasta el final de una palabra (las palabras pueden contener puntuación)
-   b- saltar hacia atrás al comienzo de una palabra
-   B- saltar hacia atrás al comienzo de una palabra (las palabras pueden contener puntuación)
-   ge- saltar hacia atrás hasta el final de una palabra
-   gE- saltar hacia atrás hasta el final de una palabra (las palabras pueden contener puntuación)
-   %- mover al carácter coincidente (pares compatibles predeterminados: '()', '{}', '[]' - usar `:h matchpairs`en vim para obtener más información)
-   0- saltar al principio de la fila
-   ^- saltar al primer carácter que no esté en blanco de la línea
-   $- saltar al final de la línea
-   g_- saltar al último carácter que no esté en blanco de la línea
-   gg- ir a la primera línea del documento
-   G- ir a la última línea del documento
-   5ggo 5G- vaya a la línea 5
-   gd- pasar a la declaración local
-   gD- pasar a la declaración global
-   fx- saltar a la siguiente aparición del carácter x
-   tx- salta a antes de la próxima aparición del carácter x
-   Fx- salta a la aparición anterior del carácter x
-   Tx- salta a después de la aparición anterior del carácter x
-   ;- repetir el movimiento anterior f, t, F o T
-   ,- repetir el movimiento anterior f, t, F o T, hacia atrás
-   }- saltar al siguiente párrafo (o función/bloque, al editar código)
-   {- saltar al párrafo anterior (o función/bloque, al editar código)
-   zz- centrar el cursor en la pantalla
-   Ctrl+ e- mover la pantalla una línea hacia abajo (sin mover el cursor)
-   Ctrl+ y- mueve la pantalla una línea hacia arriba (sin mover el cursor)
-   Ctrl+ b- retroceder una pantalla completa
-   Ctrl+ f- avanzar una pantalla completa
-   Ctrl+ d- avanzar 1/2 pantalla
-   Ctrl+ u- retroceder 1/2 pantalla

**Sugerencia** Prefije un comando de movimiento del cursor con un número para repetirlo. Por ejemplo, 4jbaja 4 líneas.

## Modo de inserción: insertar/añadir texto

-   i- insertar antes del cursor
-   I- insertar al principio de la línea
-   a- insertar (agregar) después del cursor
-   A- insertar (agregar) al final de la línea
-   o- agregar (abrir) una nueva línea debajo de la línea actual
-   O- añadir (abrir) una nueva línea encima de la línea actual
-   ea- insertar (añadir) al final de la palabra
-   Ctrl+ h- elimina el carácter antes del cursor durante el modo de inserción
-   Ctrl+ w- eliminar palabra antes del cursor durante el modo de inserción
-   Ctrl+ j- comienza una nueva línea durante el modo de inserción
-   Ctrl+ t- línea de sangría (mover a la derecha) un ancho de cambio durante el modo de inserción
-   Ctrl+ d- quitar sangría (mover a la izquierda) línea un ancho de turno durante el modo de inserción
-   Ctrl+ n- insertar (autocompletar) siguiente coincidencia antes del cursor durante el modo de inserción
-   Ctrl+ p- insertar (autocompletar) coincidencia anterior antes del cursor durante el modo de inserción
-   Ctrl+ rx- inserta el contenido del registro x
-   Ctrl+ ox- Ingrese temporalmente al modo normal para emitir un comando de modo normal x.
-   Esc- salir del modo de inserción

## Edición

-   r- reemplazar un solo carácter.
-   R- reemplazar más de un carácter, hasta ESCque se presione.
-   J- unir la línea de abajo a la actual con un espacio en medio
-   gJ- unir la línea de abajo a la actual sin espacio entre ellas
-   gwip- párrafo de reflujo
-   g~- cambie la caja al movimiento
-   gu- cambiar a minúsculas hasta el movimiento
-   gU- cambiar a mayúsculas hasta el movimiento
-   cc- cambiar (reemplazar) toda la línea
-   c$o C- cambiar (reemplazar) hasta el final de la línea
-   ciw- cambiar (reemplazar) palabra completa
-   cwo ce- cambiar (reemplazar) al final de la palabra
-   s- eliminar carácter y sustituir texto
-   S- eliminar línea y sustituir texto (igual que cc)
-   xp- transponer dos letras (eliminar y pegar)
-   u- deshacer
-   U- restaurar (deshacer) la última línea cambiada
-   Ctrl+ r- rehacer
-   .- repetir el último comando

## Marcar texto (modo visual)

-   v- inicie el modo visual, marque líneas, luego haga un comando (como y-yank)
-   V- iniciar el modo visual en línea
-   o- moverse al otro extremo del área marcada
-   Ctrl+ v- iniciar el modo de bloqueo visual
-   O- mover a otra esquina del bloque
-   aw- marcar una palabra
-   ab- un bloque con ()
-   aB- un bloque con {}
-   at- un bloque con etiquetas <>
-   ib- bloque interior con ()
-   iB- bloque interior con {}
-   it- bloque interno con etiquetas <>
-   Esc- salir del modo visual

**Sugerencia** En lugar de bo Btambién se puede utilizar (o {respectivamente.

## Comandos visuales

-   >- desplazar el texto a la derecha
-   <- desplazar el texto a la izquierda
-   y- tirar (copiar) texto marcado
-   d- eliminar texto marcado
-   ~- caja del interruptor
-   u- cambiar el texto marcado a minúsculas
-   U- cambiar el texto marcado a mayúsculas

## Registros

-   :reg[isters]- mostrar el contenido de los registros
-   "xy- tirar al registro x
-   "xp- pegar el contenido del registro x
-   "+y- tirar en el registro del portapapeles del sistema
-   "+p- pegar desde el registro del portapapeles del sistema

**Sugerencia** Los registros se almacenan en ~/.viminfo y se cargarán nuevamente en el próximo reinicio de vim.

**Sugerencia** Registros especiales:

 0- último tirón  
 "- registro sin nombre, último borrado o tirón  
 %- nombre de archivo actual  
 #- nombre de archivo alternativo  
 *- contenido del portapapeles (X11 principal)  
 +- contenido del portapapeles (portapapeles X11)  
 /- último patrón de búsqueda  
 :- última línea de comando  
 .- último texto insertado  
 -- último pequeño ( menos de una línea) eliminar  
 =- registro de expresión  
 _- registro de agujero negro  

## marcas y posiciones

-   :marks- lista de marcas
-   ma- establecer la posición actual para la marca A
-   `a- saltar a la posición de la marca A
-   y`a- tire del texto a la posición de la marca A
-   `0- ir a la posición donde se salió previamente de Vim
-   `"- ir a la posición cuando se editó por última vez este archivo
-   `.- ir a la posición del último cambio en este archivo
-   ``- ir a la posición antes del último salto
-   :ju[mps]- lista de saltos
-   Ctrl+ i- ir a la posición más nueva en la lista de salto
-   Ctrl+ o- ir a la posición anterior en la lista de salto
-   :changes- lista de cambios
-   g,- ir a una posición más nueva en la lista de cambios
-   g;- ir a la posición anterior en la lista de cambios
-   Ctrl+ ]- salta a la etiqueta debajo del cursor

**Sugerencia** Para saltar a una marca, puede usar un acento grave ( `) o un apóstrofe ( '). El uso de un apóstrofe salta al principio (el primero que no está en blanco) de la línea que contiene la marca.

## macros

-   qa- grabar una macro
-   q- dejar de grabar macros
-   @a- ejecutar macro a
-   @@- volver a ejecutar la última macro ejecutada

## Cortar y pegar

-   yy- tirar (copiar) una línea
-   2yy- tirar (copiar) 2 líneas
-   yw- tirar (copiar) los caracteres de la palabra desde la posición del cursor hasta el comienzo de la siguiente palabra
-   yiw- tirar (copiar) palabra debajo del cursor
-   yaw- tirar (copiar) la palabra debajo del cursor y el espacio antes o después de ella
-   y$o Y- tirar (copiar) hasta el final de la línea
-   p- poner (pegar) el portapapeles después del cursor
-   P- poner (pegar) antes del cursor
-   gp- poner (pegar) el portapapeles después del cursor y dejar el cursor después del nuevo texto
-   gP- poner (pegar) antes del cursor y dejar el cursor después del nuevo texto
-   dd- eliminar (cortar) una línea
-   2dd- eliminar (cortar) 2 líneas
-   dw- eliminar (cortar) los caracteres de la palabra desde la posición del cursor hasta el comienzo de la siguiente palabra
-   diw- eliminar (cortar) palabra debajo del cursor
-   daw- eliminar (cortar) la palabra debajo del cursor y el espacio antes o después de ella
-   d$o D- eliminar (cortar) hasta el final de la línea
-   x- eliminar (cortar) carácter

## Texto con sangría

-   >>- sangría (mover a la derecha) línea uno shiftwidth
-   <<- eliminar la sangría (mover a la izquierda) línea un shiftwidth
-   >%- sangrar un bloque con () o {} (cursor en llave)
-   >ib- bloque interior de sangría con ()
-   >at- sangrar un bloque con etiquetas <>
-   3==- volver a sangrar 3 líneas
-   =%- volver a sangrar un bloque con () o {} (cursor en llave)
-   =iB- volver a sangrar el bloque interior con {}
-   gg=G- volver a sangrar todo el búfer
-   ]p- pegar y ajustar la sangría a la línea actual

## saliendo

-   :w- escribir (guardar) el archivo, pero no salir
-   :w !sudo tee %- escribe el archivo actual usando sudo
-   :wqo :xo ZZ- escribir (guardar) y salir
-   :q- quit (falla si hay cambios sin guardar)
-   :q!o ZQ- salga y deseche los cambios no guardados
-   :wqa- escribir (guardar) y salir en todas las pestañas

## Buscar y reemplazar

-   /pattern- buscar patrón
-   ?pattern- buscar hacia atrás para el patrón
-   \vpattern- Patrón 'muy mágico': los caracteres no alfanuméricos se interpretan como símbolos de expresiones regulares especiales (no es necesario escapar)
-   n- repetir la búsqueda en la misma dirección
-   N- repetir la búsqueda en dirección opuesta
-   :%s/old/new/g- reemplace todo lo antiguo con nuevo en todo el archivo
-   :%s/old/new/gc- reemplace todo lo antiguo con nuevo en todo el archivo con confirmaciones
-   :noh[lsearch]- eliminar el resaltado de coincidencias de búsqueda

## Buscar en varios archivos

-   :vim[grep] /pattern/ {`{file}`}- buscar patrón en varios archivos

p.ej :vim[grep] /foo/ **/*

-   :cn[ext]- saltar al siguiente partido
-   :cp[revious]- saltar al partido anterior
-   :cope[n]- abrir una ventana que contiene la lista de coincidencias
-   :ccl[ose]- cerrar la ventana de solución rápida

## Pestañas

-   :tabnewo :tabnew {page.words.file}- abrir un archivo en una nueva pestaña
-   Ctrl+ wT- mueve la ventana dividida actual a su propia pestaña
-   gto :tabn[ext]- pasar a la siguiente pestaña
-   gTo :tabp[revious]- ir a la pestaña anterior
-   #gt- pasar a la pestaña número #
-   :tabm[ove] #- mover la pestaña actual a la posición #th (indexada desde 0)
-   :tabc[lose]- cerrar la pestaña actual y todas sus ventanas
-   :tabo[nly]- cerrar todas las pestañas excepto la actual
-   :tabdocomando: ejecute `command`en todas las pestañas (por ejemplo `:tabdo q`, cierra todas las pestañas abiertas)

## Trabajando con varios archivos

-   :e[dit] file- editar un archivo en un nuevo búfer
-   :bn[ext]- ir al siguiente búfer
-   :bp[revious]- ir al búfer anterior
-   :bd[elete]- eliminar un búfer (cerrar un archivo)
-   :b[uffer]#- ir a un búfer por índice #
-   :b[uffer] file- ir a un búfer por archivo
-   :lso :buffers- enumerar todos los búferes abiertos
-   :sp[lit] file- abrir un archivo en un nuevo búfer y ventana dividida
-   :vs[plit] file- abra un archivo en un nuevo búfer y una ventana dividida verticalmente
-   :vert[ical] ba[ll]- editar todos los búferes como ventanas verticales
-   :tab ba[ll]- editar todos los búferes como pestañas
-   Ctrl+ ws- ventana dividida
-   Ctrl+ wv- ventana dividida verticalmente
-   Ctrl+ ww- cambiar de ventana
-   Ctrl+ wq- salir de una ventana
-   Ctrl+ wx- intercambiar la ventana actual con la siguiente
-   Ctrl+ w=- hacer que todas las ventanas tengan la misma altura y anchura
-   Ctrl+ wh- mover el cursor a la ventana izquierda (división vertical)
-   Ctrl+ wl- mover el cursor a la ventana derecha (división vertical)
-   Ctrl+ wj- mueve el cursor a la ventana de abajo (división horizontal)
-   Ctrl+ wk- mover el cursor a la ventana de arriba (división horizontal)
-   Ctrl+ wH- hace que la ventana actual tenga la altura completa en el extremo izquierdo (ventana vertical más a la izquierda)
-   Ctrl+ wL- hacer que la ventana actual tenga la altura completa en el extremo derecho (ventana vertical más a la derecha)
-   Ctrl+ wJ- hacer que la ventana actual tenga el ancho completo en la parte inferior (ventana horizontal más inferior)
-   Ctrl+ wK- hacer que la ventana actual tenga el ancho completo en la parte superior (ventana horizontal superior)

## diferencia

-   zf- definir manualmente un pliegue hasta el movimiento
-   zd- eliminar pliegue debajo del cursor
-   za- alternar plegar debajo del cursor
-   zo- abrir pliegue debajo del cursor
-   zc- cerrar pliegue debajo del cursor
-   zr- reducir (abrir) todos los pliegues en un nivel
-   zm- doblar más (cerrar) todos los pliegues por un nivel
-   zi- alternar la funcionalidad de plegado
-   ]c- saltar al inicio del próximo cambio
-   [c- saltar al inicio del cambio anterior
-   doo :diffg[et]- obtener (obtener) diferencia (de otro búfer)
-   dpo :diffpu[t]- poner diferencia (a otro búfer)
-   :diffthis- hacer que la ventana actual sea parte de diff
-   :dif[fupdate]- actualizar las diferencias
-   :diffo[ff]- desactivar el modo diferencial para la ventana actual

**Sugerencia** Los comandos para plegar (p. ej za. ) funcionan en un nivel. Para operar en todos los niveles, utilice letras mayúsculas (por ejemplo, zA).

**Sugerencia** Para ver las diferencias de los archivos, se puede iniciar directamente Vim en modo diff ejecutándolo vimdiffen una terminal. Incluso se puede configurar esto como git difftool.