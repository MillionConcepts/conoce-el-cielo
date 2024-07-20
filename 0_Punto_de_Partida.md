#Inicio

Este documento, junto con su notebook complementario, tiene como objetivo enseñar lo necesario para poder utilizar el contenido interactivo en: _conoce-el-cielo_ . Incluye instrucciones sobre:

1. Descargar del contenido de GitHub
2. Como instalar y crear entornos en Conda
3.  Ejecutar el servidor Jupyter
4.  Trabajar con un cuaderno Jupyter

Si es que ya sabes como ejecutar los pasos del 1 al 4, la recomendación sería saltarte este documento.

## Requisitos Previos

No es necesario ser un experto en Python para utilizar _conoce-el-cielo_ . Sin embargo, se requiere tener cierta familiaridad básica con las características principales del lenguaje. Si es que deseas utilizar _conoce-el-cielo_ pero no tienes conocimientos sobre Python, te recomendaríamos comenzar con el [tutorial oficial de Python.](https://docs.python.org/3/tutorial/index.html)
Si no estás segura o seguro de tu nivel de familiaridad, te recomendamos ir a la sección [lista de conceptos requeridos](#required-python-concepts) al final de este documento, que también incluye referencias a secciones del tutorial de Python que cubren cada uno de esos conceptos.

## Qué es un Jupyter Notebook?

Jupyter Notebook es un entorno de codificación interactivo. Puede funcionar código en
[varios lenguajes de programación diferentes](https://github.com/jupyter/jupyter/wiki/Jupyter-kernels),
y también puede presentar o graficar texto formateado y contenido multimedia. _conoce-el-cielo_  lo usa para permitirte ejecutar código Python. (En secciones posteriores, daremos a conocer más detalles sobre cómo funciona)

Es importante saber que aunque uses Jupyter Notebook en un navegador, eso no significa que deba conectarse a Internet. La mayoría de la gente que usan Jupyter Notebooks simplemente ejecutan el servidor "localmente" (es decir, en su propias computadoras), porque es más rápido y no tienes que generar passwords ni contraseñas para hacerlo seguro. Si sigues las instrucciones de este documento, estarás ejecutando Jupyter en tu propia máquina.
Esto significa que cualquier cambio que realices en los archivos de Notebook serán totalmente privados, puedes hacer una copia de seguridad de tus cambios como quieras y ni siquiera se necesitará una conexión de red para ejecutarlos (aunque algunos de ellos
contienen secciones específicas de código para descargar datos de Internet).

Otra aclaración: la gente suele usar la frase "Jupyter Notebook" para
referirse tanto al entorno de codificación como a los archivos individuales de Notebook, que
puede resultar confuso. Procederemos a tener cuidado con eso y escribir "Archivo Notebook Jupyter" siempre que hablemos de un archivo específico en lugar del ambiente de programación.

## Requisitos Técnicos

### Sistemas Operativos y Hardware Compatibles

Las siguientes instrucciones te permitirán instalar  _conoce-el-cielo_ en la mayoría de las computadoras portátiles y de escritorio. Debe poder ejecutarse en Windows, MacOS o Linux. (Adicionalmente, debería ser factible configurarlo en un Chromebook, teléfono o tablet, pero es complicado y no operaría correctamente, por lo que no ofrecemos apoyo para esas plataformas).

Tu computadora debe tener al menos 4 GB de RAM, 4 GB de espacio libre en disco,
y una arquitectura de CPU de 64 bits. La mayoría de las computadoras de 10 años de antigüedad funcionan bien.

También, necesitarás una conexión a Internet para realizar la instalación inicial y para ejecutar las partes del contenido que descargan datos científicos. No hay ejecución de una red en tiempo real, por lo que la conexión no tiene por que ser rápida, pero en caso de que sea muy lento o inestable, podría requerir varios intentos llegando a ser frustrante.

### Excepciones

Si estás usando una computadora del trabajo o de la escuela que no te da permiso para instalar el software, estas instrucciones no funcionarán. Necesitarás hablar con
el administrador del sistema para averiguar cómo realizar las configuraciones necesarias.

De manera similar, si estás en una red que restringe el acceso a websites, es posible que necesites hablar con el administrador de sistemas para solicitar acceso y poder descargar el software y datos.

## Instalación

Para ejecutar código Python en un Jupyter Notebook, necesitas tener instalado en tu máquina el software Python y las "dependencias" adicionales (que el código necesita y que no vienen incluidas con Python). Por supuesto, también necesitas el Jupyter Notebook requerido. Esta sección contiene instrucciones paso a paso para configurar el entorno Python, descargar el contenido de _conoce-el-cielo_ y ejecutar el servidor Jupyter para poder utilizar los Notebooks.

### 1. Instalando Conda

Consideramos que la mejor manera de configurar Python para la mayoría de los proyectos de código abierto es usando el administrador de paquetes de Conda para descargar software desde un 'canal' llamado “conda-forge”.

Hemos preferido una versión de Conda proporcionada por la comunidad conda-forge llamada “Miniforge”. Lo instalaremos ahora y luego usaremos el software de administración incluido “conda” para instalar dependencias específicas para *conociendo en el siguiente paso.
[Puede obtener el instalador de Miniforge desde su página de GitHub.]
(https://github.com/conda-forge/miniforge)
Solo es cuestion de ir a esa página y seguir las instrucciones en la sección "Instalar".
Durante el proceso de instalación, simplemente acepte los valores predeterminados y seleccione "sí" a cualquiera de las indicaciones, a menos que tenga alguna otra preferencia específica.

#### Recomendaciones

1. Si tienes una versión anterior de Conda instalada en tu computadora y no la estás usando, la recomendación sería desinstalarla antes de instalar Miniforge. El resto de estas instrucciones de instalación tal vez no funcionen correctamente con diferentes versiones de Conda, y se pueden generar errores al tener varias versiones de Conda instaladas en la misma computadora.
2. Asegúrate de seguir la versión de las instrucciones para tu sistema operativo instalado. En MacOS, se debe ingresar el comando en las instrucciones en la Terminal programa a menos que tenga una consola preferida diferente.
3. Si descargas el instalador haciendo click en un enlace en lugar de usar un comando shell, asegúrate de elegir la versión "Miniforge3" del instalador, y no la "Miniforge-pypy3", ya que esta última no es recomendable para este proyecto.
También asegúrate de elegir la versión que coincida con tu sistema operativo. [y arquitectura de CPU](#what-kind-of-architecture-am-i-using - qué-tipo-de-arquitectura-estoy-usando).
4. Si tienes problemas, hay muchos tutoriales en Internet acorde a cada duda.

### 2. Instalando el contenido de _conoce-el-cielo_ 

El resto del contenido de *conociendo se ubica en el mismo repositorio de GitHub, tal y como el documento que estás leyendo ahora mismo. GitHub es una plataforma popular para distribuir y realizar un seguimiento de los cambios en los archivos. Si bien puedes navegar por GitHub en en la web, la forma más eficaz de descargar código de GitHub es mediante el uso de la aplicación ‘git’, que garantiza que el código esté bien organizado en su computadora y te permite mantenerlo actualizado de manera confiable. Lo haremos ejecutando los siguientes comandos de shell: Para instalar ‘git’ usando ‘conda’ y entonces procedemos a buscar el contenido con ‘git’.

#### Donde ejecutar los comandos

En MacOS y Linux, ‘conda’ es totalmente compatible con los programas de terminal integrados.
En MacOS, puedes usar Terminal y, si estás en Linux, probablemente ya tengas una consola definida. En Windows, sin embargo, no puedes usar la función integrada programas de símbolo del sistema o Powershell. El instalador de Windows Miniforge también
instala un programa de terminal llamado 'Miniforge Prompt', que luego de su instalación, se ubica en el menú de inicio. Puedes usarlo para ejecutar los comandos que vayas necesitando.

#### Instalación de ‘git’

Desde la línea de comando, ejecuta ‘conda install -n base git’. 
Esto significa "instalar el paquete ‘git’ en el entorno base de conda" (explicaremos más sobre entornos en breve). Di sí a las indicaciones. Ahora tienes un "git"!

#### Descargar _Conociendo el Cielo_

Define y posiciónate en la carpeta en la que deseas descargar el contenido de *conociendo mediante el uso del comando ‘cd’. Por ejemplo, si deseas descargarlo en una subcarpeta de una carpeta en tu directorio raíz llamada 'proyectos', ejecuta “cd proyectos”. Si deseas, también puedes descargarlo en una subcarpeta justo en tu directorio raíz.

Luego, descarga el contenido ejecutando ‘git clone https://github.com/MillionConcepts/knowing-the-sky.git’ (add screenshot?)
Esto significa: "cree una carpeta y descargue todos los archivos del repositorio, en esa carpeta, junto con información sobre su historial de modificaciones".
Ahora, si ejecutas ‘ls’, deberías ver una nueva carpeta llamada _conoce-el-cielo_ 

### Creando un Entorno Conda

Conda ayuda a que las dependencias de Python se organicen y ejecuten correctamente mediante la creación de "entornos" distintos y asegurarse de que todo el software de un entorno sea mutuamente compatible.
El texto ‘(base)’ que se ve justo antes de la línea de código es una señal de Conda que
estás en su entorno llamado 'base', que es el entorno predeterminado creado con cada instalación de Conda.

En general, es una buena práctica crear un entorno Conda separado para cada proyecto Python. _conoce-el-cielo_  incluye un archivo de entorno Conda - una especificación para un entorno Conda que puede ejecutar todo su contenido. Para crear ese entorno, se debe ejecutar ‘cd know-the-sky’ para pasar al repositorio carpeta, luego ejecutar ‘conda env create -f Environment.yml’. Esto significa "crear un Nuevo entorno Conda basado en la especificación del archivo Environment.yml.'
Responda sí a cualquier indicación y espere a que "conda" descargue y organice los paquetes de información.


Después de que ‘conda’ finalice esta etapa, puedes activar el entorno ejecutando ‘conda activate conoce-el-cielo’. Cuando ejecutas ese comando, el mensaje ‘(base)’ delante de su mensaje cambiará a _conoce-el-cielo_ . Cuando un ambiente está operando correctamente, los comandos de shell que actives, ejecutarán las versiones del software instalado en ese entorno. 

**IMPORTANTE:** siempre debes tener este entorno "conoce-el-cielo" activo cuando requieras ejecutar el servidor Jupyter para utilizar los notebooks "conoce-el-cielo". Es posible que no se ejecute o que se ejecute de formas incorrectas, si es que no tienes activo "conoce-el-cielo".

En este momento, tu instalación está completa!

## Usando Jupyter Notebook

### Inicializando el Servidor Jupyter

Para utilizar un Notebook en Jupyter, se debe tener en ejecución el servidor Jupyter. Se puede ejecutar desde la línea de comando ejecutando ‘jupyter notebook’.
Esto debería abrir una ventana de navegador con la interfaz de Jupyter Notebook.
Recuerda tener activo el entorno _conoce-el-cielo_ .

### Abrir un archivo de Jupyter Notebook

En tu navegador de Internet, debería aparecer la interfaz de “página de inicio” de Jupyter Notebook, que es básicamente un administrador de archivos. Deberías ver todos los archivos en el directorio base del repositorio. Si haces click en la subcarpeta ‘conoce-el-cielo’, verás un grupo de archivos .ipynb Jupyter Notebook. Si haces click en uno de ellos, Jupyter lo abrirá en una sesión interactiva.

Ahora puedes continuar con el notebook  ‘0_getting_started_companion_notebook.ipynb’ para un tutorial rápido sobre cómo utilizar dicha interfaz.

### Comentarios Generales sobre el Notebook

La mayoría de las formas de ejecutar código lo hacen de una forma "no interactiva", es decir, que todo el programa se ejecuta en una sola ocasión, únicamente deteniéndose para verificar el input solo cuando se haya especificado en el código de programación.

Por el contrario, los notebooks te permiten escribir y ejecutar fragmentos de un programa a a tu propio ritmo. Si alguna vez has utilizado una sesión interactiva en algún lenguaje de programación, desde Python hasta MATLAB, ya tendrías conocimiento de la idea de operación.

La mayor diferencia entre las línea de comandos de sesiones interactivas tradicionales y entornos como Notebook es el concepto de células persistentes. Cuando tú ejecutas una celda, todo el código en una celda se ejecuta a la vez, exactamente de la misma forma que cuando ejecutas código en una línea de comando. Sin embargo, ese código se mantiene como una celda editable en tu ventana. Puedes editarlo inmediatamente y ejecutarlo nuevamente, y, de manera más general, ejecutar celdas en cualquier orden (sin importar cómo estén organizadas en la página).

Esto genera una gran flexibilidad. Puedes examinar el output de pasos individuales antes de continuar con la siguiente línea de código, de forma que puedes averiguar lo que debas escribir en la siguiente celda de código, o decidir si regresar y cambiar algo. Esto hace que los Jupyter Notebooks sean muy populares en aplicaciones que van desde la exploración de datos, así como casos de estudio académicos, o incluso Tecnologías de Información. [Esta flexibilidad también tiene algunas desventajas.](#downsides-of-jupyter-notebook)


## Apéndices

### Qué tipo de Arquitectura estoy usando?

* En MacOS: [Sigue las instrucciones en esta página de soporte técnico de Apple para saber si estás usando una Apple Silicon Mac o una Intel Mac.] (https://support.apple.com/en-us/HT211814)
Si tiene una Apple Silicon Mac, instala Miniforge3-MacOSX-arm64.
Si tienes una Intel Mac, instala Miniforge3-MacOSX-x86_64.
* En Linux: Abre una terminal y ejecuta ‘uname -a’. Si imprime 'amd64' o 'x86_64',
 instala Miniforge3-Linux-x86_64. Si imprime 'aarch64' o 'arm64', entonces instala Miniforge3-Linux-aarch64.

### Desventajas de los Jupyter Notebooks

Nos encantan los Jupyter Notebooks, pero no son recomendables para todas las necesidades de programación. A continuación te brindamos algunas consideraciones si es que los piensas usar en otro tipo de proyectos:

1. Debido a su flexibilidad y no linealidad, es fácil que se desorganice el código introducido. Esto significa que normalmente no es una buena idea escribir aplicaciones grandes y complejas únicamente en Notebooks. Muchos desarrolladores optan por crear prototipos de secciones individuales en Notebook y a medida que el código se vuelve más complejo, lo convierten en un módulo Python normal. Luego,vuelven al Notebook, importan el código de su módulo, y siguen creando prototipos de código.
2. A menos que incluyan en una función única, todas las variables en un Notebook están en alcance global (es decir, en todo el documento). Esto puede causar colisiones entre nombres en diferentes partes del programa, lo que genera errores confusos (por ejemplo, una función definida al principio del archivo podría hacer referencia accidentalmente a una variable definida más adelante en el archivo que ni siquiera se pensó que estuviera relacionada con esa función).
3. El historial de Notebook, y sus funciones relacionadas, significan que los outputs de las celdas individuales permanecen en la memoria si no se borra el historial explícitamente. Es común que esto provoque errores con el histórico de la memoria del archivo.
4. El 'loop' que permite que Notebook funcione de forma interactiva puede interferir con otros tipos de código asíncrono o multiproceso que se estén ejecutando.
5. Si accidentalmente ejecutas código que genera una enorme cantidad de texto, un montón de imágenes enormes, o algo similar, esto pudiera generar que Notebook se vuelva muy lento o incluso llegar a congelarse, volviéndose lento o incluso imposible abrir ese Notebook más tarde si su output se guarda en el archivo.

## Conceptos Requeridos de Python

Si alguna de las expresiones en uno de estos bloques de código no te hacen sentido, te recomendamos repasar esa parte de su conocimiento de Python antes de comenzar el curso.

Te recomendamos la documentación oficial de Python como primera referencia para
conceptos fundamentales de Python y hemos incluido referencias a secciones en cada bloque. 
'PT' se refiere a secciones del [tutorial oficial de Python (Python Tutorial)] (https://docs.python.org/3/tutorial/index.html). 
'PSL' hace referencia a secciones de la [referencia de la biblioteca estándar de Python (Python Standard Library)] 
(https://docs.python.org/3/library/index.html#library-index).

### operadores básicos (PT 3.1, tipos integrados de PSL)
