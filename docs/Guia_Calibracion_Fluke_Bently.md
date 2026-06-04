|# Procedimiento Técnico Avanzado: Calibración y Ajuste de Instrumentación Crítica
> *Aplicable a Turbinas Aeroderivadas LM2500 / TM2500 y Generación Offshore.*

Este documento resume los protocolos prácticos y técnicos empleados en campo para la garantía de confiabilidad (Reliability) de los instrumentos primarios de medición que alimentan al sistema de control (PLC/DCS).

---

## 1. Calibración de Transmisores Rosemount 3051 con Documentador Fluke 754
Los transmisores de presión y presión diferencial Rosemount son el estándar en la industria. Sin embargo, en ambientes corrosivos, la deriva del cero y del spam es común. 

### 1.1 Conexión y Comunicación HART
El calibrador de procesos documentador **Fluke 754** no solo mide mA, sino que actúa como un módem HART, permitiendo configurar los parámetros digitales internos de la cápsula.
- **Hookup:** Se conecta el Fluke 754 a los bornes (+) y (-) del transmisor o a través del bloque de terminales. *Importante:* Se requiere una resistencia de lazo de 250 ohmios si el PLC/DCS no la tiene incorporada, para permitir que los paquetes HART (FSK de alta frecuencia) se solapen sobre la corriente continua 4-20mA.

### 1.2 Procedimiento de Ajuste (Sensor Trim & Analog Output Trim)
1. **Verificación de Cero:** Aislar el manifold y ventear a la atmósfera (Presión = 0). Si el Fluke 754 lee un valor diferente de 4.00 mA o la variable primaria (PV) no es 0, hay desviación.
2. **Sensor Trim (Ajuste Mecánico):** Usar la utilidad HART del Fluke para indicarle al sensor interno que la presión física actual es exactamente 0.00.
3. **Analog Output Trim (Ajuste Eléctrico D/A):** Forzar el lazo desde el Fluke a que emita 4mA, y ajustar internamente el conversor Digital/Analógico del transmisor para que la medición del propio Fluke y la lectura del PLC coincidan exactamente, repitiendo el proceso a los 20mA.

---

## 2. Configuración y Ajuste de Proximity Probes (Bently Nevada Serie 3300/3300 XL)
Las sondas Eddy Current de Bently Nevada son vitales para monitorizar el desplazamiento radial y axial de los ejes de la turbina. Una sonda mal calibrada provoca un disparo (Trip) falso o, peor aún, oculta un roce catastrófico en el babbitt.

### 2.1 Principio de Curva de Respuesta y GAP
La sonda emite un campo magnético de radiofrecuencia. Cuando el eje de acero (Target) se acerca o aleja, la amplitud de la señal disminuye (proporcional a la distancia de Gap). La electrónica del proximitor linealiza esto a **200 mV/mil** (milésimas de pulgada).

### 2.2 Procedimiento de Ajuste (El "Gap" Mecánico)
1. **Posicionamiento Manual:** El técnico (Tú) ajusta físicamente la sonda con llaves milimétricas acercándola al eje objetivo.
2. **Medición de Voltaje DC:** Usando el multímetro (Fluke) en escala de DC, se mide el voltaje entre la salida (Out) y común (Com) del proximitor.
3. **Punto Ideal (-10 Vdc):** El objetivo estándar es fijar el gap mecánico en **-10V DC**, lo que corresponde al centro de la región lineal de la sonda (usualmente a 50 mils de distancia).
    - *Desviaciones (-9V a -11V):* En la práctica, lograr un -10.0V perfecto en la carcasa con la turbina caliente/fría depende del procedimiento; sin embargo, cualquier lectura fuera del rango de -9V a -11V podría reducir el alcance dinámico del sensor durante alta vibración armónica.

### 2.3 Solución de Falsos Disparos por Humedad
- La invasión de agua salina o condensación en las "Junction Boxes" (Cajas de Paso) cortocircuita los delicados terminales coaxiales de Bently Nevada.
- **Acción Correctiva:** Sellado con conectores termocontraíbles, cintas vulcanizantes (Scotch 23) y cajas IP67 verdaderas evita la atenuación de la señal de radiofrecuencia (RF) que viaja entre la punta de la sonda y el proximitor.
