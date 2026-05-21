<div align="center">

<img src="docs/assets/logo-latinoamerica-comparte.png" alt="Logo Latinoamérica Comparte" width="180">

# 🔐 Análisis-Ciberseguridad-LatamComparte

### Laboratorio de Ciberseguridad y Seguridad Aplicada

![Cybersecurity](https://img.shields.io/badge/Cybersecurity-Lab-0A66C2?style=for-the-badge&logo=hackthebox&logoColor=white)
![Web Security](https://img.shields.io/badge/Web%20Security-Testing-111827?style=for-the-badge&logo=owasp&logoColor=white)
![AI Security](https://img.shields.io/badge/AI%20Security-Prompt%20Injection-7C3AED?style=for-the-badge&logo=openai&logoColor=white)
![Academic Project](https://img.shields.io/badge/Academic-Project-16A34A?style=for-the-badge&logo=googleclassroom&logoColor=white)

Repositorio académico para la documentación y análisis de pruebas de ciberseguridad aplicadas al portal **Latinoamérica Comparte** y al chatbot desarrollado durante el semestre.

**Repositorio:** https://github.com/alarconDaniel/Analisis-Ciberseguridad-LatamComparte

</div>

---

## 📌 Descripción general

**Análisis-Ciberseguridad-LatamComparte** es un repositorio orientado a documentar múltiples pruebas de seguridad realizadas sobre el ecosistema digital de **Latinoamérica Comparte**, incluyendo el portal web principal y el chatbot desarrollado como parte del proyecto académico.

El sitio principal analizado corresponde a:

**https://latinoamericacomparte.com/**

Se realizaron pruebas con diferentes herramientas de ciberseguridad para evaluar aspectos relacionados con reconocimiento, análisis de superficie expuesta, revisión de configuraciones, inspección de tráfico, escaneo de vulnerabilidades web y pruebas específicas contra el chatbot mediante técnicas de **Prompt Injection**.

Este repositorio reúne tanto la documentación del proceso como los reportes generados por las herramientas utilizadas.

---

## 🎯 Objetivo del laboratorio

Realizar un proceso documentado de evaluación de seguridad sobre el portal **Latinoamérica Comparte** y su chatbot asociado, utilizando herramientas reconocidas dentro del ámbito de la ciberseguridad, con el propósito de identificar riesgos, registrar evidencias y proponer oportunidades de mejora.

---

## 🧪 Alcance de las pruebas

El laboratorio contempla diferentes tipos de análisis y pruebas controladas:

- Reconocimiento inicial del sitio web.
- Identificación de servicios, puertos y tecnologías expuestas.
- Revisión de configuraciones SSL/TLS.
- Detección de posibles mecanismos de protección web.
- Análisis de tráfico HTTP/HTTPS.
- Escaneo automatizado de vulnerabilidades web.
- Inspección pasiva mediante clonación local del sitio.
- Evaluación de formularios, rutas y endpoints visibles.
- Pruebas de seguridad sobre el chatbot.
- Ejecución de ataques controlados de **Prompt Injection**.
- Registro de hallazgos, capturas, reportes y conclusiones.

---

## 🧰 Herramientas utilizadas

Las herramientas seleccionadas para el laboratorio fueron:

| Herramienta | Propósito principal | Reporte |
|---|---|---|
| **ZAP Proxy** | Escaneo y análisis de vulnerabilidades web. | [Ver reporte](./reports/zaproxy/) |
| **Nmap** | Reconocimiento de red, puertos y servicios expuestos. | [Ver reporte](./reports/nmap/) |
| **Wafw00f** | Identificación de posibles Web Application Firewalls. | [Ver reporte](./reports/wafw00f/) |
| **Sslscan** | Revisión de configuración SSL/TLS. | [Ver reporte](./reports/sslscan/) |
| **Burp Suite Community** | Interceptación, análisis y revisión manual de tráfico web. | [Ver reporte](./reports/burp-suite/) |
| **HTTrack** | Clonación local del sitio para inspección pasiva. | [Ver reporte](./reports/httrack/) |
| **Prompt Injection Scripts Python** | Ejecución de pruebas controladas contra el chatbot. | [Ver reporte](./reports/prompt-injection/) |
---

## 🤖 Seguridad del chatbot

Una parte importante del repositorio está enfocada en la evaluación de seguridad del chatbot desarrollado durante el semestre.

Las pruebas realizadas buscan analizar cómo responde el sistema ante instrucciones adversarias o intentos de manipulación del comportamiento esperado del modelo conversacional.

Algunas categorías evaluadas incluyen:

- Intentos de ignorar instrucciones previas.
- Solicitudes para revelar información interna.
- Inyección de instrucciones ocultas.
- Simulación de roles maliciosos.
- Prompts diseñados para modificar el comportamiento esperado.
- Patrones de evasión conversacional.
- Pruebas automatizadas mediante scripts en Python.

Estas pruebas permiten observar posibles riesgos asociados al uso de inteligencia artificial conversacional dentro de entornos web.

---

## 📁 Estructura del repositorio

```txt
Analisis-Ciberseguridad-LatamComparte/
│
├── docs/
│   ├── assets/
│   │   └── logo-latinoamerica-comparte.png   
│   │
│   └── documentacion-general.pdf 
│
├── reports/
│   ├── zaproxy/
│   ├── nmap/
│   ├── wafw00f/
│   ├── sslscan/
│   ├── burp-suite/
│   ├── httrack/
│   └── prompt-injection/
│
│
└── README.md
```

---

## 📚 Documentación

La documentación principal del laboratorio se encuentra en la carpeta:

```txt
docs/
```

En esta carpeta se almacenan el documento principal explicativo, donde se encuentra la metodología, evidencias, capturas, análisis y conclusiones relacionadas con las pruebas realizadas.

---

## 📊 Reportes y evidencias

Los reportes generados por las herramientas utilizadas se encuentran organizados en la carpeta:

```txt
reports/
```

Cada subcarpeta corresponde a una herramienta o tipo de prueba específica. Allí se almacenan archivos exportados, resultados de análisis, capturas y evidencias relevantes del proceso.

---

## 🧭 Metodología general

El laboratorio se desarrolló siguiendo una metodología organizada por fases:

### 1. Reconocimiento inicial

Se identificaron características generales del portal, rutas visibles, recursos públicos, tecnologías aparentes y estructura general del sitio.

### 2. Análisis de superficie expuesta

Se utilizaron herramientas como **Nmap**, **Wafw00f** y **Sslscan** para revisar servicios, configuraciones, posibles protecciones y elementos expuestos.

### 3. Análisis web

Con herramientas como **ZAP Proxy** y **Burp Suite Community**, se inspeccionó el tráfico web, las respuestas del servidor, formularios, rutas, endpoints y posibles comportamientos inseguros.

### 4. Clonación pasiva del sitio

Mediante **HTTrack** se generó una copia local del sitio con fines de inspección pasiva, evitando la interacción activa innecesaria con el servidor original.

### 5. Evaluación del chatbot

Se ejecutaron pruebas controladas de **Prompt Injection** utilizando patrones definidos y scripts en Python para analizar la robustez del chatbot frente a instrucciones adversarias.

### 6. Registro de hallazgos

Los resultados fueron documentados mediante reportes, capturas, archivos generados por herramientas y análisis escritos dentro de las carpetas `docs/` y `reports/`.

---

## 🛡️ Enfoque ético

> [!IMPORTANT]
> Este repositorio tiene un propósito exclusivamente académico, ético y formativo. Todas las pruebas deben realizarse únicamente sobre entornos autorizados, controlados o de uso permitido.

No se promueve ni se autoriza el uso de estas herramientas para afectar servicios, acceder a información privada, explotar sistemas o realizar actividades no autorizadas.

El análisis se enfoca en la identificación responsable de riesgos y en la mejora de la seguridad del sistema evaluado.

---

## 🧩 Componentes principales

### 🌐 Portal Latinoamérica Comparte

El portal web es el principal objetivo de análisis en las pruebas de seguridad web. Se revisan aspectos como estructura pública, recursos visibles, configuraciones, rutas, tráfico y posibles riesgos asociados a exposición de información.

### 🤖 Chatbot del proyecto

El chatbot desarrollado durante el semestre es evaluado desde una perspectiva de seguridad en inteligencia artificial, principalmente frente a intentos de manipulación mediante **Prompt Injection**.

### 📄 Documentación técnica

La carpeta `docs/` contiene el registro organizado del proceso, incluyendo metodología, evidencias, análisis y conclusiones.

### 📁 Reportes automatizados

La carpeta `reports/` almacena los resultados generados por herramientas como ZAP Proxy, Nmap, Wafw00f, Sslscan, Burp Suite, HTTrack y scripts de Prompt Injection.

---

## 👥 Integrantes

| Integrante |
|---|
| Jean Carlos Reyes Delgadillo |
| Daniel Esteban Alarcón Rojas |
| Nelson Felipe González Gordillo |
| Juan Esteban Silva Espejo |

---

## ⚠️ Aviso legal

Este repositorio no debe utilizarse para realizar pruebas sobre sistemas, servidores, aplicaciones o servicios sin autorización expresa.

El contenido aquí documentado tiene un enfoque educativo y busca fortalecer competencias en seguridad informática, análisis responsable y protección de sistemas digitales.

---

<div align="center">

## 🔐 Análisis-Ciberseguridad-LatamComparte

**Seguridad web, análisis responsable y protección de sistemas basados en inteligencia artificial.**

</div>
