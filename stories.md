

# 

# 

# 

# 

# **Examia**

# 

# 

# 

# 

# 

# **Historias de Usuario \- V3.0.0**

# 

# Épica: Autenticación y Control de Acceso

Descripción de la Épica: Como usuario del sistema (Docente o Estudiante), quiero contar con un mecanismo de identificación y validación de credenciales para acceder de forma segura a las funciones correspondientes a mi rol, garantizando la integridad de los datos del examen.

## Historias de Usuario para Iniciar Sesión y Registrarse

#### **US-01: Login del Docente con credenciales propias**

**Como** Profesor de la materia Testing de Aplicaciones  
**Quiero** iniciar sesión con mi mail y contraseña de docente  
**Para** acceder al panel de administración, creación de exámenes y corrección.

Criterios de aceptación

* El sistema debe permitir al docente iniciar sesión con mail y contraseña válidos.  
* El sistema debe redirigir al Dashboard principal del docente luego del login exitoso.  
* El sistema debe registrar la sesión del docente correctamente.  
* El sistema debe denegar el acceso si el mail o la contraseña son incorrectos.  
* El sistema debe mostrar el mensaje: “Credenciales inválidas. Por favor, intente nuevamente.”  
* El sistema no debe revelar cuál de los campos ingresados es incorrecto.

#### **US-02: Login del Docente con usuario UADE**

**Como** Profesor de la materia Testing de Aplicaciones  
**Quiero** iniciar sesión con mi usuario institucional UADE  
**Para** acceder a la plataforma sin necesidad de una cuenta separada.

Criterios de aceptación

* El sistema debe redirigir al docente a /auth/uade-login al presionar “Ingresar con usuario UADE”.  
* El sistema debe permitir el acceso con credenciales institucionales válidas.  
* El sistema debe redirigir al Dashboard principal del docente luego del login exitoso.  
* El sistema debe denegar el acceso si las credenciales UADE son inválidas.  
* El sistema debe mostrar el mensaje: “Credenciales inválidas. Por favor, verificá tu mail y contraseña institucional.”

#### **US-03: Login del Alumno con credenciales propias**

**Como** Alumno cursante de la materia  
**Quiero** iniciar sesión con mi mail y contraseña registrados en la plataforma  
**Para** acceder a mi espacio personal y consultar mis exámenes y correcciones.

Criterios de aceptación

* El sistema debe permitir al alumno iniciar sesión con credenciales válidas.  
* El sistema debe redirigir al alumno a /alumno/mis-examenes luego del login exitoso.  
* El sistema debe mostrar el listado de exámenes rendidos del alumno.  
* El sistema debe denegar el acceso si las credenciales son incorrectas.  
* El sistema debe mostrar el mensaje: “Credenciales inválidas. Por favor, intente nuevamente.”  
* El sistema no debe indicar cuál de los campos es incorrecto.

#### **US-04: Login del Alumno con usuario UADE**

**Como** Alumno cursante de la materia  
**Quiero** iniciar sesión con mi usuario institucional UADE  
**Para** acceder a mi espacio personal sin necesidad de una cuenta separada.

Criterios de aceptación

* El sistema debe redirigir al alumno a /auth/uade-login al seleccionar “Ingresar con usuario UADE”.  
* El sistema debe permitir el acceso con credenciales institucionales válidas.  
* El sistema debe redirigir al alumno a /alumno/mis-examenes.  
* El sistema debe denegar el acceso si las credenciales institucionales son inválidas.  
* El sistema debe mostrar el mensaje: “Credenciales inválidas. Por favor, verificá tu mail y contraseña institucional.”

#### **US-05: Acceso del Alumno al Examen mediante link o código**

**Como** Alumno cursante de la materia  
**Quiero** ingresar al examen mediante el link o código provisto por el profesor  
**Para** habilitar el entorno de resolución digital de mi parcial.

Criterios de aceptación

