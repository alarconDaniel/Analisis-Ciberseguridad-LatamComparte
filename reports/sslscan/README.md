<div align="center">

# 🔒 sslscan — Análisis de configuración TLS/SSL

![sslscan](https://img.shields.io/badge/sslscan-TLS%2FSSL_Analysis-16A34A?style=for-the-badge&logo=letsencrypt&logoColor=white)
![Target](https://img.shields.io/badge/Objetivo-latinoamericacomparte.com-0A66C2?style=for-the-badge)
![Fecha](https://img.shields.io/badge/Fecha-20%20mayo%202026-16A34A?style=for-the-badge)

</div>

---

## 📋 Ficha de la prueba

| Campo | Contenido |
|---|---|
| **ID** | WEB-004 |
| **Herramienta** | sslscan |
| **Tipo de prueba** | Análisis de configuración TLS/SSL |
| **Objetivo** | latinoamericacomparte.com |
| **IP del servidor** | 64.202.187.143 |
| **Severidad máxima** | 🔵 Baja / Informativa |

---

## 💻 Comando ejecutado

```bash
sslscan latinoamericacomparte.com | tee reporte_sslscan_latam.txt
```

---

## 📊 Estado de protocolos

| Protocolo | Estado |
|---|---|
| SSLv2 | ✅ Deshabilitado |
| SSLv3 | ✅ Deshabilitado |
| TLSv1.0 | ✅ Deshabilitado |
| TLSv1.1 | ✅ Deshabilitado |
| **TLSv1.2** | ✅ **Habilitado** |
| **TLSv1.3** | ✅ **Habilitado** |

---

## 🔐 Datos del certificado

| Campo | Valor |
|---|---|
| **Sujeto (CN)** | www.latinoamericacomparte.com |
| **Algoritmo de firma** | sha256WithRSAEncryption |
| **Longitud de llave** | RSA 2048 bits |
| **Válido desde** | 07/04/2026 |
| **Válido hasta** | ⚠️ 06/07/2026 |
| **SANs** | autodiscover, cpanel, webdisk, webmail, latinoamericacomparte.com, www |

---

## 🔍 Matriz de hallazgos

| ID | Hallazgo | Resultado | Severidad |
|---|---|---|---|
| SSL-001 | Protocolos inseguros (SSLv2, SSLv3, TLS1.0, TLS1.1) | ✅ Deshabilitados | ⚪ Positivo / Informativo |
| SSL-002 | Protocolos seguros (TLS1.2, TLS1.3) | ✅ Habilitados | ⚪ Positivo / Informativo |
| SSL-003 | Vulnerabilidad Heartbleed | ✅ No vulnerable en TLSv1.2 ni TLSv1.3 | ⚪ Positivo / Informativo |
| SSL-004 | Compresión TLS | ✅ Deshabilitada | ⚪ Positivo / Informativo |
| SSL-005 | Certificado digital | ⚠️ RSA 2048, SHA-256 — Vence 06/07/2026 | 🔵 Baja |
| SSL-006 | SANs del certificado | ⚠️ Incluye cpanel, webmail, webdisk y autodiscover | 🔵 Baja / Informativa |

---

## 📝 Conclusión

La configuración TLS del servidor es adecuada en términos generales: protocolos obsoletos deshabilitados, TLS 1.2 y 1.3 activos, sin Heartbleed y compresión TLS deshabilitada. Como punto de atención, el certificado **vence el 06/07/2026** y sus SANs exponen subdominios administrativos (`cpanel`, `webmail`, `webdisk`) que pueden facilitar reconocimiento. Se recomienda renovar el certificado con anticipación y complementar con HSTS.

---

## 🗂️ Archivos 

| Archivo | Descripción |
|---|---|
| `sslscan.txt` | Resultado completo exportado con `tee` |
| `EVID-WEB-SSLSCAN-01.png` | Protocolos TLS soportados y protocolos inseguros deshabilitados |
| `EVID-WEB-SSLSCAN-02.png` | Cifrados soportados y datos del certificado |

---

<div align="center">

[← Volver al repositorio principal](../../README.md)

</div>
