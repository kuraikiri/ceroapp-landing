# Cero — Landing Page

Landing page y política de privacidad para la app Cero.  
Diseñada para desplegarse en **GitHub Pages** con dominio personalizado `ceroapp.cl`.

## Archivos

| Archivo | Descripción |
|---------|-------------|
| `index.html` | Landing page principal |
| `privacidad.html` | Política de privacidad (requerida para Google Play) |
| `CNAME` | Configuración de dominio personalizado para GitHub Pages |

## Deploy en GitHub Pages

### 1. Crear repositorio en GitHub
```bash
git init
git add .
git commit -m "Initial landing page"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/ceroapp-landing.git
git push -u origin main
```

### 2. Activar GitHub Pages
1. Ve a **Settings** → **Pages** en tu repositorio
2. En **Source**, selecciona **Deploy from a branch**
3. Branch: `main`, carpeta: `/ (root)`
4. Click **Save**

Tu sitio estará disponible en `https://TU_USUARIO.github.io/ceroapp-landing/`

### 3. Configurar dominio personalizado `ceroapp.cl`

#### En tu registrador de dominio (NIC Chile o donde lo compres):
Agregar estos registros DNS:

**Registros A** (apuntar a GitHub Pages):
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**Registro CNAME** (para www):
```
www → TU_USUARIO.github.io
```

#### En GitHub:
1. Ve a **Settings** → **Pages**
2. En **Custom domain**, escribe `ceroapp.cl`
3. Click **Save**
4. Marca **Enforce HTTPS** (puede tomar unos minutos en activarse)

### 4. Configurar dominio en Proton Mail
1. En Proton Mail → Settings → **Nombres de dominio**
2. Click **Agregar dominio** → escribe `ceroapp.cl`
3. Sigue el asistente para agregar los registros MX y verificación TXT
4. Una vez verificado, crea tus correos: `soporte@ceroapp.cl`, `dev@ceroapp.cl`, etc.

> **Nota**: Los registros DNS de GitHub Pages (A records) y de Proton Mail (MX records) no entran en conflicto entre sí. Puedes tener ambos en el mismo dominio sin problema.

## Personalización

### Antes de publicar, revisa y ajusta:
- [ ] Los valores del ticker son de ejemplo — la app real los trae desde mindicador.cl
- [ ] El link de Google Play (actualmente `href="#"`) → reemplazar con el link real cuando la app esté publicada
- [ ] El correo `soporte@ceroapp.cl` — confirmar que ya está creado en Proton
- [ ] La fecha de la política de privacidad si la modificas

### Para agregar el badge oficial de Google Play:
Reemplaza los botones de "Descargar en Google Play" con la imagen oficial:
```html
<a href="https://play.google.com/store/apps/details?id=TU.PACKAGE.NAME">
  <img alt="Disponible en Google Play" 
       src="https://play.google.com/intl/es-419/badges/static/images/badges/es-419_badge_web_generic.png" 
       height="60">
</a>
```

## Stack
- HTML + CSS vanilla (sin dependencias)
- Google Fonts: DM Sans + JetBrains Mono
- Responsive design
- Scroll animations con IntersectionObserver
- Sin JavaScript frameworks — carga instantánea