* El sistema debe permitir el acceso al examen si el alumno pertenece al curso y se encuentra dentro del horario habilitado.  
* El sistema debe activar el modo bloqueado al iniciar el examen.  
* El sistema debe habilitar el entorno de examen correctamente.  
* El sistema debe actualizar el estado del alumno a “En curso” en el panel del docente.  
* El sistema debe validar que el alumno pertenezca al listado oficial del curso.  
* El sistema debe denegar el acceso si el alumno no pertenece al curso.  
* El sistema debe mostrar el mensaje: “No tenés acceso a este examen. Verificá que estés usando el link correcto o consultá con tu docente.”  
* El sistema debe bloquear el acceso fuera de la ventana horaria configurada.  
* El sistema debe mostrar el mensaje: “El examen no está disponible en este horario.”

#### **US-06: Selección Manual de Tema por el Alumno antes del Inicio**

**Como** Alumno ingresando a rendir el parcial

**Quiero** seleccionar el tema del examen de entre las opciones disponibles y poder modificarlo antes de comenzar

**Para** asegurar que estoy rindiendo la versión del examen que me fue asignada por el docente.

Criterios de aceptación

* El sistema debe mostrar la lista de temas disponibles para el examen según la configuración definida por el docente.  
* El sistema debe permitir seleccionar un único tema antes de iniciar el examen.  
* El sistema debe mostrar una confirmación visual indicando el tema seleccionado.  
* El botón "Comenzar Examen" debe permanecer deshabilitado hasta que el alumno seleccione un tema.  
* El sistema debe permitir modificar el tema seleccionado antes de comenzar el examen.  
* El sistema debe actualizar la confirmación visual cuando el alumno cambie de tema.  
* El sistema debe cargar las preguntas correspondientes al tema seleccionado al iniciar el examen.  
* El sistema debe ocultar o deshabilitar la opción de cambiar de tema una vez comenzado el examen.

#### 

#### 

#### **US-07: Recuperación de contraseña — Envío del código**

**Como** usuario registrado en la plataforma  
**Quiero** iniciar el proceso de recuperación de contraseña  
**Para** poder restablecer mi acceso en caso de olvidarla.

Criterios de aceptación

* El sistema debe redirigir al usuario a /auth/recuperar-contraseña al seleccionar “¿Olvidaste tu contraseña?”.  
* El sistema debe mostrar el mail enmascarado en el Paso 1\.  
* El sistema debe permitir solicitar el envío del código OTP.  
* El sistema debe simular el envío del código correctamente.  
* El sistema debe avanzar automáticamente al Paso 2 luego de enviar el código.

#### **US-08: Recuperación de contraseña — Validación del código OTP**

**Como** usuario que inició el proceso de recuperación de contraseña  
**Quiero** ingresar el código de 6 dígitos recibido en mi mail  
**Para** verificar mi identidad y poder establecer una nueva contraseña.

Criterios de aceptación

* El sistema debe permitir ingresar el código OTP en 6 inputs individuales.  
* El sistema debe validar correctamente el código ingresado.  
* El sistema debe avanzar al Paso 3 si el código es correcto y fue ingresado dentro de los 5 minutos.  
* El sistema debe mostrar un contador regresivo de 5 minutos.  
* El sistema debe deshabilitar los inputs cuando el tiempo expire.  
* El sistema debe mostrar el botón “Reenviar código” al finalizar el tiempo.  
* El sistema debe volver al Paso 1 al presionar “Reenviar código”.

#### **US-09: Recuperación de contraseña — Establecer nueva contraseña**

**Como** usuario que validó su identidad mediante el código OTP  
**Quiero** establecer una nueva contraseña  
**Para** recuperar el acceso a mi cuenta.

Criterios de aceptación

* El sistema debe permitir ingresar una nueva contraseña y repetirla.  
* La contraseña debe cumplir con los requisitos mínimos:  
  * mínimo 8 caracteres  
  * al menos una mayúscula  
  * al menos un número  
* El sistema debe mostrar un indicador de fortaleza de contraseña.  
* El sistema debe mostrar el indicador en verde cuando la contraseña sea válida.  
* El sistema debe habilitar el botón “Guardar contraseña” solo si ambas contraseñas coinciden y cumplen los requisitos.  
* El sistema debe redirigir al login luego de guardar la contraseña exitosamente.  
* El sistema debe mostrar un mensaje de éxito luego del cambio de contraseña.  
* El sistema debe mostrar niveles de fortaleza:  
  * débil en rojo  
  * media en naranja  
