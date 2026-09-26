# Historias de Usuario

## **Epica 1: Creación del login y gestión de acceso**
### **Feacture 1: Gestión de identidad y Autenticación**

#### **US-01**
- **Épica 1:** Creación del login y gestión de acceso
- **Prioridad:** Media
- **Estimación:** 4
- **Descripción:** Como estudiante de CESDE, quiero registrarme utilizando mi correo electrónico o credenciales de Google,para crear mi cuenta rápidamente y acceder a los servicios de compra.
##### Criterios de aceptación:
1. El usuario puede ingresar al modulo de registro
2. El sistema solicita un correo valido
3. El sistema valida que la contraseña sea mayor a 8 caracteres y que contenga minimo una mayuscula, un numero y un caracter especial
4. El sistema muestra un mensaje de confirmación cuando el registro fue exitoso
5. El usuario se crea en la base de datos
6. El sistema valida que el usuario no exista o ya este registrado
##### Tareas:
1. Front se encarga del diseño de la pagina para el registro la cual debe contener los campos de registro y botones de confirmación, limpieza o rechazar el registro
2. Back se encarga de la logica para la validación del usuario existente o creación del nuevo usuario y guardado en base de datos

#### **US-04**  
- **Épica:** Creación del login y gestión de acceso  
- **Prioridad:** Baja  
- **Estimación:** 3  
- **Descripción:** Como usuario de la aplicación, quiero disponer de un método para recuperar mi contraseña, para restablecer el acceso a mi cuenta en caso de olvidarla.  
##### Criterios de aceptación:
1. El usuario puede presionar "¿Olvidaste tu contraseña?" en el login.
2. El sistema pide el correo registrado y valida que exista.
3. El sistema genera y envía por correo electronico un código temporal para permitir el cambio de contraseña.
4. El sistema guarda la nueva contraseña actualizada.
##### Tareas:
1. **Front:** Crear la pantalla de solicitud de recuperación, validación de codigo de seguridad y la pantalla para ingresar la nueva contraseña.
2. **Back:** Crear servicio que envie el código por coreo y realice la validación y permita actualice la clave en la tabla de usuarios.

#### **US-01.1**
- **Épica:** Creación del login y gestión de acceso
- **Prioridad:** Baja
- **Estimación:** 3
- **Descripción:** Como usuario, quiero poder iniciar sesión en el sistema con mis credenciales, para acceder a la plataforma.
##### Criterios de aceptación:
1. El usuario puede ingresar al login de la aplicación
2. El sistema valida que el correo exista
3. el sistema valida el perfil para cargar los modulos permitidos
4. El sistema valida que la contraseña sea correcta
5. El sistema muestra un error al usuario si al loguearse, no coindicen los datos con los guardados en las bases de datos
##### Tareas:
1. Front se encarga de la visual del login para que muestre los campos de usuario y contraseña, el boton para enviar la información y tooltips que muestren si el correo no tiene el formato necesario o la cotraseña es mejor el minimo de caracteres permitido
2.  Back se encarga de la logica para validar el usuario que intenta ingresar y que perfil tiene asignado en la base de datos. Luego de estas validaciones, determina que interfaz es la que se puede cargar de acuerdo al perfil

#### **US-03**
- **Épica:** Administración de Perfiles y Roles
- **Prioridad:** Media
- **Estimación:** 3
- **Descripción:** Como administrador del sistema, quiero que a cada usuario se le asigne un perfil específico (usuario/admin) al iniciar sesión, para mostrarle únicamente las interfaces y permisos correspondientes a su rol.
##### Criterios de aceptación:
1. Si el super admin crea la cuenta, este le puede asignar el tipo de usuario que desee
2. Si el usuario crea la cuenta desde el portal de registro, el sistema debe activar automaticamente el perfil de usuario
##### Tareas:
1. back se encarga de la logica que asigna los permisos a cada tipo de usuario y que se asignen usuarios de manera especifica dependiendo de quien crea el usuario.
2. El equipo de seguridad de mano del equipo de desarrollo de encarga de entregar los niveles de seguridad y perfiles por usuario adicional de los modulos a los que podra acceder

## **Épica 2: Consulta de establecimientos y portal del sitio**

  **Feature 1: Portal y Navegación de Comercios**  
  * **US-05:** Como estudiante de CESDE, quiero visualizar un menú con los establecimientos disponibles, para elegir en cuál de ellos deseo realizar mi compra.  
  * Corrección: Como estudiante de CESDE, quiero seleccionar los establecimientos disponibles, para elegir en cuál de ellos deseo realizar mi compra.  
  * **US-08:** Como estudiante de CESDE, quiero navegar en una interfaz con diseño personalizado por cada establecimiento, para identificar fácilmente en cuál cafetería o papelería estoy comprando.  
  * Corrección: Como estudiante de CESDE, quiero navegar en la interfaz del establecimiento de modo que pueda visualizar cada producto, su descripción y que sea identificable en qué establecimiento estoy comprando.  
  *   
  * **US-06:** Como administrador, quiero modificar las imágenes de referencia y las descripciones, para mantener la información de los establecimientos actualizada en la aplicación.  
* **Feature 2: Sistema de Feedback General**  
  * **US-07:** Como estudiante de CESDE, quiero calificar el establecimiento, para compartir mi opinión sobre el servicio ofrecido.

### **Épica 3: Consulta de productos y procesamiento de pagos**

* **Feature 1: Catálogo Virtual y Carrito de Compras**  
  * **US-09:** Como estudiante de CESDE, quiero ver un menú de productos, para conocer los artículos que están disponibles en el establecimiento seleccionado.  
  * **US-12:** Como estudiante de CESDE, quiero visualizar el detalle de cada producto, para asegurarme de sus características antes de agregarlo al pedido.  
  * **US-10:** Como estudiante de CESDE, quiero seleccionar los productos y las cantidades que deseo comprar, para ir armando mi pedido según mis necesidades.  
* **Feature 2: Módulo de Checkout y Pasarela de Pagos**  
  * **US-14:** Como estudiante de CESDE, quiero realizar pagos por medio de la aplicación, seleccionando el método de pago preferido y que esté disponible.  
  * **US-14.1 (Nueva):** Como equipo de desarrollo, necesitamos integrar y configurar pasarelas de pago, para que las transacciones realizadas en el carrito de compras se procesen de manera segura.

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
- **Épica:** Infraestructura técnica y despliegue
- **Prioridad:**Alta
- **Estimación:** 5
- **Descripción:** Como equipo de desarrollo, necesitamos crear y configurar un servicio de almacenamiento en la nube, para alojar las bases de datos de forma centralizada y segura.
##### Criterios de aceptación:
1. Modelo entidad relación creado y aprobado
2. Base de datos cumpliendo con estandares de normalización
##### Tareas:
1. El equipo de infraestructura se encarga de la compra del servidor que contenga la base de datos y los administradores de bases de datos proceden a la creación de la base de datos de acuerdo al modelo entidad relación aprobado por el negocio