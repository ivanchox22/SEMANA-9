# SEMANA-9

# Control de Movimiento (Diseño de Transmisión)

## Introducción al Diseño de Transmisión

El **diseño de transmisión** se encarga de transferir potencia y movimiento entre componentes mecánicos, utilizando distintos elementos como **engranajes, correas y cadenas**. Su propósito es asegurar una **transmisión eficiente, duradera y segura**, aplicable a sistemas como maquinaria industrial, robótica, vehículos y equipos automatizados.

Un diseño adecuado debe:

- Optimizar el rendimiento energético.
- Minimizar el desgaste mecánico.
- Asegurar precisión en el control de movimiento.
- Responder eficientemente ante cargas variables.

Este diseño combina principios de **cinemática, dinámica** y **resistencia de materiales** para lograr un sistema robusto y confiable.

---

## 1. Requerimientos de Diseño

Para asegurar que el diseño en **control de movimiento** funcione correctamente, se deben tener en cuenta varios aspectos:

- ✅ Selección adecuada del **motor** y del **mecanismo de transmisión**.
- ✅ Evaluar el comportamiento del sistema ante distintos escenarios de carga.
- ✅ Cumplir con requerimientos específicos como **costo, precisión, eficiencia energética** y **tiempo de respuesta**.

### Indicadores Clave:

- **Torque del motor:** debe ser suficiente para mover la carga, incluso en condiciones extremas. Se recomienda incluir un **margen de seguridad**.
- **Relación de inercia adecuada:** entre motor y carga para lograr una respuesta dinámica eficiente.
- **Criterios adicionales:** según las necesidades específicas del sistema (precisión, costos, tiempos de ciclo, espacio físico, etc).

### Tipos de problemas en diseño:

| Escenario | Objetivo del Diseño |
|----------|---------------------|
| **Movimiento de carga deseado** | ➜ Dimensionar la transmisión y motor. |
| **Motor y transmisión existentes** | ➜ Determinar el movimiento de carga resultante. |
| **Motor existente + movimiento deseado** | ➜ Dimensionar la transmisión. |
| **Movimiento deseado + transmisión existente** | ➜ Seleccionar el motor adecuado. |

---

## 2. Inercia y Torque Reflejado

### 🔁 Inercia Reflejada

La **inercia reflejada** es la cantidad de inercia que el motor "siente" debido a los componentes conectados a través del sistema de transmisión. Se ajusta utilizando la **relación de transmisión (N)**:

\[
J_r = J_L \cdot N^2
\]

Donde:

- \( J_r \): Inercia reflejada al eje del motor.
- \( J_L \): Inercia real de la carga.
- \( N \): Relación de transmisión (generalmente definida como \( $N=\frac{W_{motor}}{W_{carga}}$ \)).

---

### 🔁 Torque Reflejado

El **torque reflejado** al eje del motor se obtiene transformando el torque necesario en la carga mediante la misma relación:

\[
$T_r = \frac{T_L}{N}$
\]

Donde:

- \( T_r \): Torque reflejado al motor.
- \( T_L \): Torque de la carga.
- \( N \): Relación de transmisión.

---

## 3. Conceptos de Transmisión: Engranajes

Los engranajes son mecanismos fundamentales para modificar velocidad y torque en sistemas mecánicos. La **relación de engranajes (N)** se define por el número de dientes o diámetros:

\[
$N = \frac{Z_{conducido}}{Z_{conductor}} = \frac{D_{conducido}}{D_{conductor}}$
\]

Donde:

- \( Z \): Número de dientes.
- \( D \): Diámetro del engranaje.

### 📉 Efectos de la relación de engranajes:

- **Reducción de velocidad (N > 1):**
  - El engranaje conducido es mayor.
  - Aumenta el torque, disminuye la velocidad.

- **Aumento de velocidad (N < 1):**
  - El engranaje conducido es más pequeño.
  - Disminuye el torque, aumenta la velocidad.

- **Relación 1:1 (N = 1):**
  - Ambos engranajes tienen el mismo tamaño.
  - No hay cambio en velocidad ni en torque.

---

### 3.1. Eficiencia