* El sistema debe deshabilitar el botón “Guardar contraseña” si la contraseña no cumple los requisitos.  
* El sistema debe mostrar un error inline si las contraseñas no coinciden.

#### **US-10: Registro de nuevo usuario**

**Como** usuario nuevo sin cuenta en la plataforma  
**Quiero** registrarme completando un formulario con mis datos personales  
**Para** crear una cuenta y acceder a las funcionalidades de la plataforma.

Criterios de aceptación

* El sistema debe permitir completar un formulario de registro con datos personales.  
* El sistema debe validar que todos los campos obligatorios estén completos.  
* El sistema debe requerir la aceptación de términos y condiciones.  
* El sistema debe crear la cuenta si los datos son válidos.  
* El sistema debe mostrar el mensaje: “¡Cuenta creada\! Revisá tu mail para verificar tu cuenta”.  
* El sistema debe ofrecer un botón “Ir al login”.  
* El sistema debe redirigir a /auth/login al presionar “Ir al login”.  
* El sistema debe validar en tiempo real la disponibilidad del nombre de usuario.  
* El sistema debe mostrar una cruz roja si el nombre de usuario ya existe.  
* El sistema debe deshabilitar el botón “Crear cuenta” si el nombre de usuario no está disponible.  
* El sistema debe validar que el mail de recupero sea distinto al mail principal.  
* El sistema debe mostrar el mensaje: “El mail de recupero debe ser distinto al mail principal.”  
* El sistema debe deshabilitar el botón “Crear cuenta” si los mails coinciden.

#### **US-11: Seguridad en el canal de comunicación**

**Como** cualquier usuario del sistema  
**Quiero** que todas mis interacciones con la plataforma viajen de forma cifrada  
**Para** garantizar que mis credenciales y datos personales no sean interceptados.

Criterios de aceptación

* El sistema debe procesar el login bajo protocolo HTTPS/TLS.  
* El sistema debe procesar el registro bajo protocolo HTTPS/TLS.  
* El sistema debe procesar el flujo de recuperación de contraseña bajo protocolo HTTPS/TLS.  
* El sistema debe cumplir con el requerimiento S-S-01 en todas las comunicaciones sensibles.

# Épica: Gestión de Cursos y Creación de Exámenes

Como Docente de la materia Testing de Aplicaciones, quiero administrar mis cursos y crear exámenes digitales para optimizar el proceso de evaluación y reducir la carga operativa manual.

## Historias de Usuario para Mis Cursos (Dashboard)

#### **US-12: Visualización del Dashboard de Mis Cursos**

**Como** Docente de la materia Testing de Aplicaciones

**Quiero** ver un resumen de mis cursos activos y exámenes recientes al ingresar a la plataforma

**Para** tener una vista general del estado de mi actividad docente sin necesidad de navegar entre secciones.

Criterios de aceptación

* El sistema debe mostrar las cards de acceso rápido: Crear examen, Correcciones pendientes y Publicar notas.  
* El sistema debe mostrar el listado de cursos activos del período actual con nombre, turno, período y cantidad de alumnos.  
* El sistema debe mostrar la tabla de exámenes recientes con nombre del examen, curso asociado, estado y cantidad de correcciones pendientes.  
* El sistema debe diferenciar visualmente el estado de cada examen: "Publicado", "Borrador" o "Activo", mediante etiquetas con color.  
* El sistema debe incluir un botón "Abrir" por cada fila de la tabla de exámenes recientes para acceder al detalle.

#### **US-13: Acceso rápido a acciones frecuentes desde el Dashboard**

**Como** Docente de la materia Testing de Aplicaciones

**Quiero** acceder a las acciones más frecuentes desde el Dashboard en un máximo de 3 clics

**Para** optimizar mi flujo de trabajo sin perder tiempo navegando por la plataforma.

Criterios de aceptación

