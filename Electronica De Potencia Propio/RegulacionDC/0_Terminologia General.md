2024-10-15 20:05

Tags:  
## _Topologia Estandar_

Convertidor convencional en una sola dirección, transfiriendo desde la entrada hasta la salida regulando el voltaje y corriente. No necesariamente almacena energía.  
## _Topologia "Pump"_ 

Convertidor que almacena energía en componentes pasivos. Tiene la capacidad de transferencia bidireccional y se bombea según el ciclo.

## _Generaciones de Conversores DC/DC_
* 1st ) Unico cuadrante 
* 2st ) Multi - cuadrante
* 3st )
---

Cualquier topologia _Pump_ 
### Shunt Capacitor

- **Función**: Se conecta en paralelo (shunt) para:
  - Mejorar el **factor de potencia** compensando cargas inductivas.
  - **Reducir pérdidas** de energía.
  - Mantener el **voltaje estable**.
  - **Filtrar armónicos** en algunos casos.

- **Aplicaciones**:
  - Líneas de transmisión y sistemas industriales.
  - Estabilización de voltaje en sistemas de distribución.
### Series Inductor

- **Función**: Se conecta en serie para:
  - **Almacenar energía** en forma de campo magnético.
  - Actuar como **filtro de corriente**, bloqueando señales de alta frecuencia.
  - **Limitar corrientes** de arranque.
  - Compensar **reactancia capacitiva** en líneas de transmisión.

- **Aplicaciones**:
  - Filtrado de señales en fuentes de alimentación.
  - Suavizado de corriente en fuentes conmutadas.
  - Corrección del factor de potencia capacitivo.

Todo esto usado para los filtros LC.

### Elementos Current Sense

Desarrollar voltaje proporcional a la corriente de salida de la carga. En caso de que se genere una _sobrecorriente_ por un voltaje muy alto, el sistema fuerza la reduccion del voltaje.

* _Voltage mode regulatos_ : Se activa al detectar una sobre corriente. (Current foldback limiting)
* _Current mode regulators_ : Se mide la corriente del primerio del transformador y se usa para la limitacion de la corriente. 
---

	Current Foldback limiting : Tecnica de proteccion usado en fuentes que limita la corriente de salida.

---
### Elementos Voltage Feedback

Usualmente un divisor de tension que reduce el _voltaje de salida_ a un voltaje de referencia.
Se compara la salida del divisor de tension despues de su ajuste con el voltaje de referencia, si _Vout > Vref o Vout < Vref_ se genera una señal de error para ajustar la salida siendo que _Error  = Diferencia entre la salida y la referencia_. 

### Etapa de Control general

Se busca cumplir los siguientes criterios:

* Voltaje -> PWM conversion
* Voltaje de referencia estable
* Oscilador
* Deteccion de sobre-corrientes
* Control de la conversion de la fuente en general

Tambien se busca incluir un _circuito de inico suave_ , circuito _dead time limiting_ y circuito _apagado remoto_. 
 
---
### Dead Time Timing

**Dead time** es un breve periodo en el que **ambos transistores en un circuito conmutado están apagados** para evitar que conduzcan simultáneamente, lo que podría causar un **cortocircuito**.

#### Función principal:
- **Evitar cortocircuitos** (shoot-through) al garantizar que un transistor esté completamente apagado antes de encender el otro.
- **Protección** de los componentes contra sobrecorrientes.
- **Mejora de eficiencia** al prevenir cortocircuitos que generarían pérdidas de energía.

#### Ajuste del Dead Time:
- **Demasiado corto**: Puede provocar cortocircuitos si ambos transistores conducen al mismo tiempo.
- **Demasiado largo**: Introduce ineficiencia y pérdida de potencia al aumentar el tiempo en que ambos transistores están apagados.

#### Aplicaciones:
- Convertidores DC-DC e inversores que utilizan transistores para controlar el flujo de corriente.

---
### Single-Ended Supply

