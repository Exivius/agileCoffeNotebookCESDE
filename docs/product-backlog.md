# Backlog final:
## **Épica 1: Creación del login y gestión de acceso**


### **Feature 1: Gestión de Identidad y Autenticación**

- [] **US-01:** Como estudiante de CESDE, quiero registrarme utilizando mi correo electrónico o credenciales de Google, para crear mi cuenta rápidamente y acceder a los servicios de compra.
- [] **US-04:** Como usuario de la aplicación, quiero disponer de un método para recuperar mi contraseña, para restablecer el acceso a mi cuenta en caso de olvidarla.
- [] **US-01.1** (Nueva): Como usuario, quiero poder iniciar sesión en el sistema con mis credenciales, para acceder a la plataforma.
- 
### **Feature 2: Administración de Perfiles y Roles**
- [] **US-02:** Como administrador del sistema, quiero que la aplicación verifique automáticamente si el estado de un usuario es activo o inactivo, para garantizar que solo las personas autorizadas puedan acceder a la plataforma.
- [] **US-03:** Como administrador del sistema, quiero que a cada usuario se le asigne un perfil específico (usuario/admin) al iniciar sesión, para mostrarle únicamente las interfaces y permisos correspondientes a su rol.
- [] **US-03.1:** Como administrador de un establecimiento, quiero tener permisos exclusivos únicamente sobre mi local, para gestionar mis productos sin afectar la información o configuraciones de otros establecimientos.

## **Épica 2: Consulta de establecimientos y portal del sitio**

### **Feature 1: Portal y Navegación de Comercios**
- [] **US-05:** Como estudiante de CESDE, quiero seleccionar los establecimientos disponibles, para elegir en cuál de ellos deseo realizar mi compra.
- [] **US-08:** Como estudiante de CESDE, quiero navegar en la interfaz del establecimiento de modo que pueda visualizar cada producto, su descripción y que sea identificable en qué establecimiento estoy comprando.
- [] **US-06:** Como administrador, quiero modificar las imágenes de referencia y las descripciones, para mantener la información de los establecimientos actualizada en la aplicación.

### **Feature 2: Sistema de Feedback General**
- [] **US-07:** Como estudiante de CESDE, quiero calificar el establecimiento, para compartir mi opinión sobre el servicio ofrecido.

## **Épica 3: Consulta de productos y procesamiento de pagos**

### **Feature 1: Catálogo Virtual y Carrito de Compras**
- [] **US-09:** Como estudiante de CESDE, quiero ver un menú de productos, para conocer los artículos que están disponibles en el establecimiento seleccionado.
- [] **US-12:** Como estudiante de CESDE, quiero visualizar el detalle de cada producto, para asegurarme de sus características antes de agregarlo al pedido.
- [] **US-10:** Como estudiante de CESDE, quiero seleccionar los productos y las cantidades que deseo comprar, para ir armando mi pedido según mis necesidades.

### **Feature 2: Módulo de Checkout y Pasarela de Pagos**
- [] **US-14:** Como estudiante de CESDE, quiero realizar pagos por medio de la aplicación, seleccionando el método de pago preferido y que esté disponible.
- [] **US-14.1** Como equipo de desarrollo, necesitamos integrar y configurar pasarelas de pago, para que las transacciones realizadas en el carrito de compras se procesen de manera segura.

## **Épica 4: Entrega, monitoreo y paneles de administración**

### **Feature 1: Seguimiento de Pedidos y Turnos**
- [] **US-04.1** Como estudiante de CESDE, quiero que se me asigne un turno tras mi compra, para organizar mi tiempo de espera.
- [] **US-04.2**Como estudiante de CESDE, quiero recibir alertas y notificaciones sobre el estado de mi pedido, para acercarme a recogerlo exactamente cuando esté listo.

## **Feature 2: Dashboard Administrativo y Métricas**

- [] **US-11:** Como administrador, quiero realizar modificaciones en tiempo real de los precios y productos, para mantener el inventario y los costos al día sin afectar las compras actuales.
- [] **US-15:** Como administrador del sistema, quiero visualizar paneles con métricas clave de uso y transacciones, para tomar decisiones informadas sobre el rendimiento y la operatividad de la plataforma. Estas métricas deben incluir los productos vendidos, montos recaudados y métodos de pago utilizados.
- [] **US-16:** Como administrador del sistema, quiero habilitar o deshabilitar módulos y funcionalidades de forma dinámica, para gestionar el alcance de la aplicación sin interrumpir el servicio general.
- [] **US-13:** Como estudiante de CESDE, quiero calificar los productos adquiridos, para dejar una referencia sobre la calidad de la comida o artículos.

## **Épica 5: Infraestructura técnica y despliegue**

### **Feature 1: Distribución Móvil**

- [] **US-17:** Como estudiante de CESDE, quiero descargar e instalar la aplicación fácilmente desde tiendas virtuales oficiales (Google Play Store, App Store), para acceder a los servicios directamente desde mi dispositivo móvil.
- [] **US-17.1:** Como administrador del proyecto, necesito gestionar la contratación de los servicios en las plataformas virtuales, para posibilitar la subida y descarga de la app en los sistemas operativos celulares.

### **Feature 2: Arquitectura y Persistencia de Datos**
- [] **US-18.1:** Como equipo de desarrollo, necesitamos crear y configurar un servicio de almacenamiento en la nube, para alojar las bases de datos de forma centralizada y segura.
