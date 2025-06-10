# Cafetera
## Diseño del control de cafetera comercial.

La cafetera cuenta con una serie de sensores que monitorean la presión y temperatura del boiler en todo momento. A su vez, la presión necesaria para extraer el café es generada por una bomba rotatoria conectada a un motor de inducción monofásico.

Como objetivo, me planteo el diseño de un variador de frecuencia que permita regular la presión de extracción del café, variando las RPM del motor. Además de esto, el controlador también deberá monitorear los distintos sensores de presión y temperatura en el boiler.

El paso de agua está controlado por una serie de válvulas solenoides que funcionan directamente a 220 V 50 Hz, por lo que será necesario utilizar relés para su control.

## Módulos del diseño

Dadas las características deseadas, voy a dividir el diseño del controlador en dos partes:

- Potencia
- Lógica

Para la parte de potencia, implementaré un variador de frecuencia con MOSFETs en un puente H. En particular, se utilizarán 2 NMOS y 2 PMOS junto con dos optoacopladores que garanticen aislamiento galvánico entre ambos módulos.

Para la parte lógica, utilizaré un Arduino Nano, 4 relés (3 para válvulas y 1 para la resistencia del boiler), un sensor de presión para monitorear la salida de la bomba, un termistor y un ADS1115 para realizar las mediciones de los sensores. 
## Esquemático del variador de frecuencia (circuito de potencia)

<img width="1150" alt="Captura de pantalla 2025-06-10 a la(s) 2 47 05 p  m" src="https://github.com/user-attachments/assets/4dd6f798-ccf5-4ffb-81b4-8a6499f17dc4" />

### Lista de componentes:
- IRFP460PBF
- IXTH10P50P
- 4N35
Falta dimensionar los valores de las resistencias para la correcta carga y descarga de los gates de los MOSFETs, además del cálculo de la capacidad para mantener un ripple pequeño.
## Simulación con componentes similares.
<img width="431" alt="Captura de pantalla 2025-06-10 a la(s) 2 38 50 p  m" src="https://github.com/user-attachments/assets/546509e4-b49f-4d4b-aa0c-d1083a756ff7" />
<img width="547" alt="Captura de pantalla 2025-06-10 a la(s) 2 39 11 p  m" src="https://github.com/user-attachments/assets/41281145-682c-46da-b7f1-2f963fbbafe1" />

## Esquematico de PCB encargada de la logica (Pendiente)

## Siguiente paso 
Para continuar con el desarrollo hace falta el ensamblado y testeo de la parte de potencia, ensayo de arranque del motor (para chequear que las pistas de la pcb y componentes puedan soportar el transistorio). Posteriormete la calibración de los sensores para comporbar el correcto funcionamiento de la cafetera con el controlador diseñado.
