# PRUEBA TECNICA DJANGO BACKEND

## Problema

El objetivo es crear un sistema de control de acceso a sedes ( punto de acceso ) para el personal de una empresa.

El mismo debe permitir crear y controlar los accesos para los empleados de cada sede.

El sistema consta de dos partes:

1. Aplicación web Django para gestión:

    + Usuarios
    + Empresas
    + Puntos de acceso dentro de la empresa
    + Franjas horarios de accesos por empleados

    Se consideran tres tipos de usuarios:

    a. Superusuario o administrador de la aplicación ( solo uno )
    b. Usuario administrador de empresa
    c. Usuario empleado de empresa

    La aplicación web debe permitir:

    + El superusuario puede:    
      - crear empresas
      - crear un usuario administrador para cada empresa creada e invitarlo por correo electronico.
  
    + El usuario administrador de empresa puede:
      - gestionar puntos de acceso de la empresa ( sedes )
      - invitar a un empleado a registrarse con un vinculo dentro de un correo electronico, el usuario se registra como perteneciente a la empresa. El vínculo lo lleva a un formulario de registro, donde el usuario llenará sus datos básicos.

    + Cuando el usuario administrador ingrese con su usuario y contraseña, se le debe presentar una página inicial, con los puntos de acceso de la empresa presentados en una grilla de tres fichas por fila con paginación.

    + El usuario administrador puede asignar a un usuario empleado de su empresa, a un punto de acceso ( sede ) y debe poder especificar varias franjas horarias, dentro de la cual dicho empleado podrá acceder a la sede. 

    + El  administrador debe poder activar o desactivar accesos a cada sede.

2. REST API de consulta por cada empresa:

    + Validar permisos de acceso a un punto de una empresa para sus  usuarios en la hora y localización actual ( sede ) desde donde se está consultando.
    + Retorna true o false junto a los  datos del punto de acceso (sede)
    + La validación debe considerar el estado activo o inactivo del punto.
    + Debe enviar cada intento de acceso fallido al correo electronico del administrador de la empresa.
    + La prueba de la API se puede hacer mediante POSTMAN.

## Requerimentos:

+ Registro e ingreso de usuarios
+ CRUD Empresa: - Usuario administrador (fk)
                - Nit
                - Nombre de la empresa 
                - Nombre comercial de la empresa
                - Dirección 
                - Teléfono
                - correo electrónico válido
                - sitio web (direccion valida)
                - país, estado, ciudad

+ CRUD Usuarios: - Apellido
                 - Nombre
                 - Empresa (fk)
                 - Dirección
                 - Teléfono
                 - correo electrónico valido
                 - pais, estado, ciudad

+ CRUD Puntos de acceso de la empresa: - Nombre
                                       - Dirección
                                       - correo electronico
                                       - empresa (fk)
                                       - geolocalizacion
                                       - estado
                                       - horarios de acceso (fk)

+ CRUD Horarios de acceso (franjas horarias): - Punto de acceso (fk)
                                              - Hora de inicio
                                              - Hora de finalización
                                              - Usuario (fk)  

## Opcionales:

1. validar los teléfonos con indicativo y su localización (+57 316 878 66 28 es un telefono de Colombia )
2. Usar un tercero para determinar el país, estado y ciudad (por ejemplo Google maps)
3. Realizar el proceso de registro de un usuario con verificacion de correo electronico mediante el envio de un enlace con un unico token.
4. Usar docker para el despliegue




  



  
