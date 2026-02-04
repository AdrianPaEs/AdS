# AdS

* 1. Acceso como Superusuario (root)
El sistema distingue entre usuarios normales y el superusuario (root), quien tiene acceso total a todos los archivos y comandos. Existen tres formas principales de acceder con estos privilegios:


Acceso directo: Entrar directamente como root, aunque se desaconseja porque no deja registro de qué administrador realizó cada acción.



Comando su: Permite sustituir la identidad de usuario. Generalmente se usa su - para cargar el entorno completo de root.



Comando sudo: Es la vía recomendada. Permite ejecutar comandos específicos como root usando la propia contraseña del usuario. Se configura mediante el archivo /etc/sudoers (editado con visudo).





2. Gestión de Cuentas de Usuario
Linux identifica a los usuarios mediante un número entero llamado UID (User ID). La información de las cuentas se almacena en:


/etc/passwd: Archivo legible por todos que contiene el nombre de usuario, UID, GID (ID de grupo primario), información adicional, directorio home y la shell de inicio.



/etc/shadow: Archivo accesible solo por root donde se guardan las contraseñas cifradas y datos sobre la caducidad de las mismas para mayor seguridad.

3. Grupos de Usuarios
Los grupos permiten organizar usuarios con intereses comunes para facilitar el acceso a recursos.

Se definen en /etc/group.

Un usuario tiene un grupo primario (en /etc/passwd) y puede tener varios grupos suplementarios.

Las contraseñas y administradores de grupos se gestionan en /etc/gshadow.


4. Procesos y Propiedad de Archivos
El acceso a los recursos se realiza mediante procesos, que heredan el UID efectivo (EUID) y GID efectivo (EGID) del usuario que los lanza para determinar sus permisos.



Cada archivo tiene un usuario propietario y un grupo propietario.

Por defecto, un archivo pertenece a quien lo crea y a su grupo primario.

Los propietarios se pueden cambiar con los comandos chown y chgrp.

5. Permisos Básicos de Acceso
Linux utiliza tres modos de acceso que se aplican a tres categorías (Usuario, Grupo y Otros):



Lectura (r): Ver el contenido de un archivo o listar un directorio.


Escritura (w): Modificar un archivo o crear/borrar archivos en un directorio.


Ejecución (x): Correr un programa o entrar (cd) en un directorio.

El sistema comprueba los permisos en orden: si el usuario es el dueño, aplica sus permisos y deja de comprobar; si no, prueba con el grupo, y finalmente con "otros".