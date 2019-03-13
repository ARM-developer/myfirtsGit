# myfirtsGit
En 2005, la relación entre la comunidad que desarrollaba el núcleo de Linux y la compañía que desarrollaba BitKeeper se vino abajo, y la herramienta dejó de ser ofrecida gratuitamente. Esto impulsó a la comunidad de desarrollo de Linux (y en particular a Linus Torvalds, el creador de Linux) a desarrollar su propia herramienta basada en algunas de las lecciones que aprendieron durante el uso de BitKeeper. Algunos de los objetivos del nuevo sistema fueron los siguientes:
    • Velocidad
    • Diseño sencillo
    • Fuerte apoyo al desarrollo no lineal (miles de ramas paralelas)
    • Completamente distribuido
    • Capaz de manejar grandes proyectos (como el núcleo de Linux) de manera eficiente (velocidad y tamaño de los datos)
Desde su nacimiento en 2005, Git ha evolucionado y madurado para ser fácil de usar y aún conservar estas cualidades iniciales. Es tremendamente rápido, muy eficiente con grandes proyectos, y tiene un increíble sistema de ramificación (branching) para desarrollo no lineal.
Git, es un software de control de versiones, Pues bien, se define como control de versiones a la gestión de los diversos cambios que se realizan sobre los elementos de algún producto o una configuración del mismo es decir a la gestión de los diversos cambios que se realizan sobre los elementos de algún producto o una configuración, y para los que aún no les queda claro del todo, control de versiones es lo que se hace al momento de estar desarrollando un software o una página web. Exactamente es eso que haces cuando subes y actualizas tu código en la nube, o le añades alguna parte o simplemente le editas cosas que no funcionan como deberían o al menos no como tú esperarías.
Distintos opciones para el uso de Git:
GitHub es una importante herramienta para el acceso centralizado a los proyectos gracias a las ventajas que plantea para el alojamiento de código. En este sentido, el servicio permite que varios participantes trabajen en un mismo proyecto a nivel global y que guarden sus cambios en cualquier momento y de forma independiente. A diferencia de otros proveedores de servicios, en lo que respecta a la administración de software open source, en GitHub el foco de atención no se sitúa en el proyecto como una compilación de código fuente, sino en la posibilidad de hacer un uso individualizado de los repositorios(directorios gestionados con Git). Los usuarios de GitHub pueden utilizar Git o Subversion como VCS (Version Control System) para gestionar, revisar y preparar sus proyectos de software.

GitLab ofrece numerosas y útiles características en su DVCS, como, por ejemplo, un proyecto wiki integrado y una página web de proyecto. Las continuas capacidades de integración de GitLab automatizan el análisis y la entrega del código, lo que permite ahorrar tiempo en la fase de prueba. Con un visor de código, pull requests y un práctico método para solucionar conflictos, GitLab permite acceder a todos los aspectos importantes de tu proyecto. La aplicación está escrita en Ruby.

SourceForge ya estaba presente en el mercado antes de GitHub y de muchas otras alternativas open source y hubo una época en la que estaba considerada como la primera opción de código abierto. En 2015, la empresa tuvo algunos problemas con el malware, pero desde enero de 2016 va por el buen camino. Actualmente, SourceForge ofrece la autenticación multifactor, lo que armoniza con una orientación generalmente segura. Entre las características adicionales que pone a disposición de los usuarios se encuentran el sistema de seguimiento de incidentes y una lista de código incorporada.

Cloud Source Repositories se encarga de la gestión de Google Cloud Platform. Con Cloud Source Repositories, que se encuentra en la versión beta, se pueden vincular otros repositorios vía GitHub o Bitbucket en función de las necesidades. En este caso, también es posible hacer uso de los repositorios propios de Google, los cuales se pueden guardar a través de la infraestructura de Google, lo que significa que tanto tu código como tus aplicaciones van de la mano. La ventaja más importante de Cloud Source Repositories es que permite buscar código directamente a través del navegador. Asimismo, también tienes la posibilidad de detectar bugs con Cloud Diagnostics mientras el código se ejecuta en un segundo plano.

