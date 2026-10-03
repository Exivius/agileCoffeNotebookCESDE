# Historias de Usuario

## *Epica 1: Creación del login y gestión de acceso*
### *Feacture 1: Gestión de identidad y Autenticación*

#### **US-01**: Como estudiante de CESDE, quiero registrarme utilizando mi correo electrónico o credenciales de Google,para crear mi cuenta rápidamente y acceder a los servicios de compra.
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

#### **US-04:** Como usuario de la aplicación, quiero disponer de un método para recuperar mi contraseña, para restablecer el acceso a mi cuenta en caso de olvidarla.  
##### Criterios de aceptación:
1. El usuario puede presionar "¿Olvidaste tu contraseña?" en el login.
2. El sistema pide el correo registrado y valida que exista.
3. El sistema genera y envía por correo electronico un código temporal para permitir el cambio de contraseña.
4. El sistema guarda la nueva contraseña actualizada.
##### Tareas:
1. *Front:* Crear la pantalla de solicitud de recuperación, validación de codigo de seguridad y la pantalla para ingresar la nueva contraseña.
2. *Back:* Crear servicio que envie el código por coreo y realice la validación y permita actualice la clave en la tabla de usuarios.

#### **US-01.1:** Como usuario, quiero poder iniciar sesión en el sistema con mis credenciales, para acceder a la plataforma.
##### Criterios de aceptación:
1. El usuario puede ingresar al login de la aplicación
2. El sistema valida que el correo exista
3. el sistema valida el perfil para cargar los modulos permitidos
4. El sistema valida que la contraseña sea correcta
5. El sistema muestra un error al usuario si al loguearse, no coindicen los datos con los guardados en las bases de datos
##### Tareas:
1. *Front* se encarga de la visual del login para que muestre los campos de usuario y contraseña, el boton para enviar la información y tooltips que muestren si el correo no tiene el formato necesario o la cotraseña es mejor el minimo de caracteres permitido2.  *Back* se encarga de la logica para validar el usuario que intenta ingresar y que perfil tiene asignado en la base de datos. Luego de estas validaciones, determina que interfaz es la que se puede cargar de acuerdo al perfil

### *Feacture 2: Administración de Perfiles y Roles*

#### **US-02:** Como administrador del sistema, quiero que la aplicación verifique automáticamente si el estado de un usuario es activo o inactivo, para garantizar que solo las personas autorizadas puedan acceder a la plataforma.
##### Criterios de aceptación:
1. Si un usuario tiene estado inactivo, el sistema no le permite iniciar sesión.
2. Si un usuario tiene estado activo, el sistema le permite iniciar sesión.
3. El sistema muestra un mensaje indicando que la cuenta se encuentra deshabilitada o suspendida.
4. El administrador puede cambiar el estado de un usuario (activo/inactivo) desde su panel.
##### Tareas:
1. *Front:* Mostrar alertas informativa en el login cuando el servicio devuelva que el usuario está inactivo y una de bienvenido para el usuario activo.
2. *Back:* Agregar el campo estado (activo/inactivo) en la tabla usuarios y validar esta bandera antes de permitir el inicio de la sesión.

#### **US-03:** Como administrador del sistema, quiero que a cada usuario se le asigne un perfil específico (usuario/admin) al iniciar sesión, para mostrarle únicamente las interfaces y permisos correspondientes a su rol.
##### Criterios de aceptación:
1. Si el super admin crea la cuenta, este le puede asignar el tipo de usuario que desee
2. Si el usuario crea la cuenta desde el portal de registro, el sistema debe activar automaticamente el perfil de usuario
##### Tareas:
1. *Back* se encarga de la logica que asigna los perfiles y sus permisos a cada tipo de usuario.
2. *Back* se debe de crear logica que asigne perfil de usuario si el usuario se crea desde la web de inicio.
3. *Back* se encarga de crear los niveles de seguridad por perfiles de usuario conectando el acceso en modulos a los que se les brinde permiso.
4. *Front* se encarga de la visual que permite crear usuarios y contraseñas, y la asignación o modificacion del perfil a su dispocisión el boton para enviar la información y tooltips que muestren si el correo no tiene el formato necesario o la cotraseña es mejor el minimo de caracteres permitido

## **Épica 2: Consulta de establecimientos y portal del sitio**

