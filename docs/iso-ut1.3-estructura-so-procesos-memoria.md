<p style="font-size: 1.3em;"><strong>CFGS Administración de Sistemas Informáticos en Red (1º curso)</strong></p>

Material elaborado para el módulo **Implementación de Sistemas Operativos**

# UT1.3. Estructura del sistema operativo: procesos y memoria

*Tercer bloque de la UT1 "Introducción a los sistemas informáticos" (14 horas totales). Este bloque ocupa 3 de esas 14 horas.*

## Programación de Aula

### Resultados de Aprendizaje

Esta unidad continúa trabajando el **Resultado de Aprendizaje 1 (RA1)** del módulo (ver UT1.1 para el texto completo del RA), centrándose especialmente en el criterio:

- **CE1.2.** Se han identificado las características, funciones y arquitectura de un sistema operativo.

!!! info "Lectura recomendada"
    Este material amplía y complementa (sin reproducirlo) el contenido del **Capítulo 4** del libro *[Conceptos básicos sobre sistemas operativos](https://somebooks.es/conceptos-basicos-sobre-sistemas-operativos/)* de SomeBooks.es (P. Ruiz).

### Planificación Temporal (1,5 sesiones / 3 horas)

| Sesión | Contenido |
| ------ | --------- |
| 1 | Elementos y estructura de un SO. Gestión de procesos |
| 2 (media sesión) | Planificación de procesos y gestión de memoria |

## 1. El sistema operativo como software de base

Todo sistema informático necesita un **software de base** que actúe como intermediario entre el hardware y el resto de aplicaciones. Ese software de base es, principalmente, el sistema operativo, que se sitúa justo por encima del hardware y por debajo de las aplicaciones de usuario, ocultando la complejidad técnica del hardware y ofreciendo una interfaz común y estable sobre la que programar.

## 2. Elementos y estructura de un sistema operativo

### 2.1 Elementos de un sistema operativo

Un sistema operativo se compone, principalmente, de:

- **Núcleo (kernel)**: el corazón del sistema operativo, encargado de las funciones más básicas (gestión de procesos, memoria y dispositivos), con acceso directo al hardware.
- **Servicios y demonios**: programas que se ejecutan en segundo plano, ofreciendo funcionalidades al resto del sistema.
- **Intérprete de comandos (shell)**: la interfaz que permite al usuario o a otros programas comunicarse con el sistema operativo.
- **Utilidades del sistema**: herramientas básicas de gestión y mantenimiento que acompañan al sistema operativo.

### 2.2 Estructura de un sistema operativo

Según cómo se organiza internamente el núcleo, se distinguen varios modelos de arquitectura:

| Estructura | Características |
| ----------- | ----------------- |
| Monolítica | Todo el sistema operativo (gestión de procesos, memoria, dispositivos, sistema de archivos...) se ejecuta como un único programa grande, con acceso directo entre sus componentes internos. Ofrece buen rendimiento, pero un fallo en cualquier parte puede afectar a todo el sistema |
| Micronúcleo (microkernel) | Solo las funciones más esenciales (comunicación entre procesos, gestión básica) se ejecutan en el núcleo; el resto de servicios se ejecutan como procesos independientes fuera de él. Más robusto ante fallos, pero con mayor sobrecarga de comunicación |
| Núcleo híbrido | Combina características de ambos modelos: mantiene en el núcleo ciertos servicios por rendimiento, mientras separa otros como en un micronúcleo. Es el enfoque más habitual en los sistemas operativos actuales (Windows, macOS) |

## 3. Funciones del sistema operativo. Recursos

El sistema operativo gestiona los distintos **recursos** del sistema, entendiendo por recurso cualquier elemento (físico o lógico) que un proceso puede necesitar para ejecutarse: el procesador, la memoria, los dispositivos de E/S, o los propios archivos. Las principales funciones del sistema operativo se organizan en torno a la gestión de estos recursos: gestión de procesos, gestión de memoria (vistas en este bloque) y gestión de entrada/salida y de archivos (que se estudiarán en el bloque UT1.4).

## 4. Gestión de procesos

Un **proceso** es un programa en ejecución: no es lo mismo el archivo del programa guardado en disco (algo estático) que la instancia de ese programa corriendo en memoria, con sus propios recursos asignados (memoria, tiempo de CPU...).

### 4.1 ¿Cómo se ejecuta un proceso?

Cuando se lanza un programa, el sistema operativo crea un proceso: reserva memoria para él, carga su código, y lo añade a la cola de procesos listos para ejecutarse, esperando su turno de acceso al procesador.

### 4.2 ¿Cómo se intercalan los procesos?

Un procesador (o cada uno de sus núcleos) solo puede ejecutar realmente un proceso a la vez en cada instante. Sin embargo, el sistema operativo da la sensación de que varios procesos se ejecutan simultáneamente gracias a la **multitarea**: va asignando pequeños intervalos de tiempo de CPU a cada proceso, alternando entre ellos tan rápido que, para el usuario, parece que ocurren de forma simultánea.

### 4.3 ¿Cuándo acaba un proceso?

Un proceso finaliza cuando termina su ejecución de forma normal, cuando el usuario o el sistema lo cancela, o cuando se produce un error grave que impide continuar (lo que suele mostrarse como un cierre inesperado de la aplicación).

### 4.4 Planificación de procesos

Cuando hay varios procesos esperando usar el procesador, el sistema operativo necesita un criterio para decidir a cuál atender primero: esto es la **planificación de procesos**. Existen distintos algoritmos de planificación, cada uno con sus ventajas e inconvenientes:

| Algoritmo | Sigla | Funcionamiento |
| ---------- | ----- | ---------------- |
| Primero en llegar, primero en ser servido | FCFS (*First Come First Served*) | Los procesos se atienden estrictamente en el orden en que llegaron, como una cola de un solo carril |
| Primero el más corto | SJF (*Shortest Job First*) | Se da prioridad al proceso que necesite menos tiempo de ejecución, minimizando el tiempo medio de espera |
| Por turnos | RR (*Round Robin*) | Cada proceso recibe un pequeño intervalo fijo de tiempo (*quantum*), y si no termina, vuelve al final de la cola, cediendo el turno al siguiente |
| Por prioridad | — | Cada proceso tiene asignado un nivel de prioridad, y se atiende primero a los de mayor prioridad |
| Reparto equitativo | FSS (*Fair-share Scheduling*) | Reparte el tiempo de CPU de forma equitativa entre distintos usuarios o grupos, no solo entre procesos individuales |
| Colas múltiples | MQS (*Multilevel Queue Scheduling*) | Los procesos se clasifican en distintas colas según su tipo (interactivos, en segundo plano...), aplicando una política de planificación distinta a cada cola |

### 4.5 Comunicación entre procesos

Los procesos, aunque se ejecutan de forma independiente, a menudo necesitan intercambiar información entre sí (por ejemplo, cuando un programa envía datos a otro). El sistema operativo ofrece mecanismos de **comunicación entre procesos (IPC)** para permitir este intercambio de forma controlada y segura.

### 4.6 Procesos y servicios

Un **servicio** (o demonio, en terminología Unix/Linux) es un tipo especial de proceso que se ejecuta en segundo plano, generalmente iniciado automáticamente por el sistema, sin interacción directa del usuario, ofreciendo una función continua (por ejemplo, un servicio de impresión o de red).

### 4.7 Administración de procesos

El sistema operativo ofrece herramientas (gráficas o de línea de comandos) que permiten al usuario o al administrador consultar qué procesos están en ejecución, su consumo de recursos, y actuar sobre ellos (finalizarlos, cambiar su prioridad...) cuando sea necesario.

## 5. Gestión de memoria principal

La **gestión de memoria** es la función del sistema operativo encargada de repartir la memoria RAM disponible entre los distintos procesos que se están ejecutando, garantizando que cada uno tenga el espacio que necesita sin interferir con los demás.

### 5.1 Gestión de memoria para un solo proceso

En los sistemas más simples (o en sus primeras etapas históricas), toda la memoria disponible se dedicaba a un único proceso en ejecución cada vez, sin necesidad de repartirla entre varios.

### 5.2 Gestión de memoria con particiones fijas

Un enfoque más avanzado divide la memoria en **particiones de tamaño fijo**, predefinidas de antemano, asignando cada proceso a la partición que mejor se ajusta a su tamaño. Es sencillo de gestionar, pero desperdicia memoria cuando un proceso es más pequeño que la partición que ocupa.

### 5.3 Gestión de memoria con particiones variables

Para reducir ese desperdicio, las **particiones variables** se ajustan al tamaño exacto de cada proceso en el momento de crearlas. Sin embargo, con el tiempo, la memoria libre puede quedar fragmentada en pequeños huecos no contiguos, difíciles de aprovechar.

### 5.4 Reubicación

La **reubicación** consiste en poder mover un proceso de una zona de memoria a otra mientras se ejecuta (o entre ejecuciones), reorganizando el espacio disponible para reducir la fragmentación y aprovechar mejor la memoria.

### 5.5 Paginación

La **paginación** divide tanto la memoria física como el espacio de direcciones de cada proceso en bloques de tamaño fijo, llamados **páginas**. De esta forma, un proceso no necesita ocupar un bloque contiguo de memoria: sus páginas pueden estar repartidas en cualquier posición libre, eliminando el problema de la fragmentación externa.

#### Otras consideraciones a tener en cuenta

La paginación introduce cierta sobrecarga adicional: el sistema necesita mantener una **tabla de páginas** que traduzca las direcciones lógicas de cada proceso a direcciones físicas reales de memoria, lo que consume tiempo y espacio adicional.

### 5.6 Segmentación

La **segmentación** divide la memoria de un proceso según su estructura lógica (por ejemplo, un segmento para el código, otro para los datos, otro para la pila), en lugar de bloques de tamaño fijo. Esto se ajusta mejor a cómo está organizado realmente un programa, aunque puede volver a introducir el problema de la fragmentación.

### 5.7 Paginación y segmentación combinadas

Muchos sistemas modernos combinan ambas técnicas: organizan la memoria de un proceso en segmentos lógicos, y cada segmento, a su vez, se divide en páginas, aprovechando las ventajas de los dos enfoques.

### 5.8 Memoria virtual

La **memoria virtual** permite que el sistema operativo utilice espacio del disco como si fuera una extensión de la memoria RAM, "intercambiando" (swap) páginas de memoria poco usadas al disco para liberar espacio en la RAM real. Esto permite ejecutar más procesos, o procesos más grandes, de los que cabrían físicamente en la memoria RAM instalada, a costa de una pérdida de rendimiento si se recurre a ella con demasiada frecuencia.

### 5.9 Administración de la memoria

El sistema operativo mantiene un control constante de qué zonas de memoria están libres, cuáles están ocupadas y por qué proceso, liberando automáticamente la memoria cuando un proceso termina, para que pueda ser reutilizada por otros.

## Ejercicios prácticos

!!! task "Tarea"
    **Ejercicio 1**. Explica la diferencia entre una estructura de sistema operativo monolítica y una de micronúcleo. ¿Cuál dirías que prioriza más la robustez del sistema?

    **Ejercicio 2**. Explica con tus palabras la diferencia entre un programa y un proceso.

    **Ejercicio 3**. Explica cómo consigue un sistema operativo que parezca que varios programas se ejecutan "a la vez" en un ordenador con un único núcleo de procesador.

    **Ejercicio 4**. Compara los algoritmos de planificación FCFS y Round Robin: ¿cuál sería más adecuado para un sistema interactivo (donde el usuario espera respuesta inmediata) y por qué?

    **Ejercicio 5**. Explica la diferencia entre gestión de memoria con particiones fijas y con particiones variables, y qué problema resuelve la paginación respecto a ambas.

    **Ejercicio 6**. ¿Qué es la memoria virtual y qué ventaja aporta? ¿Qué inconveniente tiene usarla en exceso?

    **Ejercicio 7 (práctica en el aula)**. Abre el administrador de tareas (o el comando `top`/`htop` en Linux) de un equipo y observa los procesos en ejecución. Identifica al menos 3 procesos de sistema y 2 procesos de aplicaciones de usuario, anotando su consumo de CPU y memoria.
