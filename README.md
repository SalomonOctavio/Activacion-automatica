# Activación Automática (TELCO, 2016–2017)

🧩 Caso real adaptado para portafolio profesional. Rol: Product Owner funcional (Desarrollo de Productos).  
👥 Coordinación con Ingeniería de Red, Revenue Assurance, CX, Logística, Canales, IT y Legal.

---

## 🎯 Objetivo

Eliminar el pre-aprovisionamiento de SIM prepago y evitar el uso anticipado de numeración real, mediante un sistema que activa automáticamente al primer evento de uso del cliente.

---

## ⚙️ Contexto

Antes: cada SIM debía estar previamente activada con número real, incurriendo en costos y agotando rangos de numeración regulados (SUBTEL).  
Advertencia del regulador: no se asignarían nuevos bloques si no se resolvía el sobreuso.  
Restricción operativa: mantener la secuencia técnica (CRM → BSCS → ICC).

---

## 🔧 Enfoque y decisiones clave

- Captura del primer intento de conexión desde red (negociación SIM).
- Validación cruzada entre SIM y número dummy.
- Aprovisionamiento dinámico en sistemas productivos (CRM, BSCS, ICC).
- GUI para gestión post-venta con perfiles diferenciados.
- Batería completa de pruebas: recargas, saldo, autoservicio, estrés.

---

## 📈 Resultados y métricas

| KPI                         | Línea base | Resultado | Notas                                      |
|----------------------------|------------|-----------|--------------------------------------------|
| **TTGL** (meses)           | —          | 4         | Lista en nov 2016, liberación mar 2017     |
| **TTV** (evento real)      | —          | Inmediato | Activación al primer uso real de la SIM    |
| SIMs bloqueadas por stock  | Alto       | 0         | Operación restituida en todos los canales  |

- Se destrabó la venta de prepago a nivel nacional.
- Se evitó sanción regulatoria y se optimizó uso de recursos técnicos.
- La solución fue considerada como modelo replicable para pospago.

---

## 🚀 Go-live y soporte

- UAT con ~1.000 SIMs.
- Validaciones funcionales y de estrés sobre producción.
- Go-live postergado a marzo 2017 por alta de ventas en diciembre.
- Monitoreo operativo sin incidentes.

---

## 📚 Artefactos incluidos

📁 `/diagrams`  
- [`flujo-activacion.mmd`](./diagrams/flujo-activacion.mmd): flujo desde evento de red hasta alta en sistemas.

📁 `/docs`  
- [`kpis.md`](./docs/kpis.md): definiciones de TTGL/TTV y estimaciones de impacto.

📁 `/uat`  
- [`plan-uat.md`](./uat/plan-uat.md): escenarios de prueba, canales y validaciones.  
- [`checklist-go-no-go.md`](./uat/checklist-go-no-go.md): criterios mínimos para liberación.

---

## 🧠 Aprendizajes

✅ Lo que funcionó:
- Modelo técnico sólido desde el primer release.
- API e integración modular replicable para otros casos.

🔧 Lo que se puede mejorar:
- Involucramiento funcional más temprano.
- Alineación previa entre proveedor y áreas internas para evitar cuellos.

---

🛈 **Nota:** Este caso ha sido adaptado para fines de portafolio profesional. Se han omitido nombres comerciales, cifras sensibles y detalles internos, manteniendo fiel el enfoque funcional, decisiones clave y resultados alcanzados en contexto real.

---

## 🤝 Créditos

Ingeniería de Red, TI, CX, Revenue Assurance, Legal y Canales.  
PO funcional: Desarrollo de Productos.

