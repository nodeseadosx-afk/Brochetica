# SR. BROCHETA · Reservas

Página de reservas del restaurante SR. BROCHETA. Es un solo archivo (`index.html`): no necesita instalar nada ni compilar.

## Qué hace

- El cliente elige día, hora, número de personas y zona, y envía su solicitud. La reserva queda **pendiente** hasta que el restaurante la confirme directamente.
- Reglas de reserva (hora de Colombia, UTC-5): antelación mínima de 3 horas, hasta 60 días hacia adelante, mesa ocupada 2 horas.
- Capacidad por zona y por horario (5 zonas), con agenda visual para el personal.
- Consulta de reservas por teléfono y exportación a CSV desde el panel del equipo.
- Cancelaciones y cambios se informan por WhatsApp.

## Probarla en tu computador

Abre `index.html` con doble clic, o desde la carpeta ejecuta:

```
python3 -m http.server 8000
```

y entra a `http://localhost:8000`.

Panel del equipo (valores de ejemplo, cámbialos en tu copia local): usuario `admin`, clave `cambiar-esta-clave`.

## Publicarla en GitHub Pages

1. Crea un repositorio nuevo en GitHub y sube `index.html` y `README.md`.
2. Ve a **Settings → Pages**.
3. En **Source** elige **Deploy from a branch**, la rama `main` y la carpeta `/ (root)`. Guarda.
4. Espera un par de minutos: la página queda en `https://TU-USUARIO.github.io/NOMBRE-DEL-REPOSITORIO/`.

## Configuración

Todo está al inicio del script, en el objeto `CONFIG` de `index.html`:

| Opción | Qué controla |
| --- | --- |
| `whatsappNumber` | WhatsApp del restaurante, con indicativo y sin `+` (ej. `573171361324`) |
| `minLeadMinutes` | Antelación mínima para reservar (180 = 3 horas) |
| `maxAdvanceDays` | Hasta cuántos días adelante se puede reservar |
| `tableMinutes` | Tiempo que ocupa una reserva su mesa (120 = 2 horas) |
| `serviceWindows` | Horario de atención |
| `credits` | Créditos que se muestran al pie de la página |

Las zonas y sus mesas están en la lista `ZONES`, justo debajo.

## Importante antes de usarla con clientes reales

- **Las reservas se guardan solo en el navegador de cada cliente** (`localStorage`). El restaurante todavía no las recibe en el panel; hoy llegan únicamente por el botón de WhatsApp. El siguiente paso es guardarlas en la nube (Supabase) y darle al personal un login real.
- **No subas claves reales a GitHub.** Todo lo que está en el código lo puede leer cualquiera. Las credenciales del panel que trae este archivo son de ejemplo y se reemplazarán por un login en el servidor.
- Publica una política de privacidad y conserva el registro de aceptación de los términos (Ley 1581 de 2012).

## Créditos

Creado por ING. TITO MANUEL CACERES. Desarrollado con Claude (Anthropic).
