# Lumina — Landing Page con metodología BEM

Landing page completa para el producto **Lumina** (plataforma de productividad), desarrollada aplicando **todos los conceptos de BEM** aprendidos.

## 🚀 Demo

Abre `index.html` en el navegador o despliega en Vercel / Netlify / InfinityFree.

## 📁 Estructura del proyecto

```
landing-page-bem/
├── index.html              # HTML completo
├── css/
│   ├── base.css            # Reset, variables y bloque .btn
│   ├── header.css          # Bloque header
│   ├── hero.css            # Bloque hero
│   ├── features.css        # Bloques features + feature-card
│   ├── testimonials.css    # Bloques testimonials + testimonial-card
│   ├── pricing.css         # Bloques pricing + pricing-card
│   ├── contact.css         # Bloques contact + contact-form
│   └── footer.css          # Bloque footer
├── DOCUMENTACION-BEM.md    # Justificación de decisiones BEM
└── README.md
```

## ✅ Requisitos cumplidos

| Sección | Contenido |
|---------|-----------|
| **Header** | Logo, menú de navegación con estados hover, botón CTA |
| **Hero** | Título, subtítulo, fondo con gradiente, botones de acción |
| **Features** | 4 tarjetas (ícono + título + descripción), 1 con modificador destacado |
| **Testimonials** | 3 testimonios (avatar, nombre, cargo, comentario), 1 con diseño alternativo |
| **Pricing** | 3 planes, plan recomendado con modificador, lista de features |
| **Contact** | Formulario (nombre, email, mensaje) con validación visual `:required` |
| **Footer** | Contacto, enlaces, redes sociales, copyright |

## 🎯 Conceptos BEM aplicados

- **Blocks** independientes y reutilizables (`btn`, `feature-card`, `pricing-card`…)
- **Elements** con nomenclatura `bloque__elemento`
- **Modifiers** para variaciones (`--highlighted`, `--recommended`, `--featured`, `--primary`)
- Archivos CSS organizados por componente
- Sin dependencias entre bloques

Consulta [DOCUMENTACION-BEM.md](./DOCUMENTACION-BEM.md) para el detalle completo de cada decisión de nomenclatura.

## 🛠 Cómo desplegar

### Vercel
1. Conecta el repositorio en [vercel.com](https://vercel.com)
2. Deploy automático

### Netlify
1. Arrastra la carpeta o conecta el repo en [netlify.com](https://www.netlify.com)

### InfinityFree
1. Sube los archivos por FTP al directorio `htdocs`

## 📄 Licencia

Proyecto educativo — Actividad práctica BEM.
