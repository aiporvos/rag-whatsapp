# ⚖️ Argus-Legal OS (V3.0)

**Argus-Legal** es un ecosistema integral de gestión jurídica diseñado para la alta eficiencia. Combina una potente interfaz de administración en React con un cerebro de Inteligencia Artificial basado en n8n (**Lex**) que gestiona comunicaciones por WhatsApp y realiza análisis documental avanzado (RAG).

---

## 🌟 Características Principales

-   🤖 **Lex (AI Agent):** Asistente virtual jurídico que razona mediante Chain-of-Thought para ejecutar acciones.
-   📱 **WhatsApp Business:** Integración total para atención al cliente y gestión de expedientes vía móvil.
-   📚 **RAG (Knowledge Engine):** Consultas semánticas sobre legislación y documentos internos de la firma.
-   📁 **Sincronización Cloud:** Gestión automatizada de documentos con Google Drive.
-   📧 **Herramientas Integradas:** Envío automático de emails, gestión de calendario y directorio legal.
-   🏢 **Gestión de Casos:** Panel administrativo privado para abogados y clientes.

---

## 🧩 Componentes del Ecosistema

### 1. Panel de Administración (Frontend)
Interfaz moderna construida para la gestión de expedientes, roles y visualización de datos.
- **Stack:** React 18, TypeScript, Tailwind CSS, Shadcn/UI, TanStack Query.

### 2. Cerebro de Automatización (n8n)
El núcleo que orquestra la IA y las herramientas externas.
- **Lex:** Agente de Lenguaje que coordina sub-agentes especializados.
- **RAG Engine:** Indexación vectorial en Supabase para búsqueda de leyes argentinas.
- **Buffering Inteligente:** Redis para agrupar mensajes de WhatsApp y evitar respuestas duplicadas.

---
<img width="1225" height="853" alt="image" src="https://github.com/user-attachments/assets/1262a139-169a-4fea-981d-5b2ae62abb4b" />
---


## 🚀 Guía de Inicio Rápido

### Prerequisitos
- Proyecto en **Supabase** (Postgres + pgvector).
- Instancia de **n8n** (con nodos de LangChain habilitados).
- Repositorio Git vinculado a **Dokploy** (para despliegue continuo).

### Despliegue del Frontend
1. **Configura Dokploy:** Conecta este repo y define las variables:
   ```bash
   VITE_SUPABASE_URL=https://xxxxx.supabase.co
   VITE_SUPABASE_PUBLISHABLE_KEY=eyJhbGciOiJI...
   VITE_SUPABASE_PROJECT_ID=xxxxx
   ```
2. **Deploy:** Dokploy detectará el `Dockerfile` y expondrá la app en el puerto 3000.

### Integración de n8n
1. Importa los archivos JSON de los flujos ubicados en la carpeta correspondente (ver docs).
2. Configura las credenciales de OpenAI y Supabase en n8n.
3. **Documentación Técnica n8n:** [Consulte DOCUMENTATION_N8N.md](./DOCUMENTATION_N8N.md) para detalles sobre el cerebro de IA.

---

## 📁 Estructura del Proyecto

```bash
.
├── src/                   # Interfaz React (Frontend)
├── docs/                  # Guías de despliegue y migración SQL
├── DOCUMENTATION_N8N.md   # ⭐ Manual del Cerebro de IA (Configuración Lex)
├── supabase/              # Migraciones y Edge Functions
├── Dockerfile             # Containerización para producción
└── docker-compose.yml     # Entorno de testing local
```

---

## 🔒 Seguridad y Optimización

- **RLS (Row Level Security):** Protección total de datos a nivel de base de datos.
- **Mínimo Consumo:** Sin suscripciones realtime innecesarias y llamadas a IA bajo demanda para optimizar costos.
- **Modo Supervivencia:** n8n configurado para responder incluso si fallan servicios externos.

---

## 📝 Licencia
Este proyecto está bajo la licencia MIT.

---

**Construido por Claudio Luna & Argus-Legal Team con ❤️**
