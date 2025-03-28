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
- Señal dientes de Sierra
<img src="https://github.com/user-attachments/assets/21986647-e05e-4f98-8beb-a890a45f8496" alt="Señal dientes de Sierra con offset" width="460">
<img src="https://github.com/user-attachments/assets/a2221fa0-d369-4907-8de7-e0f0229be735" alt="Señal dientes de sierra" width="340">

La señal transmitida se pudo visualizar correctamente.

- Señal senoidal
<img src="https://github.com/user-attachments/assets/7c4745c1-301d-497c-88e8-b32aa13a8ab4" alt="Señal coseno con offset" width="460">
<img src="https://github.com/user-attachments/assets/82484954-cb4a-4c32-8854-68b0f249264c" alt="Señal coseno" width="340">

<img src="https://github.com/user-attachments/assets/b44f3e22-e730-41d2-8b81-478cce6133f5" alt="Señal coseno con más offset" width="460">
<img src="https://github.com/user-attachments/assets/3478bec6-82ca-4a53-b531-50225277fc5d" alt="Señal coseno con offset" width="340">

Se pudo ver el efecto del offset. La señal se desplaza del eje de referencia e incluso se satura.

Efecto del ruido:

<img src="https://github.com/user-attachments/assets/ccfa6eb6-2f62-4cf6-9769-f0f0d28f6f08" alt="Señal senoidal con ruido" width="460">
<img src="https://github.com/user-attachments/assets/4374e666-ec32-4586-939e-c170239e55f2" alt="Señal senoidal con ruido" width="340">

Se pudo ver la distorsión provocada por el ruido.

- Señal cuadrada
<img src="https://github.com/user-attachments/assets/6e843322-ac57-4775-99e5-e54921217a1e" alt="Señal cuadrada con offset negativo" width="460">
<img src="https://github.com/user-attachments/assets/1fae2b78-2b42-45fb-b34b-037faf280945" alt="Señal cuadrada con offset negativo" width="340">

<img src="https://github.com/user-attachments/assets/ba895b4d-31b8-49e0-baff-0d012d745937" alt="Señal cuadrada" width="460">
<img src="https://github.com/user-attachments/assets/4798ebff-e109-4c62-b34a-0ee0fe4ec0fd" alt="Señal cuadrada" width="340">

Para un offset negativo, se pudo ver el desplazamiento de la señal hacia abajo.

Efecto del ruido:

<img src="https://github.com/user-attachments/assets/e4bc1cea-bc65-46c7-b49a-847686f04dba" alt="Señal cuadrada con un armónico y ruido" width="460">
<img src="https://github.com/user-attachments/assets/03d5a5f2-7f15-4912-92b8-5849a0e2819c" alt="Señal cuadrada con ruido" width="340">

Aún con la distorsión del ruido, el tipo de forma de onda era reconocible (cuadrada).

- Señal triangular
<img src="https://github.com/user-attachments/assets/e6ea59da-9744-4b50-9dbc-b89faa7e5d23" alt="Señal triangular" width="460">
<img src="https://github.com/user-attachments/assets/b8cc95ba-3371-4e5b-8739-80323c351929" alt="Señal triangular" width="340">

<img src="https://github.com/user-attachments/assets/71ca5e55-335e-4134-bab9-ca5e7f408022" alt="Señal triangular con offset" width="460">
<img src="https://github.com/user-attachments/assets/852a1bf8-6416-4766-91d0-dd7ffb9ffe6b" alt="Señal triangular con offset" width="340">

Para un offset positivo, la señal se desplaza hacia arriba y aumenta la amplitud.

<img src="https://github.com/user-attachments/assets/7c247515-d781-437d-823c-58a2ba68d409" alt="Señal triangular con offset negativo" width="460">
<img src="https://github.com/user-attachments/assets/c64ff6ec-1b3a-4162-85c3-ead2eda5b19c" alt="Señal triangular con offset negativo" width="340">

Para un offset negativo y teniendo en cuenta la señal de referencia, la señal se desplazó hacia abajo y por darse solapamientos en los extremos de las transiciones de onda, aparecen nuevos picos de menor magnitud.

#### Efecto de la frecuencia de portadora:

