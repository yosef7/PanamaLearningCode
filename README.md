# Panama Learning Code — sitio estático mínimo

Este repositorio contiene una página estática mínima que muestra únicamente el nombre de la ONG.

## Despliegue con GitHub + Netlify

Requisitos:

- Cuenta de GitHub
- Cuenta de Netlify
- Dominio registrado en Namecheap

### 1) Subir el código a GitHub

Si aún no tienes un repositorio remoto:

```bash
# En la carpeta del proyecto
git init
git add .
git commit -m "Inicial: sitio estático"
# Crea un repo vacío en GitHub y luego:
git remote add origin git@github.com:TU_USUARIO/PanamaLearningCode.git
git push -u origin main
```

### 2) Conectar el repo en Netlify

- En Netlify: “Add new site” → “Import an existing project”.
- Conecta con GitHub y selecciona este repositorio.
- Build command: (dejar vacío)
- Publish directory: `.` (raíz del repo)
- Deploy site.

> El archivo `netlify.toml` ya fija `publish = "."` para que Netlify despliegue desde la raíz.

### 3) Añadir tu dominio personalizado en Netlify

- En la página del sitio en Netlify: Site settings → Domain management → Add domain → escribe tu dominio (por ejemplo, `panamalearningcode.org`).
- Netlify te mostrará las instrucciones DNS para `www` y el dominio raíz.

### 4) Configurar DNS en Namecheap (usando Namecheap DNS)

Opción A — Mantener Namecheap como DNS:

- Registros A (host `@`):
  - `75.2.60.5`
  - `99.83.190.102`
- Registro CNAME (host `www`): apunta a tu subdominio de Netlify, por ejemplo: `TU-SITIO.netlify.app`.

Opción B — Usar Netlify DNS (delegar):

- En Netlify, activa Netlify DNS para tu dominio.
- En Namecheap cambia los nameservers a los que Netlify indique.

### 5) HTTPS

- En Netlify, Domain management → Enable HTTPS → emitir certificado Let’s Encrypt (normalmente se activa automáticamente al validar DNS).

## Estructura

- `index.html`: página con el nombre.
- `netlify.toml`: configura la carpeta de publicación en Netlify.

## Personalización futura

- Agregar logotipo, paleta de colores, secciones o enlaces de contacto cuando se necesite.

```text
Hecho con ❤️ para Panama Learning Code
```
