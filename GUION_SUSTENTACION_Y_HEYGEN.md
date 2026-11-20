# Sustentación de práctica profesional · 10 minutos

**Expositor:** Darío Esteban Gómez Ordóñez · C.C. 1080900179  
**Programa:** Ingeniería de Sistemas · Universidad CESMAG  
**Escenario:** Sistemas Palacios IPT · Área de Proyectos TI  
**Tutor empresarial:** Ing. Juan David Achicanoy Masinsoy  
**Periodo:** 5 de agosto – 20 de noviembre de 2026 · 320 horas  
**Sustentación:** 26 de noviembre de 2026

La exposición utiliza 11 diapositivas. El texto hablado es una base para ensayar con tus propias palabras; los tiempos incluyen cambios de pantalla, pausas y breves interacciones. El recorrido animado y las capturas son recursos de explicación, no una demostración conectada a producción.

## Abrir y presentar

Abre `index.html` en Chrome o Edge. Conserva la carpeta `assets` junto al archivo: contiene las imágenes y las fuentes. La presentación funciona sin conexión y no necesita arrancar la web, el gateway ni la app.

- **F** o **F11:** pantalla completa.
- **→, ↓, Espacio o AvPág:** avanzar. **←, ↑ o RePág:** retroceder.
- **Inicio / Fin:** primera / última diapositiva.
- **N:** abrir o cerrar las notas rápidas. Son visibles en la pantalla compartida; ciérralas durante la exposición.
- **G:** abrir el mapa de diapositivas para ir directamente a un tema.
- **Clic o Enter en una captura:** ampliar. **Esc:** cerrar la imagen o el mapa.
- **Tab / Mayús + Tab:** recorrer los controles. Espacio y Enter mantienen su función al estar sobre un botón.
- **Mover el ratón:** mostrar las flechas discretas de la esquina inferior derecha.

Al salir de la diapositiva se detienen el recorrido automático del teléfono y la animación del proceso. Para cambiar de diapositiva con el teclado después de usar una pestaña, haz clic en una zona vacía o usa las flechas de la esquina.

## Plan de tiempo

1. **Portada:** 0:00–0:30 · 30 s.
2. **Problema y objetivo:** 0:30–1:30 · 60 s.
3. **Recorrido de la práctica:** 1:30–2:30 · 60 s.
4. **Arquitectura:** 2:30–3:45 · 75 s.
5. **Aplicación móvil:** 3:45–5:15 · 90 s.
6. **Ubicación y correcciones:** 5:15–6:15 · 60 s.
7. **Recorrido ilustrado:** 6:15–7:10 · 55 s.
8. **Portal web y roles:** 7:10–8:25 · 75 s.
9. **Calidad y operación:** 8:25–9:10 · 45 s.
10. **Aprendizajes y recomendaciones:** 9:10–9:50 · 40 s.
11. **Cierre:** 9:50–10:00 · 10 s.

**Total: 600 segundos.** Las preguntas quedan después del cierre. Si falta tiempo, omite las ampliaciones de imágenes y las pestañas secundarias; conserva el objetivo, la explicación de los productos y la conclusión.

## Guion para ensayar

### 1. Portada · 0:00–0:30

Buenos días. Soy Darío Esteban Gómez Ordóñez, estudiante de Ingeniería de Sistemas de la Universidad CESMAG. Presento los resultados de mi práctica profesional en el área de Proyectos TI de Sistemas Palacios IPT. El proyecto principal fue Oportunidades de Venta SP: una solución para capturar, revisar y seguir solicitudes de internet mediante una aplicación móvil, un portal web y servicios de backend. La práctica comprende 320 horas, entre agosto y noviembre de 2026.

**Transición:** primero, el problema que dio origen al proyecto.

### 2. El problema y el objetivo · 0:30–1:30

Sistemas Palacios IPT presta servicios de internet en Nariño. En el proceso inicial, los asesores enviaban la información del cliente por WhatsApp y Coordinación la consolidaba manualmente en Excel. Eso dificultaba saber qué datos faltaban, quién estaba atendiendo cada caso y en qué estado se encontraba una corrección.

El objetivo fue digitalizar esa gestión: guiar la captura, validar los datos y permitir que el responsable revisara, aprobara o devolviera una solicitud con instrucciones claras. El historial debía acompañar el proceso, para que la información no dependiera de conversaciones separadas.

El resultado es una base común para trabajar entre roles. No presento una reducción porcentual de tiempos o errores porque ese impacto requiere una medición durante la operación.

**Transición:** el alcance fue creciendo en cuatro etapas.

### 3. Recorrido de la práctica · 1:30–2:30

En agosto realicé la inducción, la capacitación inicial y un CRUD de validación. Después trabajé en los requisitos, las historias de usuario y el modelo de datos.

En septiembre desarrollé los servicios, los contratos de API, las reglas del negocio y las migraciones. En octubre conecté los clientes web y móvil e incorporé mapas, actualizaciones por eventos y notificaciones.

