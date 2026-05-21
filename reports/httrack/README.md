<div align="center">

# 🌐 HTTrack — Clonación pasiva del sitio web

![HTTrack](https://img.shields.io/badge/HTTrack-Site_Cloning-111827?style=for-the-badge&logo=internetexplorer&logoColor=white)
![Target](https://img.shields.io/badge/Objetivo-latinoamericacomparte.com-0A66C2?style=for-the-badge)
![Fecha](https://img.shields.io/badge/Fecha-20%20mayo%202026-16A34A?style=for-the-badge)

</div>

---

## 📋 Ficha de la prueba

| Campo | Contenido |
|---|---|
| **Herramienta** | HTTrack Website Copier |
| **Tipo de prueba** | Clonación local del sitio para inspección pasiva |
| **Objetivo** | https://latinoamericacomparte.com |
| **Propósito** | Análisis offline de estructura, recursos, rutas y archivos del sitio |
| **Severidad** | ⚪ Informativa |

---

## 🎯 Objetivo de la herramienta

**HTTrack** permite descargar una copia completa del sitio web para su inspección en un entorno local y controlado, sin necesidad de interactuar activamente con el servidor durante el análisis. Esto permite:

- Examinar la estructura de carpetas y archivos del sitio
- Revisar recursos estáticos (CSS, JS, imágenes, fuentes)
- Identificar rutas, endpoints y enlaces expuestos
- Detectar comentarios en código fuente
- Analizar dependencias externas y terceros cargados
- Revisar metadatos de archivos descargados

---

## 💻 Comando de referencia

```bash
httrack https://latinoamericacomparte.com -O ./sitio-clonado "+*.latinoamericacomparte.com/*" -v
```

---

## 📌 Consideraciones éticas

> ⚠️ La clonación del sitio se realizó **únicamente con fines de inspección pasiva** en el marco del laboratorio académico. No se modificó, comprometió ni accedió a información privada del servidor.

El uso de HTTrack se limita al análisis de recursos públicamente accesibles del sitio, equivalente a lo que cualquier navegador descarga al visitar la página.

---


---

<div align="center">

[← Volver al repositorio principal](../../README.md)

</div>
