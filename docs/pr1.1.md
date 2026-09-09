# Proyecto 1 Parte 1 - El aula de informática

## Descripción del problema

Imagina que queremos realizar el proyecto de una red de un aula de informática con 15 PCs, salida a Internet, una impresora en red y control básico de usuarios. Se debe proponer un diseño realizable en el centro.

## Cómo redactar el **Objetivo** (1 frase, verificable)

- Debe describir el **resultado esperado** sin imponer una solución.
- Debe ser **comprobable** al final mediante pruebas.

**Modelo:** *“Proveer conectividad a Internet y acceso a impresión en red para tres PCs y una consola, garantizando cobertura Wi‑Fi estable en toda la vivienda.”*

**Evitar:** *“Instalar un PLC y un router nuevo.” (impone solución).*

---

## **Alcance**: dentro / fuera (out of scope)

- **Dentro** = lo que el proyecto **sí** cubrirá.  
- **Fuera** = lo que **no** abordará para evitar ambigüedades.

**Ejemplos (orientativos):**  
- Dentro: conectividad a Internet de 3 PCs y 1 consola; impresión en red para los PCs; cobertura Wi‑Fi mínima especificada.  
- Fuera: TV por IPTV; telefonía VoIP; domótica.

---

## **Actores / Dispositivos** (inventario)

Enumera personas/usuarios y dispositivos implicados con un nombre claro.  
Ej.: PC‑01, PC‑02, PC‑03, Consola, Impresora, Router del ISP, Punto de Acceso (si aplica).

---

## **Requisitos Funcionales (RF)**

Son **cosas que el sistema debe poder hacer**. Redáctalos con verbo activo y condición medible.

**Patrones útiles:**  
- “El dispositivo X **debe poder** [acción]…”  
- “El sistema **permitirá** [acción] desde [ubicación/dispositivo]…”

**Ejemplos bien redactados:**  
- RF‑01: Los 3 PCs y la consola **deben poder** acceder a Internet.  
- RF‑02: Los 3 PCs **deben poder** imprimir en la impresora de red.  
- RF‑03: La red **debe** permitir autenticación de los PCs con usuario/contraseña (si se decide).

**Mal redactados (evitar):**  
- “Internet para todos.” (impreciso)  
- “Instalar impresora Wi‑Fi.” (solución, no necesidad)

---

## **Requisitos No Funcionales (RNF)**

Son **propiedades de calidad**: rendimiento, seguridad, usabilidad, coste, etc. También deben ser medibles.

**Ejemplos medibles:**  
- RNF‑01 (Cobertura): Intensidad Wi‑Fi ≥ −67 dBm en salón y habitaciones 1 y 2.  
- RNF‑02 (Rendimiento): Latencia promedio a 8.8.8.8 ≤ 60 ms, pérdida ≤ 5 %.  
- RNF‑03 (Usabilidad): Impresión de una página A4 desde cualquier PC en ≤ 15 s.  
- RNF‑04 (Coste): Coste adicional de hardware ≤ 150 €.  
- RNF‑05 (Seguridad): La Wi‑Fi usará WPA2/WPA3 con contraseña de al menos 12 caracteres.

---

## **Restricciones** y **Supuestos**

- **Restricciones**: límites reales del proyecto (presupuesto, tiempo, obra civil, equipos existentes).  
  Ej.: “Se utilizará el router del ISP existente; no se permite cableado nuevo fuera de canaletas.”  
- **Supuestos**: condiciones que **se cree** que son ciertas y afectan al diseño.  
  Ej.: “La impresora puede conectarse por Ethernet o Wi‑Fi.”


---

## **Priorización** (Imprescindible / Deseable)

Clasifica cada RF/RNF en:  
- **Imprescindible**: si no se cumple, el objetivo no se considera logrado.  
- **Deseable**: mejora la calidad, pero se podría entregar sin ello.

**Técnica rápida:** marca “I” o “D” al final de cada requisito y justifica en 1 línea.

---

## **Criterios de Aceptación (CA)** y **Pruebas**

Cada requisito debe tener al menos un **CA** que indique **cómo** se verificará. Debe ser **objetivo y repetible**.

**Modelos de CA (para el caso):**  
- Para RF‑01 (Internet): “Desde cada equipo, ejecutar `ping 8.8.8.8 -n 20` (o `-c 20` en Linux). Éxito si pérdida ≤ 5 %.”  
- Para RF‑02 (Impresión): “Desde cada PC, imprimir ‘Página de prueba’. Éxito si se obtiene en ≤ 15 s.”  
- Para RNF‑01 (Cobertura): “Medir con app de análisis Wi‑Fi; éxito si RSSI ≥ −67 dBm en puntos definidos.”  
- Para RNF‑02 (Latencia): “`ping` de 30 s a `8.8.8.8`; promedio ≤ 60 ms.”  
- Para RNF‑05 (Seguridad): “La red exige WPA2/WPA3 y contraseña ≥ 12 caracteres.”

> **Consejo**: Evita CAs del tipo “probar si funciona”. Indica comando, duración y umbral de éxito.

---

## **Matriz de Trazabilidad** Requisito ↔ Prueba

Crea una tabla que relacione cada requisito con al menos un criterio de aceptación.

| Requisito | Criterio de aceptación vinculado | ¿Cumplido? |
|-----------|----------------------------------|------------|
| RF-01     | CA-01 (ping 20 paquetes)         | Sí/No      |
| RF-02     | CA-02 (página de prueba)         | Sí/No      |
| RNF-01    | CA-03 (RSSI ≥ −67 dBm)           | Sí/No      |

---

## Entregable del proyecto

Usando [la Ficha de Requisitos V1](https://docs.google.com/document/d/15XYdvNTYeuwKqG7BCrAWtBfALaQJ4Q5vrzLVDLNXVok/edit?usp=sharing), determina objetivos, alcance, requisitos, restricciones y criterios de aceptación del supuesto anterior, en grupos de 3-4 personas.

Crea una copia en tu unidad de Drive y una vez finalizada esta fase realiza su entrega en la tarea correspondiente de Moodle Centros.