###  **Feature 1: Portal y Navegación de Comercios**  
#### **US-05:** Como estudiante de CESDE, quiero seleccionar los establecimientos disponibles, para elegir en cuál de ellos deseo realizar mi compra.
  #### Criterios de aceptación:
  1. Visualización correcta del menú mostrando los diferentes establecimientos aliados a la aplicación, con el nombre del establecimiento y una breve descripción de los productos ofertados.
  2. Al seleccionar el establecimiento por medio de un click, se ingresa al portal del establecimiento
  #### Tareas:
  1. Front se encarga del diseño HTML/CSS del menú para seleccionar el establecimiento una vez el login del usuario es exitoso.
  2. Back se encargara de que se cargue desde la base de datos de forma correcta la información por cada establecimiento una vez el loguin del usuario es exitoso. Ademas, que al hacer click sobre un establecimiento, el sistema cargue el portal del establecimiento mostrando correctamente los productos y servicios ofertados.
#### **US-08:** Como estudiante de CESDE, quiero navegar en la interfaz del establecimiento de modo que pueda visualizar cada producto, su descripción y que sea identificable en qué establecimiento estoy comprando.  
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
#### **US-06:** Como administrador, quiero modificar las imágenes de referencia y las descripciones, para mantener la información de los establecimientos actualizada en la aplicación.  
  #### Criterios de aceptación:
  1. el administrador puede ingresar a un modo de edición para cada uno de los productos registrados.
  2. El administrador puede modificar las descripciones y precios en los productos.
  3. El administrador puede remover productos del menú poniendolos inactivos de modo que no se muestren de cada al usuario.
  4. El administrador puede eliminar definitivamente un producto del menú
  5. El administrador puede agregar nuevos productos desde una pantalla que le solicitara cargar una imagen de referencia e ingresar los datos necesarios para la publicación del mismo
  #### Tareas:
  1. Front se encargara de la creación de un nuevo portal o modo edición para solamente los productos que se presentan en el menú del establecimiento, mostrando claramente que campos son editables y requeridos.
  2. Back se encarga de la validación de los datos, tanto para el guardado en la base de datos como para garantizar que solo un usuario con permisos pueda realizar ediciones sobre los productos ya publicados. Validara que la totalidad de los datos requeridos sean ingresados antes de realizar el guardado.
### **Feature 2: Sistema de Feedback General**  
#### **US-07:** Como estudiante de CESDE, quiero calificar el establecimiento, para compartir mi opinión sobre el servicio ofrecido.
  #### Criterios de aceptación:
  1. Dónde se visualiza el menú del establecimiento, debera existir un boton de califación el cual se comunique con un modulo especial.
  2. El modulo de califación debera cargar por defecto el nombre del establecimiento.
  3. El modulo muestra campos para ingresar un titulo, una descripción de la calificación, y varios items a calificar como la atención, variedad de productos los cuales tendran un sistema de calificación por estrellas.
  #### Tareas
  1. Cuando el cliente seleccione el establecimiento en el que desea comprar, este contendra un boton el cual se comunicara con una interfaz a la calificación del establecimiento. Fron se encargara de que el boton rediriga a la interfaz correcta o la creación de una ventana popup
  2. Front diseñara la ventana la cual contendra, un subject, una sesión para comentatios y 5 estrelas las cuales se accionaran/llenaran al pasar el cursor sobre ellas. finalmente un boton de submit.
  3. Back se encargara de que el presionar el boton submit, esta información quede siempre relacionada al establecimiento especifico el cual se este calificando
  4. Back se encargara de redirigir la consulta para que estas reseñas se guarden de forma apropiada en la bade de datos, siempre relacionando el usuario que lo califico y el establecimiento para el cual fue hecha esa reseña


## *Épica 3: Consulta de productos y procesamiento de pagos*
### *Feature 1: Catálogo Virtual y Carrito de Compras* 

