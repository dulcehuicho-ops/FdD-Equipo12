# Equipo 12 - Fundamentos de Diseño
### Carrera de Ingeniería Ambiental / Informática / Industrial  
**Universidad Peruana Cayetano Heredia**

---

## 🌍 Descripción del Equipo  
Somos el **Equipo 12** del curso Fundamentos de Diseño 2026-1, conformado por estudiantes de Ingeniería Ambiental / Informática / Industrial. Nuestro objetivo es desarrollar soluciones tecnológicas aplicadas a la gestión segura y eficiente del agua en el hogar.

## 🎯 Introducción
El acceso y la calidad del agua en viviendas que utilizan tanques de almacenamiento es un aspecto crítico para la salud pública. En Lima Metropolitana, estos sistemas son ampliamente utilizados, pero suelen carecer de monitoreo adecuado, lo que permite la acumulación de contaminantes que no son visibles a simple vista. Esto hace que la población consuma agua en mal estado sin darse cuenta, detectándolo recién cuando ya se han producido efectos en la salud. Además, la falta de control en el llenado de los tanques puede generar desperdicio de agua. En este contexto, se plantea la necesidad de un sistema inteligente que permita supervisar la calidad del agua en tiempo real y optimizar su uso.

## ⚠️ Problemática  

En comunidades rurales donde el acceso al agua potable es gestionado por las Juntas Administradoras de Servicios de Saneamiento (JASS), se identifican dos problemáticas principales:

### 1. Deficiente desinfección del agua  
- La dosificación de cloro se realiza de manera manual y empírica.  
- No se garantiza una concentración adecuada de cloro residual (mínimo 0.5 mg/L).  
- Se han evidenciado niveles bajos o nulos de cloro en sistemas de abastecimiento.  
- Existe mayor riesgo de proliferación de microorganismos y enfermedades en la población.  

### 2. Falta de monitoreo de la calidad del agua  
- No se controlan parámetros clave como el pH y la turbidez.  
- Se pueden presentar valores fuera de los rangos adecuados para consumo humano.  
- La detección de problemas en la calidad del agua no es oportuna.  
- Se limita la capacidad de respuesta ante fallas en el sistema de abastecimiento.
  
## Problema integrador  
En muchas comunidades rurales, el acceso al agua potable es gestionado por las Juntas Administradoras de Servicios de Saneamiento (JASS), las cuales se encargan del almacenamiento y distribución del recurso hídrico mediante tanques cisterna. Sin embargo, en estos sistemas no siempre se cuenta con mecanismos adecuados para la dosificación controlada de cloro ni con herramientas de monitoreo continuo de la calidad del agua.  

Esta situación puede generar una desinfección ineficiente, la proliferación de microorganismos y la posible presencia de contaminantes, afectando la calidad del agua y representando un riesgo para la salud pública. Además, la falta de control técnico limita una gestión eficiente y sostenible del recurso hídrico en estas comunidades.
 
## Presentación de la solución  
Se propone el **diseño e implementación de un sistema de dosificación de cloro en tanques cisterna para el tratamiento de agua potable dirigido a comunidades rurales gestionadas por Juntas Administradoras de Servicios de Saneamiento (JASS)**.  

Este sistema integrará sensores para el monitoreo de parámetros como el pH, la turbidez y nivel del agua junto con un mecanismo automatizado de dosificación de cloro, permitiendo mantener niveles adecuados de desinfección en sistemas de abastecimiento comunitario.  

Asimismo, contará con un sistema de alertas que facilite a los operadores de la JASS el control oportuno de la calidad del agua, contribuyendo a mejorar la salud pública, prevenir enfermedades y fortalecer la gestión comunitaria del recurso hídrico en zonas rurales.

## El sistema sigue los pasos:

🔹Monitoreo de nivel del tanque:
El sistema inicia con la medición del nivel de agua, mediante un sensor que determina la cantidad de agua almacenada en el tanque. Esta información permite conocer el volumen disponible y evitar errores en la dosificación, como operar sin agua o sobredosificar.

🔹Monitoreo de calidad del agua:
El sistema analiza la calidad del agua mediante sensores de:
- pH (condición química del agua)
  El sistema verifica el nivel de acidez o alcalinidad del agua.
Para que la desinfección con cloro sea eficaz, se considera que el pH debe ser menor a 8, ya que en ese rango el cloro mantiene una mayor eficiencia desinfectante.
- Turbidez (presencia de partículas o suciedad)
  Permite identificar contaminación visible o carga de sólidos en el agua. Y este deberá ser menor de 5 unidades nefelométricas de turbiedad (UNT). 
