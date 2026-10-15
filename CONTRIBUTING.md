# 🤝 Guía de Contribución – Aroma Café

¡Gracias por tu interés en contribuir al proyecto **Aroma Café**!

## 📋 Antes de empezar

1. Haz un **fork** del repositorio.
2. Clona tu fork: `git clone https://github.com/TU_USUARIO/aroma-cafe-web.git`
3. Configura el remote upstream: `git remote add upstream https://github.com/REPO_ORIGINAL/aroma-cafe-web.git`

## 🌿 Flujo de Trabajo Git Flow

### Ramas principales
- **`main`** → Código de producción. Solo recibe merges desde `develop` (releases) y `hotfix/*`.
- **`develop`** → Rama de integración. Recibe merges desde `feature/*`.

### Crear una nueva funcionalidad
```bash
# 1. Actualiza develop
git checkout develop
git pull upstream develop

# 2. Crea tu rama feature
git checkout -b feature/nombre-descriptivo

# 3. Haz commits con mensajes semánticos
git commit -m "feat: descripción de la funcionalidad"

# 4. Empuja tu rama
git push origin feature/nombre-descriptivo

# 5. Abre un Pull Request hacia develop
```

### Formato de commits (Conventional Commits)
```
feat:     Nueva funcionalidad
fix:      Corrección de bug
docs:     Cambios en documentación
style:    Formato, espacios (sin cambios de lógica)
refactor: Refactorización de código
test:     Adición o corrección de tests
chore:    Tareas de mantenimiento
```

### Correcciones urgentes (Hotfix)
```bash
# 1. Crea la rama desde main
git checkout main
git checkout -b hotfix/descripcion-del-fix

# 2. Aplica la corrección y haz commit
git commit -m "fix: descripción del fix"

# 3. Fusiona hacia main Y develop
git checkout main && git merge --no-ff hotfix/descripcion-del-fix
git checkout develop && git merge --no-ff hotfix/descripcion-del-fix
```

## ✅ Checklist de Pull Request

- [ ] El código sigue el estilo del proyecto
- [ ] El mensaje de commit sigue el formato de Conventional Commits
- [ ] La rama sale desde la correcta (`develop` para features, `main` para hotfixes)
- [ ] No se incluyen archivos ignorados por `.gitignore`
