# Proyecto 3 - Aplicación web con base de datos en máquina virtual separada

## Objetivo

En grupos deberéis una aplicación web sencilla (Apache/Nginx + PHP) en una máquina virtual que se conecte a una base de datos (MariaDB/MySQL) alojada en otra máquina virtual. Ambas máquinas virtuales estarán en la misma red virtual (host-only/interna). Se validarán la conectividad entre máquinas, la apertura controlada de puertos y la persistencia tras reinicio.

Además, añade una tercera máquina virtual cliente para hacer pruebas externas (curl/navegador).

### Topología y direccionamiento:

- WEB-VM: 192.168.20.10/24 — Apache/Nginx + PHP.
- DB-VM: 192.168.20.20/24 — MariaDB/MySQL (puerto 3306).
- CLIENT-VM: 192.168.20.30/24 — para pruebas.

Todas las máquinas virtuales deben estar en la misma red host-only/interna del hipervisor y con IP fija o reservada.

### Requisitos mínimos (Criterios de aceptación):

- CA-1 (Red): ping WEB↔DB OK; ambas en /24 idéntica.
- CA-2 (BD): DB-VM escucha en 3306 y acepta solo conexiones desde WEB-VM (UFW/Firewall configurado).
- CA-3 (App): página PHP en WEB-VM que conecta a la BD y muestra “OK” + un dato leído de una tabla.
- CA-4 (Persistencia): tras reiniciar ambas VMs, apache2/nginx y mariadb/mysql están enabled + active y la app sigue funcionando.
- CA-5 (Backup/Restore): mysqldump de la BD, borrado de la tabla y restore correcto (la app vuelve a mostrar el dato).

### Entregables

- Memoria (PDF): diagrama, tabla de IPs, pasos de instalación, configuración (ficheros clave), reglas de firewall, pruebas (capturas), backup/restore, incidencias y conclusiones.
- Carpeta de evidencias: ip a/ipconfig, ss -ltn/netstat, mysql -e '...', página PHP funcionando, systemctl, backup/restore.
- Guion de pruebas ejecutado con resultados.
- Presentación breve (15 min).


### Guion de trabajo

1. Crear VMs y ponerlas en la misma red.
2. DB-VM: instalar MariaDB/MySQL, crear BD/usuario con acceso solo desde 192.168.20.10; abrir 3306 en firewall solo para WEB-VM.
3. WEB-VM: instalar Apache/Nginx + PHP; crear test_db.php que se conecte a la BD y lea un registro.
4. Pruebas WEB↔DB y capturas.
5. Backup/restore (mysqldump → borrar → importar → comprobar app).
6. Persistencia tras reinicio (servicios enabled + pruebas otra vez).

## Entrega

Comprime todos los archivos solicitados en un único archivo .zip y súbelo a la tarea de Moodle Centros correspondiente con el siguiente formato de nombre:

Apellido1Apellido1Apellido2_Nombre_PI_P3.zip