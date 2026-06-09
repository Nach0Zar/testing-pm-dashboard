

# **Examia**

# 

# 

# 

# 

# 

# **Specification Document \- V2.0.0**

# 

# 

# Problem Statement

Actualmente, la creación, administración y corrección de los primeros parciales de la materia “Testing de Aplicaciones” en UADE requiere un alto esfuerzo manual por parte del docente, especialmente cuando existen múltiples cursadas, temas de examen y respuestas abiertas o semiestructuradas. Esto genera carga operativa, dificultad para reutilizar exámenes, demoras en la devolución de notas y falta de trazabilidad homogénea sobre el proceso de corrección.

# Propósito y Objetivo

Se busca optimizar este proceso mediante una plataforma que permita al docente crear y reutilizar exámenes, administrar cursos y alumnos, recibir entregas digitales, obtener una pre-corrección asistida por IA y publicar la nota final solo luego de su revisión y aprobación explícita. El objetivo es el de optimizar tiempos de entrega a partir del asistente IA, facilitar el proceso de corrección a partir de entregas en formato digital y optimizar la gestión de cursadas, temas y preguntas.

# Requerimientos

Funcional (F)		No funcional (NF)		Seguridad/entorno (S)

## Requerimientos del Docente 

### Gestión de Cursos y Alumnos 

* **P-F-01:** El profesor debe poder crear y administrar múltiples cursos, identificándolos con nombre, descripción, turno, período académico y código de cursada.  
* **P-F-02**: El profesor debe poder cargar el listado de alumnos por curso, incluyendo datos mínimos de identificación (nombre, apellido, legajo, mail institucional y nota del examen, la cual en caso de no haberse asignado aún debe figurar como “-”).  
* **P-F-03:** El sistema debe permitir al profesor visualizar el estado de cada alumno dentro de un examen (sin iniciar, en curso y enviado).

### Creación y Configuración de Exámenes

* **P-F-04:** El profesor debe poder crear y guardar plantillas de examen con distintos tipos de preguntas.  
* **P-F-05:** El profesor debe poder asignar a las preguntas un sistema de puntuación, partiendo de preguntas entre 1, 2 o 3 puntos.  
* **P-F-06:** El profesor debe crear plantillas de exámenes cuya sumatoria de puntos sea igual a 10 (diez) puntos.  
* **P-F-07:** El profesor debe poder crear preguntas dentro de una plantilla en formato de pregunta-respuesta en texto libre.  
* **P-F-08:** El profesor debe poder crear preguntas dentro de una plantilla en formato de tablas a partir de un enunciado detallado del caso.  
* **P-F-09:** El profesor debe poder crear preguntas dentro de una plantilla en formato de árboles de decisión a partir de un enunciado detallado del caso.  
* **P-F-10:** El profesor debe poder crear preguntas de tipo múltiple choice, definiendo el enunciado, las opciones de respuesta (mínimo 2, máximo 5\) e indicando cuál o cuáles son las correctas, sin que esta información sea visible para el alumno.  
* **P-F-11:** El profesor debe poder agrupar un ejercicio en formato de árboles de decisión y otro de tabla de decisión si se desea que compartan el mismo enunciado que detalla el caso.  
* **P-F-12:** El profesor debe poder organizar las preguntas en temas, pudiendo asignar a un parcial para un curso particular como mínimo 1 tema y máximo 5\.  
* **P-F-13:** El profesor debe poder cargar las respuestas correctas o criterios de corrección para cada pregunta, sin que sean visibles para los alumnos en ningún momento.  
* **P-F-14:** El profesor debe poder reutilizar exámenes ya creados, duplicándolos y modificándolos para nuevas instancias.  
* **P-F-15:** El profesor debe poder configurar uno o más turnos de examen, definiendo fecha, horario de inicio y horario de cierre del envío, con una duración máxima de 4 horas corridas.  
* **P-F-16:** El profesor debe poder extender el horario de cierre del envío, con un máximo de 30 minutos.  
* **P-F-17:** El sistema debe generar automáticamente un link único de acceso por turno de examen y temas, que el profesor pueda distribuir a sus alumnos, en formato de QR o Código alfanumérico a ingresar dentro de la plataforma.

### Corrección y Devolución 

