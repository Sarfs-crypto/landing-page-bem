# Lumina — Landing Page con metodología BEM

Landing page completa para el producto **Lumina** (plataforma de productividad), desarrollada aplicando **todos los conceptos de BEM** aprendidos.

##  Demo en vivo

**Producción:** [https://project-lumina-blond.vercel.app](https://project-lumina-blond.vercel.app)

También puedes abrir `index.html` en el navegador de forma local.

##  Estructura del proyecto

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

## Conceptos BEM aplicados

- **Blocks** independientes y reutilizables (`btn`, `feature-card`, `pricing-card`…)
- **Elements** con nomenclatura `bloque__elemento`
- **Modifiers** para variaciones (`--highlighted`, `--recommended`, `--featured`, `--primary`)
- Archivos CSS organizados por componente
- Sin dependencias entre bloques

Consulta [DOCUMENTACION-BEM.md](./DOCUMENTACION-BEM.md) para el detalle completo de cada decisión de nomenclatura.

## Despliegue

[https://project-lumina-blond.vercel.app](https://project-lumina-blond.vercel.app)