GitKraken otorga un gran valor al ahorro de tiempo, algo que favorece a los usuarios a la hora de probar el código. Al sistema se le conoce, principalmente, por tener una interfaz muy vistosa, por centrarse en la velocidad y por el fácil manejo de Git. Con un práctico botón para deshacer operaciones se pueden revisar errores al momento, lo que hace más fácil el flujo de trabajo. La versión gratuita es apta para empresas con menos de 20 trabajadores o para organizaciones sin ánimo de lucro. La versión Pro, por su parte, ofrece características de gran utilidad, como por ejemplo el soporte de perfiles que permite separar proyectos con comodidad.

Allura es un software de código abierto de Apache para la gestión de repositorios de código fuente, informes de errores, debates, páginas wiki, blogs y otros contenidos online. Para llevar a cabo el seguimiento de incidentes en Allura puedes recurrir tanto a las opciones de formateo y archivos adjuntos de Markdown como a los tickets provistos por el sistema llamado Milestones. Asimismo, también hay disponible una sintaxis de búsqueda avanzada con la que, por ejemplo, se pueden guardar las consultas más frecuentes. Sin embargo, Apache Allura no permite el análisis del código. La plataforma, además, fue desarrollada con el lenguaje de programación Python.
Empezamos una serie de artículos sobre git-flow, conjunto de extensiones de git que facilitan la gestión de ramas y flujos de trabajo.
las ramas. Se hablaba de ramas para hacer hot-fixes urgentes, ramas para desarrollar nuevas versiones separadas de las ramas maestras donde está la versión en producción. Ramas para probar nuevas versiones, ramas y repositorios para trabajar con proveedores externos, ramas para hacer pruebas en pre-producción, ramas para que los departamentos de calidad hagan sus pruebas antes de liberar nuevas versiones. Con git podemos crear ramas “como churros” y ese fin de semana tuve la oportunidad de compartir con varios colegas de profesión cómo utilizar las ramas para hacer el bien. Sin embargo, esta facilidad para crear ramas también se puede utilizar para hacer el mal y sembrar el terror. Más de una vez he visto ramas creadas sin ningún criterio, sin ningún flujo de información detrás que las sustente. Esta situación suele llevar al repositorio al caos más absoluto.

El trabajo se organiza en dos ramas principales:
    • Rama master: cualquier commit que pongamos en esta rama debe estar preparado para subir a producción
    • Rama develop: rama en la que está el código que conformará la siguiente versión planificada del proyecto
Cada vez que se incorpora código a master, tenemos una nueva versión.
Además de estas dos ramas, Se proponen las siguientes ramas auxiliares:
    • Feature
    • Release
    • Hotfix
Feature or topic branches
    • Se originan a partir de la rama develop.
    • Se incorporan siempre a la rama develop.
    • Nombre: cualquiera que no sea master, develop, hotfix-* o release-*
Release branches
    • Se originan a partir de la rama develop
    • Se incorporan a master y develop
    • Nombre: release-*
Estas ramas se utilizan para preparar el siguiente código en producción. En estas ramas se hacen los últimos ajustes y se corrigen los últimos bugs antes de pasar el código a producción incorporándolo a la rama master.
Hotfix branches
    • Se origina a partir de la rama master
    • Se incorporan a la master y develop
    • Nombre: hotfix-*
Esas ramas se utilizan para corregir errores y bugs en el código en producción. Funcionan de forma parecida a las Releases Branches, siendo la principal diferencia que los hotfixes no se planifican.

Markdown nació como herramienta de conversión de texto plano a HTML.
Esta herramienta fue creada en 2004 por John Gruber, y se distribuye de manera gratuita bajo una licencia BSD.
Aunque en realidad Markdown también se considera un lenguaje que tiene la finalidad de permitir crear contenido de una manera sencilla de escribir, y que en todo momento mantenga un diseño legible, así que para simplificar puedes considerar Markdown como un método de escritura.
De cara al usuario final no hay ninguna diferencia, por ejemplo este artículo acerca de  como funciona transferwise está escrito en Markdown, y sin embargo ves que está perfectamente formateado.
Markdown será perfecto para ti sobre todo si publicas de manera constante en Internet, donde el lenguaje HTML está más que presente: WordPress, Squarespace, Jekyll…
Pero no estoy hablando solo de blog o páginas web.Servicios como Trello o foros como Stackoverflow también soportan este lenguaje, y con el paso del tiempo encontrarás aún más lugares que lo utilicen.