* **P-F-18:** El sistema debe ofrecer una pre-corrección automática asistida por IA que sugiera una nota por respuesta a partir de una ponderación de criterios, con justificación para cada calificación sugerida, y la nota final sugerida, siendo esta la sumatoria de cada pregunta.  
* **P-F-19:** El profesor debe poder aceptar la nota sugerida por la IA o editarla, generando una versión editable de la pre-corrección automática sin perder el registro original.  
* **P-F-20:** El profesor debe poder agregar comentarios o devoluciones escritas por pregunta o a nivel general del examen, antes de publicar la calificación final.  
* **P-F-21:** Al confirmar la corrección, el sistema debe notificar automáticamente al alumno con su nota y la devolución correspondiente.  
* **P-F-22:** Luego de confirmada la corrección, el profesor debe poder observar en la lista de alumnos la nota correspondiente a cada uno.  
* **P-F-23:** Ante eventualidades, el profesor debe poder cancelar la pre-corrección y cargado de notas ante la necesidad de recurrir al formato de exámen físico.  
* **P-F-24:** El profesor debe poder cargar, por alumno, un archivo PDF correspondiente al examen escrito de forma manual. Este archivo quedará almacenado en la plataforma únicamente como respaldo del parcial físico, sin ser procesado por el asistente de IA ni estar sujeto a corrección dentro del sistema.  
* **P-NF-01:** La interfaz de corrección debe permitir visualizar la respuesta del alumno y la respuesta correcta en forma comparada, en una misma pantalla, junto a la nota estimada por la pre-corrección automática y su corrección.  
* **P-NF-02:** La interfaz de corrección debe permitir visualizar si la entrega del alumno contiene la etiqueta “Entrega Parcial”, lo que implica que la entrega final no se realizó, independientemente de su origen.

### Monitoreo y Métricas

* **P-F-25:**El sistema debe proveer al profesor un dashboard de monitoreo por alumno y por examen, que incluya como mínimo las siguientes métricas:  
  * Cantidad de veces que el alumno salió de la pantalla del examen (pérdida de foco)  
  * Tiempo total fuera de la pantalla del examen  
  * Hora exacta de inicio del examen  
  * Hora exacta de envío (manual o automático)  
  * Tiempo total activo dentro del examen  
  * Cantidad de autoguardados registrados (entregas parciales)  
  * Indicador de si el envío fue manual (submit del alumno) o automático (por vencimiento de tiempo)  
  * Porcentaje de preguntas respondidas al momento del envío  
* **P-NF-03:** El dashboard debe permitir filtrar métricas por curso, turno de examen y alumno individual, y debe ser accesible una vez finalizado el turno.  
* **P-NF-04:** El dashboard debe presentar la información de forma visual (gráficos y tablas), permitiendo identificar rápidamente comportamientos atípicos durante el examen.


### Usabilidad y Acceso

* **P-NF-05:** El sistema debe ser accesible desde navegadores modernos sin necesidad de instalar software adicional en la computadora del profesor.  
* **P-NF-06:** Las acciones frecuentes (crear examen, ver correcciones pendientes, publicar notas) deben estar disponibles en un máximo de 3 (tres) clics desde el inicio de sesión.  
* **P-NF-07:** La interfaz debe ofrecer feedback constante sobre las acciones, notificando tanto las acciones realizadas exitosamente como las fallas en el sistema y peticiones incorrectas el docente (Por ejemplo, creación exitosa de un tema debe informar que esta fue creada exitosamente de manera clara al docente, o intentar crear un examen sin preguntas debe dar aviso al profesor de manera clara).

## Requerimientos del Estudiante 

### Acceso al Examen 

* **A-F-01:** El alumno debe poder acceder al examen mediante un link único, desde su propia computadora.  
* **A-F-02:** El sistema debe identificar al alumno al ingresar al link, solicitando datos mínimos de verificación (mail y contraseña de UADE).  
* **A-S-01:** Al iniciar el examen, la plataforma debe activar un modo bloqueado que impida al alumno navegar a otros sitios web, abrir otras aplicaciones o pestañas, o acceder al escritorio del sistema operativo durante la sesión.  
* **A-S-02:** Si el alumno intenta salir del entorno bloqueado, el sistema debe emitir una advertencia y registrar el intento, notificando al profesor.  
* **A-S-03:** El acceso al examen debe estar restringido por la ventana horaria configurada por el profesor; fuera de ese rango, el link no debe permitir el ingreso.  
* **A-S-04:** El acceso al examen debe estar restringido al alumnado del curso asociado al examen. El link no debe permitir el ingreso a externos a este listado.

