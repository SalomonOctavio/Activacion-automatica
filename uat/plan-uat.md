# Plan UAT – Activación Automática (Prepago)

## Objetivo

Validar funcionalidad completa de activación dinámica prepago, desde evento de red hasta provisión efectiva y postventa.

---

## Alcance

- Simulaciones controladas con ~1.000 SIMs.
- Pruebas en ambientes pre-productivos y apuntando a sistemas reales.
- Verificación de integración: CRM (Siebel), BSCS, ICC.
- Flujos considerados: alta, recarga, compra de bolsas, consulta de saldo, visualización en canales de autoservicio.

---

## Participantes

- Ingeniería de Red (pruebas técnicas)
- TI / QA
- Desarrollo de Productos (PO funcional)

---

## Escenarios críticos

- Activación al primer evento real (datos o voz).
- No activación en caso de SIM no reconocida.
- Coherencia en numeración y trazabilidad.
- Operaciones post-venta disponibles según perfil (GUI).

---

## Resultado esperado

100% de los escenarios críticos OK, sin bloqueantes.  
Incidentes menores deben estar documentados con workaround validado (si aplica).
