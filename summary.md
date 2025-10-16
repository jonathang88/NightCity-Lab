# Resumen del laboratorio NightCity

## 1) Reconocimiento (Recon)
- Herramientas usadas: Nmap, WhatWeb, Gobuster, Steghide, exiftool, strings.
- Comando nmap usado:
  `nmap -Pn --top-ports 200 -sV --version-light -T3 <TARGET>`
- Servicios encontrados:
  - 21/tcp: vsftpd
  - 22/tcp: OpenSSH
  - 80/tcp: Apache httpd
- Resultado from WhatWeb y Gobuster: páginas `/index.html`, `/gallery.html`, `/contact.html`, `/about.html`, `/robin`, `/secret`, `/images`, `/js`, `/robots.txt`.

## 2) Enumeración y análisis de archivos
- FTP anónimo permitido; existe `reminder.txt` con coordenadas GPS.
- Se analizaron imágenes en busca de esteganografía (`steghide`) y metadatos EXIF (se identificaron coordenadas y autor).
- Se encontró `robots.txt` con pista: "Robin has the key".

## 3) Explotación / Acceso
- Se usó steghide para extraer `pass.txt` desde `most-wanted.jpg` con la contraseña relacionada con la ubicación (ejemplo: `japon`).
- Se decodificó base64 para obtener una contraseña/flag parcial.
- Se accedió via SFTP con el usuario `joker` usando la contraseña encontrada.
- Se listaron home directories y se encontró `.joker` y `flag.txt` con la flag final: `Good job!! You just discovered the criminal!`

## 4) Post-explotación y evidencia
- Archivos relevantes guardados y sanitizados en `notes/` y `evidence/` (no incluyen credenciales reales).
- Recomendación: documentar cada paso con comandos exactos y outputs relevantes sanitizados.

## 5) Lecciones y recomendaciones
- Revisar permisos en FTP anónimo y archivos expuestos.
- Validar que las imágenes y metadatos no filtren información (EXIF/GPS).
- Mantener servicios (vsftpd, SSH, Apache) actualizados y configurados.

---

> Este resumen fue generado automáticamente a partir de las anotaciones originales (`notes/nightcity.txt`). Revisa el archivo `notes/nightcity.txt` para ver el detalle completo.