* El sistema debe redirigir al Paso 1 de creación de examen al presionar la card "Crear examen".  
* El sistema debe redirigir a la sección de correcciones pendientes al presionar la card "Correcciones pendientes".  
* El sistema debe redirigir a la sección de publicación de notas al presionar la card "Publicar notas".  
* El sistema debe garantizar que cada una de estas acciones sea accesible en un máximo de 3 clics desde el inicio de sesión, en cumplimiento con P-NF-06.

#### **US-14: Acceso al detalle de un curso desde el Dashboard**

**Como** Docente de la materia Testing de Aplicaciones

**Quiero** ingresar al detalle de cada curso activo desde el Dashboard

**Para** visualizar el listado de alumnos y gestionar la cursada correspondiente.

Criterios de aceptación

* El sistema debe mostrar un botón "Ver curso" en cada card de curso activo.  
* El sistema debe redirigir al detalle del curso correspondiente al presionar "Ver curso".  
* El sistema debe mostrar en el detalle del curso el listado de alumnos con nombre, apellido, legajo y mail institucional.  
* El sistema debe mostrar la nota de cada alumno o el valor "-" si aún no fue asignada, en cumplimiento con P-F-02.  
* El sistema debe mostrar el estado de cada alumno en el examen: "Sin iniciar", "En curso" o "Enviado", en cumplimiento con P-F-03.

## Historias de Usuario para Crear Examen

#### **US-15: Configuración inicial del examen — Paso 1**

**Como** Docente de la materia Testing de Aplicaciones

**Quiero** completar los datos básicos del examen al iniciar su creación

**Para** identificar correctamente a qué curso, turno y período pertenece el examen.

Criterios de aceptación

* El sistema debe permitir al docente completar los campos: nombre del examen, curso, turno y período.  
* El sistema debe mostrar un stepper visual con los 3 pasos del flujo: Crear examen, Cargar respuestas y Generar acceso.  
* El sistema debe indicar en qué paso se encuentra el docente en todo momento.  
* El sistema debe habilitar la sección de carga de preguntas una vez completados los datos básicos.  
* El sistema debe mostrar el puntaje acumulado en tiempo real mediante una barra de progreso con el formato "X / 10 puntos".  
* El sistema debe deshabilitar el botón "Continuar" mientras la sumatoria de puntajes no sea exactamente 10\.  
* El sistema debe mostrar el mensaje: "La sumatoria debe ser exactamente 10 para continuar." cuando el puntaje no esté completo.

#### **US-16: Agregar preguntas de texto libre al examen**

**Como** Docente de la materia Testing de Aplicaciones

**Quiero** agregar preguntas de tipo texto libre al examen

**Para** que los alumnos puedan responder con sus propias palabras dentro de un límite de palabras definido.

Criterios de aceptación

* El sistema debe mostrar el botón "+ Agregar pregunta" debajo de cada pregunta creada y al inicio cuando el tema está vacío.  
* El sistema debe permitir seleccionar el tipo "Texto libre" al presionar "+ Agregar pregunta".  
* El sistema debe permitir al docente completar el enunciado de la pregunta.  
* El sistema debe permitir asignar un puntaje de 1, 2 o 3 puntos a la pregunta.  
* El sistema debe agregar la pregunta al tema activo y actualizar el puntaje total en tiempo real.  
* El sistema debe mostrar cada pregunta creada como un card colapsable con su número, tipo, enunciado resumido y puntaje asignado.

#### **US-17: Agregar preguntas de tabla al examen**

**Como** Docente de la materia Testing de Aplicaciones

**Quiero** agregar preguntas de tipo tabla al examen

**Para** que los alumnos puedan completar estructuras tabulares como parte de su respuesta.

Criterios de aceptación

* El sistema debe permitir seleccionar el tipo "Tabla" al presionar "+ Agregar pregunta".  
* El sistema debe permitir al docente redactar el enunciado detallado del caso.  
* El sistema debe permitir asignar un puntaje de 1, 2 o 3 puntos a la pregunta.  
* El sistema debe agregar la pregunta al tema activo y actualizar el puntaje total en tiempo real.  
* El sistema debe mostrar la pregunta como un card colapsable con su número, tipo, enunciado resumido y puntaje.

#### **US-18: Agregar preguntas de árbol de decisión al examen**

