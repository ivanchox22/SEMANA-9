# SEMANA-9

# Control de Movimiento

## Diseño de Transmisión

El diseño de transmisión tiene como objetivo transferir potencia y movimiento entre diferentes elementos mecánicos, utilizando sistemas como engranajes, correas y cadenas. Esta transferencia debe ser eficiente, precisa y segura, para asegurar el correcto funcionamiento de máquinas industriales, robots, vehículos y sistemas automatizados. Un diseño bien hecho optimiza el rendimiento energético, minimiza el desgaste, asegura precisión en el movimiento y se adapta a variaciones en la carga.

Para lograrlo, se aplican principios de la cinemática, dinámica y resistencia de materiales, con el fin de construir un sistema robusto, confiable y de larga duración.

---

## Requisitos de Diseño

Antes de diseñar un sistema de control de movimiento, es necesario definir claramente sus requerimientos. Esto incluye la correcta selección del motor y del mecanismo de transmisión, así como una evaluación del comportamiento del sistema ante distintas cargas y condiciones de trabajo.

Es importante tener en cuenta factores como el costo, la precisión, el consumo de energía, el tiempo de respuesta y el espacio físico disponible. Además, el torque del motor debe estar sobredimensionado con un margen de seguridad para cubrir situaciones extremas. También se debe cuidar que la relación de inercia entre la carga y el motor no afecte la respuesta dinámica del sistema.

A continuación, se presentan diferentes situaciones que pueden surgir en el diseño:

| Situación | Enfoque |
|----------|---------|
| Se conoce el movimiento deseado | Dimensionar motor y transmisión |
| Ya existe motor y transmisión | Calcular movimiento que se obtiene |
| Motor existente y se busca un movimiento | Calcular la transmisión requerida |
| Transmisión existente y se busca un movimiento | Seleccionar motor adecuado |

---

## Inercia y Torque

### Inercia Reflejada

Cuando se conecta una carga a través de un sistema de transmisión, el motor no "siente" la inercia real de la carga, sino una versión ajustada por la relación de transmisión. Esta se conoce como inercia reflejada:

\[
$J_r = J_L \cdot N^2$
\]

Donde \( J_r \) es la inercia reflejada, \( J_L \) es la inercia de la carga, y \( N \) es la relación de transmisión.

### Torque Reflejado

De manera similar, el torque que el motor necesita entregar también cambia debido a la transmisión. Se calcula así:

\[
$T_r = \frac{T_L}{N}$
\]

Esto permite adaptar el sistema para reducir el esfuerzo del motor o ajustar el comportamiento dinámico.

---

## Engranajes

Los engranajes son esenciales para modificar el torque y la velocidad en los sistemas mecánicos. La relación de transmisión depende del número de dientes o del diámetro de los engranajes:

\[
$N = \frac{Z_{conducido}}{Z_{conductor}} = \frac{D_{conducido}}{D_{conductor}}$
\]

Donde \( Z \) representa el número de dientes y \( D \) el diámetro de cada engranaje.

- Si \( N > 1 \), se reduce la velocidad y aumenta el torque.
- Si \( N < 1 \), se incrementa la velocidad y se reduce el torque.
- Si \( N = 1 \), no hay cambios en torque ni velocidad.

---

## Eficiencia

Un sistema eficiente es aquel que logra el movimiento deseado con el menor consumo posible de energía. Esto depende de varios factores:

- Usar mecanismos con baja fricción y mínimas holguras.
- Implementar controladores adecuados como PID.
- Seleccionar motores eficientes y evitar sobrecargas.
- Diseñar trayectorias suaves con perfiles de aceleración adecuados.
- Incluir sensores de alta resolución para retroalimentación precisa.

---

## Inercia Total

La inercia total que enfrenta el motor es la suma de varias componentes:

\[
$J_{total} = J_{motor} + J_{transmision} + J_{carga\_reflejada}$
\]

Esto influye directamente en la aceleración, la estabilidad del sistema y la elección del motor.

---

## Relación de Inercia

La relación de inercia entre la carga reflejada y el motor es clave para el rendimiento:

\[
\$Ri=frac{J_{carga\_reflejada}}{J_{motor}}$
\]

- Una relación baja mejora la respuesta, pero puede requerir motores grandes.
- Una relación alta puede ser útil para movimientos lentos, aunque reduce eficiencia.

Se busca mantener esta relación dentro de un rango adecuado para lograr un equilibrio entre respuesta y consumo.

---

## Poleas y Correas

Este sistema es común por su simplicidad y bajo costo. Es ideal para transmitir movimiento entre ejes alejados.

