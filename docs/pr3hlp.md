# Proyecto 3 - Ayuda técnica

## Script de creación de la base de datos

Guarda el siguiente código en un archivo como *appdb_setup.sql* y ejecútalo en la DB-VM (MariaDB/MySQL) con ``sudo mysql -u root -p < appdb_setup.sql``.

```sql
-- appdb_setup.sql
-- Crea la base de datos y la tabla de ejemplo
CREATE DATABASE IF NOT EXISTS appdb
  CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
USE appdb;

CREATE TABLE IF NOT EXISTS saludos (
  id INT PRIMARY KEY,
  texto VARCHAR(100) NOT NULL
);

INSERT INTO saludos (id, texto) VALUES
  (1, 'Hola SMR'),
  (2, 'Proyecto Intermodular'),
  (3, 'Conectando Web + BD');

-- Crea el usuario solo para la IP de la WEB-VM (ajusta si tu web tiene otra IP)
-- Sustituye 192.168.20.10 por la IP real de la WEB-VM
CREATE USER IF NOT EXISTS 'appuser'@'192.168.20.10' IDENTIFIED BY 'ClaveFuerte!';
GRANT SELECT ON appdb.* TO 'appuser'@'192.168.20.10';
FLUSH PRIVILEGES;

-- (Opcional, SOLO si usas MySQL 8 y tienes problemas de autenticación)
-- CREATE USER 'appuser'@'192.168.20.10' IDENTIFIED WITH mysql_native_password BY 'ClaveFuerte!';
-- GRANT SELECT ON appdb.* TO 'appuser'@'192.168.20.10';
-- FLUSH PRIVILEGES;
```

## Página de inicio de la aplicación web

Guarda el siguiente código en un archivo *index.php* en la WEB-VM (en la raíz del servidor web Apache /Nginx) y edita las variables de conexión a la base de datos.

```php
<!doctype html>
<html lang="es">
<head>
  <meta charset="utf-8">
  <title>Demo BD — Saludos</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <style>body{font-family:system-ui,-apple-system,Segoe UI,Roboto,Arial,sans-serif;max-width:720px;margin:2rem auto;padding:0 1rem}code{background:#f4f4f4;padding:.1rem .3rem;border-radius:4px}</style>
</head>
<body>
  <h1>Saludos desde la base de datos</h1>
  <?php
    // AJUSTA ESTOS DATOS A TU ENTORNO
    $DB_HOST = '192.168.20.20'; // IP de la DB-VM
    $DB_USER = 'appuser';
    $DB_PASS = 'ClaveFuerte!';
    $DB_NAME = 'appdb';

    // Conexión
    $mysqli = @new mysqli($DB_HOST, $DB_USER, $DB_PASS, $DB_NAME);
    if ($mysqli->connect_errno) {
      http_response_code(500);
      echo "<p><strong>Error de conexión ({$mysqli->connect_errno}):</strong> {$mysqli->connect_error}</p>";
      exit;
    }
    $mysqli->set_charset('utf8mb4');

    // Consulta
    $sql = "SELECT id, texto FROM saludos ORDER BY id ASC";
    $res = $mysqli->query($sql);

    if (!$res) {
      echo "<p><strong>Error en la consulta:</strong> " . htmlspecialchars($mysqli->error) . "</p>";
    } else {
      echo "<ul>";
      while ($row = $res->fetch_assoc()) {
        $id = (int)$row['id'];
        $texto = htmlspecialchars($row['texto'], ENT_QUOTES, 'UTF-8');
        echo "<li><code>$id</code> — $texto</li>";
      }
      echo "</ul>";
      $res->free();
    }

    $mysqli->close();
  ?>
  <p style="margin-top:2rem;color:#666">Pista: edita este HTML como quieras; el bloque PHP imprime la lista.</p>
</body>
</html>
```