<p style="font-size: 1.3em;"><strong>CFGS Administración de Sistemas Informáticos en Red (1º curso)</strong></p>

Material elaborado para el módulo **Implementación de Sistemas Operativos**

# UT1.2. Componentes software: el sistema operativo

*Segundo bloque de la UT1 "Introducción a los sistemas informáticos" (25 horas totales). Este bloque ocupa 4 de esas 25 horas.*

## Programación de Aula

### Resultados de Aprendizaje

Esta unidad continúa trabajando el **Resultado de Aprendizaje 1 (RA1)** del módulo (ver UT1.1 para el texto completo del RA), centrándose especialmente en los criterios:

- **CE1.2.** Se han identificado las características, funciones y arquitectura de un sistema operativo.
- **CE1.3.** Se han comparado diferentes sistemas operativos, sus versiones y licencias de uso, en función de sus requisitos, características y campos de aplicación.
- **CE1.4.** Se han realizado instalaciones de diferentes sistemas operativos.
- **CE1.8.** Se ha elaborado documentación de soporte relativa a las instalaciones efectuadas y a las incidencias detectadas.

!!! info "Lectura recomendada"
    Este material amplía y complementa (sin reproducirlo) el contenido del **Capítulo 3** del libro *[Conceptos básicos sobre sistemas operativos](https://somebooks.es/conceptos-basicos-sobre-sistemas-operativos/)* de SomeBooks.es (P. Ruiz).

### Planificación Temporal (2 sesiones / 4 horas)

| Sesión | Contenido |
| ------ | --------- |
| 1 | Software de sistema/aplicación, lenguajes y licencias (propietarias y libres) |
| 2 | SO libres y propietarios. Instalación e interacción con el sistema |

## 1. Sistema operativo y aplicaciones

### 1.1 Software de sistema

El **software de sistema** es el conjunto de programas que gestionan directamente el hardware y sirven de plataforma para el resto del software. El más importante es el **sistema operativo**, pero también se incluyen aquí los controladores (drivers) y las utilidades básicas del sistema. Para que los programas de aplicación puedan aprovechar estos servicios sin tener que conocer los detalles internos del hardware, el software de sistema ofrece una **API** (Application Programming Interface): un conjunto de funciones que cualquier programador puede invocar para, por ejemplo, leer un archivo, dibujar una ventana o enviar datos por la red.

### 1.2 Software de aplicación

El **software de aplicación** son los programas que un usuario ejecuta para realizar una tarea concreta (escribir un documento, navegar por internet, editar una imagen). Se apoya siempre en el software de sistema para poder acceder al hardware. Puede clasificarse a su vez en aplicaciones de **propósito general**, útiles en prácticamente cualquier contexto (un procesador de textos, un navegador web), y aplicaciones **específicas**, pensadas para un sector o tarea concreta (un programa de contabilidad, una herramienta de diseño asistido por ordenador o un videojuego).

## 2. Los lenguajes de programación

Todo software, ya sea de sistema o de aplicación, se escribe en un **lenguaje de programación**: un conjunto de reglas y sintaxis que permite a una persona expresar instrucciones que, tras un proceso de traducción (compilación o interpretación), el procesador puede ejecutar. Existen lenguajes de muy distinto nivel: desde el lenguaje máquina (las instrucciones binarias que entiende directamente el procesador) hasta lenguajes de alto nivel, mucho más cercanos al lenguaje humano y por tanto más fáciles de escribir y mantener.

El texto que escribe el programador se llama **código fuente**; el proceso que lo traduce a lenguaje máquina se llama **compilación**, y su resultado es el **código objeto** (o ejecutable). Algunos lenguajes, en lugar de compilarse directamente a código máquina, se traducen a un **bytecode** intermedio que después ejecuta una máquina virtual (como ocurre con Java), lo que permite que el mismo programa funcione en sistemas operativos distintos sin necesidad de recompilarlo. Para facilitar el trabajo de programación se utilizan los **IDE** (Entornos de Desarrollo Integrados), que combinan en una sola herramienta el editor de código, el compilador y utilidades de depuración.

## 3. Clasificación del software según su licencia

La **licencia** de un programa establece los términos bajo los que se puede usar, copiar, modificar o redistribuir. La primera gran distinción que conviene hacer es entre el software de **código cerrado o propietario**, en el que el fabricante no distribuye el código fuente y limita lo que el usuario puede hacer con el programa, y el software de **código abierto**, que sí pone el código fuente a disposición de quien lo use.

### 3.1 Software libre y de código abierto

<img src="https://commons.wikimedia.org/wiki/Special:FilePath/Heckert_GNU_white.svg" alt="Logotipo del proyecto GNU" width="200">
*El gnu es la mascota del proyecto GNU, iniciado por Richard Stallman en 1983. (Imagen: Wikimedia Commons, CC BY-SA)*

El movimiento del **software libre** nace en 1983, cuando Richard Stallman funda el proyecto GNU y, poco después, la **Free Software Foundation (FSF)**, con el objetivo de defender la libertad de los usuarios frente al software propietario. Según la definición de la FSF, un programa es software libre cuando garantiza cuatro libertades básicas:

- **Libertad 0:** ejecutar el programa con cualquier propósito.
- **Libertad 1:** estudiar cómo funciona y adaptarlo a las propias necesidades (para lo cual es imprescindible tener acceso al código fuente).
- **Libertad 2:** redistribuir copias para ayudar a otros usuarios.
- **Libertad 3:** mejorar el programa y publicar esas mejoras, de modo que toda la comunidad se beneficie de ellas.

Conviene aclarar que **"libre" no equivale a "gratuito"**: el software libre puede venderse, siempre que el usuario conserve esas cuatro libertades una vez que dispone del programa. El término **código abierto (open source)**, promovido desde 1998 por la Open Source Initiative, describe en la práctica un conjunto de licencias muy similar, aunque pone el énfasis en las ventajas técnicas del desarrollo colaborativo más que en la libertad del usuario como valor en sí mismo; por eso es habitual encontrar la expresión conjunta **FLOSS/FOSS** (software libre y de código abierto) para referirse a ambos indistintamente.

Dentro de las licencias libres se distinguen dos grandes familias:

| Tipo | Características | Ejemplos de licencias | Ejemplos de software |
| ---- | ---------------- | ---------------------- | ---------------------- |
| **Permisivas** | Permiten modificar el programa, combinarlo con código propietario o crear productos a partir de él, sin obligación de publicar el código de esas modificaciones | BSD, MIT, Apache License | Muchas librerías y utilidades del propio núcleo Linux |
| **Copyleft (no permisivas)** | Obligan a que cualquier obra derivada se publique bajo la misma licencia (o una compatible), garantizando que las libertades se mantengan también en las versiones modificadas | GPL (v2 y v3), LGPL, MPL | El núcleo Linux (GPL), Firefox (MPL), LibreOffice (LGPL) |

### 3.2 Otras modalidades: freeware, shareware y dominio público

Además de las dos grandes familias anteriores, existen otras variantes intermedias que conviene distinguir:

- **Freeware:** software gratuito y de uso indefinido, cuya redistribución suele estar permitida, pero no así su modificación ni, en ocasiones, su uso comercial (no se entrega el código fuente).
- **Shareware:** permite evaluar el programa con algunas limitaciones de tiempo o de funcionalidad, hasta que se adquiere la versión completa de pago.
- **Dominio público:** software publicado sin ningún tipo de licencia ni restricción, que por tanto puede usarse, modificarse o redistribuirse libremente.

### 3.3 Comercialización de productos con licencias propietarias

Dentro del software propietario (de pago), existen distintas modalidades de comercialización:

| Modalidad | Descripción |
| ---------- | ----------- |
| Retail o FPP (Full Packaged Product) | Versión completa, en caja, pensada para la venta individual al usuario final |
| OEM (Original Equipment Manufacturer) | Versión más económica, vendida junto con un equipo nuevo, vinculada a ese hardware concreto |
| Licencias por volumen | Contrato único que permite instalar el software en muchos equipos de una organización, sin necesidad de gestionar una clave por unidad |

## 4. Sistemas operativos actuales

Un **sistema operativo** es el software que gestiona los recursos del hardware (procesador, memoria, dispositivos) y ofrece una plataforma común sobre la que se ejecutan las aplicaciones. En el panorama actual, conviven distintas familias de sistemas operativos según el tipo de dispositivo:

- **De escritorio:** Windows, GNU/Linux, macOS.
- **De servidor:** Windows Server, distribuciones Linux orientadas a servidor (Ubuntu Server, RedHat, CentOS...), variantes de UNIX.
- **Móviles y embebidos:** Android, iOS, y sistemas para dispositivos concretos (routers, televisores, electrodomésticos inteligentes).

Dentro de cada familia conviven además distintas **versiones**, que van sucediéndose con el tiempo; cada una con sus propios requisitos de hardware y su propio ciclo de soporte (el tiempo durante el que el fabricante sigue publicando actualizaciones de seguridad).

## 5. Sistemas operativos libres y propietarios

### 5.1 Microsoft Windows

**Windows** es el sistema operativo propietario más extendido en equipos de escritorio a nivel mundial. Se distribuye bajo licencia comercial, con distintas ediciones según el uso (Home, Pro, Enterprise, Server...), y su código fuente no es público. Windows apareció en 1985 como una interfaz gráfica sobre MS-DOS, y no fue hasta Windows XP (2001) cuando la rama de escritorio incorporó el núcleo NT que se sigue utilizando hoy en día.

### 5.2 Ubuntu Linux (y GNU/Linux en general)

<img src="https://commons.wikimedia.org/wiki/Special:FilePath/Tux.svg" alt="Tux, la mascota de Linux" width="200">
*Tux, el pingüino que representa al núcleo Linux desde 1996. (Imagen: Wikimedia Commons, dominio público)*

**Linux** no es en sí mismo un sistema operativo completo, sino el **núcleo (kernel)**, publicado por Linus Torvalds en 1991, sobre el que se construyen numerosas **distribuciones** (Ubuntu, Fedora, Debian...), cada una añadiendo su propio conjunto de programas, entorno gráfico y herramientas de gestión. La mayoría de estas distribuciones son software libre (licencia GPL), con su código fuente disponible públicamente. **Ubuntu**, patrocinada por Canonical, publica una nueva versión cada seis meses, y cada dos años una versión **LTS (Long Term Support)** con varios años de soporte extendido, recomendada para entornos de producción.

### 5.3 Ventajas y desventajas de Linux y del software libre en general

| Aspecto | Software libre | Software propietario |
| -------- | ---------------- | ----------------------- |
| Coste | Habitualmente gratuito | Requiere licencia de pago |
| Código fuente | Accesible, se puede auditar y modificar | No accesible |
| Soporte | Comunitario (foros, documentación colaborativa), aunque existen empresas que ofrecen soporte comercial | Soporte oficial del fabricante |
| Compatibilidad de software | Puede haber menos programas comerciales o de terceros adaptados | Mayor disponibilidad de software comercial específico |
| Seguridad | El código auditable por cualquiera facilita detectar y corregir vulnerabilidades rápidamente | Depende exclusivamente del fabricante para publicar parches |
| Curva de aprendizaje | Puede requerir más familiarización, según la distribución | Suele estar más orientado a la facilidad de uso inmediata |
| Actualizaciones | Gestionadas mediante repositorios, suelen incluir también las aplicaciones instaladas | Gestionadas por el propio sistema operativo; las aplicaciones se actualizan por separado |

## 6. Instalación de sistemas operativos

### 6.1 Planificación de la instalación

<img src="https://commons.wikimedia.org/wiki/Special:FilePath/GParted%201.3.1%20screenshot.png" alt="GParted mostrando el particionado de un disco" width="500">
*GParted, una herramienta libre para crear, redimensionar y gestionar particiones de disco. (Imagen: Wikimedia Commons, licencia GPL)*

Antes de instalar un sistema operativo conviene planificar cuidadosamente el proceso, ya que una mala planificación es la causa más habitual de incidencias posteriores. Entre los aspectos a valorar se encuentran:

- **Qué producto instalar:** edición o distribución concreta (por ejemplo, Windows 11 Pro o Ubuntu Desktop 24.04 LTS), en función de las necesidades del equipo y de las licencias disponibles.
- **Requisitos y compatibilidad:** comprobar que el hardware del equipo cumple los requisitos mínimos (véase 6.3) y que existen controladores disponibles para todos sus componentes.
- **Particionado del disco:** cuántas particiones crear y de qué tamaño (véase 6.4).
- **Configuración de red:** si el equipo usará una IP fija o dinámica (DHCP), y a qué dominio o grupo de trabajo pertenecerá.
- **Número de equipos:** si se trata de un único ordenador o de varios equipos idénticos (por ejemplo, en un aula o una empresa), lo que condiciona si conviene o no automatizar el proceso.
- **Copia de seguridad previa:** si el equipo ya contiene datos importantes, siempre conviene respaldarlos antes de tocar las particiones o el sistema operativo.

En función de la situación de partida, existen distintos tipos de instalación:

- **Instalación nueva (limpia):** se instala el sistema operativo sobre un disco vacío o recién formateado, sin conservar nada de lo que hubiera antes.
- **Actualización (*update*):** se instala una versión más reciente del mismo sistema operativo conservando los datos y los programas ya instalados.
- **Migración:** se sustituye por completo el sistema operativo existente por otro distinto (por ejemplo, pasar de Windows a GNU/Linux), lo que obliga a restaurar los datos desde una copia de seguridad, ya que normalmente no pueden conservarse los programas.
- **Instalación desatendida:** pensada para instalar el mismo sistema operativo en varios equipos, empleando un archivo de respuesta que contiene de antemano todos los parámetros de la instalación (idioma, particionado, cuenta de usuario, etc.), de modo que el proceso se completa sin necesidad de intervención manual en cada equipo.

Por último, conviene decidir también el **medio de instalación**: un DVD o memoria USB de arranque, una imagen ISO montada directamente, o incluso el arranque por red mediante el protocolo **PXE**, muy utilizado en instalaciones desatendidas de varios equipos a la vez.

### 6.2 Parámetros básicos de la instalación

Durante el proceso de instalación se suelen definir, como mínimo: el idioma y la configuración regional, la zona horaria, el nombre del equipo, la cuenta de usuario inicial y su contraseña, y el particionado del disco.

### 6.3 Requisitos técnicos del sistema operativo

Cada sistema operativo publica unos **requisitos mínimos** de hardware (procesador, memoria RAM, espacio en disco, tarjeta gráfica) necesarios para poder instalarse y funcionar correctamente, que deben comprobarse antes de iniciar la instalación; además de los mínimos, el fabricante suele indicar también unos requisitos recomendados para un funcionamiento fluido.

### 6.4 Particiones y sistema de archivos

El disco de destino debe estar particionado, y cada partición debe formatearse con un **sistema de archivos** compatible con el sistema operativo a instalar (por ejemplo, NTFS para Windows, ext4 para muchas distribuciones Linux). El número y tamaño de las particiones depende de cómo se quiera organizar la información: es habitual, por ejemplo, separar en una partición el sistema operativo y en otra distinta los datos del usuario, para facilitar copias de seguridad o una futura reinstalación.

### 6.5 Instalación del sistema

El proceso de instalación en sí copia los archivos del sistema operativo al disco, configura el gestor de arranque y aplica los parámetros indicados durante la planificación. Al finalizar, el equipo debe poder arrancar de forma autónoma directamente desde el disco, sin necesidad del medio de instalación (USB, DVD o red) utilizado para el proceso.

## 7. Interacción con el sistema operativo

### 7.1 Origen de las interfaces gráficas de usuario

Las primeras interfaces de los ordenadores eran puramente textuales. La **interfaz gráfica de usuario (GUI)**, con ventanas, iconos y un puntero controlado por un dispositivo señalador, surgió para hacer la interacción más intuitiva y accesible, generalizándose desde los años 80 en adelante, a partir de los trabajos pioneros de Xerox PARC y de su popularización comercial por parte de Apple y, poco después, de Microsoft con Windows.

### 7.2 Uso del ratón en las interfaces gráficas

El ratón (u otros dispositivos señaladores, como el trackpad o la pantalla táctil) permite señalar y manipular directamente los elementos que aparecen en pantalla, complementando o sustituyendo a los comandos escritos.

### 7.3 Interfaces gráficas de usuario actuales

Los sistemas operativos actuales ofrecen interfaces gráficas ricas, con soporte para gestos táctiles, múltiples escritorios virtuales y personalización avanzada, aunque mantienen los mismos principios básicos de ventanas, iconos y menús. En GNU/Linux, a diferencia de Windows, la interfaz gráfica no forma parte del propio sistema operativo, sino que se ejecuta como una capa independiente (el servidor gráfico) sobre la que se instalan distintos **entornos de escritorio** (GNOME, KDE, Xfce...), lo que permite al usuario elegir el aspecto y el comportamiento que prefiera.

### 7.4 Interfaz de texto

Junto a la interfaz gráfica, los sistemas operativos mantienen una **interfaz de texto** (línea de comandos), donde las órdenes se escriben directamente como texto. Aunque tiene una curva de aprendizaje mayor, resulta mucho más potente para tareas de automatización, administración remota o scripts, ya que permite agrupar varias órdenes en un archivo y ejecutarlas de forma repetida sin intervención manual.

### 7.5 La interfaz de texto de Windows

Tradicionalmente el símbolo del sistema (CMD), heredero de MS-DOS, con una sintaxis de comandos relativamente limitada y poco orientada a la automatización avanzada.

### 7.6 PowerShell, la interfaz de texto avanzada para Windows

**PowerShell** es la interfaz de texto avanzada de Microsoft, mucho más potente que CMD. A diferencia de un shell tradicional (que solo maneja texto), PowerShell trabaja internamente con **objetos**, lo que facilita enormemente la automatización y administración de sistemas Windows: el resultado de una orden no es simple texto, sino una estructura de datos de la que se pueden extraer propiedades concretas o que se puede pasar directamente como entrada a la siguiente orden.

### 7.7 La interfaz de texto de GNU/Linux

El shell (como **Bash**) es fundamental en la administración de sistemas Linux, siendo el mecanismo habitual para automatizar tareas mediante scripts. Existen otras shells alternativas (zsh, ksh), pero Bash es, con diferencia, la más extendida en la mayoría de distribuciones.

### 7.8 Después de instalar

Tras completar la instalación, es habitual: instalar los controladores específicos del hardware, aplicar las actualizaciones disponibles, instalar el software adicional que se vaya a necesitar y configurar las opciones básicas del sistema (red, usuarios, seguridad) antes de empezar a usarlo en producción.

### 7.9 El gestor de arranque en sistemas Windows

El gestor de arranque (Boot Manager) es el responsable de cargar el sistema operativo al encender el equipo, y de gestionar el arranque dual si hay más de un sistema instalado. En las versiones actuales de Windows, esta función corresponde a BOOTMGR, que se apoya en un almacén de configuración cifrado llamado BCD (Boot Configuration Data), gestionable con la herramienta de línea de comandos `bcdedit`.

### 7.10 El gestor de arranque en sistemas Linux

<img src="https://commons.wikimedia.org/wiki/Special:FilePath/GRUB_screenshot.png" alt="Menú de arranque de GRUB" width="500">
*Menú de GRUB mostrando varias opciones de arranque. (Imagen: Wikimedia Commons, licencia libre)*

El gestor de arranque habitual es **GRUB**, que además de arrancar Linux, puede detectar y ofrecer el arranque de otros sistemas operativos instalados en el mismo equipo (lo que se conoce como arranque dual o *dual boot*), mostrando al usuario un menú donde elegir con cuál iniciar sesión.

## 8. Elaboración de la documentación sobre la instalación e incidencias

Como recoge el criterio CE1.8, toda instalación debe quedar **documentada**: parámetros aplicados, incidencias surgidas durante el proceso, y soluciones adoptadas. Esta documentación es esencial en un entorno profesional, tanto para el propio historial del equipo como para facilitar el trabajo de otros técnicos en el futuro. Como mínimo conviene registrar un identificador único del equipo, sus características de hardware, el sistema operativo instalado (versión, fecha y clave de licencia si procede), el software adicional instalado y la configuración de red aplicada.

## Ejercicios prácticos

!!! task "Tarea"
    **Ejercicio 1**. Explica la diferencia entre software de sistema y software de aplicación, poniendo dos ejemplos de cada uno.

    **Ejercicio 2**. ¿Qué diferencia hay entre una licencia permisiva y una licencia copyleft? Pon un ejemplo de cada una.

    **Ejercicio 3**. Explica la diferencia entre una licencia OEM y una licencia Retail/FPP. ¿Cuál sería más adecuada para una empresa que compra 100 ordenadores nuevos?

    **Ejercicio 4**. Compara Windows y una distribución Linux (por ejemplo, Ubuntu) señalando al menos dos ventajas y dos inconvenientes de cada uno.

    **Ejercicio 5**. Enumera, en orden, los parámetros básicos que se suelen definir durante la instalación de un sistema operativo.

    **Ejercicio 6**. Explica la diferencia entre CMD y PowerShell en Windows. ¿Por qué se dice que PowerShell trabaja con "objetos" y no solo con texto?

    **Ejercicio 7**. ¿Qué es un gestor de arranque y qué diferencia hay entre el de Windows y GRUB (Linux)?

    **Ejercicio 8 (práctica en el aula)**. Instala un sistema operativo (en una máquina virtual) documentando cada parámetro que configures durante el proceso, siguiendo el esquema del punto 8.