### Resolución del Examen 

* **A-F-03:** El alumno debe poder responder preguntas de texto libre mediante un editor que soporte escritura digital con formato básico, con un máximo de 2500 palabras por respuesta.  
* **A-F-04:** El alumno debe poder completar preguntas que involucren tablas, ingresando datos celda por celda.  
* **A-F-05:** El alumno debe poder construir árboles de decisión mediante herramientas visuales interactivas (arrastrar, conectar nodos, etiquetar ramas).  
* **A-F-06:** El alumno debe poder responder preguntas de tipo múltiple choice seleccionando una o más opciones según lo configurado por el profesor.  
* **A-F-07:** El alumno debe poder ser advertido cuando el tiempo restante sea de 30 (treinta) minutos.  
* **A-F-08:** El alumno debe poder ser advertido una segunda vez cuando el tiempo restante sea de 15 (quince) minutos.  
* **A-NF-01:** El sistema debe guardar automáticamente las respuestas del alumno cada cierto intervalo (máximo cada 60 segundos) para evitar pérdida de datos ante fallos de conexión o cierre accidental. Estas respuestas deben ser almacenadas con una etiqueta de “Entrega parcial”.  
* **A-NF-02:** El alumno debe visualizar en todo momento un contador regresivo con el tiempo restante del examen.

### Envío y Resultados

* **A-F-09:** El alumno debe poder enviar el examen mediante un botón de envío explícito, con un paso de confirmación previo para evitar envíos accidentales.  
* **A-F-10:** Al vencer el tiempo configurado, el sistema debe enviar automáticamente el examen con las respuestas cargadas hasta ese momento.  
* **A-F-11:** El alumno debe recibir una notificación (por email o dentro de la plataforma) cuando el profesor publique su nota y devolución.  
* **A-F-12:** El alumno debe poder consultar su nota final y la devolución del profesor desde un área personal de la plataforma, en cualquier momento posterior a la publicación.

## Requerimientos del Sistema 

### Seguridad e integridad

* **S-S-01:** Toda la comunicación entre el cliente y el servidor debe estar cifrada mediante HTTPS/TLS.  
* **S-S-02:** Las respuestas correctas y los criterios de corrección cargados por el profesor no deben ser accesibles ni visibles para los alumnos, ni a través de la interfaz ni mediante herramientas de inspección del navegador.  
* **S-S-03**: El sistema debe registrar un log de actividad por alumno durante el examen (inicio, envíos parciales, intentos de salida del entorno, submit final) con marca de tiempo.  
* **S-S-04:** El acceso a funciones de administración y corrección debe estar protegido por autenticación de profesor, con soporte para inicio de sesión seguro (usuario y contraseña o SSO institucional).

### Rendimiento y Disponibilidad 

* **S-NF-1:** El sistema debe soportar el acceso concurrente de todos los alumnos de un curso durante un turno de examen sin degradación perceptible del rendimiento.  
* **S-NF-02:** La plataforma debe funcionar correctamente en los navegadores de escritorio más utilizados (Chrome, Firefox, Edge) en sus versiones actuales.  
* **S-NF-03:** El tiempo de carga inicial de la plataforma no debe superar los 5 segundos en condiciones normales de conectividad universitaria.  
* **S-NF-04:** El sistema debe almacenar la información en una infraestructura cloud para evitar pérdida de disponibilidad en momentos claves.

# Fuera del alcance

* **Bloqueo total del sistema operativo del alumno**  
   El producto no impedirá abrir otras aplicaciones, cambiar de escritorio o navegar fuera del navegador. Solo podrá registrar eventos detectables desde la web, como pérdida de foco, cambio de pestaña o salida de pantalla completa.  
* **Integración obligatoria con SSO institucional de UADE**  
   Para el producto, el acceso podrá resolverse mediante link único, mail institucional, legajo o código de acceso. La integración con SSO puede quedar como mejora futura.  