#### **US-09:** Como estudiante de CESDE, quiero ver un menú de productos, para conocer los artículos que están disponibles en el establecimiento seleccionado.
##### Criterios de aceptación:
1. Se listan los productos del local con su nombre, precio y disponibilidad.
2. Si un producto no tiene stock, aparece como "Agotado" y no se puede añadir.
3. La pagina permitira hacer srwoll up/down si los productos superan el numero permitido de acuerdo al tamaño de la pantalla
##### Tareas:
1. Front se encargara de realizar la interfaz visual con la que un cliente podra interactuar con el sistema.
2. Debera existir un portal generico el cual se alimentara de la información estructurada de la base de datos. Fron se encargara de la maquetacion para que esta tenga los espacios para cargar cada uno de los productos que oferta un establecimiento especifico.
3. Back se encargara de que Los modulos visuales se carguen con la información que este guardada en las bases de datos siempre relacionando el establecimiento al cual el usuario haya ingresado
#### **US-12:** Como estudiante de CESDE, quiero visualizar el detalle de cada producto, para asegurarme de sus características antes de agregarlo al pedido.
  #### Criterios de aceptación:
1. El usuario sera capaz de visualizar la descripción ubicada en la parte de abajo de la imagen de referencia del producto
2. La descripción debera contener los ingredientes que componen el producto, el precio a pagar, los gramajes por porcion.
  #### Tareas:
1. Front Se encargara de que los modulos del menu tengan estilos que permitan ver la correcta visualizacón del producto, separado de su nombre y descripción.
2. Los contenedores de la información del producto deberan tener separación adecuada, de modo que la imagen no quede pegada de la descripción, ni la descripción de los ingredientes que componen el producto
3. Back debera asegurar que la información que se carga en cada imagen sea la correcta.
4. Back validara que la los ingredientes que aparecen para cada preparación y/o producto realmente correspondan a este, que correspondan con la imagen de referencia y a su vez correspondan con el establecimiento que ofrece este producto.

#### **US-10:** Descripción: Como estudiante de CESDE, quiero seleccionar los productos y las cantidades que deseo comprar, para ir armando mi pedido según mis necesidades.
#### Criterios de aceptación:
1. El estudiante debera poder usar los botones o campos numeros para aumentar o disminuir la cantidad del producto
2. Cada producto debera tener un boton para agregar el producto al carrito de compras
#### Tareas:
1. Front debera agregar los botones para aumentar o disminuir la cantidad el producto
2.Front se encargara de que esta cantidad del producto sera visible en un campo de texto y debera actualizarse cada que el cliente de click sobre los botones designados para aumentar o disminuir la cantidad del producto.
3. El campo donde se visualiza la cantidad del producto tambien debera ser modificable y que el cliente pueda ingresar un numero por teclado
4. Debera existir en el contenedor de cada producto un boton que permita al usuario agregar determinada cantidad de un producto al carrito de compras.
5. Back se encargada de que una vez que el cliente presione click sobre el boton de agregar al carrito el sistema tome el producto que el cliente esta visualizando, la cantidad y el valor y lo guarde para ser mostrado en la pantalla de la orden
6. Back debera cerciorarse de que se guarden las cantidades seleccionadas por el usuario y que el calculo total por producto sea contabilizado de manera correcta

### *Feature 2: Módulo de Checkout y Pasarela de Pagos*  
#### **US-14:** Como estudiante de CESDE, quiero realizar pagos por medio de la aplicación, seleccionando el método de pago preferido y que esté disponible.
  #### Criterios de aceptación:
  1. La pantalla del carrito de compra debera contener un boton para procesar el pago
  2. Al dar click sobre este boton, debera dirigir al usuario a una pantalla donde podra procesar el pago
  3. El usuario podra elegir entre pago contra entrega, pago con tarjeta o transferencia.
  4. Si el usuario elige un pago contraentrega, el sitio debera dirigir al usuario a una pantalla donde podra visualizar los detalles de su orden y un QR para reclamar en sitio.
  5. Si el usuario elige otro metodo de pago diferente a contraentrega, debera redirigirlo a una pasarela de pagos
  #### Tareas:
  1. Front debera de agregar un boton al carrito de compras que diga "pagar"
  2. Front debera ademas diseñar una pantalla para que luego de procesado el pago, se muestre la confirmación de la orden.
  3. Si el cliente elige una forma de pago contraentrega, no debera ir a una pasarela de pagos, sino a una pantalla de resumen mostrando la información del usuario, los productos adquiridos y un QR para reclamar en caja.
  4. Fron debera encargarse de crear un cuadro de texto dentro de la pantalla de la orden para mostrar el error que se pudo causar al ser rechazado un pago y que se muestre la transacción fallida
  5. Back debera asegurar que los numeros de orden, cantidades, valores y productos se comuniquen de manera correcta con la pasarela de pagos
  6. Una vez procesado el pago, Back debera asegurarse que traer la información ya procesada desde la pasarela de pagos y que esta sea mostrada en la pantalla de la orden con el QR para reclamar en caja.
  7. Si el pago no es exitoso, back debera guardar un log de los errores