**Como** Docente de la materia Testing de Aplicaciones

**Quiero** agregar preguntas de tipo árbol de decisión al examen

**Para** que los alumnos puedan construir estructuras de decisión de forma visual como parte de su respuesta.

Criterios de aceptación

* El sistema debe permitir seleccionar el tipo "Árbol de decisión" al presionar "+ Agregar pregunta".  
* El sistema debe permitir al docente redactar el enunciado detallado del caso.  
* El sistema debe permitir asignar un puntaje de 1, 2 o 3 puntos a la pregunta.  
* El sistema debe agregar la pregunta al tema activo y actualizar el puntaje total en tiempo real.  
* El sistema debe mostrar la pregunta como un card colapsable con su número, tipo, enunciado resumido y puntaje.

#### **US-19: Agregar preguntas de múltiple choice al examen**

**Como** Docente de la materia Testing de Aplicaciones

**Quiero** agregar preguntas de tipo múltiple choice al examen

**Para** incluir consignas con opciones predefinidas donde el alumno debe seleccionar la/s correcta/s.

Criterios de aceptación

* El sistema debe permitir seleccionar el tipo "Múltiple choice" al presionar "+ Agregar pregunta".  
* El sistema debe permitir al docente redactar el enunciado de la pregunta.  
* El sistema debe permitir agregar entre 2 y 5 opciones de respuesta.  
* El sistema debe permitir marcar cuál o cuáles opciones son las correctas.  
* El sistema debe ocultar las respuestas correctas para los alumnos en todo momento, en cumplimiento con P-F-13.  
* El sistema debe permitir asignar un puntaje de 1, 2 o 3 puntos a la pregunta.  
* El sistema debe agregar la pregunta al tema activo y actualizar el puntaje total en tiempo real.

#### **US-20: Agrupar árbol de decisión y tabla bajo un mismo enunciado**

**Como** Docente de la materia Testing de Aplicaciones

**Quiero** agrupar una pregunta de árbol de decisión y una de tabla bajo un mismo enunciado de caso

**Para** evitar duplicar el enunciado cuando ambas consignas responden a la misma situación, en cumplimiento con P-F-11.

Criterios de aceptación

* El sistema debe permitir al docente vincular una pregunta de árbol de decisión y una de tabla bajo un enunciado compartido.  
* El sistema debe mostrar ambas preguntas agrupadas visualmente bajo el mismo enunciado dentro del tema activo.  
* El sistema debe contabilizar el puntaje de cada pregunta de forma independiente en el total acumulado.

#### **US-21: Organización de preguntas por temas**

**Como** Docente de la materia Testing de Aplicaciones

**Quiero** organizar las preguntas del examen en temas

**Para** diferenciar versiones del examen y asignar distintos temas a distintas filas o grupos de alumnos.

Criterios de aceptación

* El sistema debe crear automáticamente el Tema 1 al iniciar la creación del examen.  
* El sistema debe permitir agregar nuevos temas mediante el botón "+ Agregar tema".  
* El sistema debe permitir un mínimo de 1 tema y un máximo de 5 temas por examen, en cumplimiento con P-F-12.  
* El sistema debe deshabilitar el botón "+ Agregar tema" al alcanzar el límite de 5 temas.  
* El sistema debe mostrar el mensaje: "Se alcanzó el máximo de 5 temas por examen." cuando se intente superar el límite.  
* El sistema debe mostrar la cantidad de preguntas de cada tema en el tab correspondiente, por ejemplo: "Tema 1 (3)".

#### **US-22: Guardar examen como borrador**

**Como** Docente de la materia Testing de Aplicaciones

**Quiero** guardar el examen en estado borrador en cualquier momento durante su creación

**Para** poder retomar la edición posteriormente sin perder el trabajo realizado.

Criterios de aceptación

* El sistema debe permitir guardar el examen como borrador aunque la sumatoria de puntajes no sea exactamente 10\.  
* El sistema debe guardar el estado actual del examen incluyendo datos básicos, preguntas cargadas y temas creados.  
* El sistema debe mostrar el examen con el estado "Borrador" en la tabla de exámenes recientes del Dashboard.  
* El sistema debe permitir al docente retomar y editar el borrador desde el Dashboard en cualquier momento.

