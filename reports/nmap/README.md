<div align="center">

# 🗺️ Nmap — Reconocimiento de puertos y servicios

![Nmap](https://img.shields.io/badge/Nmap-Reconocimiento-4B8BBE?style=for-the-badge&logo=linux&logoColor=white)
![Target](https://img.shields.io/badge/Objetivo-latinoamericacomparte.com-0A66C2?style=for-the-badge)
![Fecha](https://img.shields.io/badge/Fecha-20%20mayo%202026-16A34A?style=for-the-badge)

</div>

---

## 📋 Ficha de la prueba

| Campo | Contenido |
|---|---|
| **ID** | WEB-002 |
| **Herramienta** | Nmap |
| **Tipo de prueba** | Reconocimiento de puertos y servicios |
| **Objetivo** | latinoamericacomparte.com |
| **IP resuelta** | 64.202.187.143 |
| **Latencia** | ~0.11s |
| **Severidad máxima** | 🔵 Baja / Informativa |

---

## 💻 Comando ejecutado

```bash
nmap -sV -sC -p 80,443 latinoamericacomparte.com -oN reporte_nmap_latam.txt
```

---

## 🔍 Matriz de hallazgos

| ID | Puerto | Estado | Servicio | Información detectada | Severidad |
|---|---|---|---|---|---|
| NMAP-001 | 80/tcp | Abierto | HTTP | Apache httpd | ⚪ Informativa |
| NMAP-002 | 443/tcp | Abierto | SSL/HTTP | Apache httpd con certificado SSL activo | 🔵 Baja / Informativa |
| NMAP-003 | 443/tcp | Abierto | Certificado SSL | CN: `www.latinoamericacomparte.com` — SAN: autodiscover, cpanel, webdisk, webmail, dominio raíz, www | 🔵 Baja |
| NMAP-004 | Host | Activo | DNS/rDNS | IP `64.202.187.143` — rDNS: `ip-64-202-187-143.ip.secureserver.net` | ⚪ Informativa |

---

## 🔐 Datos del certificado SSL detectado

| Campo | Valor |
|---|---|
| **Common Name (CN)** | www.latinoamericacomparte.com |
| **SANs detectados** | autodiscover, cpanel, webdisk, webmail, latinoamericacomparte.com, www |
| **Válido desde** | 2026-04-07 |
| **Válido hasta** | 2026-07-06 |

> ⚠️ Los subdominios administrativos expuestos en el SAN del certificado (`cpanel`, `webmail`, `webdisk`) pueden facilitar reconocimiento técnico.

---

## 📝 Conclusión

El reconocimiento con Nmap confirmó que el dominio está activo y resuelve hacia la IP `64.202.187.143`. Los puertos 80 y 443 están abiertos ejecutando Apache httpd. Los hallazgos se clasifican como informativos/bajos, ya que corresponden al funcionamiento esperado de un sitio público. Se recomienda forzar redirección HTTP → HTTPS, configurar HSTS, reducir exposición del encabezado `Server` y validar el acceso a subdominios administrativos antes del vencimiento del certificado el **06/07/2026**.

---

## 🗂️ Archivos en esta carpeta

| Archivo | Descripción |
|---|---|
| `nmap_latComparte.txt` | Resultado completo del escaneo exportado con `-oN` |
| `EVID-WEB-NMAP-01.png` | Captura de terminal con el resultado del escaneo |

---

<div align="center">

[← Volver al repositorio principal](../../README.md)

</div>
