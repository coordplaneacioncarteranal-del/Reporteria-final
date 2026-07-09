# OpsHub Central 🚀
### *Control y ejecución inteligente*

Panel centralizado de acceso a herramientas operativas del Call Center. Un solo archivo HTML, cero dependencias locales, despliegue instantáneo.

---

## 📁 Estructura del proyecto

```
opshub-central/
├── index.html      ← Todo el proyecto vive aquí
└── README.md       ← Este archivo
```

---

## ✏️ Cómo modificar los enlaces (sin conocimientos técnicos)

Abre `index.html` con cualquier editor de texto (Notepad, VS Code, Sublime Text).

Busca la sección que dice **`APP_LINKS`** — está marcada claramente con comentarios y luce así:

```javascript
const APP_LINKS = [
  {
    id: 1,
    title: "Tiempos Call Center",
    description: "Monitoreo en tiempo real de tiempos de atención...",
    url: "https://tu-url-tiempos-callcenter.com",   // ← EDITA ESTA URL
    badge: "Tiempo Real",
    accentColor: "blue",
    shortcut: "Alt+1",
    icon: "clock"
  },
  // ... más herramientas
];
```

### Cambiar una URL existente

Simplemente reemplaza el valor de `url`:

```javascript
url: "https://MI-NUEVA-URL.com",
```

Guarda el archivo. ¡Listo! No necesitas reiniciar nada.

---

### Añadir una nueva herramienta

Copia y pega un bloque al final del array (antes del `]`), cambia los valores y asegúrate de separarlo con una coma del anterior:

```javascript
{
  id: 6,                              // Número único, sigue la secuencia
  title: "Mi Nueva Herramienta",      // Nombre que aparece en la tarjeta
  description: "Descripción breve de para qué sirve esta herramienta.",
  url: "https://mi-nueva-url.com",    // ← URL del dashboard
  badge: "Etiqueta",                  // Texto pequeño arriba a la derecha
  accentColor: "rose",                // Color del acento (ver tabla abajo)
  shortcut: "Alt+6",                  // Atajo de teclado (opcional)
  icon: "chart"                       // Icono (ver tabla abajo)
},
```

---

### 🎨 Colores disponibles (`accentColor`)

| Valor    | Color           | Uso sugerido          |
|----------|-----------------|-----------------------|
| `blue`   | Azul eléctrico  | Monitoreo, tiempo real |
| `green`  | Verde éxito     | Datos, actualizaciones |
| `amber`  | Ámbar / dorado  | Analítica, reportes    |
| `purple` | Violeta         | Comunicación           |
| `cyan`   | Cian            | Bases de datos         |
| `rose`   | Rosa / rojo     | Alertas, urgente       |

---

### 🖼️ Iconos disponibles (`icon`)

| Valor      | Descripción                 |
|------------|-----------------------------|
| `clock`    | Reloj — para tiempos/métricas |
| `refresh`  | Flechas de recarga — para actualizaciones |
| `chart`    | Barras de gráfico — para analítica |
| `message`  | Burbuja de chat — para mensajería |
| `database` | Cilindro — para bases de datos |

---

### Eliminar una herramienta

Borra el bloque completo `{ ... }` del enlace que quieres eliminar del array `APP_LINKS`.  
Asegúrate de que no quede una coma extra al final del último elemento.

---

## 🚀 Cómo subir a un servidor estático

### Opción 1: Netlify (recomendado, gratis)

1. Ve a [netlify.com](https://netlify.com) e inicia sesión (o crea cuenta gratis).
2. En el panel, haz clic en **"Add new site" → "Deploy manually"**.
3. Arrastra y suelta la **carpeta `opshub-central/`** al área de deploy.
4. Netlify genera una URL pública al instante.
5. (Opcional) Ve a **Domain settings** para asignar tu propio dominio.

### Opción 2: Hostinger

1. Accede al **Panel de control de Hostinger** → **Administrador de archivos**.
2. Navega a la carpeta `public_html/`.
3. Sube el archivo `index.html` (y `README.md` si deseas).
4. La web estará disponible en tu dominio configurado.

### Opción 3: GitHub Pages (gratis)

1. Crea un repositorio en GitHub (puede ser privado o público).
2. Sube `index.html` a la rama `main`.
3. Ve a **Settings → Pages → Source: Deploy from branch → main → / (root)**.
4. GitHub te da una URL `https://tu-usuario.github.io/repositorio/`.

### Opción 4: Cualquier hosting con FTP

1. Conéctate vía FTP/SFTP (usa FileZilla o similar).
2. Sube `index.html` a la carpeta raíz del dominio (`public_html/`, `www/` o equivalente).
3. Visita tu dominio. ¡Ya está activo!

---

## ⌨️ Atajos de teclado

| Atajo   | Acción                          |
|---------|---------------------------------|
| `Alt+1` | Abrir Tiempos Call Center       |
| `Alt+2` | Abrir Jardines del Renacer      |
| `Alt+3` | Abrir Cuartiles Cartera         |
| `Alt+4` | Abrir Mensajería Masiva         |
| `Alt+5` | Abrir Cartera Actualizada       |

---

## 🛠️ Stack técnico

| Tecnología    | Uso                            | Carga         |
|---------------|--------------------------------|---------------|
| HTML5         | Estructura semántica           | Nativa        |
| CSS3 (Grid/Flex)| Layout responsive, glassmorphism | Inline      |
| JavaScript ES6| Lógica, reloj, render de cards | Inline        |
| GSAP 3.12.5   | Animaciones splash y reveal    | CDN (~50 KB)  |
| Google Fonts  | Tipografía Inter + JetBrains Mono | CDN (~12 KB) |

---

## 🔧 Personalización avanzada

### Cambiar nombre del sistema

Busca `OpsHub Central` en el HTML y reemplázalo por el nombre deseado.

### Cambiar paleta de colores

En la sección `:root` del CSS, modifica las variables:
```css
--accent-blue: #3b82f6;   /* Color principal */
--bg-primary: #0d0d0f;    /* Fondo principal */
```

### Desactivar el splash screen

Busca `runSplash()` en el JavaScript y coméntalo:
```javascript
// runSplash();
```

---

## 📋 Versión

**v2.4.0** — OpsHub Central  
Desarrollado como herramienta interna de operaciones para Call Center.

---

*"Cero fricción. Control total."*
