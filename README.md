# Metegrity - Asset Integrity Management (AIM)

Metegrity es el líder global y el entorno más confiable en Sistemas de Gestión de Integridad de Activos (**Asset Integrity Management - AIM**) especializado para la protección de plantas e instalaciones con un uso intensivo de activos, tales como la industria Química y Petroquímica, Petróleo y Gas, Generación de Energía, y Pulpa y Papel. 

**Nuestra misión principal** es mejorar la confiabilidad de las instalaciones industriales a escala mundial, reduciendo drásticamente los riesgos operativos y paradas no planificadas, todo esto mientras maximizamos el rendimiento a través de todo el ciclo de vida del activo. Implementar un software de Metegrity (como *Visions Enterprise*, *Visions RBI* y *VisionsGo*) asegura a los ingenieros de confiabilidad e inspectores que siempre contarán con datos exactos y calculados, alertas proactivas basadas en anomalías (presión, erosión, temperatura) y herramientas de gestión del riesgo avanzadas (Risk Based Inspection).

Metegrity integra inspecciones impulsadas por la innovación tecnológica, cálculos avanzados y cumplimiento normativo embebido en tiempo real.

---

## 🚀 Tecnologías del Proyecto

Este frontend corporativo está diseñado bajo la premisa de ser **extremadamente rápido (alto rendimiento), escalable y tener una interfaz "Premium" (UI/UX inmersiva)** con enfoque en las mejores prácticas de la web y SEO moderno. Hemos optado por una arquitectura robusta pero ágil, evitando librerías de interfaz de usuario infladas:

- **[Astro (v6)](https://astro.build/)**: Framework elegido para la Generación de Sitios Estáticos (SSG) y renderizado de componentes sumamente rápidos con *Cero JavaScript invasivo* en el cliente a menos que sea estrictamente necesario.
- **Vanilla CSS3 / HTML5**: Para toda la diagramación, tipografía, variables CSS nativas (`var(--space-...)`), layouts complejos (CSS Grid/Flexbox) y efectos visuales avanzados de diseño *glassmorphism*. **No** usamos librerías de estilos como Tailwind CSS; todo está customizado a mano para asegurar un control visual máximo y código limpio.
- **Vanilla JavaScript**: En favor del rendimiento, el código interactivo o animaciones, como observadores de intersección (`IntersectionObserver`) o contadores en tiempo real ubicados en la pantalla, están creados con JavaScript puro para garantizar nula dependencia en bibliotecas como React o Vue en el cliente cuando no hay cambios complejos en el árbol del DOM.
- **Animaciones SVG Avanzadas**: Toda la representación esquemática del sistema, las líneas de escáner en paralelo, partículas, e ilustraciones industriales complejas, se escribieron utilizando código SVG nativo en línea manipulado mediante CSS Animations (`@keyframes`).
- **Node.js**: Entorno base para compilación y desarrollo backend local.

---

## 📂 Estructura del Código

Buscamos mantener la arquitectura limpia y predecible apoyándonos directamente en las convenciones de Astro. El directorio de trabajo `/src` está dividido en las siguientes partes cruciales:

```text
├── public/
│   ├── images/         # Carpeta principal para todos los recursos visuales (fondos, fotos, íconos de industrias)
│   ├── favicon.*       # Íconos de página web
├── src/
│   ├── components/     # Todos los módulos de interfaz de usuario de Astro
│   │   ├── shared/     # Componentes visuales genéricos y reciclables (ej. FilterBar.astro, LegalLayout)
│   │   ├── Hero.astro  # Sección introductoria principal visual con partículas
│   │   ├── Navbar.astro, Footer.astro, Industries.astro, etc...
│   ├── layouts/        # Entornos envolventes principales
│   │   ├── Layout.astro       # Envoltura principal para páginas generales base
│   ├── pages/          # Sistema de enrutamiento estático (File-Based Routing de Astro)
│   │   ├── index.astro        # Base del inicio '/'
│   │   ├── insights/          # Contenido informativo: ebooks, the-blog, noticias, historias de éxito
│   │   ├── legal/             # Políticas de Cookies, Derechos y Términos Base
│   │   ├── products/          # Catálogo principal de la suite ("Visions Enterprise", "RBI", etc.)
│   │   ├── services/          # Catálogo de servicios adicionales (Consultoría)
│   ├── styles/         # Reglas de estilo de origen
│   │   ├── global.css         # Archivo de declaraciones de diseño central: root, resets y colores.
├── astro.config.mjs    # Configuración de compilaciones de Astro.
├── package.json        # Registro de dependencias fundamentales y scripts ("dev", "build").
```

---

## 🛠️ Cómo Trabajamos en este Repositorio

El ciclo de desarrollo está enfocado en integraciones cortas, revisiones eficientes y modularización en componentes de Astro.

1. **Instalación:** Para levantar el proyecto por primera vez, clona el repositorio y ejecuta `npm install`.
2. **Desarrollo Local:** Usa `npm run dev` para previsualizar el servidor local usando Vite integrado al cliente de Astro con soporte de recarga automática en vivo HMR. 
3. **Manejo de Estilos:** Al construir nuevas secciones se busca que los estilos se incluyan de forma localizada o de *alcance específico* dentro del mismo archivo `.astro` usando las etiquetas `<style>`. Los estilos estéticos genéricos variables se alimentan de `/src/styles/global.css`.
4. **Despliegue y Construcción:** Usa `npm run build` en el ambiente de producción (para crear el directorio `dist/` estático de alto rendimiento listo para cualquier CDN).
5. **Control de Versiones (Git):** El trabajo se unifica en la rama `main`. Cada nueva mejora del sistema UI (Por ej. componentes como el `Contact.astro` o flujos de innovación) se registra mediante *commits* descriptivos detallando los cambios. Todo despliegue corre acorde el manual básico de versionamiento.
