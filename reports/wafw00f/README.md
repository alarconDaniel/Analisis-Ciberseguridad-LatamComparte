<div align="center">

# 🛡️ Wafw00f — Detección de Web Application Firewall

![Wafw00f](https://img.shields.io/badge/Wafw00f-WAF_Detection-7C3AED?style=for-the-badge&logo=shield&logoColor=white)
![Target](https://img.shields.io/badge/Objetivo-latinoamericacomparte.com-0A66C2?style=for-the-badge)
![Fecha](https://img.shields.io/badge/Fecha-20%20mayo%202026-16A34A?style=for-the-badge)

</div>

---

## 📋 Ficha de la prueba

| Campo | Contenido |
|---|---|
| **ID** | WEB-003 |
| **Herramienta** | Wafw00f |
| **Tipo de prueba** | Detección de Web Application Firewall |
| **Objetivo** | https://latinoamericacomparte.com |
| **Solicitudes realizadas** | 7 |
| **Severidad máxima** | ⚪ Baja / Informativa |

---

## 💻 Comando ejecutado

```bash
wafw00f https://latinoamericacomparte.com | tee reporte_wafw00f_latam.txt
```

---

## 📊 Resultado obtenido

```
No WAF detected by the generic detection.
```

---

## 🔍 Hallazgo

| Campo | Detalle |
|---|---|
| **Respuesta esperada** | Identificar presencia de WAF, CDN o mecanismo de protección perimetral |
| **Respuesta obtenida** | No WAF detected by the generic detection — 7 solicitudes realizadas |
| **Impacto** | La ausencia de detección puede indicar que el sitio no cuenta con una capa adicional visible de protección frente a ataques web automatizados |
| **Severidad** | ⚪ Baja / Informativa |
| **Recomendación** | Evaluar implementación de WAF (Cloudflare, ModSecurity). Reforzar con cabeceras HTTP, validación de entradas y monitoreo de tráfico |

> ⚠️ La ausencia de detección **no confirma de forma absoluta** que el sitio carezca de controles de seguridad internos o a nivel de hosting. Wafw00f opera mediante detección de firmas conocidas.

---

## 📝 Conclusión

Wafw00f no identificó ningún WAF reconocible sobre el sitio objetivo. Esto sugiere que no existe una capa de protección perimetral web visible mediante técnicas de detección estándar. Se recomienda evaluar la implementación de un WAF para mitigar ataques automatizados como XSS, inyección SQL y abuso de formularios, especialmente si el portal maneja sesiones autenticadas o datos de usuarios.

---

## 🗂️ Archivos en esta carpeta

| Archivo | Descripción |
|---|---|
| `Wafw00f.txt` | Resultado completo exportado con `tee` |
| `EVID-WEB-WAF-01.png` | Captura de terminal con resultado: No WAF detected by the generic detection |

---

<div align="center">

[← Volver al repositorio principal](../../README.md)

</div>
