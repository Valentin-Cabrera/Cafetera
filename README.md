# Cafetera
## Diseño del control de cafetera comercial.
La cafetera cuenta con una serie de sensores que monitorean la presion y temperatura del boiler en todo momento, a su vez la presión para extraer el cafe es generada por una bomba rotatoria conectada a un motor de inducción monofasico. 
Como objetivo me planteo el diseño de un variador de frecuencia que me permita regular la presión de extraxion de cafe, variando las rmp del motor, ademas de esto el controlador también debera monitoriar los distintos sensores de presion y temperatura en el boiler.
El paso de agua esta controlado por una serie de valvulas solenoides, que funcionan directamente a 220V 50Hz por lo que para controlar las mismsa sera necesario utilizar reles.

## Modulos del diseño.
Dada las características deseadas voy a dividir el diseño del controlador en dos partes:
- Potencia
- Logica
Para la parte de potencia implementare un variador de fecuencia con MOSFETs en un puente H.
En particular seran necesarios 2 nmos y 2 pmos junto con dos octocopladores que garanticen un aislasion galvanica entre ambos modulos.
Mientras que la logica utilisare un arduino nano, 4 reles (3 valvulas y 1 para la resistencia del boiler), sensor de presion para monitorear la presion a la salida de la bomba,termistor, ads1115 para realizar las medisiones de sensores. 
## Esquematico del variador de frecuencia (Circuito de potencia).
<img width="1150" alt="Captura de pantalla 2025-06-10 a la(s) 2 47 05 p  m" src="https://github.com/user-attachments/assets/4dd6f798-ccf5-4ffb-81b4-8a6499f17dc4" />
## Simulación con componentes similares.
<img width="431" alt="Captura de pantalla 2025-06-10 a la(s) 2 38 50 p  m" src="https://github.com/user-attachments/assets/546509e4-b49f-4d4b-aa0c-d1083a756ff7" />
<img width="547" alt="Captura de pantalla 2025-06-10 a la(s) 2 39 11 p  m" src="https://github.com/user-attachments/assets/41281145-682c-46da-b7f1-2f963fbbafe1" />
