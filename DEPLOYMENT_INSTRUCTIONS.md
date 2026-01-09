# 🚀 Instrucciones de Deployment - VERANO ESTATE & HOME

## 📋 Resumen de Archivos Creados

Esta guía documenta todos los archivos creados en la rama `copilot/site-setup` para facilitar el deployment del sitio.

## 📦 Archivos Nuevos

### Imágenes y Assets
- **`assets/images/logo.svg`** - Placeholder SVG para logo de Chef Franko
- **`assets/images/chef-portrait.svg`** - Placeholder SVG para retrato profesional
- **`assets/images/wave-surf.svg`** - Placeholder SVG para imagen hero/banner
- **`assets/franko_cv_pro.txt`** - Placeholder para CV en PDF

### Páginas HTML
- **`index-redirect.html`** - Versión de index.html que redirige automáticamente a `/pages/login.html`
- **`index-cv-landing.html`** - Landing page profesional con CV y portfolio de Chef Franko

### GitHub Actions
- **`.github/workflows/deploy.yml`** - Workflow para deployment automático en GitHub Pages

## 🔄 Opciones de index.html

El sitio ofrece tres opciones para la página principal:

### Opción 1: Portal Unificado (Actual)
```bash
# Ya configurado - no requiere cambios
# index.html es el portal principal con sistema de tabs
```
**Características:**
- Sistema de tabs para POS, Formularios, Cupones, Tickets
- Requiere autenticación
- Interfaz completa de gestión

### Opción 2: Redirección a Login
```bash
# Para usar la redirección automática al login:
mv index.html index-portal-original.html
mv index-redirect.html index.html
```
**Características:**
- Redirige inmediatamente a `/pages/login.html`
- Ideal si solo quieres el sistema de gestión sin landing page
- Más directo para usuarios frecuentes

### Opción 3: Landing Page Profesional
```bash
# Para usar el CV/Landing page:
mv index.html index-portal-original.html
mv index-cv-landing.html index.html
```
**Características:**
- CV profesional de Chef Franko
- Portfolio y galería
- Enlaces a sistema de gestión y HOME
- Ideal para presentación pública

## 🌐 Deployment en GitHub Pages

### Método 1: GitHub Actions (Recomendado)

Este método es automático y se ejecuta en cada push:

1. **Activar GitHub Pages con Actions**
   ```
   Repositorio → Settings → Pages → Source: GitHub Actions
   ```

2. **Verificar el Workflow**
   - El archivo `.github/workflows/deploy.yml` ya está configurado
   - Se ejecuta automáticamente en push a `main` o `copilot/site-setup`
   - También puede ejecutarse manualmente desde la pestaña "Actions"

3. **Acceder al Sitio**
   - URL base: `https://frankocheff-boop.github.io/sol-franko/`
   - Login: `https://frankocheff-boop.github.io/sol-franko/pages/login.html`
   - HOME: `https://frankocheff-boop.github.io/sol-franko/home.html`

### Método 2: Deployment Manual desde Rama

Si prefieres no usar Actions:

1. **Configurar Pages**
   ```
   Settings → Pages → Source: Deploy from a branch
   Branch: copilot/site-setup (o main)
   Folder: / (root)
   Save
   ```

2. **Esperar Deployment**
   - GitHub tarda 2-3 minutos en construir el sitio
   - Verás un mensaje con la URL cuando esté listo

3. **Verificar**
   - La URL será la misma: `https://frankocheff-boop.github.io/sol-franko/`

## 🖼️ Reemplazar Placeholders con Imágenes Reales

Los SVG placeholders deben reemplazarse con imágenes optimizadas:

### Logo (logo.png)
```bash
# Reemplazar el SVG con imagen real
# Tamaño recomendado: 300x300px
# Formato: PNG con transparencia
cp /ruta/a/tu/logo.png assets/images/logo.png
```

### Retrato del Chef (chef-portrait.jpg)
```bash
# Foto profesional del chef
# Tamaño recomendado: 800x800px
# Formato: JPG, calidad 80-85%
cp /ruta/a/tu/chef-portrait.jpg assets/images/chef-portrait.jpg
```

### Imagen Hero (wave-surf.jpg)
```bash
# Imagen de fondo/banner
# Tamaño recomendado: 1920x1080px
# Formato: JPG, calidad 80-85%
cp /ruta/a/tu/wave-surf.jpg assets/images/wave-surf.jpg
```

### CV en PDF
```bash
# CV profesional
# Formato: PDF
# Tamaño: < 5MB recomendado
cp /ruta/a/tu/franko_cv_pro.pdf assets/franko_cv_pro.pdf
```