La **eficiencia en el control de movimiento** está relacionada con la capacidad del sistema de realizar movimientos precisos con el menor consumo energético posible.

#### Factores que afectan la eficiencia:

- **Transmisión de Energía:**
  - Utilizar mecanismos de baja fricción.
  - Diseños con juegos y holguras mínimas.

- **Control de Torque y Velocidad:**
  - Implementar algoritmos PID o controladores avanzados.
  - Relación de inercia óptima.

- **Reducción de pérdidas:**
  - Selección de motores eficientes.
  - Evitar sobrecargas y funcionamiento fuera del rango nominal.

- **Perfil de Movimiento:**
  - Aceleraciones suaves.
  - Control de trayectoria e interpolación.

- **Sensores y Realimentación:**
  - Uso de sensores de alta resolución.
  - Retroalimentación en tiempo real para corrección dinámica.

---

### 3.2. Inercia Total

La **inercia total** es la suma de todas las inercias reflejadas al eje del motor:

\[
$J_{total} = J_{motor} + J_{transmision} + J_{carga\_reflejada}$
\]

Donde:

- \( J_{motor} \): Inercia del rotor del motor.
- \( J_{transmision} \): Inercia de engranajes, poleas, correas, etc.
- \( $J_{carga\_reflejada} = J_{carga} \cdot N^2 \$)

### ⚙ Importancia:

- Afecta la aceleración del sistema.
- Influye en la selección del motor.
- Mejora la estabilidad y respuesta dinámica.

---

### 3.3. Relación de Inercia

Define el **equilibrio dinámico** entre la inercia del motor y la inercia reflejada de la carga:

\[
Relación\ de\ $Inercia = \frac{J_{carga\_reflejada}}{J_{motor}}$
\]

#### Casos prácticos:

- **Relación baja (1-2):**
  - Alta respuesta dinámica.
  - Puede requerir un motor grande (mayor costo).

- **Relación alta (>10):**
  - Útil en movimientos lentos o estables.
  - Menor eficiencia y riesgo de bajo torque.

Un diseño eficiente requiere mantener esta relación dentro de un rango adecuado para la aplicación.

---

## 4. Sistema de Transmisión Polea-Correa

El sistema de **polea y correa** es común en transmisiones mecánicas por su **simplicidad, bajo costo** y capacidad para conectar ejes distantes.

### ✅ Ventajas:

- Bajo nivel de ruido.
- Alineación flexible.
- Absorción de vibraciones.

### ❌ Desventajas:

- Pérdidas por deslizamiento.
- Requiere mantenimiento (tensión, cambio de correa).
- Menor eficiencia comparado con engranajes.

---

### 4.1. Relación de Transmisión

Se calcula como:

\[
$i = \frac{D_{conducida}}{D_{motriz}} = \frac{N_{motriz}}{N_{conducida}}$
\]

O también:

\[
$i = \frac{Velocidad_{motriz}}{Velocidad_{conducida}}$
\]

---

### 4.2. Inercia Reflejada

En una transmisión por polea-correa, la **inercia reflejada al eje del motor** se calcula como:

\[
$J_{ref} = J_{carga} \cdot i^2$
\]

Donde:

- \( J_{carga} \): Inercia real de la carga.
- \( i \): Relación de transmisión.

---

### 4.3. Torque de Carga

El torque que debe entregar el motor se ve afectado por la relación de transmisión y la eficiencia del sistema:

\[
$T_{motor} = \frac{T_{carga}}{i \cdot n}$
\]

Donde:

- \( T_{motor} \): Torque requerido por el motor.
- \( T_{carga} \): Torque de la carga.
- \( i \): Relación de transmisión.
- \( n \): Eficiencia del sistema.

---

## 🧠 Nota Final sobre Sensores

Un **sensor** es un dispositivo que detecta variaciones en una magnitud física (temperatura, presión, luz, etc.) y las convierte en señales eléctricas. Son fundamentales en sistemas de control de movimiento porque:

- Permiten **realimentación precisa**.
- Mejoran la eficiencia y exactitud.
- Aumentan la seguridad del sistema.

---
