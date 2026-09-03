<p style="font-size: 1.3em;"><strong>CFGS Administración de Sistemas Informáticos en Red (1º curso)</strong></p>

Material elaborado para el módulo **Implementación de Sistemas Operativos**

# UT1.2. Componentes software: el sistema operativo

*Segundo bloque de la UT1 "Introducción a los sistemas informáticos" (14 horas totales). Este bloque ocupa 4 de esas 14 horas.*

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
| 1 | Software de sistema/aplicación, lenguajes y licencias |
| 2 | SO libres y propietarios. Instalación e interacción con el sistema |

## 1. Sistema operativo y aplicaciones

### 1.1 Software de sistema

El **software de sistema** es el conjunto de programas que gestionan directamente el hardware y sirven de plataforma para el resto del software. El más importante es el **sistema operativo**, pero también se incluyen aquí los controladores (drivers) y las utilidades básicas del sistema.

### 1.2 Software de aplicación

El **software de aplicación** son los programas que un usuario ejecuta para realizar una tarea concreta (escribir un documento, navegar por internet, editar una imagen). Se apoya siempre en el software de sistema para poder acceder al hardware.

## 2. Los lenguajes de programación

Todo software, ya sea de sistema o de aplicación, se escribe en un **lenguaje de programación**: un conjunto de reglas y sintaxis que permite a una persona expresar instrucciones que, tras un proceso de traducción (compilación o interpretación), el procesador puede ejecutar. Existen lenguajes de muy distinto nivel: desde el lenguaje máquina (las instrucciones binarias que entiende directamente el procesador) hasta lenguajes de alto nivel, mucho más cercanos al lenguaje humano y por tanto más fáciles de escribir y mantener.

## 3. Clasificación del software según su licencia

La **licencia** de un programa establece los términos bajo los que se puede usar, copiar, modificar o redistribuir.

### 3.1 Comercialización de productos con licencias propietarias

Dentro del software propietario (de pago), existen distintas modalidades de comercialización:

| Modalidad | Descripción |
| ---------- | ----------- |
| Retail o FPP (Full Packaged Product) | Versión completa, en caja, pensada para la venta individual al usuario final |
| OEM (Original Equipment Manufacturer) | Versión más económica, vendida junto con un equipo nuevo, vinculada a ese hardware concreto |
| Licencias por volumen | Contrato único que permite instalar el software en muchos equipos de una organización, sin necesidad de gestionar una clave por unidad |

## 4. Sistemas operativos actuales

Un **sistema operativo** es el software que gestiona los recursos del hardware (procesador, memoria, dispositivos) y ofrece una plataforma común sobre la que se ejecutan las aplicaciones. En el panorama actual, conviven distintas familias de sistemas operativos según el tipo de dispositivo (escritorio, servidor, móvil), y dentro de cada familia, distintas versiones que van sucediéndose con el tiempo, cada una con sus propios requisitos de hardware y ciclo de soporte.

## 5. Sistemas operativos libres y propietarios

### 5.1 Microsoft Windows

**Windows** es el sistema operativo propietario más extendido en equipos de escritorio a nivel mundial. Se distribuye bajo licencia comercial, con distintas ediciones según el uso (doméstico, profesional, servidor), y su código fuente no es público.

### 5.2 Ubuntu Linux (y GNU/Linux en general)

**Linux** no es en sí mismo un sistema operativo completo, sino el **núcleo (kernel)** sobre el que se construyen numerosas **distribuciones** (Ubuntu, Fedora, Debian...), cada una añadiendo su propio conjunto de programas, entorno gráfico y herramientas de gestión. La mayoría de estas distribuciones son software libre, con su código fuente disponible públicamente.

### 5.3 Ventajas y desventajas de Linux y del software libre en general

| Aspecto | Software libre | Software propietario |
| -------- | ---------------- | ----------------------- |
| Coste | Habitualmente gratuito | Requiere licencia de pago |
| Código fuente | Accesible, se puede auditar y modificar | No accesible |
| Soporte | Comunitario (foros, documentación colaborativa), aunque existen empresas que ofrecen soporte comercial | Soporte oficial del fabricante |
| Compatibilidad de software | Puede haber menos programas comerciales o de terceros adaptados | Mayor disponibilidad de software comercial específico |
| Seguridad | El código auditable por cualquiera facilita detectar y corregir vulnerabilidades rápidamente | Depende exclusivamente del fabricante para publicar parches |
| Curva de aprendizaje | Puede requerir más familiarización, según la distribución | Suele estar más orientado a la facilidad de uso inmediata |

## 6. Instalación de sistemas operativos

### 6.1 Planificación de la instalación

Antes de instalar un sistema operativo conviene planificar: qué edición o distribución instalar, cómo se va a particionar el disco, qué configuración de red se necesita, y si la instalación será individual o desatendida (para varios equipos).

### 6.2 Parámetros básicos de la instalación

Durante el proceso de instalación se suelen definir, como mínimo: el idioma y la configuración regional, la zona horaria, el nombre del equipo, la cuenta de usuario inicial y su contraseña, y el particionado del disco.

