# ✅ Checklist de Deployment en Railway

## 📋 Pre-Deployment

### Preparación Local
- [ ] Ejecutar `node verificar-deployment.js`
- [ ] Verificar que no hay errores
- [ ] Ejecutar `preparar-deployment.bat`
- [ ] Revisar `GUIA_DEPLOYMENT_RAILWAY.md`

### Cuentas Necesarias
- [ ] Cuenta en Railway.app creada
- [ ] Cuenta en GitHub creada
- [ ] Git instalado localmente
- [ ] Node.js v18+ instalado

---

## 🔧 Backend

### Repositorio GitHub
- [ ] Crear repositorio `sgd-backend` en GitHub
- [ ] Navegar a carpeta `backend`
- [ ] Ejecutar `git init`
- [ ] Ejecutar `git add .`
- [ ] Ejecutar `git commit -m "Initial backend commit"`
- [ ] Conectar remote: `git remote add origin URL`
- [ ] Push: `git push -u origin main`

### Railway - Backend
- [ ] Ir a Railway.app
- [ ] Crear nuevo proyecto
- [ ] Deploy from GitHub repo
- [ ] Seleccionar repositorio `sgd-backend`
- [ ] Esperar primer deploy

### Base de Datos
- [ ] En Railway, clic en "+ New"
- [ ] Seleccionar "Database" → "PostgreSQL"
- [ ] Esperar creación de la base de datos
- [ ] Verificar que `DATABASE_URL` esté configurada

### Variables de Entorno - Backend
- [ ] Ir a Backend → Variables
- [ ] Agregar `NODE_ENV=production`
- [ ] Agregar `JWT_SECRET=[generar secret seguro]`
- [ ] Guardar cambios
- [ ] Esperar redeploy automático

### Dominio - Backend
- [ ] Ir a Backend → Settings → Networking
- [ ] Clic en "Generate Domain"
- [ ] Copiar URL generada (ej: `https://xxx.railway.app`)
- [ ] Guardar URL para configurar frontend

### Migraciones
- [ ] Opción A: Railway CLI
  - [ ] Instalar: `npm install -g @railway/cli`
  - [ ] Login: `railway login`
  - [ ] Link: `railway link`
  - [ ] Ejecutar: `railway run psql < ../database/schema.sql`
- [ ] Opción B: Dashboard
  - [ ] Ir a PostgreSQL → Data
  - [ ] Copiar contenido de `database/schema.sql`
  - [ ] Pegar y ejecutar

### Verificación - Backend
- [ ] Abrir: `https://tu-backend.railway.app/api/health`
- [ ] Verificar respuesta JSON con status "OK"
- [ ] Revisar logs en Railway para errores

---

## 🎨 Frontend

### Repositorio GitHub
- [ ] Crear repositorio `sgd-frontend` en GitHub
- [ ] Navegar a carpeta `frontend`
- [ ] Ejecutar `git init`
- [ ] Ejecutar `git add .`
- [ ] Ejecutar `git commit -m "Initial frontend commit"`
- [ ] Conectar remote: `git remote add origin URL`
- [ ] Push: `git push -u origin main`

### Railway - Frontend
- [ ] En el mismo proyecto Railway, clic "+ New"
- [ ] Seleccionar "GitHub Repo"
- [ ] Seleccionar repositorio `sgd-frontend`
- [ ] Esperar primer deploy

### Variables de Entorno - Frontend
- [ ] Ir a Frontend → Variables
- [ ] Agregar `REACT_APP_API_URL=[URL del backend]`
- [ ] Agregar `GENERATE_SOURCEMAP=false`
- [ ] Guardar cambios
- [ ] Esperar redeploy automático

### Dominio - Frontend
- [ ] Ir a Frontend → Settings → Networking
- [ ] Clic en "Generate Domain"
- [ ] Copiar URL generada (ej: `https://xxx.railway.app`)
- [ ] Guardar URL

### Verificación - Frontend
- [ ] Abrir URL del frontend en navegador
- [ ] Verificar que carga la página de login
- [ ] Abrir DevTools (F12) → Console
- [ ] Verificar que no hay errores

---

## 🔄 Configuración Final

### Actualizar CORS en Backend
- [ ] Ir a Backend → Variables en Railway
- [ ] Agregar `CORS_ORIGIN=[URL del frontend]`
- [ ] Agregar `FRONTEND_URL=[URL del frontend]`
- [ ] Guardar cambios
- [ ] Esperar redeploy

