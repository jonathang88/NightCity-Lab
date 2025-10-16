# NightCity-Lab

Repositorio con las anotaciones y archivos del laboratorio **NightCity** (CTF / laboratorio de hacking ético).

**Contenido**
- `notes/nightcity.txt`: Anotaciones paso a paso realizadas durante el laboratorio.
- `summary.md`: Resumen limpio y estructurado del laboratorio.
- `scripts/`: Scripts utilizados (plantillas).
- `evidence/`: Carpeta para evidencia sanitizada (capturas, outputs).
- `.gitignore`: Para evitar subir archivos sensibles.

> ⚠️ **Aviso ético**: Este repositorio contiene notas sobre técnicas de reconocimiento y enumeración. Está destinado a fines educativos y de aprendizaje en entornos controlados. No uses estas técnicas contra sistemas sin autorización explícita.

## Cómo usar
1. Clona el repositorio localmente:
```bash
git clone <URL-de-tu-repo>.git
cd NightCity-Lab
```

2. Revisa `notes/nightcity.txt` para ver las anotaciones completas.

3. Añade o elimina evidencia en `evidence/` según necesites. Asegúrate de no subir credenciales ni datos sensibles.

## Estructura
```
NightCity-Lab/
├── README.md
├── notes/
│   └── nightcity.txt
├── scripts/
│   └── Auditoria_Reconocimiento_Dispositivos.sh
├── evidence/
│   └── README.md
├── summary.md
└── .gitignore
```

## Comandos útiles para subir a GitHub
```bash
# Inicializar repo local
git init
git add .
git commit -m "Initial commit - NightCity lab notes"

# Crear repo remoto (en GitHub) y vincularlo (usa GitHub web o gh CLI)
# Con gh CLI:
# gh repo create <tu-usuario>/NightCity-Lab --public --source=. --remote=origin

git remote add origin git@github.com:<tu-usuario>/NightCity-Lab.git
git push -u origin main
```
