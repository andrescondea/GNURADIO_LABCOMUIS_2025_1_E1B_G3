# Laboratorio de Comunicaciones
## Universidad Industrial de Santander

# Práctica 2A: Modelo de canal

### Integrantes
- **Andrés Conde Alvarez** - 2220389
- **Jesús Alberto Escorcia Mantilla** - 2220526

Escuela de Ingenierías Eléctrica, Electrónica y de Telecomunicaciones  
Universidad Industrial de Santander

### Fecha
28 de marzo del 2025

---

## Declaración de Originalidad y Responsabilidad
Los autores de este informe certifican que el contenido aquí presentado es original y ha sido elaborado de manera independiente. Se han utilizado fuentes externas únicamente como referencia y han sido debidamente citadas.

Asimismo, los autores asumen plena responsabilidad por la información contenida en este documento. 

Uso de IA: Se usó la inteligencia articial ChatGPT para la sintaxis que requiere el formato del informe.

---
## Contenido

### Resumen
En este laboratorio se observaron fenómenos de canal de diferentes formas; esto es, por medio de la simulación con GNU Radio y visualización tanto en el osciloscopio como en el analizador de espectros. En el proceso se observó el filtrado de las señales y el efecto de su forma de transmisión (alámbrica).

**Palabras clave**: fenómenos, canal, simulación, filtrado, transmisión.

---
### Actividad 1: Actividades de simulación de canal en GNU Radio
- Señal senoidal
<img src="https://github.com/user-attachments/assets/f074226f-9bdc-4dbc-b4de-87398bf1676c" alt="Senoidal recibida sin ruido" width="500">

Se puede observar la señal de tipo senoidal recibida. Está pasando por el filtro. 

<img src="https://github.com/user-attachments/assets/1e26dbf9-2d25-4c56-a88f-460f0c0e147b" alt="Senoidal cortada por frecuencia inferior" width="500">
<img src="https://github.com/user-attachments/assets/a842445b-cdb7-41ac-bd37-a041ff5410b6" alt="Senoidal cortada por la frecuencia superior" width="500">

Cuando la frecuencia de la señal tenía un valor cercano a la de los límites del filtro, la señal recibida se hacía menos visible; lo cual se evidencia tanto en el dominio del tiempo como en el dominio de la frecuencia con la disminución de la amplitud y potencia respectivamente.

Efecto del ruido:

<img src="https://github.com/user-attachments/assets/a83a1cab-4e28-41e2-9672-89cf905988e1" alt="Senoidal con mucho ruido frecuencia" width="500">
<img src="https://github.com/user-attachments/assets/194077e0-7ac4-41b8-b032-d443e7e5b250" alt="Senoidal con mucho ruido tiempo" width="500">

Al agregar ruido a la señal transmitida, esta se volvía indistinguible en el dominio del tiempo; sin embargo, gracias al filtro, la señal recibida fue reconocible.

- Señal cuadrada
<img src="https://github.com/user-attachments/assets/4b158cf5-3d13-41ba-b27d-3b5425cf384a" alt="Señal cuadrada" width="500">

Al transmitir una señal cuadrada se vieron los armónicos en el dominio de la frecuencia.

<img src="https://github.com/user-attachments/assets/5a7ce911-c926-412c-931c-73db5f046765" alt="Señal cuadrada con mucho ruido" width="500">
<img src="https://github.com/user-attachments/assets/5797da29-f0f1-423c-94f1-73d792d1c580" alt="Señal cuadrada con mucho ruido y otro armónico" width="500">

De nuevo se agregó ruido, el cual fue filtrado. Por otra parte, modificando los límites del filtro se hizo que pasarán más armónicos de la señal; no obstante, para las simulaciones mostradas, la forma de señal cuadrada no fue reconocible.

- Señal tipo WAV
<img src="https://github.com/user-attachments/assets/e5639ac6-c742-4eac-912b-86d280cec3a9" alt="Prueba con WAV tiempo" width="500">
<img src="https://github.com/user-attachments/assets/6dc552e1-e627-4ea1-8e14-ae58f8d55884" alt="Prueba con WAV frecuencia" width="500">

En el caso de la señal tipo WAV no se pudo distinguir la señal recibida en el dominio tiempo pero sí en el dominio de la frencuecia, esto puede deberse a que en el tiempo la magnitud sea muy pequeña.

Efecto del ruido:

<img src="https://github.com/user-attachments/assets/d218edd0-240e-4bed-b6c5-a704b3de9a3b" alt="Prueba con ruido en WAV tiempo" width="500">
<img src="https://github.com/user-attachments/assets/b5a43b62-c20a-4ed8-bd8f-acf78c8db84d" alt="WAV con poco ruido frecuencia" width="500">

Nuevamente las afectaciones del ruido en la señal transmitida son contrarestadas por el filtro y ello se visualiza en la señal recibida.

### Actividad 2: Fenómenos de canal en el osciloscopio

### Actividad 3: Fenómenos de canal en el analizador de espectro
La señal de prueba fue de tipo senoidal, se hicieron diferentes variaciones de parámetros:
#### Variación de la magnitud
GNU radio 

<img src="https://github.com/user-attachments/assets/453a5e82-2aa2-4d9c-8ed8-58d8e2215823" alt="2_Señal seno con offset con más amplitud" width="500">

Analizador de espectros

<img src="https://github.com/user-attachments/assets/7ac6d201-6835-4cfc-b85e-16c735ea11f4" alt="Aumento de la amplitud 1" width="400">
<img src="https://github.com/user-attachments/assets/4296d9ae-8221-4c27-9196-fef5d0a66863" alt="Aumento de la amplitud 2" width="400">

