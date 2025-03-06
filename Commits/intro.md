# Commits
Los commits nos permiten guardar el estado actual de nuestro proyecto en el repositorio local.
No existen restricciones respecto a su uso, sino que son una herramienta que cada desarrollador puede usar de distinta manera.
Se puede trabajar con muchos commits pequeños o hacer commits grandes más espaciados, pero a menos que trabajemos sólos, conviene priorizar la salud del historial de commits y permitir que nuestros compañeros puedan auditar nuestro trabajo de forma más precisa.

### Estructura
Cada commit está identificado con un hash hexadecimal de 40 caracteres. Podemos referirnos a un commit por su hash completo:

commit **e553cfb984649e94e2f4be2a2286966f7a799241**

O, como mínimo, con sus primeros seis caracteres:

commit **e553cf**

### Utilidades asociadas a los commits
Podemos desplazarnos por el historial de commits con `git checkout` para analizar el estado del proyecto en un punto previo.

Si hicimos algún commit por error o introducimos bugs graves al código, tenemos la posibilidad de reestablecer el proyecto a un estado previo de forma permanente con `git reset`.

### Explicación técnica
Realizar un commit genera un objeto **commit** en base a los archivos que forman parte del index (ver estados de archivos e index) y lo almacena en el *object store*.
Estos archivos ya formaban parte del *object store* desde que fueron agregados al index.

Si el nuevo commit introdujo nuevos archivos o modificó el contenido de archivos existentes, se crean y almacenan nuevos **blobs**. Si se agregaron nuevos directorios, se generan nuevos **trees**. Los archivos que no sufrieron modificaciones se reutilizan en este nuevo commit, reduciendo considerablemente el tamaño del repositorio al evitar duplicaciones. Además, esta verificación se realiza muy rápidamente ya que git compara los IDs de los objetos.
Si el hash que identifica a un directorio no cambió entre versiones, entonces ninguno de sus subdirectorios cambió, y rápidamente se puede reutilizar toda esa estructura.


