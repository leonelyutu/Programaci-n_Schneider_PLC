# Programaci-n_Schneider_PLC
Material para el controlador lógico Schneider.
# Descripción del TM 221C Logic Controller

## Descripción General

El TM221C Logic Controller tiene una amplia Variedad de potentes funciones y puede servir para una amplia gama de aplicaciones.

La configuración, programación y puesta en funcionamiento del software se lleva a cabo con el software EcoStruxure Macine Expert.

## Lenguajes de programación
M221 Logic Controller se configura y programa con el software EcoStruxure Machine Expert-Basic, compatible con los siguientes IEC 61131-3 lenguajes de programación.

* IL: Lista de instrucciones
* LD: Diagrama de contactos
* Grafcet (lista)
* Grafcet (SFC)

## Fuente de alimentación 
La fuente de alimentacion del TM221C Logic Controller es de 24 V CC o de 100-240 V CA.

##Reloj de Tiempo real
El M221 Logic Controller incluye un sistema de reloj en tiempo real (TRC).

## Run/Stop
El M221 Logic Controller se puede utilizar extremadamente mediante los metodos siguientes:
* Un conmutador Ejecutar/Detener de una entrada digital dedidcada, definida en la configuración del software.
* EcoStruxure Machine Expert - Basic Software
* Un TMH2GDB Visualización gráfica remota.

## Memoria 
En esta tabla se describen los distintos tipos de memoria:

| **Tipo de Memoria** | **Tamaño** | **Uso a** |
| :------- | :------: | -----: |
|  RAM   | 512 Kbytes de memoria RAM: 256 Kbytes para variaciones internas y 256 Kbytes para aplicación y datos       | Ejecutar la aplicación y contener datos   |
| No Volátil   | 1,5 Mbytes, de los cuales 256 Kbytes se utilizan para realizar una copia de seguridad de la aplicación y de los datos en caso de corte de alimentación     | Guardad la aplicación |

## Objetos
**Descripcion General**
EcoStruxure Machine Expert - Basic, el término *Objeto* se utiliza para representar un área de le memoria del controlador lógico reservada para que la utilice en una aplicación. Los objetos pueden ser:

* Variables de software simpes, como bits de memoria y palabras
* Direcciones de las entradas y salidas digitales o analógicas
* Variables internas del controlador, como palabras y bits del sistema.
* Funciones predefinidas del sistema o de los bloques de funciones, como temporizadores y contadores.

Los objetos solo pueden ser direccionados pro un programa una vez que se ha asignado memoria. 
Los objetos se direccionan mediante el prefijo %. Por ejemplo %MW12 es la dirección de una palabra de memoria. %Q0.3 es la dirección de una salida digital incrustada y %TM0 es la dirección de un bloque de funciones Timer.

| Tipo de Objeto | Objetvo | Función del Objeto |Descripción |
| :------- | :------: | -----: |-----: |
|  Objetos de Memoria   | %M       | Bits de memoria   |Almacena el bit de memoria |
|           | %MW     | Palabras de memoria |Almacena la palabra de memoria de 16 bits |
|           | %MD     | Palabras dobles de memoria |Almacena la palabra de memoria de 32 bits |
|           | %MF     | Memoria de coma flotante |Almacena la coma flotante de memoria en un argumento matemático que tiene un decimal en su expresión |
|           | %KW     | Palabras flotantes constantess |Almacena la palabra constante de 16 bits |
|           | %KD     | Palabras dobles constantes |Almacena la palabra constante de 32 bits |
|           | %KF     | comas flotantes constantes |Almacena la coma flotante constante en un argumento matemático que contiene un decimal en su expresión. |

## Estructura de las Tareas

El Modicon TM221M Logic Controller admite los siguientes tipos de tareas:

* Tarea Maestra
* Tarea Periódica
* Tarea de eventos

La tarea maestra se puede configurar en las modalidades de exploración siguientes:

* Modalidad de ejecición libre
* Modalidad de ejecución peródica

## Modalidades de Explocación

La modalidad de ejecución libre es una modalidad de exploración cíclica contínua. En esta modalidad, una nueva exploración se inicia inmediatamente después de que la exploración previa se haya completado.

## Transiciones de estado del Controlador
### Arranque del Controlador
**Efecto** : Da una orden de reinicio de logic controller. 

**Métodos**
* Apagado y encendido
* Reinicio por script
* EL srcipt en una tarjeta SD puede emitir REBOOT como comando final.

## Configuración de los generadores de pulsos

### Introducción
Los bloques de funciones de gneradores de pulsos, *Pulse (PLS), Pulse with Modulation (PWM), Pulse Train Output (PTO) y Frecuency Generator (FREQUEN) se utilizan para generar señales de onda cuadrada o modulada en los canales de salida especializada %Q0.0 o %Q0.1.

Las salidas PWM tienen una señal de onda modulada con un ancho variable y un ciclo de servicio, mientras que las salidas PTO generan una onda cuadrada para controlar un motor paso a paso de un solo eje lineal o servounidad en modalidad de bucle abierto. El PLS tambien crea una onda cuadrada para un número programado de pulsos.



