# Laboratorio de Comunicaciones
## Universidad Industrial de Santander

# Práctica 1C: Mediciones de potencia y frecuencia 

### Integrantes
- **Andrés Conde Alvarez** - 2220389
- **Jesús Alberto Escorcia Mantilla** - 2220526

Escuela de Ingenierías Eléctrica, Electrónica y de Telecomunicaciones  
Universidad Industrial de Santander

### Fecha
5 de marzo del 2025

---

## Declaración de Originalidad y Responsabilidad
Los autores de este informe certifican que el contenido aquí presentado es original y ha sido elaborado de manera independiente. Se han utilizado fuentes externas únicamente como referencia y han sido debidamente citadas.

Asimismo, los autores asumen plena responsabilidad por la información contenida en este documento. 

Uso de IA: Se usó la inteligencia articial ChatGPT para la sintaxis que requiere el formato del informe.

---
## Contenido

### Resumen
En este laboratorio se midieron y analizaron parámetros clave de las comunicaciones como la potencia, el ancho de banda, relación señal a ruido (SNR) y piso de ruido. Lo anterior fue posible gracias al uso de herramientas de software, como GNU radio, y equipos de medición como el USRP 2920, el osciloscopio R&S RTB2004 y el analizador de espectros R&S FPC1000.

**Palabras clave**: parámetros, comunicaciones, software, equipos, medición.
---
### Actividad 1: Revisión de especificaciones de los equipos
A continuación se encuentran 5 especificaciones sobre cada uno los equipos utilizados:
#### USRP 2920
- Rango de frecuencia: 50 MHz - 2.2 GHz
- Paso de frecuencia: 1 kHz
- Rango de ganancia: 0 - 31.5 dB
- Paso de ganancia: 0.5 dB
- Alimentación: DC 6V, 3A
#### Osciloscopio R&S RTB2004
- Ancho de banda: 70 - 300 MHz
- Frecuencia de muestreo: 2.5 Gmuestras/s
- Impedancia de entrada: 1 MΩ
- Resolución ADC: 10 bit
- Sensibilidad mínima de entrada: 1 mV/div
#### Analizador de espectros R&S FPC1000
- Rango de frecuencias: 5 kHz - 1 GHz
- Resolución de frecuencia: 1 Hz
- Ancho de banda de resolución: 1 Hz - 300 MHz en secuencia 1/3
- Impedancia de entrada: 50 Ω
- Potencia de entrada máxima: +30 dBm
#### Calculo del piso de ruido en Analizador de espectros
Para la realización de esta medición se usó la siguiente imagen:
- Piso de ruido del analizador de espectros
<img src="https://github.com/user-attachments/assets/b170819e-a4ae-4906-bb3e-684a60f0411f" alt="Noisefloor" width="500">

Teniendo en cuenta que `Nf = PNref[dBm]-10log(RBW/1)` donde `PNref[dBm]=-75[dBm]` y `RBW=1[MHz]`, estos valores se muestran en la imagen anterior

### Actividad 2: Simulación de señales en GNU radio
#### Simulación de diferentes tipos de señales:
- Señal constante con y sin ruido
<img src="https://github.com/user-attachments/assets/3520eddf-33db-47e2-9984-aca9c7c6c072" alt="2_Señal constante con ruido" width="500">
<img src="https://github.com/user-attachments/assets/c11ef2d0-1242-40d6-8a22-64acf6311aca" alt="1_Señal constante" width="500">

- Señal senoidal
<img src="https://github.com/user-attachments/assets/57e97618-a2b5-47b6-a21a-61899a73944b" alt="1_Señal senoidal" width="500">

- Señal cuadrada compleja 
<img src="https://github.com/user-attachments/assets/a206d15c-dc59-4aae-a8e5-9c0be07480ce" alt="2_Señal compleja cuadrada" width="500">

