# PROMPT: Diseño de Correo HTML para Confirmación de Subasta Exclusiva

Crea un mensaje de correo electrónico en formato HTML completo y responsivo, diseñado para enviarse desde una webapp de Google Sheets mediante Google Apps Script. El correo confirma la participación en una subasta privada exclusiva.

---

## ⚠️ REQUISITOS TÉCNICOS OBLIGATORIOS

- Todo el código HTML y CSS debe estar **EN UN SOLO ARCHIVO**, sin dependencias externas:
  - Sin Google Fonts
  - Sin hojas de estilo externas
  - Sin imágenes alojadas
- Usa únicamente **fuentes seguras para email**: `'Segoe UI'`, `Tahoma`, `Geneva`, `Verdana`, `sans-serif`
- Usa exclusivamente etiquetas `<table>`, `<tr>`, `<td>` con atributos `role="presentation"` para la estructura principal
- **Compatible con clientes de correo**: Outlook, Gmail, Apple Mail
- Incluye **reseteo CSS específico**:
  - `mso-table-lspace: 0pt`
  - `mso-table-rspace: 0pt`
  - `-webkit-text-size-adjust: 100%`
  - `-ms-text-size-adjust: 100%`
- **Placeholders claramente identificables** con doble llave `{{PLACEHOLDER}}` para reemplazo desde Google Apps Script
- **Ancho máximo**: 600px
- **Diseño completamente responsivo**

---

## 🎨 DISEÑO Y ESTILO REQUERIDO

### 1. CABECERA (HEADER)

- **Fondo**: Gradiente elegante en tonos azul profundo (`#1a2a6c` a `#4a6fa5`)
- **Efecto**: Luz radial sutil animada con CSS `@keyframes`
- **LOGO SVG inline** (sin enlace externo) de 70x70px aproximadamente:
  - Círculo exterior con borde punteado dorado semitransparente
  - Círculo interior con relleno blanco semitransparente
  - Martillo de subasta estilizado:
    - Mango marrón
    - Cabeza con gradiente dorado (`#FFD700` a `#FFA500`)
  - Pequeños destellos o puntos blancos alrededor
- **TÍTULO PRINCIPAL**: "SUBASTA EXCLUSIVA"
  - Color: blanco
  - Tamaño: 32px
  - Peso: 700
  - Sombra de texto
  - Espaciado de letras amplio
- **SUBTÍTULO**: "Tu participación está confirmada"
  - Color: blanco semitransparente
  - Mayúsculas
  - Tamaño: 16px
  - Peso: 300
  - Tracking: 2px

### 2. CUERPO DEL MENSAJE

- **Fondo**: Blanco
- **Padding**: 30px 25px
- **SALUDO PERSONALIZADO**: "¡Hola, {{NOMBRE_PARTICIPANTE}}!"
  - Nombre en color azul `#4a6fa5`
  - Peso bold
  - Línea decorativa inferior
- **MENSAJE DE ALEGRÍA**:
  - Caja con fondo `#f8fafc`
  - Borde izquierdo de 4px color `#4a6fa5`
  - Bordes redondeados de 12px
  - Texto que exprese entusiasmo por la participación
  - Mencionar que es un honor contar con ellos
  - Destacar que hay piezas excepcionales
  - Usar emojis relevantes (🎉) con moderación

### 3. BOTONES DE ACCIÓN (DOS BOTONES)

- **Contenedor**: Flex que en móvil se apile en columna y en escritorio esté en fila
- **BOTÓN 1 - "📅 Añadir al Calendario"**:
  - Estilo outlined
  - Fondo: blanco
  - Texto y borde: `#2d4374`
  - Hover: fondo `#2d4374`, texto blanco, sombra, elevación sutil
  - Enlace: `{{URL_CALENDARIO}}`
- **BOTÓN 2 - "🔨 Ver Ofertas en Vivo"**:
  - Estilo sólido
  - Fondo: `#2d4374`
  - Texto: blanco
  - Hover: fondo `#1a2a6c`, sombra, elevación
  - Enlace: `{{URL_OFERTAS}}`
- **Ambos botones**:
  - Padding: 14px 28px
  - Border-radius: 50px
  - Peso: 600
  - Sombra suave
  - Transición: 0.3s
  - Icono emoji integrado

### 4. DETALLES ADICIONALES

- **Separador decorativo**: Gradiente lineal horizontal
- **Fecha de la subasta**: Centrada, texto pequeño
  - Emoji reloj ⏰
  - Formato: "⏰ Fecha de la subasta: **{{FECHA_SUBASTA}}**"

### 5. AVISO DE PRIVACIDAD Y CONFIDENCIALIDAD

- **Fondo**: Gris muy claro `#f9fafb`
- **Borde**: Superior sutil
- **Icono**: Candado 🔒 al inicio
- **Texto**: Tamaño 12px, color `#999`, centrado
- **Contenido obligatorio**:
  - "Este mensaje es privado y confidencial"
  - "Prohibido el reenvío"
  - Instrucción de eliminar si se recibe por error

### 6. FOOTER

- Copyright dinámico con `{{AÑO_ACTUAL}}`
- Aviso de mensaje automático

---

## 📋 PLACEHOLDERS PARA GOOGLE APPS SCRIPT

Deben marcarse **exactamente así** en el HTML:

| Placeholder | Descripción |
|-------------|-------------|
| `{{NOMBRE_PARTICIPANTE}}` | Nombre completo del destinatario |
| `{{FECHA_SUBASTA}}` | Fecha y hora de la subasta |
| `{{URL_CALENDARIO}}` | Enlace para añadir evento al calendario |
| `{{URL_OFERTAS}}` | Enlace a la página de ofertas en vivo |
| `{{AÑO_ACTUAL}}` | Año actual para el copyright |

---

## 🎯 OBJETIVO FINAL

Un correo electrónico visualmente impactante, profesional, que transmita exclusividad y emoción por la subasta, técnicamente impecable para clientes de correo, y fácilmente personalizable desde Google Apps Script mediante reemplazo de placeholders con `HtmlService.createTemplateFromFile()`.

### Tono del mensaje

- Cálido
- Profesional
- Ligeramente exclusivo
- Diseño que refleje seriedad, confianza y la emoción de una casa de subastas de alto nivel