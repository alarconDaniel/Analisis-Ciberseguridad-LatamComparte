<div align="center">

# ⚡ OWASP ZAP — Reporte de seguridad web

![ZAP](https://img.shields.io/badge/OWASP_ZAP-2.16.1-E44D26?style=for-the-badge&logo=owasp&logoColor=white)
![Target](https://img.shields.io/badge/Objetivo-latinoamericacomparte.com-0A66C2?style=for-the-badge)
![Fecha](https://img.shields.io/badge/Fecha-20%20mayo%202026-16A34A?style=for-the-badge)

</div>

---

## 📋 Ficha de la prueba

| Campo | Contenido |
|---|---|
| **ID** | WEB-001 |
| **Herramienta** | OWASP ZAP 2.16.1 |
| **Tipo de prueba** | Escaneo pasivo / análisis de configuración web |
| **Objetivo** | https://latinoamericacomparte.com |
| **Fecha de ejecución** | 20 de mayo de 2026 |
| **Severidad máxima** | 🟡 Media |

---

## 💻 Comando ejecutado

```bash
zaproxy -cmd -quickurl https://latinoamericacomparte.com -quickout reporte_zap_latam.html
```

---

## 📊 Resumen de alertas

| Riesgo | Cantidad |
|---|---|
| 🔴 Alto | 0 |
| 🟡 Medio | 4 |
| 🔵 Bajo | 5 |
| ⚪ Informativo | 2 |
| **Total** | **11** |

---

## 🔍 Matriz de hallazgos

| ID | Alerta | Riesgo | Cantidad | Impacto | Recomendación |
|---|---|---|---|---|---|
| ZAP-001 | Ausencia de Tokens Anti-CSRF | 🟡 Medio | 3 | Puede permitir ataques CSRF en formularios con sesión autenticada | Implementar tokens Anti-CSRF en formularios y solicitudes que modifiquen estado |
| ZAP-002 | Cabecera CSP no configurada | 🟡 Medio | 10 | Aumenta riesgo ante XSS e inyección de contenido | Definir política CSP restrictiva para scripts, estilos, imágenes y fuentes |
| ZAP-003 | Directory Browsing | 🟡 Medio | 6 | Puede permitir enumeración de archivos expuestos públicamente | Deshabilitar listado de directorios en Apache |
| ZAP-004 | Falta cabecera Anti-Clickjacking | 🟡 Medio | 3 | La página podría ser embebida en iframes maliciosos | Configurar `X-Frame-Options: DENY` o `frame-ancestors` en CSP |
| ZAP-005 | Divulgación de timestamps Unix | 🔵 Bajo | 1 | Aporta información para reconocimiento técnico | Evitar exponer timestamps internos en respuestas |
| ZAP-006 | Falta X-Content-Type-Options | 🔵 Bajo | 67 | Puede permitir interpretación incorrecta de tipos MIME | Configurar `X-Content-Type-Options: nosniff` |
| ZAP-007 | Scripts JavaScript entre dominios | 🔵 Bajo | 3 | Riesgo si un tercero es comprometido | Validar dominios externos y usar SRI cuando aplique |
| ZAP-008 | Falta HSTS | 🔵 Bajo | 74 | Navegador no queda obligado a usar HTTPS | Configurar `Strict-Transport-Security` con `max-age` e `includeSubDomains` |
| ZAP-009 | ZAP desactualizado | 🔵 Bajo | 1 | Puede no tener reglas de detección actualizadas | Actualizar OWASP ZAP antes de próximas ejecuciones |
| ZAP-010 | Aplicación Web Moderna | ⚪ Informativo | 3 | Hallazgo informativo — comportamiento dinámico del sitio | Usar AJAX Spider para rutas dinámicas |
| ZAP-011 | Revisar directivas de caché | ⚪ Informativo | 3 | Respuestas podrían almacenarse en caché de forma no deseada | Revisar `Cache-Control`, `Pragma` y `Expires` en contenido sensible |

---

## 📝 Conclusión

El análisis con OWASP ZAP no evidenció hallazgos de severidad alta. Sin embargo, se identificaron **4 alertas de riesgo medio** que deben priorizarse: ausencia de CSP, falta de tokens Anti-CSRF, Directory Browsing y ausencia de protección Anti-Clickjacking. Las 5 alertas de riesgo bajo corresponden principalmente a cabeceras de seguridad no configuradas (HSTS, X-Content-Type-Options) y dependencias externas de JavaScript.

---

## 🗂️ Archivos en esta carpeta

| Archivo | Descripción |
|---|---|
| `2026-05-20-ZAP-Report-.html` | Reporte completo exportado por OWASP ZAP |
| `EVID-WEB-ZAP-01.png` | Panel de alertas con 11 tipos de hallazgos |
| `EVID-WEB-ZAP-02.png` | Historial de peticiones HTTP capturadas |
| `EVID-WEB-ZAP-03.png` | Petición raw GET a latinoamericacomparte.com |
| `EVID-WEB-ZAP-04.png` | Respuesta HTTP del servidor |

---

<div align="center">

[← Volver al repositorio principal](../../README.md)

</div>
