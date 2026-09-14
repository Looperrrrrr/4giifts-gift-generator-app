# 🎁 4Gifts - Generador de ideas de regalos con IA

**Gestiona tus contactos y genera ideas de regalos personalizadas con inteligencia artificial**

> Proyecto final del Bootcamp Full Stack Developer de **4Geeks Academy** (Enero 2026)

---

## 📌 ¿Qué es 4Gifts?

Aplicación web que ayuda a gestionar contactos (familiares, amigos, pareja) y genera ideas de regalos personalizadas usando IA generativa, según el perfil, hobbies y personalidad de cada contacto. Nunca más pierdas tiempo buscando el regalo perfecto.

### Problema resuelto
❌ No saber qué regalar a personas específicas
❌ Gastar horas buscando el regalo adecuado
❌ Olvidar fechas importantes (cumpleaños, aniversarios)

✅ Generador de ideas con IA basado en el perfil de cada persona
✅ Guardar y compartir tus ideas favoritas
✅ Recordatorios de fechas importantes

---

## ✨ Características principales

- 👥 **Gestión de contactos** — Guarda personas con sus hobbies, ocupación, personalidad y fecha de nacimiento
- 🤖 **Generador de ideas con IA** — Sugerencias de regalos generadas con Google Gemini (IA generativa), personalizadas según el perfil del contacto
- ⭐ **Favoritos** — Guarda las ideas que más te gusten para cada contacto
- 📜 **Historial** — Consulta las ideas generadas anteriormente
- 🔗 **Compartir listas** — Comparte tu lista de favoritos con un link público (sin necesidad de cuenta)
- 🔔 **Recordatorios** — Configura avisos antes de una fecha importante
- 👤 **Autenticación segura** — Registro y login con JWT + contraseñas cifradas (bcrypt)
- 🔑 **Recuperación de contraseña** — Por email (Flask-Mail)
- 📱 **Interfaz responsive** — Funciona en desktop, tablet y móvil

---

## 🛠️ Stack Tecnológico

| Capa | Tecnología |
|------|-----------|
| **Frontend** | React 18, Vite, React Router, CSS Modules |
| **Backend** | Python 3.13, Flask, SQLAlchemy ORM, Flask-Migrate |
| **Base de datos** | PostgreSQL (Render.com) |
| **IA** | Google Generative AI (Gemini) — generación de ideas de regalos |
| **Autenticación** | JWT (Flask-JWT-Extended) + Bcrypt |
| **Otros servicios** | Cloudinary (imágenes), Flask-Mail (emails) |
| **Deploy** | Render.com (backend Flask sirve el frontend compilado) |

---

## 👨‍💻 Mi rol en este proyecto

Trabajé en un **equipo de 3-4 desarrolladores** en la rama frontend. Mi contribución principal:

### 🎯 Frontend Lead
- ✅ Diseño y arquitectura de componentes React
- ✅ Implementación de vistas principales:
  - Dashboard de usuario
  - Gestión de contactos (crear, editar, listar)
  - Componentes del generador de ideas de regalos
  - Página de login/registro
- ✅ Enrutado con React Router
- ✅ Gestión de estado con `useReducer` (hook global `useGlobalReducer`)
- ✅ Consumo de la API Flask (fetch)
- ✅ Estilos con CSS Modules — diseño responsivo
- ✅ Flujo de usuario end-to-end

### 📚 Lo que aprendí
- Cómo estructurar una aplicación React de nivel profesional
- Comunicación frontend-backend vía REST API
- Manejo de autenticación JWT en el cliente
- Prácticas de Git y trabajo en equipo (merges, pull requests)
- Deploy de aplicaciones full stack (backend + frontend en un solo servicio)

---

## 🚀 Demostración en vivo