#### **US-23: Carga de respuestas correctas — Paso 2**

**Como** Docente de la materia Testing de Aplicaciones

**Quiero** cargar las respuestas correctas o criterios de corrección para cada pregunta del examen

**Para** que el asistente de IA pueda realizar la pre-corrección automática de las entregas de los alumnos, en cumplimiento con P-F-12 y P-F-18.

Criterios de aceptación

* El sistema debe mostrar el Paso 2 luego de que el docente presiona "Continuar" en el Paso 1 con puntaje completo.  
* El sistema debe listar todas las preguntas del examen con su enunciado visible y un campo editable para la respuesta o criterio.  
* El sistema debe permitir al docente completar la respuesta correcta o criterio de corrección para cada pregunta.  
* El sistema debe almacenar las respuestas correctas de forma oculta para los alumnos, en cumplimiento con S-S-02.  
* El sistema debe deshabilitar el botón "Continuar" si al menos una pregunta tiene el campo de respuesta vacío.  
* El sistema debe indicar visualmente qué preguntas tienen el campo de respuesta sin completar al intentar avanzar.  
* El sistema debe habilitar el botón "Continuar" únicamente cuando todas las preguntas tengan su respuesta o criterio cargado.

#### **US-24: Generación de acceso por tema — Paso 3**

**Como** Docente de la materia Testing de Aplicaciones

**Quiero** que el sistema genere automáticamente los accesos por tema del examen

**Para** distribuir a cada grupo de alumnos el código o link correspondiente a su versión del examen, en cumplimiento con P-F-17.

Criterios de aceptación

* El sistema debe generar para cada tema del examen un código QR descargable, un link único y un código alfanumérico propios e independientes.  
* El sistema debe mostrar todos los temas y sus accesos en una misma pantalla con scroll si es necesario.  
* El sistema debe incluir un botón de copiar individual para el link y el código alfanumérico de cada tema.  
* El sistema debe permitir descargar el código QR de cada tema de forma individual.  
* El sistema debe permitir al docente configurar la fecha, horario de inicio y horario de cierre del turno de examen.  
* El sistema debe validar que la duración entre el horario de inicio y cierre no supere las 4 horas corridas, en cumplimiento con P-F-15.  
* El sistema debe restringir el acceso de los alumnos únicamente dentro de la ventana horaria configurada, en cumplimiento con A-S-03.  
* El sistema debe permitir extender el horario de cierre hasta un máximo de 30 minutos adicionales sobre el horario original, en cumplimiento con P-F-16.  
* El sistema debe deshabilitar la opción de extensión una vez superado ese límite de 30 minutos.

# Épica: Entorno Digital del Estudiante y Resolución de Examen

Como Alumno de la materia, quiero resolver exámenes digitales dentro de un entorno controlado para completar y enviar mis respuestas de forma segura y confiable.

## Historias de Usuario para Resolución de Exámenes

#### **US-25: Visualización del Contador Regresivo y Guardado Automático (Entregas Parciales)**

**Como** Alumno rindiendo el examen

**Quiero** visualizar el tiempo restante en pantalla y que mis respuestas se guarden automáticamente

**Para** evitar la pérdida de datos ante fallos técnicos o cortes de conectividad.

Criterios de aceptación

* El sistema debe mostrar en todo momento un contador regresivo visible con el tiempo restante del examen desde el momento en que el alumno inicia la resolución.  
* El sistema debe guardar automáticamente las respuestas del alumno cada 60 segundos de forma continua.  
* El sistema debe persistir las respuestas guardadas automáticamente en la base de datos cloud.  
* El sistema debe asociar cada guardado automático con la etiqueta interna *"Entrega Parcial"* sin que esta sea visible para el alumno durante la resolución.  
* El sistema debe mostrar al alumno un indicador visible del último guardado automático realizado, por ejemplo: *"Guardado hace X segundos"*.

#### **US-26: Sistema de Alertas por Vencimiento de Tiempo (Regla de Fronteras)**

**Como** Alumno rindiendo el examen

