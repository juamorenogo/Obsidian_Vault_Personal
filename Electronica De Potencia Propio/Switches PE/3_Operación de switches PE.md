2024-10-09 16:35

Tags: #Potencia #Transistores #PESwitch #Thyristor

 A priori, se divide en 2 grandes categorías de operación (Recomendaciones de diseño en _Motorola Series in solid state electronics_). En general, la regulacion lineal consta de un flujo continuo de corriente para mantener un voltaje constante. Por otro lado, la regulacion conmutada varia el ciclo de trabajo y la rapidez de conmutacion para variar la salida.
### Linear Mode Regulator
Posee las siguientes **ventajas**:
* Modelo simple.
* Operación silenciosa ( Ruido generalmente despreciable a la salida).
* Respuesta dinámica rápida a cambios de carga. 
* Para salidas _< 10 W_ mucho mas barato.

Posee las siguientes _desventajas_:
* Solo puede ser usado como _Buck_ o _Step Down_.
* Solo es capaz de regular una entrada a la vez.
* Poca eficiencia en potencia (_30% - 60% de eficiencia_).
### Switching Mode Regulator
Posee las siguientes **ventajas**:
* Alta eficiencia en potencia (_68% - 90% de eficiencia_) (Los transistores de potencia trabajan en sus puntos óptimos, _Saturación_ y _Corte_).
* Mayor independencia entre _Vin_ y _Vo_, lo que significa que sirve como _Buck_ o _Boost_.
* Mas barato en altas potencias.

Posee las siguientes _desventajas_:
* Modelo mucho mas complicado.
* Operación ruidosa (Aplica considerable ruido a la señal de salida) que involucra _EMC_ .
* Respuesta dinámica lenta a cambios de carga (transient response time).
### Diferenciación y entendimiento.

#### Diferencias clave:

1. **Regulador Lineal**:
    
    - En un regulador lineal, el dispositivo de control (generalmente un transistor en modo lineal) **actúa como una resistencia variable**, disipando el exceso de energía para reducir el voltaje de entrada a un nivel de salida más bajo.
    - La corriente que fluye a través de la carga es la misma que la que fluye a través del transistor, lo que significa que para mantener un voltaje constante, también debe mantenerse un flujo **constante de corriente**.
    - La eficiencia es baja, ya que la diferencia entre el voltaje de entrada y el de salida se disipa como calor.
2. **Regulador Conmutado**:
    
    - En un regulador conmutado (conmutador), el **principio básico** es que el interruptor (por ejemplo, un MOSFET) se enciende y apaga rápidamente. En lugar de disipar el exceso de energía como calor, se **almacena y libera** energía en componentes como un **inductor** o un **capacitor**.
    - Durante el ciclo de conmutación:
        - **Cuando el interruptor está encendido**, la corriente fluye desde la fuente de entrada a través de un inductor (en un convertidor buck, por ejemplo) hacia la carga. El inductor almacena energía en su campo magnético.
        - **Cuando el interruptor está apagado**, la energía almacenada en el inductor continúa fluyendo hacia la carga, manteniendo un flujo de corriente casi constante.
    - Este proceso de almacenamiento y liberación de energía permite que un regulador conmutado entregue corriente continua a la carga, aunque la corriente de entrada varíe debido a la conmutación.

Si se supone a cada regulador como una _black-box con 2 terminales_, ambos casos actúan igual, no obstante, un _regulador lineal_ maneja un **flujo continuo de corriente** de la entrada a la carga para mantener una voltaje constante en la salida. 

Por otro lado, en un _regulador conmutado_ el flujo de corriente _no es constante en el interruptor_ pero si en su _salida_ (se crean pulsos de corriente que el inductor suaviza junto al _DT_). Si la carga exige mas corriente, se modifica el porcentaje de _on-time_.  
#### Tipos básicos de regulador conmutado Pulsewidth modulated (PWM)
* Foward - mode regulators.
* Flyback - mode regulators.

![](Electronica De Potencia Propio/Regulacion)