![image](https://github.com/user-attachments/assets/da4a4a6d-ef63-4c43-9983-d250f38fd836)

***FIG 1. Poleas y correas***


### Ventajas

- Bajo nivel de ruido.
- Tolerancia a desalineaciones.
- Amortiguación de vibraciones.

### Desventajas

- Pérdidas por deslizamiento.
- Requiere mantenimiento regular.
- Menor eficiencia que los engranajes.

### Relación de Transmisión

Se puede calcular mediante:

\[
$i = \frac{D_{conducida}}{D_{motriz}} = \frac{N_{motriz}}{N_{conducida}} = \frac{Vel_{motriz}}{Vel_{conducida}}$
\]

![image](https://github.com/user-attachments/assets/096d988f-9b4b-4dd0-a189-e23603b14ed6)

***FIG 2. Relacion de trasmision***

### Inercia Reflejada

La carga reflejada al motor se calcula con:

\[
$J_{ref} = J_{carga} \cdot i^2$
\]


![image](https://github.com/user-attachments/assets/a2bc9217-411f-4ba9-83ff-43fdadfb3793)

***FIG 3. Inercia refejada***

### Torque

El torque requerido en el motor depende de la transmisión y la eficiencia:

\[
$T_{motor} = \frac{T_{carga}}{i \cdot n}$
\]

![image](https://github.com/user-attachments/assets/0ec7c7d9-4f22-449e-9c6e-876145e17ac6)

***FIG 4. Torque***

Donde \( n \) es la eficiencia del sistema.

---

## Sensores

Los sensores son elementos fundamentales en cualquier sistema de control de movimiento. Permiten medir variables como posición, velocidad o aceleración, y enviar esta información a un controlador.

Gracias a la retroalimentación que ofrecen, se puede ajustar el comportamiento del sistema en tiempo real, mejorando la precisión, eficiencia y seguridad.

---

---

## Ejemplos

### Ejemplo: Cálculo de inercia reflejada

Una carga de **50 kg** debe ser posicionada usando un tornillo esferado de acero con:

- **Densidad:** 0.14 kg/cm³  
- **Diámetro:** 0.182 cm  
- **Longitud:** 36 cm  
- **Paso:** 0.75 cm/rev  
- **Eficiencia:** 90%  
- **Peso del carro:** 0.23 kg  

Se desea calcular la **inercia reflejada** por la transmisión hacia el eje de entrada.

#### Fórmula general de inercia reflejada:

\[
$J_{\text{trans ref}} = J_{\text{screw}} + \frac{1}{\eta N_s^2} \left( \frac{W_L + W_C}{g} \right)$
\]

Donde:

- \( $J_{\text{screw}}$ \): Inercia del tornillo  
- \( \eta \): Eficiencia del tornillo  
- \( N_s \): Relación de transmisión del tornillo  
- \( W_L \): Peso de la carga  
- \( W_C \): Peso del carro  
- \( g \): Aceleración gravitacional  
- \( $J_{\text{load-in}} \)$ y \( $J_{\text{carriage-in}}$ \): Se asumen despreciables

#### Cálculo de la relación de transmisión:

\[
$N_s = \frac{2\pi}{P} = \frac{2\pi}{0.75} = 8.38$
\]

#### Cálculo de la inercia del tornillo (suponiendo cilindro alargado):

\[
$J_{\text{screw}} = \frac{\pi L \rho D^4}{32g}$
\]

Donde:

- \( $L = 0.36 \, \text{m}$\)  
- \( $\rho = 140000 \, \text{kg/m}^3$ \)  
- \( $D = 0.00182 \, \text{m} \$)

\[
$J_{\text{screw}} = \frac{\pi \cdot 0.36 \cdot 140000 \cdot (0.00182)^4}{32} = 5.42 \times 10^{-8} \, \text{kg·m}^2$
\]

#### Sustituyendo todo en la fórmula principal:

\[
$J_{\text{trans ref}} = 5.42 \times 10^{-8} + \frac{1}{0.9 \cdot (8.38)^2} \left( \frac{50 + 0.23}{9.89} \right)$
\]

\[
$J_{\text{trans ref}} \approx 8.1 \, \text{kg·m}^2$
\]


---

## Conclusiones

- El cálculo de la **inercia reflejada** hacia el eje de entrada es fundamental para el dimensionamiento correcto del motor en sistemas de transmisión con tornillo esferado, permitiendo prever el comportamiento dinámico del sistema y garantizar un control preciso.

- La **mayor contribución a la inercia reflejada** proviene de la carga útil y el carro, más que del tornillo en sí, lo cual subraya la importancia de considerar el peso total desplazado en el análisis.

- La **relación de transmisión \(N_s\)** tiene un efecto cuadrático inverso sobre la inercia reflejada, lo que significa que un diseño con una relación adecuada puede reducir significativamente el esfuerzo requerido por el motor.

- La **eficiencia mecánica \(\eta\)** de la transmisión también afecta directamente la inercia reflejada: una eficiencia baja incrementa la inercia equivalente, por lo que es esencial emplear componentes de alta calidad y bajo coeficiente de fricción.

- El uso correcto de **modelos geométricos** (como suponer el tornillo como cilindro alargado) y fórmulas específicas (como \( $J_{\text{screw}} = \frac{\pi L \rho D^4}{32}$ \)) permite estimar con mayor precisión la inercia del sistema, siempre que se utilicen unidades consistentes y adecuadas (SI o sistema inglés).

- Finalmente, este tipo de análisis no solo optimiza la selección del motor, sino que también mejora la vida útil del sistema, reduce el consumo energético y mejora la seguridad operativa del conjunto.
