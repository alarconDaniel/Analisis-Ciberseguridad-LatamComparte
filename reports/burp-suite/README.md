<div align="center">

# 🕷️ Burp Suite Community — Interceptación HTTP/HTTPS

![Burp](https://img.shields.io/badge/Burp_Suite-Community-E44D26?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZD0iTTEyIDJDNi40OCAyIDIgNi40OCAyIDEyIDIgMTcuNTIgNi40OCAyMiAxMiAyMiAxNy41MiAyMiAyMiAxNy41MiAyMiAxMiAyMiA2LjQ4IDE3LjUyIDIgMTIgMnoiIGZpbGw9IndoaXRlIi8+PC9zdmc+&logoColor=white)
![Target](https://img.shields.io/badge/Objetivo-latinoamericacomparte.com-0A66C2?style=for-the-badge)
![Fecha](https://img.shields.io/badge/Fecha-20%20mayo%202026-16A34A?style=for-the-badge)

</div>

---

## 📋 Ficha de la prueba

| Campo | Contenido |
|---|---|
| **ID** | WEB-005 |
| **Herramienta** | Burp Suite Community |
| **Tipo de prueba** | Interceptación y análisis pasivo HTTP/HTTPS |
| **Objetivo** | https://latinoamericacomparte.com |
| **IP del servidor** | 64.202.187.143 |
| **Método** | Navegación desde navegador integrado con proxy activo en el puerto 8080 |
| **Severidad máxima** | 🟡 Media |

---

## 💻 Método de ejecución

```
Navegación desde el navegador integrado de Burp Suite
Proxy activo en: 127.0.0.1:8080
```

---

## 📊 Solicitud capturada

```http
GET / HTTP/2
Host: latinoamericacomparte.com
→ HTTP/2 200 OK
→ Content-Type: text/html
→ Content-Length: 136239 bytes
→ IP: 64.202.187.143
→ Server: Apache
```

---

## 🔍 Matriz de hallazgos

| ID | Hallazgo | Evidencia observada | Impacto | Severidad | Recomendación |
|---|---|---|---|---|---|
| BURP-001 | Captura exitosa del tráfico HTTPS | GET / → HTTP/2 200 OK | Confirma disponibilidad del sitio | ⚪ Informativa | Mantener trazabilidad como evidencia |
| BURP-002 | Exposición del servidor web | Header `Server: Apache` | Facilita fingerprinting tecnológico | 🔵 Baja | Reducir u ocultar información del servidor en headers HTTP |
| BURP-003 | Ausencia de CSP | No se observa `Content-Security-Policy` en la respuesta | Aumenta riesgo ante XSS o recursos no autorizados | 🟡 Media | Implementar política CSP restrictiva |
| BURP-004 | Ausencia de HSTS | No se observa `Strict-Transport-Security` | Puede debilitar protección de transporte seguro | 🟡 Media | Configurar HSTS con `max-age`, `includeSubDomains` y evaluar `preload` |
| BURP-005 | Ausencia de Anti-Clickjacking | No se observa `X-Frame-Options` ni `frame-ancestors` | El sitio podría ser embebido en iframes maliciosos | 🟡 Media | Configurar `X-Frame-Options: SAMEORIGIN` o `frame-ancestors` en CSP |
| BURP-006 | Ausencia de X-Content-Type-Options | No se observa `X-Content-Type-Options: nosniff` | Puede permitir interpretación incorrecta de tipos MIME | 🔵 Baja | Agregar `X-Content-Type-Options: nosniff` |

---

## ⚠️ Nota adicional

Durante la captura también se observaron solicitudes hacia `colombiacomparte.com`, incluyendo rutas asociadas a WordPress como `/wp-admin/admin-ajax.php`. Estas entradas **no corresponden al dominio principal evaluado** y se consideran tráfico fuera del alcance de esta prueba.

---

## 📝 Conclusión

Burp Suite Community confirmó y complementó manualmente los hallazgos reportados por OWASP ZAP. La respuesta principal del sitio expone el servidor Apache y carece de cabeceras de seguridad fundamentales: CSP, HSTS, X-Frame-Options y X-Content-Type-Options. Estos hallazgos deben priorizarse en el plan de mitigación.

---

## 🗂️ Archivos

| Archivo | Descripción |
|---|---|
| `BurpSuiteLatComparte.xml` | Exportación del historial HTTP capturado por Burp Suite |
| `EVID-WEB-BURP-01.png` | Navegador integrado de Burp cargando el sitio con tráfico interceptado |
| `EVID-WEB-BURP-02.png` | Historial HTTP con solicitud GET / hacia latinoamericacomparte.com |
| `EVID-WEB-BURP-03.png` | Respuesta HTTP/2 200 OK con headers visibles |
| `EVID-WEB-BURP-04.png` | Tráfico hacia colombiacomparte.com — marcado como fuera de alcance |
| `EVID-WEB-BURP-05.png` | Recursos adicionales observados en Burp — evidencia complementaria |

---

<div align="center">

[← Volver al repositorio principal](../../README.md)

</div>