**Quiero** recibir avisos emergentes cuando quede poco tiempo

**Para** administrar el cierre de mis respuestas y realizar la entrega explícita.

Criterios de aceptación

* El sistema debe mostrar un aviso en pantalla cuando el contador regresivo alcance exactamente los 30 minutos restantes.  
* El sistema debe emitir una segunda advertencia visual cuando el contador llegue a los 15 minutos restantes.  
* El sistema debe cambiar el color del contador regresivo a naranja al llegar a los 30 minutos restantes.  
* El sistema debe cambiar el color del contador regresivo a rojo al llegar a los 15 minutos restantes.  
* Las advertencias no deben interrumpir ni bloquear la edición de las respuestas del alumno.

#### **US-27: Finalización y Envío del Examen (Manual vs. Automático)**

**Como** Alumno en el entorno de resolución

**Quiero** confirmar mi entrega manualmente o que el sistema lo haga por mí al vencer el plazo

**Para** asegurar que mi parcial quede registrado y listo para ser corregido.

Criterios de aceptación

* El sistema debe mostrar un botón de envío explícito visible en todo momento durante la resolución del examen.  
* El sistema debe solicitar una confirmación explícita antes de procesar el envío manual para evitar envíos accidentales.  
* El sistema debe registrar el examen con estado *"Enviado"* y origen *"Manual"* al confirmar el envío voluntario del alumno.  
* El sistema debe bloquear la edición de todos los campos de respuesta cuando el contador regresivo llegue a 00:00:00.  
* El sistema debe recuperar la última versión guardada de las respuestas y procesar un envío automático al vencerse el tiempo.  
* El sistema debe registrar el examen con estado *"Enviado"* y origen *"Automático"* cuando el envío es disparado por vencimiento de tiempo.  
* El sistema debe actualizar el estado del alumno a *"Enviado"* en el panel del docente independientemente del origen del envío.

# 

# Épica: Corrección Asistida por IA y Publicación de Notas

Como Docente de la materia, quiero corregir y publicar exámenes digitales con asistencia de IA para agilizar el proceso de evaluación manteniendo el control pedagógico.

## Historias de Usuario para Corrección y Publicación de Notas

#### **US-28: Pre-corrección Automática Asistida por IA**

**Como** Profesor de la materia

**Quiero** que el asistente de IA analice las entregas digitales según mis criterios guardados

**Para** obtener sugerencias de notas justificadas que agilicen mi flujo operativo.

Criterios de aceptación

* El sistema debe permitir iniciar la pre-corrección una vez finalizado el examen.  
* El sistema debe analizar las respuestas abiertas utilizando los criterios configurados por el docente.  
* El sistema debe generar una nota sugerida por cada pregunta.  
* El sistema debe generar una justificación textual para cada corrección sugerida.  
* El sistema debe calcular automáticamente una nota final mediante la sumatoria de puntajes.  
* El sistema debe mostrar la información generada en la pantalla de corrección.

#### **US-29: Panel de Control y Listado de Calificaciones Consolidadas**

**Como** Profesor de la materia

**Quiero** ingresar a una lista centralizada con todas las notas (sugeridas y editadas) del examen

**Para** evaluar el rendimiento general del curso, identificar entregas pendientes y proceder con el cierre masivo de notas.

Criterios de aceptación

* El sistema debe mostrar una tabla con todos los alumnos inscriptos al examen.  
* El sistema debe visualizar el estado de entrega de cada alumno: "Entregado", "Entrega Parcial" o "Ausente".  
* El sistema debe visualizar el estado de corrección: "Pendiente", "Pre-corregido por IA" o "Revisado por Docente".  
* El sistema debe mostrar la nota sugerida por la IA.  
* El sistema debe mostrar la nota final aprobada o editada por el docente.  
* El sistema debe destacar visualmente entregas parciales o discrepancias significativas entre la nota sugerida y la nota final.  
* El sistema debe permitir acceder a la pantalla de corrección desde cada fila de alumno.

#### **US-30: Edición, Aprobación y Devolución del Docente**

**Como** Profesor de la materia

