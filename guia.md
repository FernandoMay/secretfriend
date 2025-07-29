# 🚀 Guía Completa: Git y GitHub para Challenge Amigo Secreto

## 📋 Índice
1. [Configuración Inicial de Git](#configuración-inicial)
2. [Crear Repositorio en GitHub](#crear-repositorio)
3. [Subir Proyecto a GitHub](#subir-proyecto)
4. [Comandos Git Esenciales](#comandos-esenciales)
5. [Workflow de Desarrollo](#workflow)
6. [GitHub Pages (Opcional)](#github-pages)
7. [Troubleshooting](#troubleshooting)

---

## 🔧 Configuración Inicial de Git

### 1. Verificar Instalación de Git
```bash
# Verificar si Git está instalado
git --version

# Si no está instalado, descarga desde: https://git-scm.com/
```

### 2. Configurar Usuario Global
```bash
# Configurar nombre de usuario
git config --global user.name "Tu Nombre Completo"

# Configurar email
git config --global user.email "tu.email@ejemplo.com"

# Verificar configuración
git config --list
```

### 3. Configuraciones Adicionales Recomendadas
```bash
# Configurar editor por defecto (opcional)
git config --global core.editor "code --wait"

# Configurar colores en terminal
git config --global color.ui true

# Configurar rama por defecto
git config --global init.defaultBranch main
```

---

## 📁 Crear Repositorio en GitHub

### Paso 1: Crear Repositorio Web
1. Ve a [GitHub.com](https://github.com)
2. Haz clic en el botón verde **"New"** o **"+"** → **"New repository"**
3. Completa la información:
   ```
   Repository name: challenge-amigo-secreto
   Description: Challenge ONE - Aplicación web para sorteo de amigo secreto
   ✅ Public (para que sea visible)
   ❌ Add a README file (lo crearemos nosotros)
   ❌ Add .gitignore
   ❌ Choose a license
   ```
4. Haz clic en **"Create repository"**

### Paso 2: Copiar URL del Repositorio
```bash
# URL HTTPS (recomendada para principiantes)
https://github.com/tu-usuario/challenge-amigo-secreto.git

# URL SSH (para usuarios avanzados)
git@github.com:tu-usuario/challenge-amigo-secreto.git
```

---

## 📤 Subir Proyecto a GitHub

### Método 1: Proyecto Nuevo (Desde Cero)

#### 1. Crear Estructura del Proyecto
```bash
# Crear directorio del proyecto
mkdir challenge-amigo-secreto
cd challenge-amigo-secreto

# Crear archivos principales
touch index.html
touch README.md
touch .gitignore
```

#### 2. Inicializar Repositorio Git
```bash
# Inicializar Git en el directorio
git init

# Verificar estado
git status
```

#### 3. Crear .gitignore
```bash
# Crear archivo .gitignore con contenido básico
echo "# Archivos temporales
.DS_Store
Thumbs.db
*.tmp
*.temp

# Carpetas de dependencias
node_modules/
.npm/

# Archivos de configuración local
.env
.vscode/settings.json

# Archivos de backup
*.bak
*.backup" > .gitignore
```

#### 4. Agregar Archivos y Hacer Primer Commit
```bash
# Agregar todos los archivos al staging area
git add .

# O agregar archivos específicos
git add index.html README.md .gitignore

# Hacer el primer commit
git commit -m "🎉 Initial commit: Challenge Amigo Secreto setup"

# Verificar el commit
git log --oneline
```

#### 5. Conectar con GitHub y Subir
```bash
# Agregar repositorio remoto
git remote add origin https://github.com/tu-usuario/challenge-amigo-secreto.git

# Verificar remote
git remote -v

# Cambiar nombre de rama a main (si es necesario)
git branch -M main

# Subir al repositorio remoto
git push -u origin main
```

### Método 2: Proyecto Existente

#### Si ya tienes archivos listos:
```bash
# Navegar al directorio del proyecto existente
cd ruta/a/tu/proyecto

# Inicializar Git
git init

# Agregar archivos
git add .

# Hacer commit inicial
git commit -m "🎉 Initial commit: Challenge Amigo Secreto"

# Conectar con GitHub
git remote add origin https://github.com/tu-usuario/challenge-amigo-secreto.git

# Subir archivos
git branch -M main
git push -u origin main
```

---

## ⚡ Comandos Git Esenciales

### Comandos Básicos de Workflow
```bash
# Ver estado actual
git status

# Ver diferencias
git diff

# Agregar archivos específicos
git add index.html
git add README.md

# Agregar todos los archivos modificados
git add .

# Hacer commit con mensaje descriptivo
git commit -m "✨ Add: Función de sorteo aleatorio"

# Subir cambios a GitHub
git push

# Descargar cambios del repositorio remoto
git pull
```

### Comandos de Información
```bash
# Ver historial de commits
git log
git log --oneline
git log --graph --oneline --all

# Ver información de branches
git branch
git branch -a

# Ver remotes configurados
git remote -v

# Ver diferencias específicas
git diff HEAD~1  # Comparar con commit anterior
git diff --staged  # Ver cambios en staging area
```

### Comandos para Deshacer Cambios
```bash
# Deshacer cambios en un archivo (antes de add)
git checkout -- index.html

# Quitar archivo del staging area
git reset HEAD index.html

# Deshacer último commit (mantener cambios)
git reset --soft HEAD~1

# Deshacer último commit (perder cambios)
git reset --hard HEAD~1
```

---

## 🔄 Workflow de Desarrollo Recomendado

### Flujo Básico para el Challenge
```bash
# 1. Verificar estado antes de trabajar
git status
git pull  # Por si hay cambios remotos

# 2. Hacer cambios en tu código
# (Editar archivos en tu editor)

# 3. Revisar cambios
git status
git diff

# 4. Agregar cambios al staging area
git add .
# o específicamente: git add index.html

# 5. Hacer commit con mensaje descriptivo
git commit -m "🐛 Fix: Validación de nombres duplicados"

# 6. Subir a GitHub
git push
```

### Mensajes de Commit Recomendados
```bash
# Estructura: [emoji] [tipo]: [descripción]

git commit -m "🎉 Initial commit: Setup del proyecto"
git commit -m "✨ Add: Función agregar amigos"
git commit -m "🐛 Fix: Error en sorteo con menos de 2 personas"
git commit -m "💄 Style: Mejoras en diseño responsive"
git commit -m "📝 Docs: Actualizar README con screenshots"
git commit -m "♻️ Refactor: Optimizar función de validación"
git commit -m "🚀 Deploy: Configurar GitHub Pages"
```

### Emojis Útiles para Commits
- 🎉 `:tada:` - Commit inicial
- ✨ `:sparkles:` - Nueva funcionalidad
- 🐛 `:bug:` - Corrección de errores
- 💄 `:lipstick:` - Mejoras de UI/styling
- 📝 `:memo:` - Documentación
- ♻️ `:recycle:` - Refactoring
- 🚀 `:rocket:` - Deploy/performance
- 🔧 `:wrench:` - Configuración

---

## 🌐 GitHub Pages (Hosting Gratuito)

### Activar GitHub Pages
1. Ve a tu repositorio en GitHub
2. Clic en **Settings** (Configuración)
3. Scroll down a **Pages** en el sidebar izquierdo
4. En **Source** selecciona **Deploy from a branch**
5. En **Branch** selecciona **main** y **/ (root)**
6. Clic en **Save**

### Tu sitio estará disponible en:
```
https://tu-usuario.github.io/challenge-amigo-secreto/
```

### Actualizar GitHub Pages
```bash
# Cualquier push a main actualizará automáticamente tu sitio
git add .
git commit -m "🚀 Update: Mejoras en la aplicación"
git push
```

---

## 🔥 Ejemplo Completo: Desde Cero hasta Deploy

### Paso a Paso Completo
```bash
# 1. Crear directorio y archivos
mkdir challenge-amigo-secreto
cd challenge-amigo-secreto

# 2. Crear los archivos del proyecto
# (Aquí pegas el código HTML que te proporcioné)
code index.html  # Pegar código de la aplicación
code README.md   # Pegar README que creamos

# 3. Crear .gitignore
echo ".DS_Store
Thumbs.db
*.tmp" > .gitignore

# 4. Inicializar Git
git init

# 5. Primer commit
git add .
git commit -m "🎉 Initial commit: Challenge Amigo Secreto completo"

# 6. Conectar con GitHub (repo ya creado en web)
git remote add origin https://github.com/tu-usuario/challenge-amigo-secreto.git

# 7. Subir código
git branch -M main
git push -u origin main

# 8. Activar GitHub Pages desde la web

# 9. ¡Listo! Tu aplicación está online
```

---

## 🆘 Troubleshooting (Solución de Problemas)

### Error: "Repository not found"
```bash
# Verificar URL del remote
git remote -v

# Cambiar URL si está incorrecta
git remote set-url origin https://github.com/tu-usuario/challenge-amigo-secreto.git
```

### Error: "Permission denied"
```bash
# Verificar configuración de usuario
git config user.name
git config user.email

# Reconfigurar si es necesario
git config --global user.name "Tu Nombre"
git config --global user.email "tu.email@ejemplo.com"
```

### Error: "Updates were rejected"
```bash
# Descargar cambios primero
git pull origin main

# Si hay conflictos, resolverlos manualmente
# Luego hacer push
git push origin main
```

### Olvidé hacer commit de cambios importantes
```bash
# Ver cambios no committeados
git diff

# Hacer stash para guardar temporalmente
git stash

# Aplicar stash después
git stash pop
```

### Cómo deshacer el último commit
```bash
# Mantener cambios en working directory
git reset --soft HEAD~1

# Eliminar cambios completamente
git reset --hard HEAD~1
```

---

## 📚 Comandos de Referencia Rápida

### Configuración Inicial
```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```

### Workflow Básico
```bash
git init                    # Inicializar repo
git add .                   # Agregar archivos
git commit -m "mensaje"     # Hacer commit
git remote add origin URL   # Conectar GitHub
git push -u origin main     # Subir primera vez
git push                    # Subir cambios
git pull                    # Descargar cambios
```

### Información
```bash
git status                  # Estado actual
git log --oneline          # Historial
git diff                   # Ver cambios
git remote -v              # Ver remotes
```

---

## ✅ Checklist Final

Antes de entregar el challenge, verifica:

- [ ] ✅ Repositorio creado en GitHub
- [ ] ✅ Código subido correctamente
- [ ] ✅ README.md completo y detallado
- [ ] ✅ .gitignore configurado
- [ ] ✅ Commits con mensajes descriptivos
- [ ] ✅ GitHub Pages activado (opcional)
- [ ] ✅ URL del repositorio lista para entregar

### URL para Entregar
```
https://github.com/tu-usuario/challenge-amigo-secreto
```

---

## 🎯 Próximos Pasos

1. **Clona** o crea tu repositorio siguiendo esta guía
2. **Pega** el código de la aplicación en `index.html`
3. **Copia** el README que creamos
4. **Sigue** el workflow de Git para subir todo
5. **Activa** GitHub Pages para tener tu sitio online
6. **Entrega** la URL de tu repositorio

¡Ya tienes todo listo para entregar tu Challenge! 🚀

---

*Guía creada para el Challenge Amigo Secreto - Oracle Next Education & Alura Latam*