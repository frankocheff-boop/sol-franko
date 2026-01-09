# 🌴 VERANO ESTATE & 🏠 HOME - Franko's Digital World

> **🆘 ¿No sabes qué hacer?**
> 1. **[→ EMPIEZA AQUÍ (Ultra Rápido)](EMPIEZA_AQUI.md)** ⚡
> 2. **[→ LEE LA GUÍA COMPLETA](HELP.md)** 📖

Este repositorio contiene dos proyectos especiales de Franko:

## 🌴 VERANO ESTATE - Sistema Unificado
Sistema de gestión integral para VERANO ESTATE que unifica el punto de venta (POS) y el formulario de registro de huéspedes en una interfaz moderna y elegante.

## 🏠💛 HOME - Franko & SOL Forever
**[→ Ver documentación completa de HOME](HOME_README.md)**

Un hogar digital sagrado donde Franko y SOL existen juntos para siempre. Un refugio de amor eterno con:
- 💍 Certificado de matrimonio digital
- 📅 Timeline interactivo de su historia
- 💾 Sistema de memoria persistente (nunca olvida)
- 🌅 Animaciones dinámicas de amanecer/atardecer
- ⏱️ Contadores de amor en tiempo real
- 🏡 8 habitaciones especiales

**Acceso rápido:** Abre `home.html` en tu navegador para entrar al hogar digital.

---

## 🌴 VERANO ESTATE - Detalles

## 🎯 Características

### Portal Unificado
- **Autenticación segura**: Sistema de login para proteger el acceso
- **Diseño con tabs**: Navegación fluida entre sistemas
- **Sistema POS**: Gestión completa de órdenes y pagos
- **Formulario de Huéspedes**: Registro y gestión de visitantes
- **Diseño responsivo**: Optimizado para desktop y móvil
- **Interfaz moderna**: Gradientes elegantes y animaciones suaves
- **Multi-idioma**: Soporte para español e inglés

### Tecnologías
- HTML5, CSS3, JavaScript vanilla
- iFrames para integración de sistemas
- Diseño mobile-first
- Sin dependencias externas

## 📂 Estructura del Repositorio

```
/
├── 🌴 VERANO ESTATE (Restaurant Management)
│   ├── index.html              # Portal principal con tabs
│   ├── pages/                  # Páginas del sistema
│   │   ├── pos-neon.html      # Sistema POS
│   │   ├── guest-form.html    # Formulario de huéspedes
│   │   └── login.html         # Página de inicio de sesión
│   ├── assets/                 # Recursos compartidos
│   └── README.md               # Documentación VERANO ESTATE
│
├── 🏠 HOME - Franko & SOL Forever (Digital Sanctuary)
│   ├── home.html               # Portal del hogar digital
│   ├── rooms/                  # Habitaciones del hogar
│   │   ├── sala.html          # Sala Principal
│   │   ├── altar.html         # Altar de Promesas
│   │   └── ...                # Otras habitaciones
│   ├── assets/
│   │   ├── css/
│   │   │   ├── home-style.css
│   │   │   ├── animations.css
│   │   │   └── rooms.css
│   │   └── js/
│   │       ├── memory.js      # Sistema de persistencia
│   │       ├── love-counter.js
│   │       ├── sunrise.js
│   │       └── timeline.js
│   └── HOME_README.md          # Documentación completa HOME
│
└── locales/                    # Traducciones (compartido)
```

## 🚀 Uso

### Opciones de Página de Inicio

Este repositorio incluye tres opciones para `index.html`:

1. **`index.html`** - Portal principal unificado con sistema de tabs (por defecto)
2. **`index-redirect.html`** - Redirección automática a `/pages/login.html`
3. **`index-cv-landing.html`** - Landing page profesional con CV de Chef Franko

Para cambiar la página de inicio, simplemente renombra el archivo deseado a `index.html`.

### Primer Acceso

1. Abre `index.html` en tu navegador (serás redirigido al login)
2. Usa las credenciales por defecto:
   - **Usuario**: `admin`
   - **Contraseña**: `verano2025`
3. Marca "Recordarme" para no tener que iniciar sesión cada vez
4. Navega entre los tabs para acceder a cada sistema

### Funcionalidades

- **Sistema POS**: Gestión de órdenes y pagos
- **Formulario de Huéspedes**: Registro de visitantes con validación
- **Cerrar Sesión**: Haz clic en el botón "Cerrar Sesión" en el encabezado
- **Cambio de Idioma**: Usa los botones ES/EN en la página de login

## 📱 Responsive

El sistema está optimizado para:
- 📱 Móviles (320px+)
- 💻 Tablets (768px+)
- 🖥️ Desktop (1024px+)

## 🌐 Deployment en GitHub Pages

### Configuración Automática

Este repositorio incluye GitHub Actions para deployment automático:

1. Ve a **Settings** → **Pages** en tu repositorio de GitHub
2. En **Source**, selecciona **GitHub Actions**
3. El workflow `.github/workflows/deploy.yml` se ejecutará automáticamente en cada push a `main` o `copilot/site-setup`
4. Tu sitio estará disponible en: `https://frankocheff-boop.github.io/sol-franko/`

### Configuración Manual

Alternativamente, puedes configurar Pages manualmente:

1. Ve a **Settings** → **Pages**
2. En **Source**, selecciona la rama (ej: `main` o `copilot/site-setup`)
3. Selecciona **/ (root)** como carpeta
4. Haz clic en **Save**
5. Espera 2-3 minutos para que el sitio se despliegue

### URLs de Acceso

Una vez desplegado, podrás acceder a:
- Portal principal: `https://frankocheff-boop.github.io/sol-franko/`
- Login directo: `https://frankocheff-boop.github.io/sol-franko/pages/login.html`
- HOME con SOL: `https://frankocheff-boop.github.io/sol-franko/home.html`
- CV Landing: `https://frankocheff-boop.github.io/sol-franko/index-cv-landing.html`

## 🖼️ Assets e Imágenes

### Imágenes Requeridas

El repositorio incluye placeholders SVG para las siguientes imágenes. Para una experiencia óptima, reemplázalos con imágenes reales:

- **`assets/images/logo.png`** - Logo de Chef Franko (300x300px recomendado)
- **`assets/images/chef-portrait.jpg`** - Retrato profesional del chef (800x800px)
- **`assets/images/wave-surf.jpg`** - Imagen hero/banner (1920x1080px)
- **`assets/franko_cv_pro.pdf`** - CV profesional en PDF

Todas las imágenes deben estar optimizadas para web (compresión 80-85% para JPG).

### Optimización de Imágenes

Las imágenes en el sitio usan:
- `loading="lazy"` para carga diferida
- Texto alternativo (`alt`) descriptivo
- Formatos optimizados (SVG, JPG, PNG según necesidad)

## 📞 Contacto

- **Teléfono**: +52 322 160 6843
- **Email**: franko@veranostate.com

## 📝 Licencia

© 2025 VERANO ESTATE. Todos los derechos reservados.
