2024-10-20 00:33

Tags: #Topologia #Potencia 

# Playlist Power supplies

![](https://youtube.com/playlist?list=PLUTV_UMnJSciYeKoJLuQ6jxYsMEeWET3f&si=DVA62JLb710QZ_0s)

Antes del capacitor de filtrado en AC/DC se debe proponer una medida para la _inrush current_ siendo un pico de corriente generado por el primer instante donde el capacitor actua como un corto.

Para solucionar esto se usa , por ejemplo, un NTC (Negative Temperature Coefficient), siendo un termistor que:

* Cuando esta frio, se tiene una alta resistencia, que actua como limitador de la corriente 
* Cuando se caliente, se tiene una baja resistencia, lo que ya no limita la corriente.

Generando un limitador de corriente simple, aun asi tiene desventajas como:
 
 * Se debe dejar enfriar totalmente cuando se apaga el circuito.
 * Perdidas de potencia.

 Se puede disponer de un _Power Factor Correction circuit_ antes del capacitor de filtrado, para mejorar la eficiencia energetica del circuito, reducir armonicos en la corriente y reducir la corriente de entrada alineando las fases de voltaje y corriente.

De aca se divide en 2 caminos: 
* Fase de manejo de potencia.
* Control de fase de manejo de potencia.

---

Opto-acoplador para separar el circuito de potencia del de control. 
## Stand - by circuit

### Inductores 

Toroidales generalmente mas usados frente a inductor tradicional, debido a:

* Mayor eficiencia magnetica, debido a que la forma del nucleo minimiza las perdidas de flujo magnetico
* Menor radiacion EMI
* Mas inductancia en un espacio menor.
* Mejor rendimiento termico
* Manejo de altas frecuencias

