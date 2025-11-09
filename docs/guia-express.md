# Guía Express – Activación Automática (Prepago) (versión ejecutiva)

Última actualización: 9 nov 2025 · Versión 1.0

---

## 1) Contexto y disparador

Situación inicial: el proceso de activación de líneas prepagas requería pre-aprovisionamiento con numeración real. Esto implicaba costos por suscripción en sistemas y uso anticipado de rangos numéricos asignados por el regulador (SUBTEL).

Problema: uso ineficiente de numeración y riesgo de sanciones regulatorias al acercarse al límite de rangos disponibles.

Gatillante: advertencia formal del regulador de no entregar más rangos si no se resolvía el sobreuso.

Solicitante: áreas involucradas incluyeron Revenue Assurance, Logística, Ingeniería de Red, Legal, CX, Canales de Venta, y más. Desarrollo de Productos (autor) actuó como enlace funcional y de coordinación.

---

## 2) Problema de negocio (antes)

* Se provisionaban SIMs con numeración real sin certeza de activación.
* Se pagaban licencias y subscripciones aún si no se usaba la línea.
* Limitación del recurso numérico = cuello de botella para ventas.

---

## 3) Alcance y restricciones

Objetivo: permitir activación solo al primer evento real de uso (no antes), sin comprometer numeración ni incurrir en costos innecesarios.

Restricción: debía mantenerse el orden de integración de aprovisionamiento (Siebel → BSCS → ICC), cumpliendo con las reglas de red.

Must-have del release:

* Alta solo cuando el cliente usa por primera vez la línea.
* Validación cruzada entre SIM y numeración dummy.
* Aprovisionamiento dinámico en sistemas productivos.
* GUI interna para gestión post-venta (acciones y perfiles).

---

## 4) Enfoque

Solución técnica del proveedor:
Captura del primer intento de conexión de la SIM → búsqueda en base dummy → si coincide, aprovisionamiento real vía APIs en orden técnico (Siebel CRM, BSCS CX, ALU 8610 ICC).

Rol del autor (PO funcional):
Apoyo en validación de procesos, articulación con áreas internas, planificación, y liberación. El trabajo base fue impulsado por Ingeniería, pero la gestión y coordinación para puesta en producción requirió intervención activa desde el rol funcional.

---

## 5) Go-live y validación

Validación previa:

* Pruebas en ambientes pre-productivos y apuntando a sistemas reales.
* Batería funcional completa: recargas, compras, saldo, autoservicio, estrés.
* Se utilizaron ~1.000 SIMs para prueba controlada.

Go-live: marzo 2017 (liberación postergada desde nov 2016 por peak comercial en diciembre).

Monitoreo post: seguimiento directo en producción. Sin incidentes críticos.

---

## 6) Resultados (después)

* Resolución completa del bloqueo de stock por numeración.
* Incremento de líneas prepago disponibles para la venta.
* Cumplimiento regulatorio y habilitación de ventas en todos los canales.

**TTGL**: funcionalidad lista en noviembre 2016.
**TTV**: activación inmediata a partir del uso real (primer evento).
**Impacto**: permitió continuar operación sin nuevas sanciones ni inversiones adicionales.

---

## 7) Aprendizajes

Lo que funcionó:

* Solución técnica eficiente y estable desde la primera versión.
* Integración ordenada con sistemas core y GUI funcional.

Lo que se puede mejorar:

* Mayor involucramiento funcional desde el inicio.
* Comunicación más fluida entre proveedor y áreas internas.
* El autor tuvo que intervenir de emergencia para resolver bloqueos por falta de articulación previa.

---

## Anexo A: Línea de sistemas (para CV/RFP)

Oracle Siebel CRM, Ericsson BSCS CX, ALU 8610 ICC, Sistema Activación Automática (custom), GUI postventa

---

## Anexo B: “Elevator pitch” (3–4 líneas)

Se implementó un sistema de activación automática para prepago, eliminando la necesidad de pre-aprovisionamiento y uso anticipado de numeración. Al detectar el primer uso real de una SIM, se ejecuta el alta con numeración válida y trazabilidad completa. Esto permitió destrabar stock, cumplir con el regulador y mantener la operación comercial sin interrupciones.
