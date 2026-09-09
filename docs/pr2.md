# Proyecto 2 - Documentar una instalación de software

## Objetivo

Realizar la instalación y configuración básica de un **servicio de red sencillo** en un equipo local y **documentar** el proceso con capturas, decisiones técnicas y **pruebas de verificación**. El enfoque es **técnico y reproducible**.

### Opción principal (recomendada)
**Servidor web local (Apache en Linux o Nginx).**

- Sistema base sugerido: Debian/Ubuntu o derivadas (en máquina virtual).
- [Tutorial de instalación de Apache en Linux](https://www.digitalocean.com/community/tutorials/how-to-install-the-apache-web-server-on-ubuntu-20-04-es).
- [Tutorial de instalación de Nginx en Debian](https://raul-profesor.github.io/Despliegue/P1.1/).

### Otras opciones

- **Servidor FTP** (FileZilla Server en Windows o vsftpd/proftpd en Linux).
- **Servidor SFTP/SSH** (OpenSSH server) para intercambio seguro de archivos.
- **Servidor de archivos SMB** (Samba básico) para compartir una carpeta en LAN.

## Entregables

1. **Memoria técnica (5–7 páginas)** en PDF, con índice y numeración, que incluya:
    - Objetivo y alcance.
    - Inventario (sistema, versión, rol de máquina, red).
    - **Procedimiento paso a paso** con capturas y notas (errores y decisiones).
    - **Pruebas de aceptación** (guion de pruebas ejecutado + resultados).
    - Resultados y conclusiones (qué funcionó, qué mejorarías).
2. **Carpeta de evidencias**: capturas originales (PNG/JPG) y, si procede, ficheros de configuración (.conf).
3. **Script/guion de pruebas ejecutable** (TXT/MD) con los comandos y verificaciones.

**Convenciones de nombres**

- Carpeta raíz: `M1_Apellido1Apellido2_Nombre_Grupo`
- Memoria: `M1_Memoria_Apellido1Nombre.pdf`
- Evidencias: `evidencias/2025MMDD_paso_X.png`
- Confs: `confs/nombre_fichero.conf`

## Requisitos mínimos

- El servicio **arranca** automáticamente tras reinicio (enable/start correcto).
- El puerto del servicio está **escuchando** y accesible localmente.
- Existe al menos **una prueba por requisito** con umbral de éxito (p. ej., `curl`, `ping`, `telnet`, cliente web/FTP).
- La documentación permite **reproducir** la instalación.

## Criterios de aceptación (CA) — ejemplos por opción

A) Apache/Nginx (web)

- CA‑W1: `systemctl status` indica *active (running)* y `systemctl is-enabled` → *enabled*.
- CA‑W2: `ss -ltn` (o `netstat -ano`) muestra el puerto 80/8080 en escucha.
- CA‑W3: `curl http://localhost` devuelve 200 OK y la página de prueba o `index.html` propio.
- CA‑W4: tras reiniciar, el servicio sigue activo (*enabled*).

B) FTP (FileZilla/vsftpd/proftpd)

- CA‑F1: servicio en *running* y *enabled*.
- CA‑F2: conexión exitosa desde cliente con usuario creado; **no** permite anónimos (si se exige).
- CA‑F3: subida/descarga de un archivo de prueba a la carpeta definida.

C) SFTP/SSH (OpenSSH)

- CA‑S1: servicio en *running* y *enabled*.
- CA‑S2: conexión SFTP desde cliente; escritura/lectura en el *home* del usuario.
- CA‑S3: autenticación por contraseña habilitada (o por clave si se define así).

D) Samba (SMB)

- CA‑Smb1: recurso compartido visible desde otro equipo de la red.
- CA‑Smb2: autenticación de usuario; acceso de lectura/escritura según permisos.
- CA‑Smb3: el servicio está *running* y *enabled*.

## Proceso sugerido
- **Semana 1 (2 h)**: preparación del entorno, instalación del servicio, verificación básica y capturas.
- **Semana 2 (2 h)**: endurecimiento mínimo (p. ej., deshabilitar anónimo/crear usuario, puerto), pruebas formales y cierre de memoria.

## Plantilla de memoria

Puedes encontrarla [aquí](plantilla_memoria_p2.md).

## Entrega

Comprime todos los archivos solicitados en un único archivo .zip y súbelo a la tarea de Moodle Centros correspondiente con el siguiente formato de nombre:

Apellido1Apellido1Apellido2_Nombre_PI_P2.zip