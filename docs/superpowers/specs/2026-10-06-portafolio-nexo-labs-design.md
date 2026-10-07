# Portafolio Nexo Labs — Design Spec

**Fecha:** 2026-10-06
**Autor:** Darwin Salinas
**Estado:** Aprobado para implementación

## Contexto y motivación

Darwin ha construido dos aplicaciones completas de punta a punta (entrenador-personal,
rastreo-encomiendas) además de herramientas internas en Temple (Forkcast, tablero de
destilería). Ha recibido señales de interés de terceros que vieron estos proyectos, pero
no tiene todavía un lugar único y profesional para mostrarlos a alguien que no lo conoce.

Esto es el primer paso concreto de un objetivo más amplio: convertir esta habilidad en un
negocio paralelo (side business, part-time, sin dejar Temple) que desarrolle herramientas
a medida para otras empresas. El cuello de botella identificado para conseguir los
primeros clientes reales es la falta de portafolio — no la falta de marca ni de canal de
prospección, que se abordarán después.

**Alcance de este spec:** únicamente el sitio de portafolio (landing page). La
formalización del negocio (legal, pricing detallado, canal activo de prospección de
leads) queda fuera de alcance y se definirá en un sub-proyecto posterior.

## Identidad de marca

- **Nombre:** Nexo Labs
- **Propuesta de valor (una frase):** "Convertimos procesos manuales en sistemas
  automatizados"
- **Estilo visual:** Dark Tech
  - Fondo navy oscuro: `#0b1220`
  - Acento cian eléctrico: `#22d3ee`
  - Texto secundario: `#94a3b8` / `#e2e8f0`
  - Tipografía: system-ui (sans-serif del sistema, sin fuente custom en v1)
- Validado con 3 mockups de estilo comparados (Dark Tech / Clean Minimal / Warm
  Professional) vía companion visual de brainstorming — Dark Tech fue la elección
  explícita del usuario.

## Estructura del sitio

Landing de una sola página (single-page), navegación por scroll, en este orden:

1. **Hero**
   - Nombre de marca + propuesta de valor
   - CTA: "Ver casos de estudio" (scroll a la sección de casos)

2. **Casos de estudio** (4 tarjetas, formato *problema → solución → resultado*)
   - *Gestión de pedidos para distribuidora de bebidas* — basado en Forkcast.
     **Anonimizado**: sin mencionar a Temple ni mostrar datos/marca reales.
   - *Tablero de control para destilería* — basado en el tablero de destilería.
     **Anonimizado**: mismo criterio que el anterior.
   - *App de seguimiento de entrenamiento y dieta* — basado en entrenador-personal.
     Puede usar el nombre del proyecto; es un proyecto personal sin restricción de
     confidencialidad.
   - *Plataforma de rastreo de encomiendas* — basado en rastreo-encomiendas.
     **Genérico**: sin mencionar al cliente real ("Envíos ETM"); describir como
     "empresa de encomiendas".

   Cada tarjeta debe responder en pocas líneas: qué problema manual resolvía, qué se
   construyó, y qué cambió para el negocio (ej. tiempo ahorrado, visibilidad ganada).

3. **Sobre mí**
   - Bio breve: quién es Darwin, su experiencia construyendo estas herramientas, por qué
     confiar en él para un proyecto a medida.

4. **Servicios / cómo trabajo**
   - Tipos de proyecto que toma (dashboards, apps a medida, automatización de procesos)
   - Proceso de trabajo en 3-4 pasos (ej. diagnóstico → propuesta → desarrollo →
     entrega/soporte)

5. **Contacto**
   - CTA final: botón con link directo a WhatsApp, con mensaje predefinido (ej. "Hola,
     vi tu portafolio y quiero contarte sobre un proyecto").

## Stack técnico

- HTML/CSS/JS estático, sin backend ni build tools ni frameworks.
- Hosteado gratis en GitHub Pages (subdominio tipo `usuario.github.io/nexo-labs`).
- Responsive, mobile-first — gran parte de los visitantes (dueños de PyME) va a entrar
  desde el celular.
- Sin dependencias externas de CDN pesadas; CSS y JS inline o en archivos propios del
  repo.

## Fuera de alcance (v1, YAGNI explícito)

- Formulario de contacto con backend propio (el link de WhatsApp cubre esta necesidad).
- Blog o sección de artículos.
- Dominio propio comprado (se evalúa más adelante, después de validar con los primeros
  contactos reales).
- Nombres reales de clientes/empleador en los casos anonimizados o genéricos.
- Multi-idioma (el sitio se lanza solo en español).
- Analytics/tracking de visitas (puede agregarse después si hace falta medir tráfico).

## Testing / verificación

Al no haber backend ni lógica de negocio, la verificación es manual:

- Revisar el sitio en mobile y desktop (Chrome DevTools + un dispositivo real).
- Verificar que los 4 links/CTAs funcionen (scroll a casos de estudio, link de
  WhatsApp con mensaje predefinido correcto).
- Revisar que ningún caso de estudio mencione a Temple o a Envíos ETM por nombre.
- Lighthouse rápido para performance/accesibilidad básica (sitio estático, debería ser
  alto sin esfuerzo extra).

## Próximos pasos (fuera de este spec)

Una vez lanzado el portafolio, los siguientes sub-proyectos a definir por separado son:
canal activo de prospección de clientes, definición de pricing/paquetes de servicio, y
eventualmente la formalización legal del negocio si el volumen de trabajo lo justifica.