### 6.3 Requisitos técnicos del sistema operativo

Cada sistema operativo publica unos **requisitos mínimos** de hardware (procesador, memoria RAM, espacio en disco) necesarios para poder instalarse y funcionar correctamente, que deben comprobarse antes de iniciar la instalación.

### 6.4 Particiones y sistema de archivos

El disco de destino debe estar particionado, y cada partición debe formatearse con un **sistema de archivos** compatible con el sistema operativo a instalar (por ejemplo, NTFS para Windows, ext4 para muchas distribuciones Linux).

### 6.5 Instalación del sistema

El proceso de instalación en sí copia los archivos del sistema operativo al disco, configura el gestor de arranque y aplica los parámetros indicados durante la planificación.

## 7. Interacción con el sistema operativo

### 7.1 Origen de las interfaces gráficas de usuario

Las primeras interfaces de los ordenadores eran puramente textuales. La **interfaz gráfica de usuario (GUI)**, con ventanas, iconos y un puntero controlado por un dispositivo señalador, surgió para hacer la interacción más intuitiva y accesible, generalizándose desde los años 80 en adelante.

### 7.2 Uso del ratón en las interfaces gráficas

El ratón (u otros dispositivos señaladores, como el trackpad) permite señalar y manipular directamente los elementos que aparecen en pantalla, complementando o sustituyendo a los comandos escritos.

### 7.3 Interfaces gráficas de usuario actuales

Los sistemas operativos actuales ofrecen interfaces gráficas ricas, con soporte para gestos táctiles, múltiples escritorios virtuales y personalización avanzada, aunque mantienen los mismos principios básicos de ventanas, iconos y menús.

### 7.4 Interfaz de texto

Junto a la interfaz gráfica, los sistemas operativos mantienen una **interfaz de texto** (línea de comandos), donde las órdenes se escriben directamente como texto. Aunque tiene una curva de aprendizaje mayor, resulta mucho más potente para tareas de automatización, administración remota o scripts.

### 7.5 La interfaz de texto de Windows

Tradicionalmente el símbolo del sistema (CMD), heredero de MS-DOS, con una sintaxis de comandos relativamente limitada.

### 7.6 PowerShell, la interfaz de texto avanzada para Windows

**PowerShell** es la interfaz de texto avanzada de Microsoft, mucho más potente que CMD. A diferencia de un shell tradicional (que solo maneja texto), PowerShell trabaja internamente con **objetos**, lo que facilita enormemente la automatización y administración de sistemas Windows.

### 7.7 La interfaz de texto de GNU/Linux

El shell (como **Bash**) es fundamental en la administración de sistemas Linux, siendo el mecanismo habitual para automatizar tareas mediante scripts.

### 7.8 Después de instalar

Tras completar la instalación, es habitual: instalar los controladores específicos del hardware, aplicar las actualizaciones disponibles, y configurar las opciones básicas del sistema antes de empezar a usarlo en producción.

### 7.9 El gestor de arranque en sistemas Windows

El gestor de arranque (Boot Manager) es el responsable de cargar el sistema operativo al encender el equipo, y de gestionar el arranque dual si hay más de un sistema instalado.

### 7.10 El gestor de arranque en sistemas Linux

El gestor de arranque habitual es **GRUB**, que además de arrancar Linux, puede detectar y ofrecer el arranque de otros sistemas operativos instalados en el mismo equipo.

## 8. Elaboración de la documentación sobre la instalación e incidencias

Como recoge el criterio CE1.8, toda instalación debe quedar **documentada**: parámetros aplicados, incidencias surgidas durante el proceso, y soluciones adoptadas. Esta documentación es esencial en un entorno profesional, tanto para el propio historial del equipo como para facilitar el trabajo de otros técnicos en el futuro.

## Ejercicios prácticos

!!! task "Tarea"
    **Ejercicio 1**. Explica la diferencia entre software de sistema y software de aplicación, poniendo dos ejemplos de cada uno.

    **Ejercicio 2**. Explica la diferencia entre una licencia OEM y una licencia Retail/FPP. ¿Cuál sería más adecuada para una empresa que compra 100 ordenadores nuevos?

    **Ejercicio 3**. Compara Windows y una distribución Linux (por ejemplo, Ubuntu) señalando al menos dos ventajas y dos inconvenientes de cada uno.

    **Ejercicio 4**. Enumera, en orden, los parámetros básicos que se suelen definir durante la instalación de un sistema operativo.

    **Ejercicio 5**. Explica la diferencia entre CMD y PowerShell en Windows. ¿Por qué se dice que PowerShell trabaja con "objetos" y no solo con texto?

    **Ejercicio 6**. ¿Qué es un gestor de arranque y qué diferencia hay entre el de Windows y GRUB (Linux)?

    **Ejercicio 7 (práctica en el aula)**. Instala un sistema operativo (en una máquina virtual) documentando cada parámetro que configures durante el proceso, siguiendo el esquema del punto 8.