#### **US-14.1** (Nueva):* Como equipo de desarrollo, necesitamos integrar y configurar pasarelas de pago, para que las transacciones realizadas en el carrito de compras se procesen de manera segura.
#### Criterios de aceptación:
1. La plataforma de pagos debera integrarse con la plataforma para la compra y pago de productos de nuestros locales internos
2. Aun siendo una sola pasarela, esta debera dirigir el pago al establecimiento correcto
3. Debera existir un log de errores para capturar las posibles fallas durante el pago
4. Deberan asegurarse los puentes apropiados para el envio de la información para la compra y el recibo de la información ya procesada.
#### Tareas:
1. Back debera establecer los canales apropiados y niveles de seguridad necesarios para la visualización de la información de pago
2. Bajo ningun motivo la información de la tarjeta de credito debera guardarse
3. Bajo ningun motivo la información de pago sera visible para los administradores
4. Los datos deberan viajar a la plataforma de pago de acuerdo a lso requerimientos de la misma.
5. Los datos seran recibidos de la pasarela de pagos y deberan procesarse para que solo la información necesaria sea mostrada al usuario en la confirmación de pago.
6. Se debe asegurar los niveles apropiados de seguridad que guarda la base de datos con la información de pago aportada por el usuario.
7. Se debera encriptar tal información para ser transmitida de acuerdo a la pasarela de pagos y para ser contenida de acuerdo a lso protocolos internos de segurdad de la información.

### **Épica 4: Entrega, monitoreo y paneles de administración**

### **Feature 1: Seguimiento de Pedidos y Turnos**  
#### **US-04.1 (Nueva):** Como estudiante de CESDE, quiero que se me asigne un turno tras mi compra, para organizar mi tiempo de espera.
#### **US-04.2 (Nueva):** Como estudiante de CESDE, quiero recibir alertas y notificaciones sobre el estado de mi pedido, para acercarme a recogerlo exactamente cuando esté listo.  
### **Feature 2: Dashboard Administrativo y Métricas**  
#### **US-11:** Como administrador, quiero realizar modificaciones en tiempo real de los precios y productos, para mantener el inventario y los costos al día sin afectar las compras actuales.  
#### **US-15:** Como administrador del sistema, quiero visualizar paneles con métricas clave de uso y transacciones, para tomar decisiones informadas sobre el rendimiento y la operatividad de la plataforma. Estas métricas deben incluir los productos vendidos, montos recaudados y métodos de pago utilizados.  
#### **US-16:** Como administrador del sistema, quiero habilitar o deshabilitar módulos y funcionalidades de forma dinámica, para gestionar el alcance de la aplicación sin interrumpir el servicio general.  
#### **US-13:** Como estudiante de CESDE, quiero calificar los productos adquiridos, para dejar una referencia sobre la calidad de la comida o artículos.

### **Épica 5: Infraestructura técnica y despliegue**

### **Feature 1: Distribución Móvil**  
#### **US-17:** Como estudiante de CESDE, quiero descargar e instalar la aplicación fácilmente desde tiendas virtuales oficiales (Google Play Store, App Store), para acceder a los servicios directamente desde mi dispositivo móvil.  
#### **US-17.1 (Nueva \- Tarea Técnica):** Como administrador del proyecto, necesito gestionar la contratación de los servicios en las plataformas virtuales, para posibilitar la subida y descarga de la app en los sistemas operativos celulares.  
### **Feature 2: Arquitectura y Persistencia de Datos**


#### **US-18.1** Como equipo de desarrollo, necesitamos crear y configurar un servicio de almacenamiento en la nube, para alojar las bases de datos de forma centralizada y segura.
##### Criterios de aceptación:
1. Modelo entidad relación creado y aprobado
2. Base de datos cumpliendo con estandares de normalización
##### Tareas:
1. El equipo de infraestructura se encarga de la compra del servidor que contenga la base de datos y los administradores de bases de datos proceden a la creación de la base de datos de acuerdo al modelo entidad relación aprobado por el negocio