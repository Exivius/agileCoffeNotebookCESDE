# Sprint 1

## Historias de usuario a trabajar

**US-18.1**
Épica: Infraestructura técnica y despliegue
Prioridad:Alta
Estimación: 5
Descripción: Como equipo de desarrollo, necesitamos crear y configurar un servicio de almacenamiento en la nube, para alojar las bases de datos de forma centralizada y segura.
### Criterios de aceptación:
1. Modelo entidad relación creado y aprobado
2. Base de datos cumpliendo con estandares de normalización
#### Tareas:
1. El equipo de infraestructura se encarga de la compra del servidor que contenga la base de datos y los administradores de bases de datos proceden a la creación de la base de datos de acuerdo al modelo entidad relación aprobado por el negocio

**US-01**
Épica: Creación del login y gestión de acceso
Prioridad: Media
Estimación: 4
Descripción: Como estudiante de CESDE, quiero registrarme utilizando mi correo electrónico o credenciales de Google, para crear mi cuenta rápidamente y acceder a los servicios de compra.
### Criterios de aceptación:
1. El usuario puede ingresar al modulo de registro
2. El sistema solicita un correo valido
3. el sistema valida que la contraseña sea mayor a 8 caracteres y que contenga minimo una mayuscula, un numero y un caracter especial
4. El sistema muestra un mensaje de confirmación cuando el registro fue exitoso
5. El usuario se crea en la base de datos
6. El sistema valida que el usuario no exista o ya este registrado
#### Tareas:
1. Front se encarga del diseño de la pagina para el registro la cual debe contener los campos de registro y botones de confirmación, limpieza o rechazar el registro
2. Back se encarga de la logica para la validación del usuario existente o creación del nuevo usuario y guardado en base de datos

**US-03**
Épica: Administración de Perfiles y Roles
Prioridad: Media
Estimación: 3
Descripción: Como administrador del sistema, quiero que a cada usuario se le asigne un perfil específico (usuario/admin) al iniciar sesión, para mostrarle únicamente las interfaces y permisos correspondientes a su rol.
### Criterios de aceptación:
1. Si el super admin crea la cuenta, este le puede asignar el tipo de usuario que desee
2. Si el usuario crea la cuenta desde el portal de registro, el sistema debe activar automaticamente el perfil de usuario
#### Tareas:
1. back se encarga de la logica que asigna los permisos a cada tipo de usuario y que se asignen usuarios de manera especifica dependiendo de quien crea el usuario.
2. El equipo de seguridad de mano del equipo de desarrollo de encarga de entregar los niveles de seguridad y perfiles por usuario adicional de los modulos a los que podra acceder

**US-01.1**
Épica: Creación del login y gestión de acceso
Prioridad: Baja
Estimación: 3
Descripción: Como usuario, quiero poder iniciar sesión en el sistema con mis credenciales, para acceder a la plataforma.
### Criterios de aceptación:
1. El usuario puede ingresar al login de la aplicación
2. El sistema valida que el correo exista
3. el sistema valida el perfil para cargar los modulos permitidos
4. El sistema valida que la contraseña sea correcta
5. El sistema muestra un error al usuario si al loguearse, no coindicen los datos con los guardados en las bases de datos
#### Tareas:
1. Front se encarga de la visual del login para que muestre los campos de usuario y contraseña, el boton para enviar la información y tooltips que muestren si el correo no tiene el formato necesario o la cotraseña es mejor el minimo de caracteres permitido
2. 2. Back se encarga de la logica para validar el usuario que intenta ingresar y que perfil tiene asignado en la base de datos. Luego de estas validaciones, determina que interfaz es la que se puede cargar de acuerdo al perfil