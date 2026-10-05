# Documentación BEM — Landing Page Lumina

## ¿Qué es BEM?

**BEM** (Block, Element, Modifier) es una metodología de nomenclatura CSS que organiza el código de forma predecible, independiente y escalable.

- **Block**: componente independiente (`header`, `hero`, `feature-card`)
- **Element**: parte de un bloque (`header__logo`, `feature-card__title`)
- **Modifier**: variación de un bloque o elemento (`feature-card--highlighted`, `btn--primary`)

---

## Estructura de archivos CSS

```
css/
├── base.css          → Reset, variables CSS y bloque reutilizable `.btn`
├── header.css        → Bloque `.header`
├── hero.css          → Bloque `.hero`
├── features.css      → Bloques `.features` + `.feature-card`
├── testimonials.css  → Bloques `.testimonials` + `.testimonial-card`
├── pricing.css       → Bloques `.pricing` + `.pricing-card`
├── contact.css       → Bloques `.contact` + `.contact-form`
└── footer.css        → Bloque `.footer`
```

Cada archivo CSS corresponde a un componente (bloque) o a un grupo lógico de bloques relacionados. Esto facilita el mantenimiento y permite cargar solo lo necesario en proyectos más grandes.

---

## Inventario de bloques, elementos y modificadores

### 1. Bloque: `btn` (base.css)

| Clase | Tipo | Descripción |
|-------|------|-------------|
| `.btn` | Block | Botón base reutilizable |
| `.btn--primary` | Modifier | Estilo principal (fondo indigo) |
| `.btn--secondary` | Modifier | Estilo secundario (borde) |
| `.btn--lg` | Modifier | Tamaño grande |

**Decisión:** El botón es un bloque independiente porque se reutiliza en header, hero, pricing y contact. No depende de ningún contenedor.

---

### 2. Bloque: `header`

| Clase | Tipo | Descripción |
|-------|------|-------------|
| `.header` | Block | Cabecera fija |
| `.header__container` | Element | Contenedor interno |
| `.header__logo` | Element | Enlace del logo |
| `.header__logo-icon` | Element | Icono del logo |
| `.header__logo-text` | Element | Texto del logo |
| `.header__nav` | Element | Navegación |
| `.header__menu` | Element | Lista de menú |
| `.header__menu-item` | Element | Ítem de menú |
| `.header__link` | Element | Enlace de navegación |
| `.header__cta` | Element | Botón CTA del header |
| `.header__burger` | Element | Botón hamburguesa (móvil) |
| `.header__burger-line` | Element | Línea del icono hamburguesa |

**Decisión:** No se usó modificador para estados de hover/focus; se resolvieron con pseudo-clases (`:hover`, `:focus`) para no sobrecargar el HTML.

---

### 3. Bloque: `hero`

| Clase | Tipo | Descripción |
|-------|------|-------------|
| `.hero` | Block | Sección principal |
| `.hero__overlay` | Element | Capa decorativa de gradiente |
| `.hero__container` | Element | Contenedor centrado |
| `.hero__content` | Element | Contenido textual |
| `.hero__title` | Element | Título principal |
| `.hero__subtitle` | Element | Subtítulo |
| `.hero__actions` | Element | Contenedor de botones |

**Decisión:** El fondo oscuro se aplica al bloque. Los botones secundarios se ajustan con un selector de contexto (`.hero .btn--secondary`) porque el modificador del botón no conoce el fondo del padre. Esto es una excepción aceptable y documentada.

---

### 4. Bloque: `features` + `feature-card`

| Clase | Tipo | Descripción |
|-------|------|-------------|
| `.features` | Block | Sección de características |
| `.features__container` | Element | Contenedor |
| `.features__header` | Element | Cabecera de sección |
| `.features__title` | Element | Título |
| `.features__subtitle` | Element | Subtítulo |
| `.features__grid` | Element | Grid de tarjetas |
| `.feature-card` | Block | Tarjeta de característica (independiente) |
| `.feature-card--highlighted` | Modifier | Variación destacada |
| `.feature-card__badge` | Element | Badge "Más popular" |
| `.feature-card__icon` | Element | Contenedor del icono |
| `.feature-card__icon--blue` | Modifier | Color azul del icono |
| `.feature-card__icon--purple` | Modifier | Color púrpura |
| `.feature-card__icon--green` | Modifier | Color verde |
| `.feature-card__icon--orange` | Modifier | Color naranja |
| `.feature-card__title` | Element | Título de la tarjeta |
| `.feature-card__description` | Element | Descripción |

**Decisión clave:** `feature-card` es un **bloque independiente**, no un elemento de `features`. Esto permite reutilizar la tarjeta en otras secciones (por ejemplo, un blog o un dashboard) sin arrastrar estilos de `features`.

El modificador `--highlighted` marca la característica principal con borde, sombra y fondo sutil.

---

### 5. Bloque: `testimonials` + `testimonial-card`

| Clase | Tipo | Descripción |
|-------|------|-------------|
| `.testimonials` | Block | Sección de testimonios |
| `.testimonials__container` | Element | Contenedor |
| `.testimonials__header` | Element | Cabecera |
| `.testimonials__title` | Element | Título |
| `.testimonials__subtitle` | Element | Subtítulo |
| `.testimonials__grid` | Element | Grid |
| `.testimonial-card` | Block | Tarjeta de testimonio |
| `.testimonial-card--featured` | Modifier | Diseño alternativo (fondo gradient) |
| `.testimonial-card__quote` | Element | Texto del testimonio |
| `.testimonial-card__author` | Element | Contenedor de autor |
| `.testimonial-card__avatar` | Element | Imagen de avatar |
| `.testimonial-card__info` | Element | Nombre + cargo |
| `.testimonial-card__name` | Element | Nombre |
| `.testimonial-card__role` | Element | Cargo |

