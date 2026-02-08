# 🚀 Sistema de Gestión Documental - Railway Ready

## 📌 Resumen Ejecutivo

Este proyecto ha sido completamente preparado para deployment en Railway con arquitectura separada de Backend y Frontend. Todo está listo para desplegar en menos de 40 minutos.

## ✅ Estado del Proyecto

```
✅ Backend:      Listo para Railway
✅ Frontend:     Listo para Railway  
✅ Base de Datos: Configurada para PostgreSQL
✅ Documentación: Completa
✅ Scripts:      Incluidos
✅ Verificación: 24/24 checks pasados
```

## 🎯 Inicio Rápido

### Opción 1: Deployment Completo (Recomendado)

```bash
# 1. Verificar que todo esté listo
node verificar-deployment.js

# 2. Preparar proyecto
preparar-deployment.bat

# 3. Seguir la guía paso a paso
# Abrir: GUIA_DEPLOYMENT_RAILWAY.md
```

### Opción 2: Desarrollo Local

```bash
# Terminal 1: Backend
cd backend
npm install
npm run dev

# Terminal 2: Frontend
cd frontend
npm install
npm start
```

## 📚 Documentación Disponible

| Archivo | Descripción | Cuándo Usar |
|---------|-------------|-------------|
| **GUIA_DEPLOYMENT_RAILWAY.md** | Guía completa paso a paso | Para deployment inicial |
| **CHECKLIST_DEPLOYMENT.md** | Lista de verificación | Durante el deployment |
| **COMANDOS_RAPIDOS_RAILWAY.md** | Referencia de comandos | Para consultas rápidas |
| **ARQUITECTURA_SEPARADA_RAILWAY.md** | Documentación técnica | Para entender la arquitectura |
| **RESUMEN_ARQUITECTURA_RAILWAY.md** | Resumen ejecutivo | Para overview rápido |
| **backend/README.md** | Documentación del backend | Para desarrollo backend |
| **frontend/README.md** | Documentación del frontend | Para desarrollo frontend |

## 🏗️ Estructura del Proyecto

```
proyecto/
│
├── 📁 backend/                    # Backend API (Independiente)
│   ├── config/                    # Configuración
│   │   └── database.js           # ✅ Soporta Railway DATABASE_URL
│   ├── middleware/                # Middlewares
│   ├── routes/                    # Rutas de la API
│   ├── uploads/                   # Archivos subidos
│   ├── server.js                 # ✅ Servidor principal
│   ├── package.json              # ✅ Dependencias backend
│   ├── railway.json              # ✅ Config Railway
│   ├── .env.example              # ✅ Template variables
│   ├── .gitignore                # ✅ Git ignore
│   └── README.md                 # ✅ Documentación
│
├── 📁 frontend/                   # Frontend React (Independiente)
│   ├── public/                    # Archivos estáticos
│   ├── src/                       # Código fuente
│   │   ├── components/           # Componentes React
│   │   ├── contexts/             # Context API
│   │   ├── hooks/                # Custom hooks
│   │   └── theme/                # Tema Material-UI
│   ├── package.json              # ✅ Dependencias frontend
│   ├── railway.json              # ✅ Config Railway
│   ├── .env.example              # ✅ Template variables
│   ├── .env.production           # ✅ Variables producción
│   ├── .gitignore                # ✅ Git ignore
│   └── README.md                 # ✅ Documentación
│
├── 📁 database/                   # Schemas SQL
│   ├── schema.sql                # Schema principal
│   └── notifications-schema.sql  # Schema notificaciones
│
├── 📄 GUIA_DEPLOYMENT_RAILWAY.md         # 📖 Guía principal
├── 📄 CHECKLIST_DEPLOYMENT.md            # ✅ Checklist
├── 📄 COMANDOS_RAPIDOS_RAILWAY.md        # ⚡ Comandos
├── 📄 ARQUITECTURA_SEPARADA_RAILWAY.md   # 🏗️ Arquitectura
├── 📄 RESUMEN_ARQUITECTURA_RAILWAY.md    # 📊 Resumen
├── 📄 preparar-deployment.bat            # 🔧 Script preparación
└── 📄 verificar-deployment.js            # ✅ Script verificación
```

## 🔧 Tecnologías

### Backend
- **Node.js** v18+ - Runtime
- **Express** - Framework web
- **PostgreSQL** - Base de datos
- **JWT** - Autenticación
- **Bcrypt** - Hash de contraseñas
- **Multer** - Subida de archivos

### Frontend
- **React** v19 - Librería UI
- **Material-UI** v7 - Componentes
- **React Router** v7 - Enrutamiento
- **Axios** - Cliente HTTP
- **Monaco Editor** - Editor de código

### Infraestructura
- **Railway** - Hosting y deployment
- **GitHub** - Control de versiones
- **PostgreSQL** - Base de datos gestionada

## 🚀 Proceso de Deployment

### Diagrama de Flujo

```
┌─────────────────┐
│  Código Local   │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  GitHub Repos   │
│  - Backend      │
│  - Frontend     │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Railway.app    │
│  - Auto Deploy  │
│  - PostgreSQL   │
│  - HTTPS        │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Producción     │
│  ✅ Backend URL │
│  ✅ Frontend URL│
└─────────────────┘
```

### Tiempo Estimado

| Fase | Tiempo | Dificultad |
|------|--------|------------|
| Preparación Local | 5 min | Fácil |
| Backend GitHub | 5 min | Fácil |
| Frontend GitHub | 5 min | Fácil |
| Backend Railway | 10 min | Media |
| Frontend Railway | 10 min | Media |
| Configuración Final | 5 min | Fácil |
| **TOTAL** | **40 min** | **Fácil** |