Un **single-ended supply** es un tipo de fuente de alimentación que proporciona solo un voltaje positivo o negativo respecto a tierra (**ground**), en lugar de ambos (como en una fuente de alimentación simétrica).
#### Características:
- **Un solo voltaje**: Solo se suministra un voltaje (positivo o negativo) respecto a tierra.
- **Conexión a tierra**: Uno de los terminales está conectado directamente a tierra, y el otro lleva el voltaje de salida.
- **Común en circuitos sencillos**: Usado en amplificadores y circuitos de bajo consumo que no requieren fuentes simétricas.

#### Ejemplos:
- **Fuentes de alimentación de 5V, 12V o 24V**.
- **Uso en amplificadores operacionales** que funcionan con voltaje positivo respecto a tierra.

---
### Double-Ended Switch

Un **double-ended switch** es un dispositivo de conmutación que utiliza dos transistores o interruptores electrónicos, generalmente en configuraciones de puente completo o media puente, donde ambos extremos de la carga están conectados a interruptores. Esto permite el control del flujo de corriente en ambas direcciones a través de la carga.

#### Características:
- **Control bidireccional**: Permite que la corriente fluya en ambas direcciones a través de la carga.
- **Uso de dos interruptores**: Conformado por dos transistores o MOSFETs en la configuración de conmutación.
- **Alta eficiencia**: Optimiza el uso de energía en circuitos de potencia.

#### Aplicaciones:
- **Convertidores de potencia** como inversores y convertidores DC-DC.
- **Motor drivers**: Control de motores en aplicaciones que requieren inversión de la dirección del flujo de corriente.

#### Ventajas:
- **Mejor control** sobre la dirección de la corriente.
- **Mayor flexibilidad** en aplicaciones de potencia.

#### Desventajas:
- **Mayor complejidad**: Requiere más componentes y un diseño más sofisticado en comparación con un solo interruptor.

---
### Flip-Flop

Un **flip-flop** es un tipo de circuito secuencial que tiene dos estados estables y puede almacenar un bit de información (0 o 1). Se utiliza en sistemas digitales para el **almacenamiento de datos** y el **control de secuencias**.

#### Características:
- **Biestable**: Tiene dos estados posibles (alto o bajo, 1 o 0).
- **Almacena un bit**: Puede recordar su estado hasta que se actualice con una señal externa.
- **Controlado por señales de reloj**: Normalmente sincronizado con un pulso de reloj que controla cuándo cambia de estado.

#### Tipos de Flip-Flop:
- **SR Flip-Flop**: Controlado por entradas "Set" (S) y "Reset" (R).
- **D Flip-Flop**: Almacena el valor presente en la entrada de datos (D) en el flanco del reloj.
- **JK Flip-Flop**: Similar al SR, pero sin el estado inválido.
- **T Flip-Flop**: Cambia de estado (toggle) con cada pulso de reloj.

#### Aplicaciones:
- **Memoria digital**: Almacenamiento temporal en registros y contadores.
- **Sistemas de control**: Sincronización y control de secuencias en circuitos digitales.
- **Divisores de frecuencia**: Usado para reducir la frecuencia de una señal.

--- 
### Bipolar Flux Mode of Operation

El **bipolar flux mode of operation** es un modo de funcionamiento común en transformadores y convertidores de potencia que involucran el flujo magnético en dos direcciones opuestas durante el ciclo de operación. En este modo, el núcleo magnético del transformador o inductor alterna entre dos niveles de saturación, generando flujo en ambas polaridades (positiva y negativa).

#### Características:
- **Flujo magnético bidireccional**: El flujo magnético cambia de dirección dentro del núcleo, alternando entre polaridades positiva y negativa.
- **Uso eficiente del núcleo**: Este modo aprovecha al máximo el núcleo magnético al permitir que funcione en ambas direcciones.
- **Aplicación en conmutación**: Se utiliza en convertidores de potencia conmutada y en transformadores que operan en circuitos AC.

#### Ventajas:
- **Mayor utilización del núcleo magnético**: Se utiliza todo el ciclo de histéresis del núcleo, aumentando la eficiencia.
- **Reducción de tamaño**: Se puede usar un núcleo más pequeño al aprovechar ambos extremos de la curva de saturación.
  
