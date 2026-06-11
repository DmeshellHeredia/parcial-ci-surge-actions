# Parcial CI — Surge.sh + GitHub Actions

Página web personal desplegada de forma automática mediante **integración continua (CI)**
con **GitHub Actions** y **Surge.sh**.

- **Estudiante:** Michael D Meshell Sanchez Heredia
- **Matrícula:** 2024-0063
- **Asignatura:** DevOps — 1er Parcial

## Descripción

Este proyecto consiste en una landing page personal hecha con **HTML, CSS interno y
JavaScript mínimo** (sin frameworks). Cada vez que se hace `push` a la rama `main`,
GitHub Actions ejecuta el flujo de integración continua y publica automáticamente la
página en Surge.sh.

## Sitio en vivo

https://michael-sanchez-2024-0063-ci.surge.sh

## Estructura del proyecto

```
.
├── .github/
│   └── workflows/
│       └── main.yaml   # Flujo de CI: instala Surge y despliega en cada push a main
├── CNAME               # Dominio de Surge: michael-sanchez-2024-0063-ci.surge.sh
├── index.html          # Página web (HTML + CSS interno + JS mínimo)
└── README.md
```

## ¿Cómo funciona la integración continua?

1. Se hace `push` a la rama `main`.
2. GitHub Actions inicia el workflow definido en `.github/workflows/main.yaml`.
3. El workflow clona el repositorio, instala Node.js e instala Surge (`npm install -g surge`).
4. Despliega el contenido en Surge.sh usando el dominio del archivo `CNAME`.

## Seguridad — GitHub Secrets

La autenticación con Surge **no expone credenciales** en el código. Se utilizan
**GitHub Secrets**, leídos como variables de entorno en el workflow:

| Secret         | Uso                                  |
| -------------- | ------------------------------------ |
| `SURGE_LOGIN`  | Correo de la cuenta de Surge         |
| `SURGE_TOKEN`  | Token de autenticación de Surge      |

Estos valores se configuran en GitHub en:
`Settings → Secrets and variables → Actions`.

## Tecnologías

HTML5 · CSS3 · JavaScript · Git · GitHub · GitHub Actions · Surge.sh · CI/CD
