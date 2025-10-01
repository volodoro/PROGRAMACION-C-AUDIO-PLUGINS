### ¿Qué es FIFO?

FIFO sería como cuando uno va al banco y hace una fila para que lo atiendan. Se supone que el primero que fue al banco debiese ser el primero al que atiendan, asumiendo que todas las personas realizarán el mismo trámite y la misma fila.
Cuando vayamos a procesar audio en tiempo real hay que procesar en el mismo orden en el que ocurren las conversiones.

Cuánto tiempo tiene un plugin para devolver el audio procesado? ---> (Buffer size / fs) [en segundos]

-------------------------------

¿Qué diferencia hay entre usar una FFT con una ventana de 512 y una con una ventana de 2048?

Una FFT con una ventana de 512 entrega 256 Bandas, por lo tanto la de 2048 entrega 1024. Es decir, existe más resolución en el segundo caso. ¿En qué parte del espectro frecuencial es más deficiente la resolución? En frecuencias bajas, porque físicamente están más separadas.
Por lo tanto, si queremos analizar el comportamiento de un micrófono en frecuencias bajas, qué ventana nos senviría más? Recordemos que 512 significa que en una unidad de tiempo hay 512 muestras temporales. Como la longitud de onda está relacionada al período de una onda y
mientras más grande la frecuencia, mayor el período, es decir, más tiempo tarda la onda en completar un ciclo. Por lo tanto mientras más datos nos entregue la ventana, más nos aseguramos de que la FFT será capaz de analizar durante más tiempo.

FIFO -> Memoria -> Buffer -> 4096
El buffer size es lo que define la latencia.

¿Cómo podemos hacer que la latencia sea la del buffer size (definida en el setup) y no la del tamaño del FIFO?
Partimos de 0, entran 512 muestras, las ubico en los primeros 512 espacios de la memoria en mi FIFO
