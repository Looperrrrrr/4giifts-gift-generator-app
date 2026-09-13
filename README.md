# 🎁 4Gifts - Gift Generator & Calendar Manager
 
**Generador inteligente de ideas de regalos + Gestor de fechas especiales**
 
> Proyecto final del Bootcamp Full Stack Developer de **4Geeks Academy** (Enero 2026)
 
---
 
## 📌 ¿Qué es 4Gifts?
 
Aplicación web que ayuda a gestionar fechas importantes (cumpleaños, aniversarios, eventos) y genera ideas personalizadas de regalos basadas en preferencias del usuario. Nunca más olvides un cumpleaños ni pierdas tiempo buscando el regalo perfecto.
 
### Problema resuelto
❌ Olvidar cumpleaños y aniversarios  
❌ Gastar horas buscando el regalo adecuado  
❌ No saber qué regalar a personas específicas  
 
✅ Calendario inteligente con recordatorios  
✅ Generador de ideas en segundos  
✅ Guardar y reutilizar sugerencias  
 
---
 
## ✨ Características principales
 
- 📅 **Calendario de eventos** — Crea eventos con fecha, persona y tipo (cumpleaños, aniversario, etc.)
- 🎁 **Generador de ideas de regalos** — Obtén sugerencias automáticas basadas en categorías y presupuesto
- 👤 **Autenticación de usuarios** — Registro y login con JWT (seguro)
- 💾 **Persistencia de datos** — Todos tus eventos y preferencias guardadas en base de datos
- 📱 **Interfaz responsive** — Funciona en desktop, tablet y móvil
- 🎨 **Diseño intuitivo** — UI limpia y fácil de usar
---
 
## 🛠️ Stack Tecnológico
 
| Capa | Tecnología |
|------|-----------|
| **Frontend** | React 18, Vite, CSS Modules, Context API |
| **Backend** | Python 3.10, Flask, SQLAlchemy ORM |
| **Base de datos** | PostgreSQL (Render.com) |
| **Autenticación** | JWT (JSON Web Tokens) |
| **Herramientas** | Git, GitHub, Render.com (Deploy) |
 
---
 
## 👨‍💻 Mi rol en este proyecto
 
Trabajé en un **equipo de 3-4 desarrolladores** en la rama frontend. Mi contribución principal:
 
### 🎯 Frontend Lead
- ✅ Diseño y arquitectura de componentes React
- ✅ Implementación de vistas principales:
  - Dashboard de usuario
  - Formulario de creación de eventos
  - Componentes del generador de regalos
  - Página de login/registro
- ✅ Gestión de estado con Context API
- ✅ Consumo de la API Flask (fetch)
- ✅ Estilos con CSS Modules — diseño responsivo
- ✅ Flujo de usuario end-to-end
### 📚 Lo que aprendí
- Cómo estructurar una aplicación React de nivel profesional
- Comunicación frontend-backend via REST API
- Manejo de autenticación JWT en el cliente
- Prácticas de Git y trabajo en equipo (merges, pull requests)
- Deploy de aplicaciones full stack
---
 
## 🚀 Demostración en vivo
 
**URL de deploy:** [🔗 4Gifts en Render.com](link-aqui-cuando-despliegues)
 
> ⚠️ **Nota:** En desarrollo. Deploy en proceso.
 
### Credenciales de prueba
```
Email: test@example.com
Password: test123
```
 
---
 
## 📦 Instalación y Setup Local
 
### Requisitos previos
- Python 3.10+
- Node.js 20+
- PostgreSQL 14+ (o SQLite para desarrollo)
- Git
### 1️⃣ Backend (Python + Flask)
 
```bash
# Clonar el repositorio
git clone https://github.com/Looperrrrrr/Final_Project-4Giifts.git
cd Final_Project-4Giifts
 
# Crear y activar ambiente virtual
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
 
# Poblar base de datos con test data (opcional)
pipenv run insert-test-data
 
# Iniciar servidor Flask
pipenv run start
# El backend estará en: http://localhost:5000
```
 
### 2️⃣ Frontend (React + Vite)
 
En otra terminal:
 
```bash
# Asegúrate de que ya instalaste dependencias
npm install
 
# Iniciar servidor de desarrollo
npm run start
# La app estará en: http://localhost:3000
```
 
Listo. El frontend se conectará automáticamente al backend.
 
---
 