El aumento de la magnitud de la señal resultó en la saturación del analizador de espectros. Con que fuera mayor a 1 ya empezaba a saturarse.
#### Variación de ruido
- Señal sin ruido
<img src="https://github.com/user-attachments/assets/1141c76f-e97f-40f4-89fe-a074ce9591be" alt="Sin ruido" width="400">

- Señal con ruido
<img src="https://github.com/user-attachments/assets/bb20d996-20c7-4d14-95b8-371b7d349122" alt="Con ruido" width="400">

Se observó el aumento de ruido en la señal viendo como el piso de ruido era mayor.
#### Adición de Offset
GNU Radio

<img src="https://github.com/user-attachments/assets/801fb938-048b-48d4-ba2d-8405f6dd30a3" alt="2_Señal seno con offset" width="500">

Analizador de espectros

<img src="https://github.com/user-attachments/assets/d27db3a4-b060-4fbb-be4c-f3674c7e2b50" alt="Adición de offset" width="400">

La adición de offset resultó en la aparición de un nuevo pico de potencia.
#### Variación de la frecuencia
- Aumento de la frecuencia
<img src="https://github.com/user-attachments/assets/cf7c6857-3ec8-4dfc-914e-a688ca18f406" alt="2_Señal real coseno" width="500">
<img src="https://github.com/user-attachments/assets/fdedcd31-a4f9-48f3-a947-8ace0248217a" alt="Variación de la frencuencia 2" width="400">

- Disminución de la frecuencia
<img src="https://github.com/user-attachments/assets/61e3481c-ba8a-4541-a49f-4b878b007356" alt="2_Señal real coseno 2" width="500">
<img src="https://github.com/user-attachments/assets/49b68505-8448-4c73-b5b3-b2fbbf21ffcb" alt="Variación de la frecuencia 1" width="400">

La variación de la frecuencia resultó en el desplazamiento de los picos de potencia. Lo anterior tiene sentido porque la transformada de Fourier de una señal senoidal son dos impulsos en ±f, siendo f su frecuencia fundamental, si se varía la frecuencia se desplazan los impulsos.

#### Variación de la fase
<img src="https://github.com/user-attachments/assets/6ce118fe-4565-42b9-b45c-a8534f1a2128" alt="2_Señal coseno con cambio de fase" width="500">

No se observaron cambios al variar la fase de la señal.
#### Espectro de una señal FM
Por otro lado, se observó gracias al uso de una antena, una señal FM alrededor de los 95.8 MHz.
<img src="https://github.com/user-attachments/assets/85dfbe84-75aa-4e24-8a7a-311bafd3091d" alt="Medición emisora FM" width="500">

- El ancho de banda de la señal FM fue de: 200 kHz.
- La relación señal a ruido de la señal FM fue de: -65 dBm -(-90 dBm) = 35 dB.

### Actividad 4: Análisis de resultados y conclusiones
La principal diferencia entre los modelos que se simulan y el modelo que se puede ver en el analizador de espectros son las restricciones que posee un equipo en la vida real, ya que éstos trabajan en ciertos parámetros que no se pueden evitar, siendo uno de estos casos la frecuencia donde a la frecuencia que se encontraron de los espectros de las señales se le adicionaba 100[MHz] ya que de otra forma el dispositivo no iba a ser capaz de entregar la señal, otro ejemplo de esto es el barrido de la frecuencia donde se debe ajustar el parámetro en rangos relativamente altos ya que valores como 20[kHz] le costaba realizar el barrido y se auto-ajustaba, además de factores como el ruido de una señal, se puede modelar en el simulador pero generalmente éstas perturbaciones se dan en el dispositivo de medición y en ciertos casos este piso no tenía menos de 20dB entre la señal y el mismo, por lo cual costaba el análisis respectivo.

Uno de los parámetros más importantes vistos en ésta práctica fue el ruido, en la mayor parte del laboratorio se hizo presente y aparentemente no estaba muy alejado de la señal de interés, la relacion señal a ruido(SNR) es importante en estos casos ya que se necesita saber qué tanto de la información se puede ver afectada por el ruido, ya que éste afecta cálculos importantes como el del ancho de banda y como se puede apreciar en las imágenes correspondientes a las respuestas de las señales, específicamente en la señal cuadrada, el ruido está al nivel del segundo armónico de esta señal, esto para una reconstrucción podría ser grave ya que no permitiría un buen análisis, ésto tambien se debe tener en cuenta en etapas como recepción de información ya que si el ruido es grande, podía pasar las etapas de filtrado y contaminar la señal de información.

---
### Conclusiones
Se puede ver la importancia de usar los dispositivos en sus rangos de operación ideales, ya que de otra forma se pueden generar modificaciones en la señal transmitida haciendo que el mensaje cambie, de igual forma se debe tener especial cuidado en las perturbaciones que son intrínsecas del aparato de medición, ya que ésto puede hacer que se facilite o no el análisis de una señal.

### Referencias
- «USRP-2920 Specifications». https://www.farnell.com/datasheets/3752193.pdf
- «R&S®RTB2000 Osciloscopio digital». https://www.farnell.com/datasheets/2723043.pdf
- «R&S®FPC1000 Analizador de espectro». https://www.farnell.com/datasheets/2342799.pdf

---

Volver al [INICIO](#laboratorio-de-comunicaciones)
