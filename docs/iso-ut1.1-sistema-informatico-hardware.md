<p style="font-size: 1.3em;"><strong>CFGS Administración de Sistemas Informáticos en Red (1º curso)</strong></p>

Material elaborado para el módulo **Implementación de Sistemas Operativos**

# UT1.1. El sistema informático: hardware

*Primer bloque de la UT1 "Introducción a los sistemas informáticos" (25 horas totales). Este bloque ocupa 4 de esas 25 horas.*

## Programación de Aula

### Resultados de Aprendizaje

Esta unidad trabaja el **Resultado de Aprendizaje 1 (RA1)** del módulo, según el Real Decreto 1629/2009 y la guía didáctica del centro:

**RA1.** Instala sistemas operativos, analizando sus características e interpretando la documentación técnica.

Este bloque se centra especialmente en el criterio:

- **CE1.1.** Se han identificado los elementos funcionales de un sistema informático.

!!! info "Lectura recomendada"
    Este material amplía y complementa (sin reproducirlo) el contenido del **Capítulo 1** del libro *[Conceptos básicos sobre sistemas operativos](https://somebooks.es/conceptos-basicos-sobre-sistemas-operativos/)* de SomeBooks.es (P. Ruiz), publicado bajo licencia Creative Commons.

### Planificación Temporal (2 sesiones / 4 horas)

| Sesión | Contenido |
| ------ | --------- |
| 1 | El ordenador, el sistema informático y el procesador |
| 2 | Memoria, unidades de E/S, buses y placa base |

## 1. ¿Qué es un ordenador?

Un **ordenador** es una máquina electrónica capaz de recibir datos, procesarlos siguiendo una secuencia de instrucciones (un programa) y producir un resultado. A diferencia de una calculadora, un ordenador es una máquina de **propósito general**: no está diseñado para hacer una única tarea, sino que puede ejecutar cualquier programa que se le indique, lo que le da su enorme versatilidad.

### 1.1 Tipos de ordenadores

Según su tamaño, potencia y propósito, se distinguen distintos tipos de ordenadores:

| Tipo | Características |
| ----- | ----------------- |
| Superordenador | Máxima potencia de cálculo, usado en investigación científica, meteorología, simulaciones complejas |
| Mainframe (gran ordenador) | Da servicio simultáneo a muchísimos usuarios y procesos, típico de grandes corporaciones y bancos |
| Servidor | Ofrece servicios y recursos a otros equipos de una red |
| Ordenador personal (PC) | Equipo de sobremesa o portátil, de uso individual |
| Dispositivo móvil | Smartphones, tablets: ordenadores de propósito general en formato reducido |
| Sistema embebido | Ordenador integrado dentro de otro dispositivo (electrodomésticos, coches, cajeros...) para una función específica |

## 2. El sistema informático

Un **sistema informático** es el conjunto de elementos necesarios para el tratamiento automático de la información, formado por tres componentes que se complementan entre sí:

- **Hardware**: los componentes físicos y tangibles del ordenador.
- **Software**: los programas e instrucciones que hacen funcionar el hardware, sin existencia física propia.
- **Componente humano (humanware)**: las personas que diseñan, usan y mantienen el sistema.

Este bloque se centra en los **componentes físicos** del sistema informático; el bloque UT1.2 abordará el software.

## 3. El procesador

El **procesador** (o CPU, Unidad Central de Procesamiento) es el componente encargado de ejecutar las instrucciones de los programas: interpreta cada instrucción, la ejecuta, y coordina el resto de componentes del sistema.

### 3.1 El juego de instrucciones

Cada procesador entiende un conjunto concreto y limitado de instrucciones básicas (llamado **juego de instrucciones** o *instruction set*), como sumar dos valores, mover datos de un sitio a otro, o comparar dos números. Cualquier programa, por complejo que sea, se traduce en última instancia en una larguísima secuencia de estas instrucciones elementales.

### 3.2 El ciclo de instrucción

Para ejecutar cada instrucción, el procesador repite un ciclo de varias fases:

1. **Búsqueda (fetch)**: se obtiene la siguiente instrucción desde la memoria.
2. **Decodificación (decode)**: se interpreta qué operación representa esa instrucción.
3. **Ejecución (execute)**: se realiza la operación indicada.
4. **Almacenamiento (store)**: si la operación genera un resultado, se guarda en el destino correspondiente (un registro o una posición de memoria).

Este ciclo se repite de forma constante, miles de millones de veces por segundo, mientras el equipo está en funcionamiento.

### 3.3 Interrupciones

Una **interrupción** es una señal que indica al procesador que debe detener momentáneamente lo que está haciendo para atender un evento urgente (por ejemplo, se ha pulsado una tecla, ha llegado un dato por la red, o un dispositivo necesita atención). Tras atender la interrupción, el procesador retoma exactamente donde se había quedado. Este mecanismo es lo que permite que un ordenador parezca "hacer varias cosas a la vez" y responder con rapidez a eventos externos.

### 3.4 Estructura física del procesador

- **Frecuencia de reloj**: el número de ciclos por segundo que puede ejecutar el procesador, medido en gigahercios (GHz). A mayor frecuencia, en igualdad de condiciones, mayor velocidad, aunque no es el único factor que determina el rendimiento.
- **Microprocesadores y núcleos**: un procesador puede integrar varios núcleos de procesamiento independientes dentro del mismo chip, capaces de ejecutar instrucciones en paralelo, multiplicando la capacidad de trabajo del sistema.
- **Rendimiento del procesador**: depende de la combinación de frecuencia, número de núcleos, arquitectura interna y memoria caché; no se puede juzgar solo por un único dato.
- **Componentes de un microprocesador**: unidad de control, unidad aritmético-lógica (ALU) y registros, coordinados entre sí para ejecutar el ciclo de instrucción.
- **Nivel de integración**: el número de transistores que caben en el chip, relacionado con el tamaño del proceso de fabricación (medido en nanómetros); a menor tamaño, más transistores caben en el mismo espacio.
- **Memoria caché**: pequeñas cantidades de memoria ultrarrápida integradas en el propio procesador, organizadas en varios niveles (L1, L2, L3), que guardan los datos usados con más frecuencia para reducir el tiempo de espera al acceder a la memoria principal.
- **Comunicación del procesador con la placa base**: el procesador se conecta a la placa base a través de un zócalo (socket), por el que intercambia datos con la memoria y el resto de componentes.
- **La cubierta del procesador**: la carcasa metálica (IHS, *Integrated Heat Spreader*) que protege el núcleo del chip y ayuda a repartir el calor de forma uniforme hacia el disipador.
- **Refrigeración**: dado el calor que genera al trabajar, el procesador necesita un sistema de disipación (pasiva, activa con ventilador, o líquida) para mantenerse dentro de su rango de temperatura seguro.

## 4. La memoria

La **memoria** almacena, de forma temporal, los datos y las instrucciones que el procesador necesita mientras un programa se está ejecutando. Su contenido se pierde al apagar el equipo (es *volátil*), por lo que no debe confundirse con el almacenamiento permanente (disco duro, SSD).

### 4.1 Memoria caché

Como ya se ha mencionado al hablar del procesador, la **memoria caché** actúa de intermediaria entre el procesador (muy rápido) y la memoria principal (más lenta), guardando copias de los datos de uso más frecuente para acelerar el acceso.

La velocidad de acceso a la memoria es muy inferior a la del procesador, por lo que existe una **jerarquía de memoria**: desde los registros internos del procesador (los más rápidos, pero de capacidad mínima), pasando por la memoria caché (varios niveles, cada vez más grande y más lenta), hasta la memoria principal (RAM), mucho más grande pero también más lenta.

## 5. Unidades de entrada/salida

Los dispositivos de **entrada/salida (E/S)** permiten al sistema comunicarse con el exterior: recibir datos (entrada) y mostrar o transmitir resultados (salida).

### 5.1 Discos duros

Dentro de las unidades de E/S se incluye el **almacenamiento secundario** (discos duros, SSD), que a diferencia de la memoria principal, conserva la información de forma permanente incluso sin alimentación eléctrica, aunque con una velocidad de acceso considerablemente menor que la memoria RAM.

## 6. Los buses

Un **bus** es el conjunto de líneas de comunicación que permite el intercambio de información entre los distintos componentes del sistema (procesador, memoria, dispositivos de E/S). Cada bus transporta un tipo concreto de información: direcciones (para indicar dónde), datos (la información en sí) y señales de control (que coordinan cuándo y cómo se realiza la transferencia).

## Anexo: La placa base

La **placa base** es el circuito impreso al que se conectan todos los componentes del sistema. Sobre ella se sitúan (o a ella se conectan) los siguientes elementos:

| Elemento | Función |
| --------- | ------- |
| BIOS | Firmware que arranca el equipo y comprueba el hardware antes de ceder el control al sistema operativo |
| Memoria CMOS | Pequeña memoria alimentada por una pila, que conserva la configuración de la BIOS (fecha, hora, orden de arranque...) aunque el equipo esté apagado |
| Chipset | Circuitos que gestionan la comunicación entre el procesador y el resto de componentes |
| Socket para el procesador | Zócalo donde se inserta el procesador |
| Slots de memoria | Ranuras donde se instalan los módulos de RAM |
| Conectores para discos duros | Puertos (SATA, M.2...) para conectar el almacenamiento |
| Ranuras de expansión | Slots (PCIe) para instalar tarjetas adicionales |
| Conectores para dispositivos (USB, PS/2...) | Puertos externos para periféricos |

### Otros elementos de la placa base

Además de los elementos anteriores, la placa base incorpora circuitos reguladores de voltaje (VRM), el altavoz interno (*speaker*) para los códigos de pitido de la POST, y conectores para el panel frontal de la caja (botón de encendido, LEDs).

### Aspecto físico y tamaño de la placa base

La placa base tiene un **formato** (o factor de forma) normalizado —ATX, Micro-ATX, Mini-ITX...— que determina su tamaño físico, la disposición de sus componentes y con qué modelos de caja es compatible.

## Ejercicios prácticos

!!! task "Tarea"
    **Ejercicio 1**. Explica con tus propias palabras la diferencia entre hardware, software y componente humano dentro de un sistema informático.

    **Ejercicio 2**. Describe, en orden, las cuatro fases del ciclo de instrucción de un procesador.

    **Ejercicio 3**. ¿Qué es una interrupción y por qué es un mecanismo fundamental para que el ordenador pueda responder a eventos externos con rapidez?

    **Ejercicio 4**. Clasifica estos dispositivos según el tipo de ordenador al que corresponden: un cajero automático, el ordenador de un centro de investigación meteorológica, tu propio smartphone, un servidor de correo de una empresa.

