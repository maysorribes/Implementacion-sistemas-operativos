<p style="font-size: 1.3em;"><strong>CFGS Administración de Sistemas Informáticos en Red (1º curso)</strong></p>

Material elaborado para el módulo **Implementación de Sistemas Operativos**

# UT1.4. Estructura del sistema operativo: entrada/salida y archivos

*Cuarto y último bloque de la UT1 "Introducción a los sistemas informáticos" (14 horas totales). Este bloque ocupa las 3 horas restantes.*

## Programación de Aula

### Resultados de Aprendizaje

Esta unidad completa el **Resultado de Aprendizaje 1 (RA1)** del módulo (ver UT1.1 para el texto completo del RA), centrándose especialmente en los criterios:

- **CE1.2.** Se han identificado las características, funciones y arquitectura de un sistema operativo.
- **CE1.7.** Se han utilizado herramientas para conocer el software instalado en el sistema y su origen.

!!! info "Lectura recomendada"
    Este material amplía y complementa (sin reproducirlo) el contenido del **Capítulo 5** del libro *[Conceptos básicos sobre sistemas operativos](https://somebooks.es/conceptos-basicos-sobre-sistemas-operativos/)* de SomeBooks.es (P. Ruiz).

### Planificación Temporal (1,5 sesiones / 3 horas)

| Sesión | Contenido |
| ------ | --------- |
| 1 | Gestión de Entrada/Salida y gestión de archivos |
| 2 (media sesión) | Sistemas de archivos, inodos y sistemas transaccionales. Repaso general de la UT1 |

## 1. Introducción

Tras estudiar en el bloque UT1.3 la gestión de procesos y de memoria, esta unidad completa la visión de las funciones internas del sistema operativo con dos aspectos igualmente esenciales: cómo se comunica el sistema con los dispositivos periféricos (**gestión de E/S**) y cómo organiza y almacena la información de forma persistente (**gestión de archivos**).

## 2. Gestión de Entrada/Salida

Cada dispositivo periférico (disco, teclado, impresora, tarjeta de red...) tiene sus propias particularidades de funcionamiento. La **gestión de E/S** del sistema operativo se encarga de ofrecer una interfaz uniforme para que las aplicaciones puedan usar cualquier dispositivo sin necesidad de conocer sus detalles técnicos concretos, delegando esa complejidad en los **controladores (drivers)** específicos de cada dispositivo.

### 2.1 Técnicas para las operaciones de entrada/salida

Existen distintas estrategias para gestionar la comunicación con los dispositivos de E/S:

| Técnica | Funcionamiento |
| -------- | ---------------- |
| E/S programada | El procesador espera activamente (consultando repetidamente) a que el dispositivo esté listo, sin hacer otra cosa mientras tanto |
| E/S por interrupciones | El procesador continúa con otras tareas y el dispositivo le avisa (interrupción) cuando está listo, mucho más eficiente que la espera activa |
| Acceso directo a memoria (DMA) | El propio dispositivo transfiere datos directamente a memoria sin que el procesador intervenga en cada byte, liberándolo casi por completo durante la transferencia |

### 2.2 Concepto de almacenamiento intermedio

Un **buffer** (memoria intermedia) es una pequeña zona de memoria donde se van acumulando temporalmente los datos que entran o salen de un dispositivo, para compensar la diferencia de velocidad entre el dispositivo (normalmente más lento) y el resto del sistema. Por ejemplo, al imprimir un documento, los datos se almacenan en un buffer y se envían a la impresora al ritmo que esta puede procesarlos, sin bloquear el resto del sistema.

## 3. Gestión de archivos

Un **archivo** es la unidad lógica en la que el sistema operativo organiza la información almacenada, independientemente de cómo esté físicamente distribuida en el disco. La **gestión de archivos** es la función del sistema operativo que permite crear, leer, modificar, eliminar y organizar esta información.

### 3.1 Atributos y permisos

Cada archivo tiene una serie de **atributos** que describen sus características: nombre, tamaño, fecha de creación y de última modificación, y en muchos sistemas, también atributos especiales (oculto, de solo lectura, de sistema...).

Además, los sistemas operativos actuales incorporan **permisos**, que determinan quién puede leer, modificar o ejecutar un archivo concreto, siendo un mecanismo fundamental de seguridad en sistemas multiusuario.

### 3.2 Organización del sistema de archivos: nombres y rutas

Los archivos se organizan en una estructura jerárquica de **directorios** (o carpetas), formando un árbol. La **ruta** de un archivo indica su ubicación exacta dentro de ese árbol, ya sea de forma absoluta (desde la raíz del sistema) o relativa (desde la ubicación actual).

#### Caracteres comodín (Wildcard)

Al trabajar con archivos, especialmente desde la línea de comandos, es habitual usar **caracteres comodín** para referirse a varios archivos a la vez sin escribir cada nombre completo: el asterisco (`*`) sustituye a cualquier secuencia de caracteres, y el interrogante (`?`) sustituye a un único carácter cualquiera.

### 3.3 Otros sistemas de archivos: ¿qué es FUSE?

**FUSE** (*Filesystem in Userspace*) es una tecnología que permite implementar sistemas de archivos personalizados sin necesidad de modificar el núcleo del sistema operativo, ejecutándose en el espacio del usuario. Gracias a ella, es posible, por ejemplo, "montar" servicios remotos (como un servidor en la nube) como si fueran una carpeta más del sistema.

## 4. Tipos de sistemas de archivos y sus características

Un **sistema de archivos** define cómo se organiza, física y lógicamente, la información dentro de una partición. Cada familia de sistemas operativos ha desarrollado los suyos propios:

### 4.1 Sistemas de archivos de la familia Microsoft

| Sistema de archivos | Características |
| --------------------- | ----------------- |
| FAT32 | Sistema de archivos más antiguo y sencillo, con gran compatibilidad entre sistemas operativos, pero con limitaciones importantes (tamaño máximo de archivo de 4 GB) |
| NTFS | Sistema de archivos moderno de Windows, con soporte de permisos avanzados, cifrado, compresión y archivos de gran tamaño |
| exFAT | Diseñado para unidades extraíbles, combina la compatibilidad amplia de FAT32 con la eliminación de sus límites de tamaño |

#### Organización interna de FAT32

FAT32 organiza el disco mediante una **tabla de asignación de archivos** (File Allocation Table), que va enlazando los distintos bloques (clústeres) que forman cada archivo, como una lista encadenada.

#### Inconvenientes del sistema de archivos FAT

Además del límite de tamaño de archivo, FAT carece de funciones modernas como permisos de usuario detallados, journaling (registro de cambios para recuperación ante fallos) o soporte nativo de cifrado, por lo que ha quedado relegado principalmente a su uso en soportes extraíbles por su compatibilidad.

### 4.2 Sistemas de archivos de la familia Apple

macOS ha utilizado tradicionalmente **HFS+**, y en sus versiones más recientes **APFS** (Apple File System), optimizado especialmente para unidades SSD, con funciones como los clones de archivos (copias que no ocupan espacio adicional hasta que se modifican) y cifrado nativo.

### 4.3 Sistemas de archivos de la familia GNU/Linux

Las distribuciones Linux han utilizado distintos sistemas de archivos a lo largo del tiempo, siendo la familia **ext** (ext2, ext3, ext4) la más extendida.

#### Qué es un inodo

Un **inodo** es la estructura de datos que almacena toda la información sobre un archivo (permisos, propietario, fechas, tamaño, y la ubicación de sus bloques de datos en el disco), excepto su nombre, que se guarda por separado en el directorio que lo contiene. Cada archivo tiene asociado un único inodo, identificado por un número.

#### Estructura de inodos en ext3

En ext3 (evolución de ext2 con soporte de journaling), cada inodo apunta a los bloques de datos del archivo mediante punteros directos e indirectos, permitiendo representar archivos tanto pequeños como muy grandes de forma eficiente.

#### Cambios para el diseño de ext4

ext4, la evolución más reciente de esta familia, introdujo mejoras como los **extents** (rangos contiguos de bloques, más eficientes que los punteros indirectos tradicionales para archivos grandes), soporte de particiones de mayor tamaño, y mejoras de rendimiento y fiabilidad.

## 5. Transacciones. Sistemas transaccionales

Un **sistema de archivos transaccional** (o con journaling) registra las operaciones que va a realizar en un **diario (journal)** antes de ejecutarlas de verdad. Si el sistema sufre un corte de energía o un fallo a mitad de una operación, al reiniciar puede consultar ese diario para saber exactamente qué se completó y qué no, y así reparar la estructura del sistema de archivos de forma mucho más rápida y fiable que con los métodos de comprobación tradicionales (que debían revisar todo el disco).

## 6. Administración de los sistemas de archivos

La administración de sistemas de archivos incluye tareas como: crear y formatear particiones, comprobar y reparar posibles errores, gestionar el espacio libre disponible, y en algunos sistemas, definir cuotas que limiten cuánto espacio puede usar cada usuario.

## Ejercicios prácticos

!!! task "Tarea"
    **Ejercicio 1**. Explica la diferencia entre la E/S programada y la E/S por interrupciones. ¿Por qué la segunda es más eficiente?

    **Ejercicio 2**. ¿Qué es un buffer y qué problema resuelve al imprimir un documento?

    **Ejercicio 3**. Explica con un ejemplo qué hacen los caracteres comodín `*` y `?` al buscar archivos desde la línea de comandos.

    **Ejercicio 4**. Compara FAT32 y NTFS: indica al menos dos diferencias relevantes y en qué situación seguirías usando FAT32 hoy en día.

    **Ejercicio 5**. Explica qué es un inodo en un sistema de archivos Linux y qué información contiene (y qué información NO contiene).

    **Ejercicio 6**. ¿Qué ventaja aporta un sistema de archivos con journaling frente a uno sin él, ante un corte de luz repentino?

    **Ejercicio 7 (repaso general de la UT1)**. Elabora un mapa conceptual o esquema que relacione los 4 bloques de esta unidad (hardware, software/SO, procesos/memoria, E/S/archivos), señalando cómo se conectan entre sí.

    **Ejercicio 8 (práctica en el aula)**. Crea una partición de prueba (en una máquina virtual) y formatéala con dos sistemas de archivos distintos (por ejemplo, NTFS y ext4), comprobando las diferencias que observas al gestionarla desde el explorador de archivos o la línea de comandos.