En noviembre el trabajo se concentró en el portal público, Contact Center, la autenticación corporativa y la documentación de entrega. La distribución fue de 72, 94, 92 y 62 horas: 320 en total.

Además desarrollé Ruta Segura Pasto, un simulador vial en Godot para la Semana de Seguridad y Salud en el Trabajo, mientras se resolvían dependencias de integración del proyecto principal.

**Transición:** para sostener ese crecimiento, separé las responsabilidades de la solución.

### 4. Arquitectura · 2:30–3:45

**Interacción:** selecciona **Solicitudes** y luego **Tiempo real**. Amplía el anexo solo si el jurado lo pide.

La web Angular y la app Flutter utilizan un gateway como entrada común. Detrás de él se distribuyen las responsabilidades: autenticación, solicitudes, catálogos, sedes, notificaciones, integración con SP e indicadores.

El núcleo es la gestión de solicitudes. Allí se controlan las validaciones, los estados, las devoluciones y el historial. La base de datos utiliza PostgreSQL, con datos organizados por dominio y migraciones versionadas con Flyway.

Para comunicar los cambios se registra un evento junto con la operación del negocio mediante el patrón Outbox. Ese evento permite actualizar las bandejas y generar los avisos correspondientes.

La autenticación de SP Sales se adaptó al servicio corporativo que suministró la empresa. La identidad inicial fue provisional. Esta evolución también mostró la importancia de acordar contratos antes de integrar componentes desarrollados por equipos distintos.

**Transición:** así se traduce la arquitectura en la experiencia del asesor.

### 5. Aplicación móvil · 3:45–5:15

**Interacción:** muestra **Acceso por correo**, **Ubicación** y **Revisión y envío**. Usa el visor manual para explicar a tu ritmo; el recorrido automático es opcional.

La aplicación móvil acompaña al asesor en campo. Mantiene la identidad visual de la empresa y comprueba la sesión antes de cargar la información. El acceso vigente es por correo y contraseña; cuando la cuenta tiene segundo factor habilitado, también solicita el código de verificación.

Desde el inicio se accede a una nueva solicitud y a las correcciones pendientes. El formulario tiene cuatro pasos: datos, ubicación, servicio y revisión. Las cinco opciones que se ven aquí corresponden a capturas del producto; no son cinco pasos del formulario.

La ubicación reúne departamento, municipio, sector y dirección. El mapa ayuda a identificar el lugar de instalación y exige confirmar el punto que se quiere utilizar. Antes de enviar, el resumen permite revisar los datos del cliente, la ubicación y el plan elegido.

El propósito es que el asesor detecte un dato incompleto antes de radicar y tenga una instrucción concreta si después recibe una devolución.

**Transición:** dos decisiones de esta captura merecen una explicación adicional.

### 6. Ubicación y correcciones en campo · 5:15–6:15

La primera es separar la lectura del GPS del punto de instalación. El GPS indica dónde y con qué precisión se hizo la captura; el pin permite señalar dónde se instalará el servicio. Ajustar ese pin no debe alterar la lectura original.

La segunda es dirigir las correcciones. Cuando una solicitud se devuelve, la cuenta responsable ve el motivo y la instrucción, y solo puede editar los campos habilitados para ese caso. Así se conserva el control sobre los datos que ya fueron revisados.

El detalle permite consultar los estados y los avisos asociados. En Android también se incorporaron notificaciones push mediante Firebase Cloud Messaging, cuyo funcionamiento en el ambiente final depende de la configuración y de los permisos del dispositivo.

**Transición:** el siguiente esquema reúne ese recorrido completo.

### 7. Recorrido ilustrado · 6:15–7:10

**Interacción:** pulsa **Ilustrar recorrido** una vez. La animación dura unos segundos y no realiza llamadas a servicios.

El asesor captura y confirma los datos. El servidor aplica las reglas y guarda la solicitud. Después, el evento actualiza la bandeja autorizada. Coordinación revisa el caso y decide si lo aprueba o lo devuelve para corregir. Finalmente, el responsable consulta el resultado y recibe los avisos.

Dentro de ese flujo hay tres controles: detectar posibles duplicados, conservar el historial de las decisiones y separar la integración con el proveedor externo. La detección de duplicados no reemplaza la revisión humana. En las pruebas, los envíos a SP permanecen deshabilitados y se utilizan dobles controlados.

**Transición:** en la web, cada rol participa de una forma diferente.

### 8. Portal web y roles · 7:10–8:25

**Interacción:** muestra **Bandeja**, **Comparador** y **Contact Center**. Reserva Detalle, Cliente, Sedes, Empleados y Tema oscuro para preguntas.

Coordinación cuenta con una bandeja para filtrar, revisar y seguir las solicitudes. El detalle reúne datos, alertas e historial. El comparador presenta solicitudes relacionadas y resalta sus diferencias sin modificar los registros.

También existe un portal público para que un cliente solicite internet sin iniciar sesión. Esas solicitudes siguen un circuito diferente: llegan a Contact Center, donde una cuenta toma el caso de manera exclusiva, lo revisa y solicita su envío a SP cuando corresponde. Coordinación puede consultarlas en solo lectura.

