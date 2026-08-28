[README.md](https://github.com/user-attachments/files/31567007/README.md)
# Retrouvaille Monterrey
### Landing page · Automatización de sesiones informativas

Página web oficial del programa matrimonial Retrouvaille en Monterrey, N.L. Incluye la landing de captación y el flujo automatizado de confirmación de sesiones informativas vía Make.com.

---

## 🌐 Sitio en producción

**[retrouvaille-monterrey.netlify.app](https://retrouvaille-monterrey.netlify.app)**

---

## 📁 Archivos del repositorio

```
retrouvaille-monterrey/
├── index.html        ← Landing principal con iframe de Calendly
└── README.md         ← Este archivo
```

---

## ⚙️ Flujo de automatización

```
Anuncio en Facebook
        ↓
Landing (index.html) → sección #agendar
        ↓
Pareja elige fecha en Calendly
(martes · 8–9 PM · 29 sep – 26 oct 2025)
        ↓
Se llena manualmente en Google Sheets
        ↓
Make detecta nueva fila → Gmail envía
correo de confirmación automático
```

### Herramientas conectadas

| Herramienta | Uso |
|---|---|
| Netlify | Hosting y deploy automático desde GitHub |
| Calendly | Agendado de sesiones informativas |
| Google Sheets | Base de datos de leads (`Leads Retrouvaille`) |
| Make.com | Automatización del correo de confirmación |
| Gmail | Envío del correo desde `retrouvaillemty@gmail.com` |

### Columnas del Google Sheet

| Columna | Contenido |
|---|---|
| A — Fecha Registro | Fecha en que se registró la pareja |
| B — Nombre Completo | Nombre de quien agenda |
| C — Nombre Cónyuge | Nombre del cónyuge |
| D — Email | Correo para envío de confirmación |
| E — Teléfono | WhatsApp de contacto |
| F — Fecha de Sesión | Martes elegido (ej: 26/10/2026) |
| G — Notas | Campo libre |

---

## 📧 Correo de confirmación

El correo se genera automáticamente por Make (módulo 6 → Gmail módulo 7) cuando se agrega una nueva fila al Sheet. Usa las variables:
- `{{6.B}}` → Nombre completo
- `{{6.5}}` → Fecha de sesión (posición raw de columna F)
- `{{6.D}}` → Email destinatario (campo "To")

---

## 📞 Contacto

- **WhatsApp:** +52 81 3432 6461
- **Correo:** retrouvaillemty@gmail.com
- **Programa:** [ayudanuestromatrimonio.org](https://ayudanuestromatrimonio.org)

---

## 🚀 Deploy

El sitio se despliega automáticamente en Netlify cada vez que se hace push a la rama `main`. No requiere build command — es HTML estático puro.

---

*Retrouvaille Monterrey · Apostolado matrimonial sin fines de lucro · 2025*