**Nota:** Los placeholders SVG funcionan perfectamente mientras obtienes las imágenes reales. El sitio es completamente funcional con los placeholders.

## 🔧 Optimización de Imágenes

Para optimizar imágenes antes de subirlas:

### Usando ImageMagick (Línea de comandos)
```bash
# Optimizar JPG
convert input.jpg -quality 85 -resize 1920x1080 output.jpg

# Optimizar PNG
convert input.png -resize 300x300 output.png
```

### Usando Herramientas Online
- [TinyPNG](https://tinypng.com/) - Compresión inteligente de PNG y JPG
- [Squoosh](https://squoosh.app/) - Editor y compresor de imágenes
- [ImageOptim](https://imageoptim.com/) - Mac app para optimización

### Características ya Implementadas
Todas las imágenes en el sitio ya tienen:
- ✅ `loading="lazy"` para carga diferida
- ✅ Atributos `alt` descriptivos
- ✅ Dimensiones apropiadas en CSS

## 🔐 Credenciales por Defecto

**IMPORTANTE:** Después del deployment, considera cambiar las credenciales:

- **Usuario actual:** `admin`
- **Contraseña actual:** `verano2025`

Para cambiar las credenciales, edita: `assets/js/auth.js`

## ✅ Checklist Post-Deployment

Después de hacer deployment, verifica:

- [ ] El sitio carga correctamente en la URL de GitHub Pages
- [ ] Las páginas principales son accesibles:
  - [ ] `/` (index.html)
  - [ ] `/pages/login.html`
  - [ ] `/home.html`
- [ ] El sistema de autenticación funciona
- [ ] Los tabs en el portal principal funcionan correctamente
- [ ] Las imágenes cargan (aunque sean placeholders)
- [ ] El sitio es responsive (prueba en móvil)
- [ ] Los enlaces de contacto funcionan

## 📊 Monitoreo del Deployment

### Ver Estado del Deployment
1. Ve a la pestaña **Actions** en GitHub
2. Verás el historial de deployments
3. Click en cualquier workflow para ver detalles

### Logs de Deployment
```
Actions → Workflow run → Deploy to GitHub Pages → Deploy job
```

## 🐛 Troubleshooting

### El sitio no se despliega
- Verifica que GitHub Pages esté activado en Settings
- Revisa que el workflow tenga permisos de Pages (Settings → Actions → General → Workflow permissions)
- Asegúrate de que `.nojekyll` existe en la raíz

### Error 404 en recursos
- Verifica que las rutas sean relativas
- Si usas subdirectorios, asegúrate de que las rutas comiencen con `.` o `/sol-franko/`

### Imágenes no cargan
- Verifica que los archivos existen en la ubicación correcta
- Los placeholders SVG siempre deberían funcionar
- Revisa la consola del navegador para errores

### El workflow de Actions falla
- Ve a Actions → Workflow run para ver el error específico
- Verifica los permisos del repositorio
- Asegúrate de que el workflow tenga acceso a Pages

## 📝 Próximos Pasos

1. **Actualizar con Imágenes Reales**
   - Reemplaza los SVG placeholders con imágenes optimizadas
   - Sube el CV en PDF

2. **Personalizar Contenido**
   - Actualiza textos en `index-cv-landing.html` si usas esa opción
   - Ajusta información de contacto si es necesario

3. **Dominio Personalizado (Opcional)**
   - Puedes configurar un dominio personalizado en Settings → Pages
   - Agrega un archivo `CNAME` con tu dominio

4. **Seguridad**
   - Considera cambiar las credenciales por defecto
   - Evalúa implementar autenticación más robusta si es necesario

## 🎯 Resumen Rápido

**Para deployment inmediato:**
```bash
# 1. Asegúrate de estar en la rama correcta
git checkout copilot/site-setup

# 2. Sube los cambios (si hay alguno pendiente)
git push origin copilot/site-setup

# 3. Activa GitHub Pages
# Settings → Pages → Source: GitHub Actions

# 4. Espera 2-3 minutos

# 5. Visita: https://frankocheff-boop.github.io/sol-franko/
```

**Para reemplazar imágenes luego:**
```bash
# Agrega tus imágenes reales
cp /ruta/a/imagenes/* assets/images/

# Commit y push
git add assets/images/
git commit -m "Add optimized images"
git push origin copilot/site-setup
```

¡Listo! 🚀

---

**Soporte:**
- 📞 +52 322 160 6843
- ✉️ franko@veranostate.com

© 2025 VERANO ESTATE - Chef Franko