<img src="https://github.com/user-attachments/assets/03361797-bd7f-4386-bf39-ce395a68951a" alt="Señal cuadrada con fc 50 MHz" width="460">
<img src="https://github.com/user-attachments/assets/42962281-5129-4abc-a29c-f3d0f7444b1f" alt="Señal cuadrada con fc 50 MHz" width="340">

<img src="https://github.com/user-attachments/assets/d066b660-3878-415a-ad8b-74c2ef5883a7" alt="Señal cuadrada con fc 70 MHz" width="460">
<img src="https://github.com/user-attachments/assets/4f2c427b-6ead-4de5-923e-ba10aaa99519" alt="Señal cuadrada con fc 70 MHz" width="340">

<img src="https://github.com/user-attachments/assets/a4dabd77-a41a-4add-9b03-f3f20ebba3c1" alt="Señal cuadrada con fc 90 MHz" width="460">
<img src="https://github.com/user-attachments/assets/bf684eca-daa9-44a5-9aa5-e5d2ba11f9c3" alt="Señal cuadrada con fc 90 MHz" width="340">

<img src="https://github.com/user-attachments/assets/a3b4e86c-e5b7-4e36-afa7-a63add8052db" alt="Señal cuadrada con fc 100 MHz" width="460">
<img src="https://github.com/user-attachments/assets/01364e54-dd08-4819-906b-b89dd4e791ea" alt="Señal cuadrada con fc 100 MHz" width="340">

Al aumentar la frecuencia de portadora, nos estabamos acercando al límite impuesto por el ancho de banda del osciloscopio. De allí que la señal estuviera siendo menos percibida, esto se evidenció en la disminución de su amplitud. 

<img src="https://github.com/user-attachments/assets/6437eca0-20fb-49c7-ba11-6c13a14bdfdc" alt="Señal cuadrada con fc 500 MHz" width="460">
<img src="https://github.com/user-attachments/assets/681968ee-9c17-43b9-94da-f7a934fa6686" alt="Señal cuadrada con fc 500 MHz" width="340">

Cuando se superó el ancho de banda del osciloscopio, la señal simplemente no fue reconocida por este.

### Actividad 3: Fenómenos de canal en el analizador de espectro

### Análisis de resultados 
La principal diferencia entre los modelos que se simulan y el modelo que se puede ver en el analizador de espectros son las restricciones que posee un equipo en la vida real, ya que éstos trabajan en ciertos parámetros que no se pueden evitar, siendo uno de estos casos la frecuencia donde a la frecuencia que se encontraron de los espectros de las señales se le adicionaba 100[MHz] ya que de otra forma el dispositivo no iba a ser capaz de entregar la señal, otro ejemplo de esto es el barrido de la frecuencia donde se debe ajustar el parámetro en rangos relativamente altos ya que valores como 20[kHz] le costaba realizar el barrido y se auto-ajustaba, además de factores como el ruido de una señal, se puede modelar en el simulador pero generalmente éstas perturbaciones se dan en el dispositivo de medición y en ciertos casos este piso no tenía menos de 20dB entre la señal y el mismo, por lo cual costaba el análisis respectivo.

Uno de los parámetros más importantes vistos en ésta práctica fue el ruido, en la mayor parte del laboratorio se hizo presente y aparentemente no estaba muy alejado de la señal de interés, la relacion señal a ruido(SNR) es importante en estos casos ya que se necesita saber qué tanto de la información se puede ver afectada por el ruido, ya que éste afecta cálculos importantes como el del ancho de banda y como se puede apreciar en las imágenes correspondientes a las respuestas de las señales, específicamente en la señal cuadrada, el ruido está al nivel del segundo armónico de esta señal, esto para una reconstrucción podría ser grave ya que no permitiría un buen análisis, ésto tambien se debe tener en cuenta en etapas como recepción de información ya que si el ruido es grande, podía pasar las etapas de filtrado y contaminar la señal de información.

---
### Conclusiones
Se puede ver la importancia de usar los dispositivos en sus rangos de operación ideales, ya que de otra forma se pueden generar modificaciones en la señal transmitida haciendo que el mensaje cambie, de igual forma se debe tener especial cuidado en las perturbaciones que son intrínsecas del aparato de medición, ya que ésto puede hacer que se facilite o no el análisis de una señal.

---

Volver al [INICIO](#laboratorio-de-comunicaciones)