## 🔐 Seguridad

### Variables de Entorno

**Backend (Railway)**:
```env
NODE_ENV=production
JWT_SECRET=genera-secret-aleatorio-seguro
CORS_ORIGIN=https://tu-frontend.railway.app
DATABASE_URL=postgresql://... (auto-configurada)
```

**Frontend (Railway)**:
```env
REACT_APP_API_URL=https://tu-backend.railway.app
GENERATE_SOURCEMAP=false
```

### Mejores Prácticas Implementadas

- ✅ Contraseñas hasheadas con bcrypt
- ✅ JWT para autenticación
- ✅ CORS configurado correctamente
- ✅ Variables de entorno para secretos
- ✅ SSL/HTTPS automático en Railway
- ✅ Validación de inputs
- ✅ Middleware de autenticación

## 📊 Características del Sistema

### Funcionalidades
- ✅ Sistema de autenticación con roles
- ✅ Gestión completa de documentos (CRUD)
- ✅ Editor de documentos integrado
- ✅ Apertura en editores externos
- ✅ Sistema de notificaciones
- ✅ Gestión de usuarios (Admin)
- ✅ Gestión de categorías
- ✅ Dashboard con estadísticas
- ✅ Búsqueda y filtrado
- ✅ Responsive design

### Roles de Usuario
- **Admin**: Acceso completo al sistema
- **Editor**: Puede crear y editar documentos
- **Asesor**: Solo lectura de documentos

## 💰 Costos en Railway

### Plan Hobby ($5/mes)
- ✅ $5 de crédito incluido
- ✅ Backend + Frontend + PostgreSQL
- ✅ Suficiente para proyectos pequeños
- ✅ HTTPS incluido
- ✅ Deploys ilimitados

### Estimación de Uso
- Backend: ~$2-3/mes
- Frontend: ~$1-2/mes
- PostgreSQL: Incluido
- **Total**: ~$5/mes

## 🛠️ Scripts Disponibles

### Preparación
```bash
preparar-deployment.bat    # Prepara el proyecto
verificar-deployment.js    # Verifica configuración
```

### Desarrollo
```bash
# Backend
npm run dev               # Desarrollo con nodemon
npm start                 # Producción

# Frontend
npm start                 # Desarrollo
npm run build            # Build de producción
npm run serve            # Servir build localmente
```

### Utilidades
```bash
reset-admin-rapido.js     # Restablecer password admin
test-login-api.js         # Probar API de login
diagnostico-login.js      # Diagnosticar problemas
```

## 🐛 Troubleshooting

### Problemas Comunes

| Problema | Solución |
|----------|----------|
| Backend no responde | Revisar logs en Railway |
| Error de CORS | Verificar CORS_ORIGIN |
| Login falla | Verificar usuarios en DB |
| Build falla | Revisar dependencias |
| Variables no cargan | Verificar prefijo REACT_APP_ |

### Comandos de Diagnóstico

```bash
# Verificar configuración
node verificar-deployment.js

# Probar API local
node test-login-api.js

# Diagnosticar login
node diagnostico-login.js

# Ver logs en Railway
railway logs --follow
```

## 📞 Soporte

### Recursos
- 📖 [Railway Docs](https://docs.railway.app)
- 💬 [Railway Discord](https://discord.gg/railway)
- 📧 [Railway Support](https://railway.app/support)

### Documentación del Proyecto
- `GUIA_DEPLOYMENT_RAILWAY.md` - Guía completa
- `CHECKLIST_DEPLOYMENT.md` - Lista de verificación
- `COMANDOS_RAPIDOS_RAILWAY.md` - Referencia rápida

## 🎯 Próximos Pasos

1. **Ahora**: Ejecutar `node verificar-deployment.js`
2. **Luego**: Ejecutar `preparar-deployment.bat`
3. **Después**: Abrir `GUIA_DEPLOYMENT_RAILWAY.md`
4. **Finalmente**: Seguir la guía paso a paso

## ✨ Características de la Arquitectura

### Ventajas
- ✅ **Escalabilidad**: Servicios independientes
- ✅ **Mantenimiento**: Cambios aislados
- ✅ **Performance**: Optimización por servicio
- ✅ **Desarrollo**: Equipos paralelos
- ✅ **Deployment**: Independiente y rápido
- ✅ **Costos**: Optimización de recursos

### Arquitectura Cloud

```
Internet (HTTPS)
    │
    ├─► Frontend (React)
    │   └─► Servido con 'serve'
    │
    └─► Backend (Node.js)
        └─► PostgreSQL
```

## 📝 Licencia

Este proyecto es privado y confidencial.

## 👥 Usuarios de Prueba

| Usuario | Contraseña | Rol |
|---------|------------|-----|
| admin | admin123 | Administrador |
| editor | editor123 | Editor |
| asesor | asesor123 | Asesor |

## 🎉 ¡Listo para Desplegar!

Tu proyecto está **100% preparado** para Railway. Sigue la guía y tendrás tu aplicación en la nube en menos de 40 minutos.

```bash
# Comienza ahora
node verificar-deployment.js
```

---

**Fecha de preparación**: 2 de febrero de 2026
**Estado**: ✅ Listo para Railway
**Verificación**: 24/24 checks pasados
**Tiempo estimado**: 40 minutos

---

**¡Buena suerte con tu deployment! 🚀**
