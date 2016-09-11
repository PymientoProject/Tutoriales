# Web

Para actualizar los contenidos de la web hay dos puntos importantes a tocar:

* El archivo **structure.json** del raíz
* Los archivos **data.md** de cada directorio

## structure.json

En este archivo se estructura el árbol de contenidos de la web. Cada nodo es una página, con sus propiedades particulares. Por ejemplo:

``` 
"pages":[
		{
			"title":"About",
			"introduction":"",
			"published": true,
            "link": true,
			"image":"",
			"url":"about",
			"pages":[]
		}
     ]
     ```

Como en el ejemplo anterior, si la propiedad "pages" está vacío, esta página se puede considerar que es una hoja del árbol. En el caso contrario, como es el caso de Works y People, pages funciona a modo de rama.

### Creando nuevos contenidos
Al crear una página nueva, por ejemplo un proyecto nuevo, tenemos que duplicar el directorio "empty" renombrándolo con el nombre del proyecto a modo de URL amigable, por ejemplo: "super-cool-project". Esta carpeta nueva contiene 2 archivos: un index.html al que no hay que meterle mano, y un data.md que es el que utilizaremos para rellenarlo con nuestros contenidos con el formato Markdown. Si este proyecto nuevo tiene imágenes, lo recomendable es subirlas dentro del directorio, para acceder a ellas sin tener que recordar el nombre de la ruta de la imágen.

### Eliminar contenidos
Si tocamos la estructura, por ejemplo de proyectos, y queremos hacer desaparecer, por ejemplo "super-cool-project", podemos cambiarle la propiedad "published", haciéndole desaparecer de la lista. Esto no hace que se borre ni que no se pueda acceder teniendo la URL. Para ello hay que borrar el directorio y eliminar la página del json.

### published y link
La propiedad "published" muestra o no el contenido en el listado. 
Por otro lado "link" crea un enlace al contenido. Por ejemplo, el perfil de "Gonzalo Moyano" en "People" tiene el "link"=true porque tiene rellena la página con contenidos más o menos terminados/visibles, en cambio hay gente que aun no ha rellenado sus contenidos, o no lo rellenarán nunca, y es mejor que el acceso a estas páginas estén desactivadas. Lo mismo para para los proyectos. Habrán proyectos que inicialmente sean enunciados, pero que posiblemente no se concreten y posteriormente sean borrados.

## data.md
Por ejemplo, si Cristo quisiera rellenar su perfil personal, dentro del directorio people/cristo-contreras-rubio podrá encontrar un archivo data.md. En ese archivo podrá rellenar todos sus contenidos de texto en formato Markdown. Siguiendo el ejemplo, si quisiera poner una imagen suya, lo conveniente es que la suba dentro de su propio directorio, por ejemplo "people/cristo-contreras-rubio/mi-foto.jpg" y que la enlace con Markdown del siguiente modo:

 ```
 \[Conectando servidores]\(mi-foto.jpg)
 ```

La imágen se ajusta automáticamente al ancho máximo del contenido que es 880 píxeles.

Si quisiéramos que la imagen ocupe el ancho completo de la pantalla tenemos que agregar un parámetro adicional después del parámetro del archivo. Este parámetro se escribe así:
 ```
 \(full)
 ```

Y se usa así:
 ```
 \[Conectando servidores]\(mi-foto.jpg)\(full)
 ```

Para ver un ejemplo de esta diferencia entre imagen a 880px o "full" podéis pasar por aquí:  

[http://thepymientoproject.com/people/gonzalo-moyano/](http://thepymientoproject.com/people/gonzalo-moyano/)

## Consideraciones
* El javascript que parsea los Markdown es de código ajeno y tiene unos pequeños problemas: cuando creen un "# Titulo" siempre hay que dejar un espacio entre el # y el texto, y por último siempre hay qye dejar más de un salto de linea después de un titular.
* Para un futuro cercano quiero modificar el markdown del link para hacer que pueda tener un "target=_blank" ya que no me parece bien estar yéndote la página de pimiento ante cualquier referencia externa que pongamos.
* Finalmente, haré un markdown nuevo para embeber vídeos de youtube, vimeo, etc.
