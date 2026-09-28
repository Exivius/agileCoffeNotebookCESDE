# Historias de Usuario

## *Epica 1: Creación del login y gestión de acceso*
### *Feacture 1: Gestión de identidad y Autenticación*

#### *US-01*
- *Descripción:* Como estudiante de CESDE, quiero registrarme utilizando mi correo electrónico o credenciales de Google,para crear mi cuenta rápidamente y acceder a los servicios de compra.
##### Criterios de aceptación:
1. El usuario puede ingresar al modulo de registro
2. El sistema solicita un correo valido
3. El sistema valida que la contraseña sea mayor a 8 caracteres y que contenga minimo una mayuscula, un numero y un caracter especial
4. El sistema muestra un mensaje de confirmación cuando el registro fue exitoso
5. El usuario se crea en la base de datos
6. El sistema valida que el usuario no exista o ya este registrado
##### Tareas:
1. *Front* se encarga del diseño de la pagina para el registro la cual debe contener los campos de registro y botones de confirmación, limpieza o rechazar el registro
2. *Back* se encarga de la logica para la validación del usuario existente o creación del nuevo usuario y guardado en base de datos

#### *US-04*  
- *Descripción:* Como usuario de la aplicación, quiero disponer de un método para recuperar mi contraseña, para restablecer el acceso a mi cuenta en caso de olvidarla.  
##### Criterios de aceptación:
1. El usuario puede presionar "¿Olvidaste tu contraseña?" en el login.
2. El sistema pide el correo registrado y valida que exista.
3. El sistema genera y envía por correo electronico un código temporal para permitir el cambio de contraseña.
4. El sistema guarda la nueva contraseña actualizada.
##### Tareas:
1. *Front:* Crear la pantalla de solicitud de recuperación, validación de codigo de seguridad y la pantalla para ingresar la nueva contraseña.
2. *Back:* Crear servicio que envie el código por coreo y realice la validación y permita actualice la clave en la tabla de usuarios.

#### *US-01.1*
- *Descripción:* Como usuario, quiero poder iniciar sesión en el sistema con mis credenciales, para acceder a la plataforma.
##### Criterios de aceptación:
1. El usuario puede ingresar al login de la aplicación
2. El sistema valida que el correo exista
3. el sistema valida el perfil para cargar los modulos permitidos
4. El sistema valida que la contraseña sea correcta
5. El sistema muestra un error al usuario si al loguearse, no coindicen los datos con los guardados en las bases de datos
##### Tareas:
1. *Front* se encarga de la visual del login para que muestre los campos de usuario y contraseña, el boton para enviar la información y tooltips que muestren si el correo no tiene el formato necesario o la cotraseña es mejor el minimo de caracteres permitido2.  *Back* se encarga de la logica para validar el usuario que intenta ingresar y que perfil tiene asignado en la base de datos. Luego de estas validaciones, determina que interfaz es la que se puede cargar de acuerdo al perfil

### *Feacture 2: Administración de Perfiles y Roles*

##### *US-02*
- *Descripción:* Como administrador del sistema, quiero que la aplicación verifique automáticamente si el estado de un usuario es activo o inactivo, para garantizar que solo las personas autorizadas puedan acceder a la plataforma.
##### Criterios de aceptación:
1. Si un usuario tiene estado inactivo, el sistema no le permite iniciar sesión.
2. Si un usuario tiene estado activo, el sistema le permite iniciar sesión.
3. El sistema muestra un mensaje indicando que la cuenta se encuentra deshabilitada o suspendida.
4. El administrador puede cambiar el estado de un usuario (activo/inactivo) desde su panel.
##### Tareas:
1. *Front:* Mostrar alertas informativa en el login cuando el servicio devuelva que el usuario está inactivo y una de bienvenido para el usuario activo.
2. *Back:* Agregar el campo estado (activo/inactivo) en la tabla usuarios y validar esta bandera antes de permitir el inicio de la sesión.