**Quiero** revisar, editar o aceptar las sugerencias de la IA e incorporar mis comentarios de devolución

**Para** mantener el control pedagógico sobre la calificación definitiva de mis alumnos.

Criterios de aceptación

* El sistema debe mostrar la respuesta del alumno y la pre-corrección de IA en pantalla dividida.  
* El sistema debe permitir editar el puntaje sugerido por la IA.  
* El sistema debe conservar el registro original generado por la IA sin sobrescribirlo.  
* El sistema debe permitir guardar una versión editada de la corrección.  
* El sistema debe destacar visualmente las entregas etiquetadas como "Entrega Parcial".

#### **US-31: Notificación de Notas y Bloqueo de Modificaciones**

**Como** Profesor de la materia

**Quiero** confirmar y publicar las notas definitivas de la cursada

**Para** que los alumnos reciban sus devoluciones y el acta local quede inmutable.

Criterios de aceptación

* El sistema debe incluir un botón "Confirmar y Publicar".  
* El sistema debe notificar automáticamente al alumno cuando la nota es publicada.  
* El sistema debe actualizar la grilla del curso con la nota final publicada.  
* El sistema debe bloquear cualquier modificación de notas luego de la publicación.  
* El sistema debe mantener el examen en estado "Publicado" una vez confirmada la operación.

#### **US-32: Plan de Contingencia por Cancelación (Carga de Respaldo PDF)**

**Como** Profesor de la materia

**Quiero** cancelar el proceso digital del examen ante eventualidades técnicas y subir un PDF de respaldo

**Para** recurrir al examen en formato físico sin perder trazabilidad del parcial.

Criterios de aceptación

* El sistema debe permitir cancelar la pre-corrección digital del examen.  
* El sistema debe habilitar la carga de archivos PDF por alumno luego de la cancelación.  
* El sistema debe almacenar los archivos PDF exclusivamente como respaldo en infraestructura cloud.  
* El sistema no debe aplicar OCR ni procesamiento de IA sobre los archivos PDF cargados.  
* El sistema debe permitir identificar las entregas cargadas como respaldo manual.

# 

# Épica: Monitoreo y Auditoría Antifraude Web

Como Docente de la materia, quiero monitorear la actividad de los alumnos durante el examen para detectar comportamientos sospechosos y preservar la integridad académica.

## Historias de Usuario para Monitoreo y Auditoría

#### **US-33: Monitoreo de Eventos en Tiempo Real (Log de Pérdida de Foco)**

**Como** Sistema de Monitoreo

**Quiero** registrar las acciones y cambios de estado del navegador del alumno durante la sesión

**Para** compilar un registro de auditoría que mitigue riesgos de copia en el aula presencial.

Criterios de aceptación

* El sistema debe detectar cambios de pestaña, minimización del navegador o apertura de ventanas externas.  
* El sistema debe registrar cada evento con marca de tiempo precisa.  
* El sistema debe incrementar la métrica de "Pérdida de foco" por cada evento detectado.  
* El sistema debe emitir una advertencia visual al alumno cuando ocurra una pérdida de foco.  
* El sistema debe almacenar todos los eventos en el log de actividad del examen.

#### **US-34: Dashboard Analítico Post-Examen para el Docente**

**Como** Profesor de la materia

**Quiero** acceder a un panel visual de métricas con filtros por curso, turno y alumno una vez concluida la fecha

**Para** evaluar el rendimiento técnico e identificar comportamientos atípicos durante el parcial.

Criterios de aceptación

* El dashboard debe permanecer bloqueado mientras el examen esté en curso.  
* El sistema debe habilitar el acceso al dashboard una vez finalizado el examen.  
* El sistema debe mostrar gráficos y tablas interactivas con las métricas del examen.  
* El sistema debe visualizar las siguientes métricas obligatorias:  
  * Cantidad de pérdidas de foco.  
  * Tiempo acumulado fuera del examen.  
  * Hora de inicio.  
  * Hora de envío.  
  * Tiempo activo.  
  * Cantidad de autoguardados.  
  * Tipo de envío.  
  * Porcentaje completado.  
* El sistema debe permitir filtrar información por curso, turno y alumno.

