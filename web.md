# Web

Para actualizar los contenidos de la web hay dos puntos importantes a tocar.

* el archivo structure.json del raíz
* los archivos .md de cada directorio

## structure.json

En este archivo se estructura el árbol de contenidos de la web. Cada nodo es una página, con sus propiedades particulares. Por ejemplo:

>>> "pages":[
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

Como en el ejemplo anterior, si la propiedad "pages" está vacio, esta página se puede considerar que es una hoja del árbol. En el caso contrario, como es el caso de Works y People, pages funciona a modo de rama.

### Creando nuevos conenidos
Al crear una página nueva, por ejemplo un proyecto nuevo, tenemos que duplicar el directorio "empty" renombrándolo con el nombre del proyecto a modo de URL amigable, por ejemplo: "super-cool-project". Esta carpeta nueva contiene 2 archivos: un index.html al que no hay que meterle mano, y un data.md que es el que utilizaremos para rellenarlo con nuestros contenidos con el formato Markdown. Si este proyecto nuevo tiene imágenes, lo recomendable es subirlas dentro del directorio, para acceder a ellas sin tener que recordar el nombre de la ruta de la imágen.

### Eliminar contenidos
Si tocamos la estructura, por ejemplo de proyectos, y queremos hacer desaparecer, por ejemplo "super-cool-project", podemos cambiarle la propiedad "published", haciéndole desaparecer de la lista. Esto no hace que se borre ni que no se pueda acceder teniendo la URL. Para ello hay que borrar el directorio y eliminar la página del json.

### published y link
La propiedad "published" muestra o no el contenido en el listado. "link" crea un link al contenido. Por ejemplo, mi perfil en "People" tiene el "link"=true porque tengo relleno los contenidos de mi perfil, en cambio hay gente que aun no ha rellenado sus contenidos, o no lo rellenarán nunca, y es mejor que el acceso a estas páginas estén desactivadas.