Administración gestiona empleados, correos de acceso, roles, contraseñas y estado de las cuentas. La web también contempla sedes y funciones de captura para los perfiles autorizados. La idea es que cada persona tenga las acciones necesarias para su trabajo, con permisos comprobados en el servidor.

**Transición:** además de las pantallas, la entrega necesita evidencia técnica y validación operativa.

### 9. Calidad y puesta en operación · 8:25–9:10

Se implementaron validaciones, permisos por rol, historial y cierre de sesión en el servidor. La verificación combina pruebas de lógica, integración e interfaz, utilizando cuentas ficticias y servicios aislados.

La puesta en operación requiere otra comprobación: desplegar la autenticación actualizada, validar HTTPS, Maps y WebSocket en el dominio final, y completar la firma y publicación de Android. Estas actividades se coordinan con los responsables del ambiente. Por eso, la entrega incluye código, pruebas y documentación, sin confundir el desarrollo de una función con su validación final en producción.

**Antes del ensayo final:** actualiza el estado de estos pendientes con el tutor; la versión de esta presentación conserva el corte de revisión del 19 de noviembre de 2026.

### 10. Aprendizajes y recomendaciones · 9:10–9:50

El aprendizaje principal fue que integrar exige acordar responsabilidades, probar los contratos y dejar decisiones documentadas. El simulador de SST también me permitió adaptarme a una necesidad distinta de la empresa.

A Sistemas Palacios recomiendo mantener la validación del ambiente final y el seguimiento de errores. A la Universidad, reforzar las prácticas de integración, pruebas y seguridad. A los próximos practicantes, acordar prioridades con el tutor, documentar desde el inicio y conservar evidencia de lo que funciona.

### 11. Cierre · 9:50–10:00

Gracias a Sistemas Palacios IPT, a mi tutor empresarial y a la Universidad CESMAG por el acompañamiento. Quedo atento a sus preguntas.

## Preparación y posibles preguntas

- Ensaya con cronómetro. Llegar a la diapositiva 8 cerca de 7:10 te deja margen para concluir.
- Lleva la carpeta completa en el equipo de presentación y comprueba las fuentes y las imágenes sin internet.
- No abras cuentas reales ni introduzcas contraseñas durante la sustentación. Las capturas existentes permiten explicar el producto sin depender del ambiente.
- Si piden una demostración conectada, hazla después de los diez minutos y solo en un ambiente de prueba previamente validado.
- Conserva los anexos del informe para ampliar arquitectura, integración y evidencia. No necesitas leerlos durante la exposición.

**¿Qué desarrollaste tú y qué suministró la empresa?** Describe los clientes, los servicios y la integración que implementaste. Reconoce que la empresa suministró el servicio corporativo de autenticación y que el despliegue se coordina con sus responsables.

**¿Cómo sabes que mejora el proceso?** Explica qué controles incorpora frente al proceso manual. Distingue esa mejora funcional de un impacto cuantitativo, que requiere medición operativa.

**¿Por qué separar GPS y punto de instalación?** Porque la posición de quien toma los datos puede no coincidir con el lugar que requiere el servicio; ambas evidencias tienen usos distintos.

**¿Por qué no puede cualquier cuenta corregir un caso?** La devolución corresponde a la cuenta responsable y a campos concretos, con comprobaciones del lado del servidor.

**¿Ya está todo publicado?** Responde con el estado confirmado el día de la sustentación. No presentes Google Play, la integración SP o la autenticación de producción como concluidos sin comprobarlo con el responsable.

## Video / HeyGen opcional · fuera de los diez minutos

No es necesario generar un video para utilizar esta presentación. Si se prepara después, este guion breve sirve como base; el montaje debe usar las capturas reales y diferenciar un esquema animado de una demostración conectada.

**Texto base:**

Oportunidades de Venta SP nació durante la práctica profesional en Sistemas Palacios IPT para organizar la captura, revisión y seguimiento de solicitudes de internet. El proceso inicial combinaba mensajes por WhatsApp y consolidación manual en Excel.

La solución reúne una aplicación móvil Flutter, un portal web Angular y servicios de backend. El asesor registra los datos, confirma la ubicación y revisa el resumen antes de enviar. Coordinación consulta las alertas y el historial, compara solicitudes relacionadas y devuelve únicamente los campos que requieren corrección.

El portal público permite que el cliente registre una solicitud que atiende Contact Center. La asignación exclusiva identifica a la cuenta responsable, mientras Administración gestiona empleados, roles y sedes.

La arquitectura separa el núcleo de solicitudes, los catálogos, la autenticación, los eventos y la integración externa. El trabajo se acompaña de pruebas y documentación para su continuidad. La validación del ambiente final y la publicación móvil se coordinan con los responsables de la empresa.

La práctica fortaleció mi capacidad para integrar componentes, acordar contratos y sustentar decisiones con evidencia. También incluyó Ruta Segura Pasto, un simulador vial en Godot para la Semana de Seguridad y Salud en el Trabajo.
