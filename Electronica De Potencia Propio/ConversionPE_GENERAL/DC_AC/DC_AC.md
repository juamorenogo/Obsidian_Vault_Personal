2024-10-04 18:14

Tags:  #Potencia #Topologia 

Convierte un nivel _Vin_ DC de entrada a una onda cualquiera AC. Existe tanto para una fase como polifásico y _half bridge Converters_ / _Full Bridge Converters_.
### Single - Phase Converter 

Representacion mas simple **Full-bridge**:

![Full bridge Inverter Simplest form](FullInverter1.jpeg)

Al activar unicamente los _P-Switches_ se tiene un ciclo positivo de la onda, posteriormente, al activar unicamente los _N-Switches_ se tiene un ciclo negativo de la onda.  Lo que corresponde a un _Dt = 0.5_.

Representacion mas simple _Half-bridge_ :

![Half-inverter simplest form](Halfinverter1.jpeg)


Únicamente depende de que _switch_ este operando y cual no. Ambos casos dependen de la conmutación para poner generar una _onda AC cuadrada_ sin offset. La onda obtenida tiene un _AC Fundamental Frecuency_ . Por Serie de Fourier se sabe que la amplitud de un **n - sin V** se puede obtener desde la onda cuadrada _Vo_:

$$ \Large V_{sin} = \frac {2}{T} \int_{0}^{T} Vo(t)(\sin(n\omega t)) = \frac {4Vi}{n\pi}$$

Con n siendo impar. Si _n=1_ se tiene el primer armonico y la expresion:

$$ \LARGE \frac {4Vi}{\pi} $$
Amplitud de una onda seno fundamental de la onda cuadrada (La misma frecuencia de la onda cuadrada base) 

Por lo que, se puede realizar un filtro LC _Low-pass_ que filtre una gran parte de los armónicos, haciendo que la amplitud se vuelva fija y a su vez generar un suavizado en la onda, no obstante, menor a la amplitud original.
