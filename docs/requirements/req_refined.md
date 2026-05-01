IA: Gemini



Miembros: Martín Zehnder, Nicolás Crispín Santucci



1\. Ambigüedades en Datos Personales

Sexo (Checkbox): Un checkbox es un elemento binario (activado/desactivado). Si el sexo es binario (Masculino/Femenino), ¿qué estado representa el "check" vacío? Además, si el CUIT depende del sexo, se requiere un valor definido. Sugerencia: Usar Radio Buttons o un Desplegable.



Formato de Nombre y Apellido: No se especifican límites de caracteres (mínimo/máximo) ni si se permiten caracteres especiales, tildes o números.



Fecha de Nacimiento: Se menciona "de 1940 en adelante", pero ¿cuál es el límite superior? ¿Puede ser una fecha futura? ¿Puede ser la fecha de hoy? (Un beneficiario podría ser un recién nacido).



Número de Documento: No se especifica si es solo numérico o alfanumérico (crucial para documentos extranjeros como PAS o CE). Tampoco se define la longitud.



Cuit: Se dice que se "autogenera" si es DNI. Pero, ¿es editable si el usuario quiere corregirlo? Si el tipo de documento no es DNI, el campo "deja de ser obligatorio", pero ¿sigue siendo visible? ¿Se puede cargar manualmente?



2\. Ambigüedades en Domicilio

Piso: No se aclara si es obligatorio (la mayoría de las casas no tienen piso).



País: Se pide como campo obligatorio, pero no se listan los valores posibles. ¿Es un texto libre o un desplegable?



Código Postal: ¿Es alfanumérico (como en Reino Unido o el nuevo sistema de Argentina) o solo numérico? ¿Qué longitud debe tener?



Localidad y Provincia: ¿Están vinculadas? (Ej: que al elegir una provincia solo se muestren sus localidades).



3\. Lógica del "Porcentaje de Beneficio" (El punto más crítico)

Esta sección presenta la mayor complejidad para los casos de prueba:



Suma del 100%: Si el sistema debe sumar siempre 100%, ¿cómo se comporta al cargar el primer beneficiario? ¿Se le asigna 100% por defecto?



Edición de terceros: Se menciona que "se debe habilitar la edición del porcentaje de esos beneficiarios" (los ya existentes).



¿Esta edición ocurre en la misma pantalla de alta?



¿Qué pasa si al intentar ajustar los porcentajes para que den 100, el usuario deja una suma de 90 o 110 y presiona guardar?



Mínimos: El porcentaje no debe ser 0. ¿Pero puede ser 0.5%? ¿Cuántos decimales se permiten?



4\. Reglas de Negocio y Persistencia

Autocompletado y Bloqueo: Si una persona ya existe y los campos se bloquean: ¿Qué pasa si los datos existentes en el sistema están desactualizados (ej. cambió su estado civil)? ¿Hay algún botón de "Editar datos básicos" o el bloqueo es absoluto?



Validaciones de Error: Se menciona "mostrar un mensaje de error". ¿Es un mensaje general arriba de la pantalla o un mensaje específico por cada campo inválido?



Condición de IVA: El alta de un beneficiario en un seguro de vida personal no suele requerir Condición de IVA (es un dato más propio de facturación o autónomos). ¿Es realmente obligatorio para todos los casos?



5\. Estados del Sistema

Buscador y Botón: Se menciona que el botón de alta aparece según si la cuenta está activa, suspendida o de baja.



¿Qué sucede si el usuario logra acceder a la URL de alta directamente por fuera del flujo del botón? ¿El sistema debe validar el estado de la cuenta nuevamente en el backend?



¿Existe un límite máximo de beneficiarios permitidos por cuenta?