#### *US-03*
- *Descripción:* Como administrador del sistema, quiero que a cada usuario se le asigne un perfil específico (usuario/admin) al iniciar sesión, para mostrarle únicamente las interfaces y permisos correspondientes a su rol.
##### Criterios de aceptación:
1. Si el super admin crea la cuenta, este le puede asignar el tipo de usuario que desee
2. Si el usuario crea la cuenta desde el portal de registro, el sistema debe activar automaticamente el perfil de usuario
##### Tareas:
1. *Back* se encarga de la logica que asigna los perfiles y sus permisos a cada tipo de usuario.
2. *Back* se debe de crear logica que asigne perfil de usuario si el usuario se crea desde la web de inicio.
3. *Back* se encarga de crear los niveles de seguridad por perfiles de usuario conectando el acceso en modulos a los que se les brinde permiso.
4. *Front* se encarga de la visual que permite crear usuarios y contraseñas, y la asignación o modificacion del perfil a su dispocisión el boton para enviar la información y tooltips que muestren si el correo no tiene el formato necesario o la cotraseña es mejor el minimo de caracteres permitido

## **Épica 2: Consulta de establecimientos y portal del sitio**

  **Feature 1: Portal y Navegación de Comercios**  
  * **US-05:** Como estudiante de CESDE, quiero seleccionar los establecimientos disponibles, para elegir en cuál de ellos deseo realizar mi compra.
  #### Criterios de aceptación:
  1. Visualización correcta del menú mostrando los diferentes establecimientos aliados a la aplicación, con el nombre del establecimiento y una breve descripción de los productos ofertados.
  2. Al seleccionar el establecimiento por medio de un click, se ingresa al portal del establecimiento
  #### Tareas:
  1. Front se encarga del diseño HTML/CSS del menú para seleccionar el establecimiento una vez el login del usuario es exitoso.
  2. Back se encargara de que se cargue desde la base de datos de forma correcta la información por cada establecimiento una vez el loguin del usuario es exitoso. Ademas, que al hacer click sobre un establecimiento, el sistema cargue el portal del establecimiento mostrando correctamente los productos y servicios ofertados.
  * **US-08:** Como estudiante de CESDE, quiero navegar en la interfaz del establecimiento de modo que pueda visualizar cada producto, su descripción y que sea identificable en qué establecimiento estoy comprando.  
  #### Criterios de aceptación:
  1. Se puede hacer scroll up/down sin ningun error
  Se pueden visualizar correctamente en una lista o por paginas dentro de la misma interfaz los productos ofertados.
  2. Cada producto ofertado debera mostrar la descripción del producto, una imagen de referencia y el precio.
  3. cada producto debe tener en la parte inferior del contenedor los botones para aumentar o disminuir la cantidad del producto, ademas de un boton para agregar el producto al carrito de compras.
  4. Debera existir un boton que premita regresar al menú de establecimientos.
  5. Debe existir un boton que permita la visualización del carrito de compras el cual al activar el evento, carga el modulo del carrito de compras.
  6. Debe existir un boton para finalizar la compra el cual lleva a la pantalla de la orden.
  #### Tareas:
  1. Fron se encarga del diseño funcional y dinamico de la aplicación, permitiendo la correcta visualización desde cualquier pantalla y disponsitivo, implementando contenedores para los diferentes productos y botones claros que indiquen al usuario las acciones a realizar.
  2. Back se encarga de la logica que permite cargar la información de cada producto y que los botones dentro de esta pantalla comuniquen a los modulos correspondientes.
  * **US-06:** Como administrador, quiero modificar las imágenes de referencia y las descripciones, para mantener la información de los establecimientos actualizada en la aplicación.  
  #### Criterios de aceptación:
  1. el administrador puede ingresar a un modo de edición para cada uno de los productos registrados.
  2. El administrador puede modificar las descripciones y precios en los productos.
  3. El administrador puede remover productos del menú poniendolos inactivos de modo que no se muestren de cada al usuario.
  4. El administrador puede eliminar definitivamente un producto del menú
  5. El administrador puede agregar nuevos productos desde una pantalla que le solicitara cargar una imagen de referencia e ingresar los datos necesarios para la publicación del mismo
  #### Tareas:
  1. Front se encargara de la creación de un nuevo portal o modo edición para solamente los productos que se presentan en el menú del establecimiento, mostrando claramente que campos son editables y requeridos.
  2. Back se encarga de la validación de los datos, tanto para el guardado en la base de datos como para garantizar que solo un usuario con permisos pueda realizar ediciones sobre los productos ya publicados. Validara que la totalidad de los datos requeridos sean ingresados antes de realizar el guardado.