### Crear Usuarios Iniciales
- [ ] Opción A: Railway CLI
  - [ ] `railway link` (en carpeta backend)
  - [ ] `railway run node ../reset-admin-rapido.js`
- [ ] Opción B: SQL Directo
  - [ ] Ir a PostgreSQL → Data
  - [ ] Ejecutar INSERT de usuarios
- [ ] Opción C: Desde la app
  - [ ] Usar endpoint de registro si está habilitado

### Verificación de Usuarios
- [ ] Conectar a PostgreSQL en Railway
- [ ] Ejecutar: `SELECT * FROM usuarios;`
- [ ] Verificar que existen usuarios

---

## ✅ Pruebas Finales

### Test de Conectividad
- [ ] Abrir frontend en navegador
- [ ] Abrir DevTools (F12) → Network
- [ ] Intentar login con `admin` / `admin123`
- [ ] Verificar que request va al backend correcto
- [ ] Verificar respuesta 200 OK

### Test de Funcionalidades
- [ ] Login exitoso
- [ ] Dashboard carga correctamente
- [ ] Listar documentos funciona
- [ ] Crear documento funciona
- [ ] Editar documento funciona
- [ ] Eliminar documento funciona
- [ ] Notificaciones funcionan
- [ ] Logout funciona

### Test de Roles
- [ ] Login como admin → Acceso completo
- [ ] Login como editor → Puede editar
- [ ] Login como asesor → Solo lectura

---

## 🐛 Troubleshooting

### Si Backend no Responde
- [ ] Revisar logs: Railway → Backend → Logs
- [ ] Verificar variables de entorno
- [ ] Verificar conexión a base de datos
- [ ] Verificar que el puerto no esté hardcodeado

### Si Frontend no Carga
- [ ] Revisar logs: Railway → Frontend → Logs
- [ ] Verificar que build fue exitoso
- [ ] Verificar `REACT_APP_API_URL`
- [ ] Limpiar caché del navegador

### Si hay Error de CORS
- [ ] Verificar `CORS_ORIGIN` en backend
- [ ] Verificar que incluye URL completa del frontend
- [ ] Verificar que usa HTTPS (no HTTP)
- [ ] Redeploy backend después de cambiar

### Si Login Falla
- [ ] Verificar que usuarios existen en DB
- [ ] Verificar `JWT_SECRET` configurado
- [ ] Verificar que backend responde en `/api/auth/login`
- [ ] Revisar logs del backend

---

## 📊 Monitoreo Post-Deployment

### Primeras 24 Horas
- [ ] Revisar logs cada hora
- [ ] Verificar uso de recursos
- [ ] Probar todas las funcionalidades
- [ ] Verificar que no hay memory leaks

### Primera Semana
- [ ] Revisar logs diariamente
- [ ] Monitorear costos en Railway
- [ ] Verificar performance
- [ ] Recopilar feedback de usuarios

### Mantenimiento Regular
- [ ] Revisar logs semanalmente
- [ ] Actualizar dependencias mensualmente
- [ ] Hacer backups de base de datos
- [ ] Revisar métricas de uso

---

## 🎉 Deployment Completado

### URLs Finales
- [ ] Backend: `https://_____.railway.app`
- [ ] Frontend: `https://_____.railway.app`
- [ ] Health Check: `https://_____.railway.app/api/health`

### Credenciales
- [ ] Usuario admin: `admin` / `admin123`
- [ ] Usuario editor: `editor` / `editor123`
- [ ] Usuario asesor: `asesor` / `asesor123`

### Documentación
- [ ] URLs guardadas en lugar seguro
- [ ] Credenciales documentadas
- [ ] Variables de entorno respaldadas
- [ ] Guías de deployment archivadas

---

## 📝 Notas Adicionales

### Información Importante
```
Proyecto: Sistema de Gestión Documental
Fecha de Deployment: _______________
Backend URL: _______________________
Frontend URL: ______________________
Database: PostgreSQL en Railway
```

### Contactos
```
Railway Support: https://railway.app/support
GitHub Repos:
  - Backend: ________________________
  - Frontend: _______________________
```

### Próximos Pasos
- [ ] Configurar dominio personalizado (opcional)
- [ ] Configurar SSL personalizado (opcional)
- [ ] Configurar CI/CD avanzado (opcional)
- [ ] Configurar monitoreo externo (opcional)
- [ ] Configurar backups automáticos (opcional)

---

**Estado**: ⬜ No iniciado | 🟡 En progreso | ✅ Completado

**Fecha de inicio**: _______________
**Fecha de completado**: _______________
**Tiempo total**: _______________

---

¡Buena suerte con tu deployment! 🚀
