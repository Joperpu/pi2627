# Proyecto 1 Parte 2 - Del requisito al diseño

**Objetivo de la sesión:** transformar la *Ficha de Requisitos v1* en un **Diseño v1** compuesto por

- un **diagrama de red** claro y 
- una **Hoja de decisiones de diseño** con justificaciones breves.

## ¿Qué significa “diseñar” aquí?
Diseñar es **proponer cómo** cumplir los requisitos: qué equipos intervienen, cómo se conectan,
qué direcciones usar, qué servicios hacen falta y por qué. No es ejecutar todavía; es **definir y justificar**.

## Elementos mínimos del diagrama
- Router/salida a Internet (gateway) y su función.
- Switch del aula y enlaces a puestos.
- 15 PCs (puedes agruparlos por bloques, p. ej., 01–05, 06–10, 11–15).
- Impresora de red con **IP fija**.
- (Opcional) Servidor de usuarios.
- Notas de direccionamiento: red, gateway, rango DHCP, IP fija impresora.
- (Opcional) VLANs y ACLs, si decidís segmentar.

## Normas de dibujo
- Usa **símbolos consistentes** (router, switch, PC, impresora).
- Etiqueta enlaces relevantes (hacia router, hacia impresora/servidor).
- Incluye un **título** y un **bloque de notas** con el plan de direccionamiento.
- Evita saturar: usa agrupaciones de PCs y leyenda.

## Hoja de decisiones de diseño (qué y por qué)
Redacta decisiones cortas con justificación: p. ej. “DHCP en router (sencillez de gestión); impresora IP fija .50 (descubrible y estable), etc.”.

## Coherencia requisito→diseño
Comprueba que **cada requisito** tiene un elemento de diseño que lo atiende (impresión en red → impresora IP fija; cobertura → ubicación/tecnología; seguridad Wi‑Fi → WPA2/WPA3).

## Entregables
- **Diagrama de red** (imagen o PDF).
- **Hoja de decisiones** (siguiendo la [ficha correspondiente](https://docs.google.com/document/d/1UIiYqt9voJIugczHqJBq6F_4GGD4Ob8ySGMbz5Gdd78/edit?usp=sharing)).

Sube estos archivos entregables en la tarea de Moodle Centros habilitada para tal efecto.