- Señal cuadrada real con y sin ruido
<img src="https://github.com/user-attachments/assets/5e2e0581-e665-4b88-bd52-bf1afd91abfc" alt="2_Señal real cuadrada con ruido" width="500">
<img src="https://github.com/user-attachments/assets/f9683e4d-8ec9-4a86-a1b2-f15f297cd5d9" alt="2_Señal real cuadrada" width="500">

#### Cálculos
Se hizo el cálculo de una resistencia equivalente de la simulación y de la potencia de una señal constante.
- Señal senoidal
<img src="https://github.com/user-attachments/assets/d1f13f76-e87f-44e8-adec-b3fb9a167131" alt="1_Potenica señal senoidal" width="500">

Teniendo en cuenta que `P = (V_rms^2)/R` donde `V_rms = V_p/sqrt(2)` y `P = 10^(P_dB/10)`, además de que se ve solo una de las dos partes del espectro. El despeje de `R` dio como resultado: `R = 7.78 [Ω]`, este resultado se interpretará como una variable de normalización

- Señal constante
<img src="https://github.com/user-attachments/assets/a23bc488-bf4d-4233-9b62-287358b133bf" alt="1_Potencia señal constante" width="500">

Dada la resistencia de `R = 7.78 [Ω]` hallada anteriormente, calculamos `P = (V^2)/R` de allí `P = (25/7.78) ≈ 3.21 [W]` y pasando dicho valor a escala logarítmica tenemos `10log(3.21)=5.07 [dB]` que era justo lo que esperábamos.

### Actividad 3: Transmisión y medición de señales con el USRP 2920
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

- El ancho de banda de la señal FM fue de: 200 kHz
- La relación señal a ruido de la señal FM fue de: -65 dBm -(-90 dBm) = 35 dB

### Actividad 4: Análisis de resultados y conclusiones

---
### Conclusiones
Se sintetizan los principales aportes y puntos relevantes de la práctica, evitando repetir lo ya consignado en las otras secciones del informe. 

### Referencias
- «USRP-2920 Specifications». https://www.farnell.com/datasheets/3752193.pdf
- «R&S®RTB2000 Osciloscopio digital». https://www.farnell.com/datasheets/2723043.pdf
- «R&S®FPC1000 Analizador de espectro». https://www.farnell.com/datasheets/2342799.pdf

---

## Inclusión de Imágenes
### Imagen de referencia dentro del repositorio:
![Networking](my%20file/test.png)

### Imagen de fuente externa
![GNU Radio logo](https://kb.ettus.com/images/thumb/5/50/gnuradio.png/600px-gnuradio.png)

### Uso de html para cambiar escala de la imagen
<img src="https://kb.ettus.com/images/thumb/5/50/gnuradio.png/600px-gnuradio.png" alt="GNU Radio Logo" width="300">

## Uso de Expresiones Matemáticas
Se pueden incluir ecuaciones en el archivo `README.md` utilizando sintaxis similar a [LaTeX](https://manualdelatex.com/tutoriales/ecuaciones):

### Ecuaciones en Línea
```
La energía de una señal exponencial es $E = \int_0^\infty A^2 e^{-2t/\tau} dt$.
```
**Salida renderizada:**
La energía de una señal exponencial es $E = \int_0^\infty A^2 e^{-2t/\tau} dt$.

### Ecuaciones en Bloque
```
$$E = \int_0^\infty A^2 e^{-2t/\tau} dt = \frac{A^2 \tau}{2}$$
```
**Salida renderizada**
$$E = \int_0^\infty A^2 e^{-2t/\tau} dt = \frac{A^2 \tau}{2}$$

## Creación de Tablas

**Tabla 1.** Ejemplo de tabla en Markdown.

| Parámetro | Valor |
|-----------|-------|
| Frecuencia (Hz) | 1000 |
| Amplitud (V) | 5 |
| Ciclo útil (%) | 50 |

## Inclusión de código

```python
def hello_world():
    print("Hello, World!")
```

También es posible resaltar texto tipo código como `print("Hello, World!")`.

---

Volver al [INICIO](#laboratorio-de-comunicaciones)