#### Aplicaciones:
- **Convertidores DC-DC**: En configuraciones como push-pull o puente completo.
- **Transformadores**: Para transformar energía en sistemas de corriente alterna.

#### Desventajas:
- **Requiere conmutación precisa** para evitar la saturación excesiva del núcleo.
- **Mayor complejidad** en el control comparado con modos unipolares.


---

# Interference Capacitor en Fuentes de Alimentación

Un **interference capacitor**, también conocido como **capacitor de interferencia** o **capacitor de supresión de interferencias**, es un componente utilizado en fuentes de alimentación y otros circuitos electrónicos para **reducir el ruido eléctrico** o interferencias electromagnéticas (EMI) generadas por la rápida conmutación de transistores, diodos y otros elementos activos en el circuito.

## Función principal

La función principal del **interference capacitor** es **filtrar o suprimir** las señales de alta frecuencia no deseadas, previniendo que interfieran con el funcionamiento del dispositivo o de otros dispositivos cercanos. Estas interferencias suelen ser generadas en **fuentes de alimentación conmutadas (SMPS)**.

## Ubicaciones clave

Los **capacitores de interferencia** se suelen colocar en las siguientes ubicaciones dentro de una fuente de alimentación:

1. **Entre la línea de entrada y tierra**: Para reducir el ruido que podría transmitirse a la red eléctrica o hacia otros dispositivos.
2. **Entre la línea de entrada y el neutro**: Para bloquear las señales de alta frecuencia que intentan pasar por el circuito de alimentación.
3. **En paralelo con otros componentes**: Para absorber señales de ruido no deseadas generadas por componentes como transistores de conmutación.

## Tipos de Interference Capacitors

Existen dos tipos principales de capacitores de interferencia:

- **Capacitores Clase X**: Usados entre las líneas de fase y neutro. Están diseñados para soportar sobretensiones transitorias.
- **Capacitores Clase Y**: Usados entre fase y tierra o entre neutro y tierra. Se encargan de evitar que el ruido se propague hacia la tierra.

## Importancia en Fuentes de Alimentación

En una **fuente de alimentación conmutada (SMPS)**, los **interference capacitors** ayudan a:

- **Proteger contra interferencias electromagnéticas (EMI)** generadas por los transistores de conmutación de alta frecuencia.
- **Mejorar el rendimiento** de la fuente de alimentación.
- **Cumplir con los estándares de compatibilidad electromagnética (EMC)**, que limitan la cantidad de interferencia electromagnética que los dispositivos pueden generar.

## Resumen

Un **interference capacitor** en fuentes de alimentación es clave para **filtrar las interferencias eléctricas de alta frecuencia**, garantizando un funcionamiento limpio y seguro del sistema y evitando que el ruido afecte a otros dispositivos o la red eléctrica.

---
# Inrush Current (Corriente de Irrupción)

La **inrush current** (corriente de irrupción o corriente de arranque) es un pico de corriente que ocurre cuando un dispositivo eléctrico se enciende por primera vez. Este pico es generalmente mucho mayor que la corriente operativa normal del dispositivo y puede durar desde unos pocos milisegundos hasta unos segundos, dependiendo del tipo de equipo.

## Características principales:
- **Duración breve**: Aunque el pico de corriente es elevado, su duración es corta, normalmente unos milisegundos o segundos.
- **Equipos afectados**: Dispositivos con grandes condensadores, motores eléctricos, transformadores o cualquier equipo con bobinas y elementos inductivos son propensos a generar alta inrush current.
- **Causa principal**: Se produce cuando ciertos componentes, como los condensadores, se cargan inicialmente o cuando se establecen los campos magnéticos en inductores o transformadores.

## Ejemplos de equipos afectados:
1. **Transformadores**: Al encenderse, pueden experimentar altos picos de corriente debido a la magnetización del núcleo.
2. **Motores eléctricos**: Consumen una gran corriente cuando arrancan, ya que inicialmente están en reposo y necesitan superar la inercia.
3. **Fuentes de alimentación**: Los condensadores en las fuentes de alimentación pueden generar un alto pico de corriente cuando se cargan al encenderse.