**URL de deploy:** [🔗 4Gifts en Render.com](https://fourgiifts-gift-generator.onrender.com)

> Para probar la app, regístrate con tu propio email desde la pantalla de Signup — toma unos segundos y así puedes ver el flujo completo (login → añadir contacto → generar ideas de regalo).

---

## 📦 Instalación y Setup Local

### Requisitos previos
- Python 3.13
- Node.js 20+
- PostgreSQL 14+ (o SQLite para desarrollo)
- Git

### 1️⃣ Backend (Python + Flask)

```bash
# Clonar el repositorio
git clone https://github.com/Looperrrrrr/4giifts-gift-generator-app.git
cd 4giifts-gift-generator-app

# Instalar dependencias y crear entorno virtual
pipenv install

# Configurar variables de entorno
cp .env.example .env

# Editar .env con tu DATABASE_URL
# Ejemplo PostgreSQL:
# DATABASE_URL=postgres://usuario:password@localhost:5432/4gifts_db
# Ejemplo SQLite (rápido para testing):
# DATABASE_URL=sqlite:////tmp/test.db

# Ejecutar migraciones
pipenv run migrate
pipenv run upgrade

# Iniciar servidor Flask
pipenv run start
# El backend estará en: http://localhost:3001
```

### 2️⃣ Frontend (React + Vite)

En otra terminal:

```bash
# Instalar dependencias
npm install

# Configurar variable de entorno del frontend
# En tu .env, añade:
# VITE_BACKEND_URL=http://localhost:3001

# Iniciar servidor de desarrollo
npm run start
# La app estará en: http://localhost:3000
```

---

## 🏗️ Estructura del Proyecto

```
4giifts-gift-generator-app/
├── src/
│   ├── api/                       # Backend Flask
│   │   ├── models.py              # Modelos: User, Contactos, Producto, Historial, Favorite, Reminder
│   │   ├── routes.py              # Endpoints de la API
│   │   ├── commands.py            # Comandos CLI (flask insert-test-users, etc.)
│   │   ├── admin.py                # Panel de administración (Flask-Admin)
│   │   └── extensions.py          # Configuración de Flask-Mail
│   │
│   ├── front/                      # Frontend React
│   │   ├── pages/                  # Páginas de la app
│   │   │   ├── Home.jsx
│   │   │   ├── Login.jsx / Signup.jsx
│   │   │   ├── Dashboard.jsx
│   │   │   ├── GiftIdeas.jsx       # Generador de ideas de regalo
│   │   │   ├── MyFavorites.jsx / SharedFavorites.jsx
│   │   │   ├── ProfileEdit.jsx
│   │   │   └── RecoverRequest.jsx / ResetPassword.jsx
│   │   ├── components/             # Navbar, Footer, Card, RemindersCarousel...
│   │   ├── hooks/useGlobalReducer.jsx  # Estado global
│   │   ├── routes.jsx              # Definición de rutas (React Router)
│   │   └── services.js             # Llamadas a la API
│   │
│   ├── app.py                      # Punto de entrada Flask
│   └── wsgi.py                     # Entry point para gunicorn (producción)
│
├── public/                         # Assets estáticos
├── package.json                    # Dependencias Frontend
├── Pipfile                         # Dependencias Backend
├── render.yaml                     # Configuración de deploy en Render
├── render_build.sh                 # Script de build (frontend + backend)
├── .env.example                    # Variables de entorno ejemplo
└── README.md                       # Este archivo
```

---

## 🔌 API Endpoints principales

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| POST | `/api/signup` | Registrar usuario |
| POST | `/api/login` | Login y obtener JWT |
| PUT / DELETE | `/api/user/<id>` | Editar / eliminar usuario |
| GET / POST | `/api/contacts` | Listar / crear contactos |
| GET / PUT / DELETE | `/api/contacto/<id>` | Ver, editar o eliminar un contacto |
| POST | `/api/generate_gift_ideas` | Generar ideas de regalo con IA para un contacto |
| GET / DELETE | `/api/history/<contact_id>` | Historial de ideas generadas |
| POST / GET | `/api/favorites` | Guardar / listar favoritos |
| DELETE | `/api/favorite/<id>` | Eliminar un favorito |
| POST | `/api/user/share_link` | Generar link para compartir favoritos |
| GET | `/api/shared/favorites/<token>` | Ver favoritos compartidos (público) |
| GET / POST / DELETE | `/api/reminders` | Gestionar recordatorios |
| POST | `/api/recover/request` | Solicitar recuperación de contraseña |
| POST | `/api/recover/reset` | Restablecer contraseña |

---

## 🐛 Troubleshooting

### Error: "Cannot connect to backend" / pantalla "Missing BACKEND_URL"
- Verifica que la variable `VITE_BACKEND_URL` está definida en tu `.env` (no en `.env.example`)
- Verifica que Flask está corriendo en `http://localhost:3001`
- Revisa la consola del navegador (F12 → Network) para ver la request fallida

### Error: "Database connection failed"
- Comprueba que PostgreSQL está corriendo
- Verifica la `DATABASE_URL` en `.env`

### Error: "npm install falla"
- Elimina `node_modules` y `package-lock.json`
- Ejecuta `npm install` de nuevo

---

## 🚀 Deploy en Render.com

Este proyecto está desplegado como un único **Web Service** en Render:

1. `render_build.sh` compila el frontend (`npm run build`) y luego instala las dependencias de Python (`pipenv install`)
2. Flask sirve el frontend compilado (`dist/`) como archivos estáticos y expone la API bajo `/api`
3. Arranca con `gunicorn wsgi --chdir ./src/`
4. Variables de entorno necesarias: `FLASK_APP`, `FLASK_APP_KEY`, `DATABASE_URL`, `VITE_BACKEND_URL`, `FRONTEND_URL`

📖 [Ver guía de deploy de 4Geeks](https://4geeks.com/docs/start/deploy-to-render-com)

---

## 🤝 Trabajo en equipo

Este fue un **proyecto colaborativo**. Trabajé con:
- **Alejandro Gonzalez**
- **Harold Maldonado**
- **Hugo Alexander**

**Lecciones de teamwork:**
- Comunicación clara en stand-ups diarios
- Resolución de conflictos en Git (merge conflicts)
- Code reviews y feedback constructivo
- Distribución de tareas según fortalezas

---

## 📝 Licencia

Este proyecto es parte de los materiales de **4Geeks Academy**.

---

## 📧 Contacto

¿Preguntas sobre el proyecto?

- **Email:** asif.covilha@gmail.com
- **LinkedIn:** [in/asif-alam-973b7a146](https://www.linkedin.com/in/asif-alam-973b7a146/)
- **GitHub:** [@Looperrrrrr](https://github.com/Looperrrrrr)

---

## 🎯 Próximos pasos

Estoy planeando una **versión mejorada** de este proyecto con:
- ✅ Más features del generador (filtros avanzados, presupuesto)
- ✅ Integración con tiendas online (Amazon, ASOS)
- ✅ Notificaciones por email para recordatorios
- ✅ Tests automatizados

**Status:** En planning

---

## ⭐ Si te gustó este proyecto

Dale una ⭐ en GitHub y comparte con otros desarrolladores en busca de bootcamp.

---

**Hecho con ❤️ por Asif Alam | Full Stack Developer | Madrid, Spain**

*Actualizado: Septiembre 2026*