## 📸 Screenshots
 
### Dashboard Principal
*[Captura: vista general con calendario y próximos eventos]*
 
### Crear Evento
*[Captura: formulario para añadir cumpleaños/aniversarios]*
 
### Generador de Regalos
*[Captura: interfaz mostrando ideas de regalos sugeridas]*
 
### Login
*[Captura: página de autenticación]*
 
> 💡 **Próximamente:** Añadiré GIFs animados mostrando el flujo completo.
 
---
 
## 🏗️ Estructura del Proyecto
 
```
Final_Project-4Giifts/
├── src/
│   ├── api/                    # Backend Flask
│   │   ├── models.py           # Modelos de base de datos
│   │   ├── routes.py           # Rutas/endpoints
│   │   └── commands.py         # Comandos CLI
│   │
│   └── components/             # Componentes React (Frontend)
│       ├── EventList.jsx        # Listado de eventos
│       ├── EventForm.jsx        # Formulario crear evento
│       ├── GiftGenerator.jsx    # Generador de ideas
│       ├── Dashboard.jsx        # Vista principal
│       └── Auth/                # Autenticación
│
├── public/                      # Assets estáticos
├── package.json                 # Dependencias Frontend
├── Pipfile                      # Dependencias Backend
├── .env.example                 # Variables de entorno ejemplo
└── README.md                    # Este archivo
```
 
---
 
## 🔌 API Endpoints principales
 
| Método | Endpoint | Descripción |
|--------|----------|-------------|
| POST | `/auth/register` | Registrar usuario |
| POST | `/auth/login` | Login y obtener JWT |
| GET | `/events` | Listar eventos del usuario |
| POST | `/events` | Crear nuevo evento |
| DELETE | `/events/<id>` | Eliminar evento |
| GET | `/gifts/suggestions` | Obtener ideas de regalos |
 
---
 
## 🐛 Troubleshooting
 
### Error: "Cannot connect to backend"
- Verifica que Flask está corriendo en `http://localhost:5000`
- Revisa la consola del navegador (F12 → Network) para ver la request fallida
- Si CORS error: añade origen en Flask
### Error: "Database connection failed"
- Comprueba que PostgreSQL está corriendo
- Verifica la `DATABASE_URL` en `.env`
- Ejecuta: `psql -U tu_usuario -d 4gifts_db` para verificar conexión
### Error: "npm install falla"
- Elimina `node_modules` y `package-lock.json`
- Ejecuta: `npm install` de nuevo
---
 
## 🚀 Deploy en Render.com
 
Este proyecto está configurado para deployar fácilmente en Render.com:
 
1. Haz push a tu rama `main`
2. Conecta tu repo en [Render.com](https://render.com)
3. Render detecta automáticamente que es React + Flask
4. Configura variables de entorno
5. Deploy automático en ~10 minutos
📖 [Ver guía completa de deploy](https://4geeks.com/docs/start/deploy-to-render-com)
 
---
 
## 📚 Tecnologías aprendidas
 
Este proyecto cubrió el stack full stack completo:
 
### Frontend
- React Hooks (useState, useContext, useEffect)
- Componentes funcionales
- CSS Modules para estilos encapsulados
- Fetch API para consumir endpoints
- Rutas con React Router (si aplica)
### Backend
- Flask blueprints y rutas
- SQLAlchemy para ORM
- Autenticación JWT
- Manejo de CORS
- Migraciones de base de datos
### DevOps
- Git workflow (branches, merges)
- Deploy en producción
- Variables de entorno
- Debugging en navegador y servidor
---
 
## 🤝 Trabajo en equipo
 
Este fue un **proyecto colaborativo**. Trabajé con:
- **Alejandro Gonzalez**
- **Harold Maldonado**
- **Hugo Alexander**
- 
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
- ✅ Más features de generador (filtros avanzados, presupuesto)
- ✅ Recomendaciones basadas en IA
- ✅ Integración con tiendas online (Amazon, ASOS)
- ✅ Compartir listas de regalos con amigos
- ✅ Notificaciones por email
**Status:** En planning
 
---
 
## ⭐ Si te gustó este proyecto
 
Dale una ⭐ en GitHub y comparte con otros desarrolladores en busca de bootcamp.
 
---
 
**Hecho con ❤️ por Asif Alam | Full Stack Developer | Madrid, Spain**
 
*Actualizado: Septiembre 2026*
 