## Problemas asociados:
- **Sobrecarga de fusibles o disyuntores**: El inrush current puede ser tan alto que provoque la activación de los dispositivos de protección, apagando el equipo o el circuito.
- **Daño a componentes electrónicos**: Si no se gestiona adecuadamente, puede dañar componentes sensibles.

## Métodos para reducir la inrush current:
- **Resistencias NTC (coeficiente de temperatura negativo)**: Limitan la corriente al inicio y disminuyen su resistencia a medida que se calientan.
- **Relés de arranque suave**: Encienden gradualmente un equipo para reducir el impacto del pico inicial.
- **Controladores de motores**: Usan arranque suave o controladores de frecuencia variable para reducir la corriente de arranque en motores eléctricos.

---
# Inductores o "Choke" en Convertidores DC/DC

## ¿Qué es un inductor o "choke"?

Un **inductor** o **choke** es un componente que almacena energía en un campo magnético cuando la corriente fluye a través de él. En los **convertidores DC/DC**, los inductores se utilizan para suavizar las variaciones de corriente y para transferir energía eficientemente desde la fuente de entrada hasta la carga o el capacitor de salida.

## Funcionamiento en Convertidores DC/DC

En los convertidores de tipo **buck** (reductor) o **boost** (elevador), el inductor desempeña un papel crucial en la conversión de voltaje. Se puede describir en dos fases:

1. **Fase de almacenamiento**:
   - Durante una parte del ciclo de conmutación, el inductor almacena energía cuando el interruptor está encendido. La corriente a través del inductor aumenta linealmente mientras el campo magnético se genera.

2. **Fase de entrega**:
   - Cuando el interruptor se apaga, el campo magnético en el inductor colapsa y la energía almacenada se libera, entregando corriente a la carga o al capacitor de salida, manteniendo un flujo continuo de corriente hacia la carga.

## Tipos de Convertidores DC/DC que usan Inductores

1. **Convertidor Buck (reductor)**:
   - Reduce el voltaje de entrada a un voltaje más bajo. El inductor suaviza el flujo de corriente para entregar energía continua a la salida.

2. **Convertidor Boost (elevador)**:
   - Eleva el voltaje de entrada a un nivel superior. El inductor almacena energía cuando el interruptor está encendido y la entrega a la salida cuando se apaga.

3. **Convertidor Buck-Boost**:
   - Puede aumentar o reducir el voltaje de entrada, dependiendo de la configuración. El inductor almacena y entrega energía según sea necesario.

4. **Convertidor Flyback**:
   - Utiliza un transformador para transferir energía entre dos circuitos separados. A diferencia de los inductores, el transformador en un **flyback** permite el aislamiento galvánico entre la entrada y la salida.

## Importancia del Inductor en Convertidores DC/DC

- **Almacenamiento de energía**: El inductor almacena energía en un campo magnético, permitiendo una entrega eficiente de energía.
- **Regulación de corriente**: Ayuda a regular la corriente, manteniendo un flujo estable y continuo hacia la carga.
- **Reducción de rizado (ripple)**: Los inductores reducen el ripple de corriente, mejorando la estabilidad del voltaje de salida.

## Resumen

Los **inductores (choke)** son componentes clave en los **convertidores DC/DC** como buck, boost y buck-boost. Permiten almacenar y transferir energía de manera eficiente, regulando el flujo de corriente y reduciendo el ripple. Los inductores son esenciales para la operación eficiente y estable de los convertidores de voltaje.

---

# Optoacoplador (Opto-coupler)

## ¿Qué es un optoacoplador?

Un **optoacoplador** o **opto-isolador** es un componente electrónico que permite la transmisión de señales eléctricas entre dos partes de un circuito mientras mantiene un **aislamiento eléctrico** entre ellas. Este aislamiento es posible mediante el uso de luz para transferir la señal, en lugar de un contacto eléctrico directo.

El optoacoplador generalmente está compuesto por un **emisor de luz** (típicamente un **LED**) y un **fotodetector** (como un **fototransistor**, fotodiodo o fototriac) dentro de un paquete sellado.

## Funcionamiento básico