**Decisión:** Se crearon dos variaciones de diseño: la normal (fondo claro) y la `--featured` (fondo gradient). Los elementos internos adaptan color con selectores de contexto dentro del modificador, manteniendo el HTML limpio.

---

### 6. Bloque: `pricing` + `pricing-card`

| Clase | Tipo | Descripción |
|-------|------|-------------|
| `.pricing` | Block | Sección de precios |
| `.pricing__container` | Element | Contenedor |
| `.pricing__header` | Element | Cabecera |
| `.pricing__title` | Element | Título |
| `.pricing__subtitle` | Element | Subtítulo |
| `.pricing__grid` | Element | Grid de planes |
| `.pricing-card` | Block | Tarjeta de plan |
| `.pricing-card--recommended` | Modifier | Plan recomendado (escala + borde) |
| `.pricing-card__badge` | Element | Badge "Recomendado" |
| `.pricing-card__name` | Element | Nombre del plan |
| `.pricing-card__price` | Element | Contenedor de precio |
| `.pricing-card__amount` | Element | Cantidad |
| `.pricing-card__period` | Element | Periodo (/mes) |
| `.pricing-card__description` | Element | Descripción corta |
| `.pricing-card__features` | Element | Lista de características |
| `.pricing-card__feature` | Element | Ítem de característica |
| `.pricing-card__feature--disabled` | Modifier | Característica no incluida |
| `.pricing-card__btn` | Element | Botón del plan |

**Decisión:** El modificador `--recommended` aplica `scale(1.03)` y un borde de 2px para destacar visualmente el plan Pro. El modificador de elemento `--disabled` cambia el check por una ✕ y reduce la opacidad.

---

### 7. Bloque: `contact` + `contact-form`

| Clase | Tipo | Descripción |
|-------|------|-------------|
| `.contact` | Block | Sección de contacto |
| `.contact__container` | Element | Contenedor |
| `.contact__header` | Element | Cabecera |
| `.contact__title` | Element | Título |
| `.contact__subtitle` | Element | Subtítulo |
| `.contact-form` | Block | Formulario (independiente) |
| `.contact-form__group` | Element | Grupo label + input |
| `.contact-form__label` | Element | Etiqueta |
| `.contact-form__input` | Element | Input de texto |
| `.contact-form__textarea` | Element | Textarea |
| `.contact-form__error` | Element | Mensaje de error |
| `.contact-form__submit` | Element | Botón de envío |

**Decisión:** La validación visual usa `:user-invalid` (y fallback con `:invalid:not(:placeholder-shown)`). No se necesita JavaScript para mostrar errores básicos de campos `required`.

---

### 8. Bloque: `footer`

| Clase | Tipo | Descripción |
|-------|------|-------------|
| `.footer` | Block | Pie de página |
| `.footer__container` | Element | Contenedor |
| `.footer__top` | Element | Zona superior |
| `.footer__brand` | Element | Logo + tagline |
| `.footer__logo` | Element | Logo |
| `.footer__logo-icon` | Element | Icono |
| `.footer__logo-text` | Element | Texto |
| `.footer__tagline` | Element | Eslogan |
| `.footer__links` | Element | Contenedor de columnas |
| `.footer__column` | Element | Columna de enlaces |
| `.footer__column-title` | Element | Título de columna |
| `.footer__list` | Element | Lista de enlaces |
| `.footer__link` | Element | Enlace |
| `.footer__contact-item` | Element | Dato de contacto |
| `.footer__bottom` | Element | Zona inferior |
| `.footer__copyright` | Element | Copyright |
| `.footer__social` | Element | Contenedor redes |
| `.footer__social-link` | Element | Enlace de red social |

---

## Principios aplicados

### 1. Independencia de bloques
Los bloques no dependen de otros bloques. `feature-card`, `testimonial-card`, `pricing-card` y `btn` pueden usarse en cualquier contexto sin conflictos de estilos.

### 2. Reutilización
- `.btn` se usa en header, hero, pricing y contact.
- Las tarjetas (`*-card`) son bloques propios, no elementos anidados.

### 3. Modificadores en lugar de estilos contextuales excesivos
Cuando una variación es intencional (plan recomendado, testimonio destacado, característica principal), se usa un modificador explícito en el HTML.

### 4. Consistencia de nomenclatura
- Bloques: `kebab-case` (`feature-card`, `contact-form`)
- Elementos: `bloque__elemento`
- Modificadores: `bloque--modificador` o `bloque__elemento--modificador`

### 5. Evitar anidamiento profundo
Ningún selector CSS supera 2-3 niveles. No hay cadenas del tipo `.header .nav .menu .item .link`.

---

## Conclusión

La metodología BEM aplicada en este proyecto demuestra:

- **Código predecible**: cada clase indica su rol (bloque, elemento o modificador).
- **Mantenibilidad**: cambiar el estilo de una tarjeta no afecta al header ni al footer.
- **Escalabilidad**: se pueden añadir nuevos bloques sin riesgo de colisiones de nombres.
- **Colaboración**: cualquier desarrollador entiende la estructura solo leyendo las clases.

> "Es más importante tener un concepto consistente que perderse buscando el perfecto."