Estos parámetros permiten determinar si el agua es apta, está en estado de alerta o no es apta para consumo, evaluando cambios en tiempo real.

🔹Procesamiento y control (Arduino):
Toda la información de los sensores es enviada a un Arduino, que procesa los datos y toma decisiones automáticas según las condiciones del sistema:
- Evalúa la calidad del agua
- Verifica el nivel del tanque
- Determina si se requiere dosificación de cloro o generación de alerta
- Considera el rango de pH adecuado para una desinfección eficiente
  
🔹Dosificación automática de cloro:
Si las condiciones lo requieren, el Arduino activa una bomba dosificadora, que aplica cloro en cantidades controladas. La dosificación se ajusta según el volumen de agua disponible en el tanque, asegurando una desinfección eficiente sin sobredosificación.

🔹Sistema de alertas:
El sistema genera alertas automáticas cuando detecta:
- pH
  🟢 Normal: 6.5 – 8.0
  🟡 Alerta: 8.0 – 8.5 (disminuye la eficiencia del cloro)
  🔴 Crítico: < 6.5 o > 8.5 (riesgo para consumo y desinfección ineficiente)
- Turbidez
  🟢 Normal: ≤ 5 NTU
  🔴 Crítico: > 5 NTU (alta presencia de partículas o contaminación)
  Alta turbidez reduce la efectividad del cloro porque protege microorganismos.

## 🎯 Objetivos de Desarrollo Sostenible

🚰 ODS 6: Agua limpia y saneamiento  
El proyecto se alinea con este objetivo porque busca garantizar que el agua almacenada en tanques domésticos sea segura para el consumo humano. A través del monitoreo continuo de la calidad del agua, el sistema permite detectar contaminantes que no son visibles a simple vista, evitando que las personas utilicen agua en mal estado sin saberlo. Además, el sistema emite alertas cuando la calidad del agua no es adecuada, lo que permite tomar acciones inmediatas como la limpieza o mantenimiento del tanque. De esta manera, se mejora la gestión del recurso hídrico en el hogar, se reduce el riesgo de consumo de agua contaminada y se promueve un uso más responsable y seguro del agua potable.

❤️ ODS 3: Salud y bienestar  
Este objetivo se relaciona directamente con la prevención de enfermedades asociadas al consumo de agua contaminada. En el contexto del Perú, el uso de agua almacenada sin control puede contribuir a enfermedades gastrointestinales y otras afecciones relacionadas con la mala calidad del agua, e incluso agravar condiciones sanitarias en el entorno. El sistema propuesto actúa como un mecanismo de alerta temprana, ya que detecta cambios en la calidad del agua antes de que estos generen daños en la salud de las personas. Asimismo, al indicar cuándo es necesario realizar mantenimiento o limpieza del tanque, ayuda a prevenir la acumulación de bacterias y contaminantes. En conjunto, esto permite proteger la salud de los usuarios y mejorar su calidad de vida mediante la reducción de riesgos sanitarios prevenibles.

## 📸 Fotografía del Equipo  
<p align="center">
<img width="1408" height="768" alt="imagen_alumnos_IA" src="Recursos/Imágenes/imagen grupal .jpeg" />
  <em>Figura 1. Fotografía del equipo 12</em>
</p>

---

## 👥 Integrantes del Equipo  

| Foto | Nombre | Rol | Intereses |
|------|--------|-----|-----------|
| <img src="/Recursos/Imágenes/60885051.jpg" width="90"/> | **Ariana Cortéz** | Líder del equipo | Innovación social, sostenibilidad. |
| <img src="/Recursos/Imágenes/Luis.jpeg" width="90"/> | **Luis Huaccha** | Responsable de investigación | Gestión ambiental, desarrollo comunitario. |
| <img src="Recursos/Imágenes/70589968.jpg" width="90"/> | **Dulce Huicho** | Diseñadora | Diseño de prototipos, creatividad visual y enfoque ambiental. |
| <img src="/Recursos/Imágenes/claudiana.jpeg" width="90"/> | **Claudiana Pineda** | Encargada de documentación | Comunicación científica, redacción técnica. |
| <img src="/Recursos/Imágenes/renato.jpeg" width="90"/> | **Giacomo Jimenez** | Programador - Modelador | Programación, análisis de datos, simulación. |

---

## 📌 Resumen Final  
Este README describe de manera clara la identidad del equipo, sus motivaciones y los Objetivos de Desarrollo Sostenible (ODS) en los que se centrará el trabajo a lo largo del curso. 