* **Corrección perfecta o determinística por IA**  
   La IA brindará una sugerencia basada en criterios cargados por el docente, pero no se garantizará equivalencia total con una corrección humana.  
* **Generación automática completa de exámenes por IA**  
   El producto permite crear, reutilizar y modificar exámenes, pero no generar exámenes completos automáticamente.  
* **Editor visual avanzado para árboles de decisión**  
   Para el MVP puede limitarse a una versión simplificada, por ejemplo carga textual/estructurada o imagen adjunta. Un editor drag-and-drop completo podría quedar para una iteración posterior.  
* **Soporte mobile completo para rendir exámenes**  
   El sistema debería priorizar navegadores de escritorio modernos, como ya aparece en los requerimientos no funcionales .  
* **Múltiples materias o uso institucional generalizado**  
   El alcance inicial está limitado a la materia “Testing de Aplicaciones” y al primer parcial.  
* **Analítica avanzada de desempeño académico**  
   Reportes complejos, comparativas históricas, dashboards por tema, dificultad de preguntas o evolución por cursada pueden quedar fuera del MVP.  
* **Mecanismos antifraude avanzados**  
   No se incluyen reconocimiento facial, grabación de pantalla, monitoreo con cámara, detección biométrica ni proctoring avanzado.  
* **Carga de exámenes físicos en el sistema**   
  No se incluirá la carga manual de notas ante cancelación de exámenes de cualquier índole.  
* **Gestión de presencialidad**  
  El sistema no gestionará la presencialidad del alumno en el exámen, centrándose en la evaluación.  
* **Corrección o modificación de notas post confirmación del profesor**  
  El sistema no permitirá la revisión y modificación de un examen que ya fue cargado por el profesor.

## Supuestos

* **SUP-01 — Identidad del alumno:** Se asume que el alumno que realiza el examen es el mismo que ingresó con las credenciales institucionales (mail y contraseña UADE). El sistema no implementa verificación biométrica ni reconocimiento facial. La autenticidad de la identidad queda bajo responsabilidad de la institución y la supervisión presencial del docente.  
* **SUP-02 — Asignación correcta de tema por fila:** Se asume que, al momento de indicar qué tema corresponde a cada fila de alumnos, el docente comunica correctamente la asignación y los alumnos ingresan al link o código del tema que les fue indicado. El sistema no valida que el alumno esté sentado en la fila correcta.  
* **SUP-03 — Conectividad mínima garantizada:** Se asume que los alumnos cuentan con conectividad a internet suficiente para acceder y operar la plataforma durante toda la duración del examen. La institución debe garantizar disponibilidad de red en el aula.  
* **SUP-04 — Equipamiento propio del alumno:** Se asume que cada alumno dispone de una computadora personal en condiciones operativas el día del examen. El sistema no contempla gestión de equipos compartidos ni situaciones de fallo de hardware.  
* **SUP-05 — Supervisión presencial del docente:** Se asume que el docente o un ayudante está presente físicamente durante el examen para intervenir ante situaciones que el sistema no puede controlar, como el uso de celulares, comunicación entre alumnos o suplantación de identidad.  
* **SUP-06 — Validez de las credenciales UADE:** Se asume que los alumnos tienen activas sus credenciales institucionales (mail y contraseña UADE) al momento del examen y que estas son personales e intransferibles.  
* **SUP-07 — Criterios de corrección suficientemente detallados:** Se asume que el docente carga criterios de corrección lo suficientemente claros y completos para que el asistente de IA pueda generar sugerencias de nota con utilidad real. Una carga incompleta o ambigua impactará directamente en la calidad de la pre-corrección.  
* **SUP-08 — Uso honesto del entorno bloqueado:** Se asume que el bloqueo a nivel de navegador actúa como disuasivo suficiente para el contexto de examen presencial. No se garantiza que un alumno con conocimientos técnicos avanzados no pueda evadir el control; la supervisión presencial complementa esta limitación.  
* **SUP-09 — Exámenes PDF son legibles:** Para el caso de la carga de exámenes escritos en formato PDF (P-F-23), se asume que el docente es responsable de que los archivos cargados sean legibles y correspondan al alumno indicado. El sistema no valida el contenido del PDF.