1. **Emisión de luz**:
   - Cuando una señal eléctrica se aplica al lado de entrada del optoacoplador, el **LED** emite luz en función de la magnitud de la corriente que pasa a través de él.

2. **Detección de luz**:
   - El **fotodetector** (como un fototransistor) en el lado de salida detecta esta luz y convierte la señal óptica de nuevo en una señal eléctrica. Este proceso permite que la señal eléctrica se transmita entre las dos partes del circuito sin una conexión directa.

3. **Aislamiento galvánico**:
   - El **aislamiento galvánico** proporcionado por el optoacoplador es clave para evitar que los voltajes elevados en un lado del circuito afecten al otro lado, protegiendo así componentes sensibles o circuitos de bajo voltaje.

## Aplicaciones del optoacoplador

Los optoacopladores se utilizan comúnmente en aplicaciones donde es necesario:
- **Aislar eléctricamente** dos partes de un circuito.
- **Proteger circuitos de bajo voltaje** de picos de alto voltaje o interferencias.
- **Transmitir señales** entre diferentes sistemas con potenciales de tierra distintos.
- **Interfaz entre circuitos de potencia y microcontroladores**, evitando que los circuitos de control sufran daños por picos de voltaje.

### Ejemplos de aplicaciones:
- **Fuentes de alimentación conmutadas**: Los optoacopladores se usan para retroalimentar la información de regulación de voltaje desde el lado de salida aislado hacia el controlador en el lado de entrada.
- **Control de motores**: Permiten controlar motores de alto voltaje desde circuitos de control de bajo voltaje.
- **Sistemas de protección**: Se utilizan para aislar circuitos de protección, como fusibles electrónicos o sistemas de monitoreo, del circuito de potencia principal.

## Tipos de optoacopladores

1. **Optoacoplador con fototransistor**:
   - Es el tipo más común. El fototransistor en la salida actúa como un interruptor controlado por la luz emitida por el LED. Ideal para señales de conmutación o de baja potencia.

2. **Optoacoplador con fotodiodo**:
   - Proporciona una respuesta más rápida que el fototransistor, lo que lo hace adecuado para aplicaciones de alta velocidad.

3. **Optoacoplador con fototriac**:
   - Utilizado para controlar cargas de corriente alterna (AC). El fototriac en la salida puede conmutar señales AC, comúnmente usado para control de cargas como motores o iluminación.

4. **Optoacoplador con lógica digital**:
   - Diseñado para aplicaciones digitales, permite transmitir señales de alta velocidad y bajo ruido entre circuitos con diferentes niveles de voltaje.

## Ventajas del uso de optoacopladores

- **Aislamiento eléctrico**: Protege los circuitos de control sensibles de corrientes peligrosas o picos de voltaje.
- **Reducción de interferencias**: Al no haber conexión directa, se reducen las interferencias electromagnéticas y los bucles de tierra.
- **Compatibilidad**: Pueden funcionar en una variedad de sistemas de potencia y lógica digital, y son compatibles con microcontroladores y otros dispositivos de bajo voltaje.

## Limitaciones de los optoacopladores

- **Velocidad limitada**: Los optoacopladores con fototransistores tienen una velocidad de respuesta limitada, lo que los hace inadecuados para aplicaciones de alta frecuencia o señales rápidas.
- **Degradación con el tiempo**: Los LEDs dentro de los optoacopladores pueden degradarse con el tiempo, afectando la eficiencia y la fiabilidad a largo plazo.
- **Corriente limitada**: No pueden manejar altas corrientes directamente, por lo que generalmente se utilizan para conmutar señales o controlar dispositivos de mayor potencia con la ayuda de otros componentes.

## Resumen

Un **optoacoplador** es un componente que permite la transferencia de señales eléctricas entre dos partes de un circuito mientras mantiene el aislamiento eléctrico entre ellas. Utiliza luz para transmitir señales y es comúnmente utilizado en aplicaciones de protección y control. Hay varios tipos de optoacopladores, cada uno diseñado para diferentes aplicaciones, desde conmutación de señales hasta control de cargas AC.

--- 