* **Feature 2: Sistema de Feedback General**  
  * **US-07:** Como estudiante de CESDE, quiero calificar el establecimiento, para compartir mi opinión sobre el servicio ofrecido.
  #### Criterios de aceptación:
  1. Dónde se visualiza el menú del establecimiento, debera existir un boton de califación el cual se comunique con un modulo especial.
  2. El modulo de califación debera cargar por defecto el nombre del establecimiento.
  3. El modulo muestra campos para ingresar un titulo, una descripción de la calificación, y varios items a calificar como la atención, variedad de productos los cuales tendran un sistema de calificación por estrellas.
  #### Tareas

## *Épica 3: Consulta de productos y procesamiento de pagos*
### *Feature 1: Catálogo Virtual y Carrito de Compras* 

#### *US-09:*
- *Descripción:* Como estudiante de CESDE, quiero ver un menú de productos, para conocer los artículos que están disponibles en el establecimiento seleccionado.
##### Criterios de aceptación:
1. Se listan los productos del local con su nombre, precio y disponibilidad.
2. Si un producto no tiene stock, aparece como "Agotado" y no se puede añadir.
##### Tareas:
1. 
  * *US-12:* Como estudiante de CESDE, quiero visualizar el detalle de cada producto, para asegurarme de sus características antes de agregarlo al pedido.  
  * *US-10:* Como estudiante de CESDE, quiero seleccionar los productos y las cantidades que deseo comprar, para ir armando mi pedido según mis necesidades.
### *Feature 2: Módulo de Checkout y Pasarela de Pagos*  
  * *US-14:* Como estudiante de CESDE, quiero realizar pagos por medio de la aplicación, seleccionando el método de pago preferido y que esté disponible.  
  * *US-14.1 (Nueva):* Como equipo de desarrollo, necesitamos integrar y configurar pasarelas de pago, para que las transacciones realizadas en el carrito de compras se procesen de manera segura.

### **Épica 4: Entrega, monitoreo y paneles de administración**

* **Feature 1: Seguimiento de Pedidos y Turnos**  
  * **US-04.1 (Nueva):** Como estudiante de CESDE, quiero que se me asigne un turno tras mi compra, para organizar mi tiempo de espera.  
  * **US-04.2 (Nueva):** Como estudiante de CESDE, quiero recibir alertas y notificaciones sobre el estado de mi pedido, para acercarme a recogerlo exactamente cuando esté listo.  
* **Feature 2: Dashboard Administrativo y Métricas**  
  * **US-11:** Como administrador, quiero realizar modificaciones en tiempo real de los precios y productos, para mantener el inventario y los costos al día sin afectar las compras actuales.  
  * **US-15:** Como administrador del sistema, quiero visualizar paneles con métricas clave de uso y transacciones, para tomar decisiones informadas sobre el rendimiento y la operatividad de la plataforma. Estas métricas deben incluir los productos vendidos, montos recaudados y métodos de pago utilizados.  
  * **US-16:** Como administrador del sistema, quiero habilitar o deshabilitar módulos y funcionalidades de forma dinámica, para gestionar el alcance de la aplicación sin interrumpir el servicio general.  
  * **US-13:** Como estudiante de CESDE, quiero calificar los productos adquiridos, para dejar una referencia sobre la calidad de la comida o artículos.

### **Épica 5: Infraestructura técnica y despliegue**

* **Feature 1: Distribución Móvil**  
  * **US-17:** Como estudiante de CESDE, quiero descargar e instalar la aplicación fácilmente desde tiendas virtuales oficiales (Google Play Store, App Store), para acceder a los servicios directamente desde mi dispositivo móvil.  
  * **US-17.1 (Nueva \- Tarea Técnica):** Como administrador del proyecto, necesito gestionar la contratación de los servicios en las plataformas virtuales, para posibilitar la subida y descarga de la app en los sistemas operativos celulares.  
* **Feature 2: Arquitectura y Persistencia de Datos**


**US-18.1**
- **Descripción:** Como equipo de desarrollo, necesitamos crear y configurar un servicio de almacenamiento en la nube, para alojar las bases de datos de forma centralizada y segura.
##### Criterios de aceptación:
1. Modelo entidad relación creado y aprobado
2. Base de datos cumpliendo con estandares de normalización
##### Tareas:
1. El equipo de infraestructura se encarga de la compra del servidor que contenga la base de datos y los administradores de bases de datos proceden a la creación de la base de datos de acuerdo al modelo entidad relación aprobado por el negocio