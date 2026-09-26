
# Sprint 01 - Review

## 1. Resumen Ejecutivo
* **Objetivo del Sprint:** Implementar el prototipo de autenticación de usuarios y la arquitectura base de la base de datos de pruebas.
* **Estado:** Parcialmente completado.

---

## 2. Qué se hizo (Incremento completado)

### US-18.1: Base de Datos de Pruebas
* Se diseñó el diagrama UML como guía conceptual.
* Se desplegó una base de datos de prueba funcional en ambiente de laboratorio para soportar las ejecuciones iniciales.

### US-01: Maquetación y Validaciones de Registro / Login
* Se construyó la interfaz visual de login y registro utilizando HTML5 y CSS3.
* Se incorporaron validaciones en el formulario: correo con formato válido, campos obligatorios (nombre y apellido) y contraseña con longitud mínima de 8 caracteres.

### US-01.1: Autenticación e Interfaz de Inicio
* Se desarrolló la pantalla inicial de inicio de sesión.
* Se integró la validación contra la base de datos de prueba (verificación de existencia de correo y coincidencia de contraseña) con despliegue de mensajes de error en caso de fallo.

---

## 3. Qué no se hizo / Desviaciones

### US-03: Asignación de Perfiles y Permisos
* **Estado:** No realizado.
* **Causa:** El sistema aún no cuenta con la lógica para asignar roles en el registro ni para restringir módulos según el nivel de autorización. Se reingresa al Product Backlog.

### US-18.1: Base de Datos Definitiva
* La base de datos actual es únicamente un entorno de prueba provisional. La estructura final requerirá ajustes a medida que evolucionen los requerimientos.

### Deuda de Diseño Identificada (Inconsistencia de Datos)
* **Conflicto US-01 / US-01.1:** La pantalla de registro no solicita un "nombre de usuario", pero el login lo está requiriendo (se había planteado autenticar mediante correo electrónico). Se creará una tarea de refactorización para unificar el criterio a autenticación por email.

---

## 4. Conclusiones y Próximos Pasos
* **Repriorización:** Es necesario redefinir las prioridades del Sprint 02 para resolver la inconsistencia en los campos de autenticación antes de avanzar con la gestión de perfiles.
* **Impacto en Pruebas:** Al no contar con la US-03 (perfiles de usuario), las pruebas de navegación basada en roles quedan pospuestas para el siguiente ciclo.