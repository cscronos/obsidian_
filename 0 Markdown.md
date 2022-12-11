# Markdown
[Pagina](https://tutorialmarkdown.com/aplicaciones/obsidian) donde se ven todas las partes de markdown para escribir bonito en Obsidian.


```md
Cambia de directorio con el comando `cd`
```

[]()
## Listas
**Formas de escribir listas**
*Lista 1*
<ol>
  <li>Primer elemento</li>
  <li>Segundo elemento</li>
  <li>Tercer elemento</li>
</ol>

*Lista 2*
1. Primer elemento
2. Segundo elemento
3. Tercer elemento

* Parte 1
* Parte 2

## Listas no ordenadas
*html*
<ul>
  <li>Primer elemento</li>
  <li>Segundo elemento</li>
</ul>

# Resaltado de sintaxis
````md
```javascript
const value = 3;
let result = value * 4;
```
````

# Enlaces
[Enlace](https://linux.com)
[Encabezados](#Markdown)
[EncabezadosListas](##Listas)
<https://linux.com>
<me@email.com>

html
<a href="https://linux.com">Enlace</a>

Usa el comando `cd`
```md
Cambia de directorio con el comando `cd`
```

```md
``let str = `texto de la cadena`;``

```
```md
``let str = `texto de la cadena` ``
```


```html
Me gusta el editor <a href="https://editormarkdown.com" title="Mejor editor Markdown">Editor Markdown</a>
```

```md
Enlace al **[Editor en negrita](https://editormarkdown.com)**.
Enlace al *[Editor en cursiva](https://editormarkdown.com)*.
Enlace al ***[Editor en negrita y cursiva](https://editormarkdown.com)***.
```

```md
Enlace al [`código`](https://neoguias.com).
```

```md
[1]: https://neoguias.com/php "Programa con PHP"
[2]: https://neoguias.com/javascript 'Programa con JavaScript'
[3]: <https://neoguias.com/python> (Programa con Python)
```

Enlace a una [referencia][1]  
...  
[1]: https://dom.tld}

> donde sera
> > pero si
> 

```md
> #### Esta es una cita de ejemplo!
>
> - Me he comprado la PS5
> - Y otro ordenador
>
>  *Estaré* forever **alone** pero `feliz`
```