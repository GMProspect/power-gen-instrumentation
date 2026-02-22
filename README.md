# Confiabilidad en Instrumentación Industrial (Power Gen)
> *Mantenimiento predictivo y correctivo en entornos de alta corrosión para turbinas aeroderivadas (LM2500).*



La generación eléctrica en zonas costeras enfrenta un enemigo silencioso: la **corrosión galvánica**. Cajas de conexión (Junction Boxes) IP65 fallan prematuramente, y la humedad en sondas de vibración (Eddy Current) provoca disiparos falsos en turbinas, afectando la disponibilidad de la planta y la seguridad operativa.

## 💡 La Solución
Implementación de protocolos rigurosos de **Confiabilidad Operacional** basados en estándares API 670 y diagnósticos avanzados HART. No se trata solo de cambiar piezas, sino de asegurar la integridad de la señal desde el sensor hasta el sistema de control.

### Tecnologías & Herramientas Clave
- ✅ **Calibración de Procesos (Fluke 754)**:
    - Verificación y ajuste (Trim) de transmisores de presión **Rosemount 3051** vía HART.
    - Simulación de lazos de control 4-20mA para validación de lógica en PLC.
    - Documentación automática de "As Found / As Left" para auditorías.
- ✅ **Análisis de Vibración (Bently Nevada)**:
    - Mantenimiento y ajuste de sondas de proximidad (Proximity Probes) serie 3300.
    - Verificación de voltajes de GAP (-9V a -11V DC) y linealidad.
    - Reemplazo y sellado de Junction Boxes (JB6) con grado marino.
- ✅ **Instrumentación de Campo**:
    - Transmisores de Presión Diferencial (Manifolds 3-way/5-way).
    - Termocuplas y RTDs para monitoreo de gases de escape (EGT).
- Actuadores neumáticos y posicionadores inteligentes.

## 📂 Documentación Técnica Avanzada
Este repositorio incluye guías detalladas sobre los procedimientos exactos ejecutados en campo:
- [Guía Práctica: Calibración con Fluke 754 y Ajuste de Proximity Probes (Bently Nevada)](docs/Guia_Calibracion_Fluke_Bently.md)

## 📸 Evidencia de Campo
| Diagnóstico | Intervención |
|-------------|--------------|
| **Falla por Corrosión** | **Restauración y Sellado** |
| ![Caja Corroida](ruta/caja_corroida.jpg)<br>*Ingreso severo de humedad en JB crítica.* | ![JB Restaurada](ruta/jb_nueva.jpg)<br>*Reemplazo con terminales cerámicos y prensaestopas IP67.* |

## 🚀 Impacto
- **Disponibilidad**: Reducción de paradas no programadas por falsos contactos en instrumentación crítica.
- **Seguridad**: Detección temprana de desplazamiento axial en ejes de turbina antes de falla catastrófica.
- **Trazabilidad**: Historial técnico detallado para facilitar intervenciones futuras en turnos rotativos.

## 🔒 Nota
Este repositorio documenta procedimientos y mejores prácticas.
*Experiencia práctica aplicada en Turbinas LM2500 / TM2500.*

---
**Gustavo Matheus**
*Especialista en Instrumentación & Control*
