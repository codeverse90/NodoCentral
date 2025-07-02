
<div align="center">

## **Guía de Contribución al Proyecto**

[![Contributors Welcome](https://img.shields.io/badge/contributors-welcome-brightgreen.svg?style=for-the-badge)](CONTRIBUTING.md)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=for-the-badge)](http://makeapullrequest.com)
[![First Timers Only](https://img.shields.io/badge/first--timers--only-friendly-blue.svg?style=for-the-badge)](https://www.firsttimersonly.com/)
[![Code Quality](https://img.shields.io/badge/code%20quality-A+-green.svg?style=for-the-badge)]()
[![Documentation](https://img.shields.io/badge/documentation-complete-blue.svg?style=for-the-badge)]()

> *"El código es poesía, y cada contribución es un verso que mejora el proyecto"*

</div>

---

## **Tabla de Contenidos**

<details>
<summary><strong>Expandir índice completo</strong></summary>

1. [**Introducción**](#introducción)
2. [**Configuración del Entorno**](#configuración-del-entorno)
3. [**Tipos de Contribuciones**](#tipos-de-contribuciones)
4. [**Flujo de Trabajo con Git**](#flujo-de-trabajo-con-git)
5. [**Estándares de Código**](#estándares-de-código)
6. [**Testing y Calidad**](#testing-y-calidad)
7. [**Documentación**](#documentación)
8. [**Proceso de Code Review**](#proceso-de-code-review)
9. [**Despliegue y CI/CD**](#despliegue-y-cicd)
10. [**Comunidad y Comunicación**](#comunidad-y-comunicación)
11. [**Troubleshooting**](#troubleshooting)
12. [**Reconocimientos**](#reconocimientos)

</details>

---

## **Introducción**

Bienvenido al proyecto. Esta guía está diseñada para ayudarte a contribuir de manera efectiva y mantener la calidad del código. Valoramos cada contribución, desde correcciones de errores hasta nuevas características.

### **Código de Conducta**

Antes de contribuir, lee nuestro [Código de Conducta](CODE_OF_CONDUCT.md). Esperamos que todos los participantes se adhieran a estos estándares.

### **Primeros Pasos**

Si eres nuevo en contribuciones de código abierto, revisa estos recursos:

- [How to Contribute to Open Source](https://opensource.guide/how-to-contribute/)
- [First Timers Only](https://www.firsttimersonly.com/)
- [Git Handbook](https://guides.github.com/introduction/git-handbook/)

---

## **Configuración del Entorno**

### **Requisitos Previos**

Asegúrate de tener instalado:

```bash
# Versiones mínimas requeridas
Node.js >= 18.0.0
npm >= 8.0.0
Git >= 2.30.0
```

### **Instalación Local**

```bash
# 1. Fork el repositorio y clónalo
git clone https://github.com/tu-usuario/nombre-proyecto.git
cd nombre-proyecto

# 2. Instala las dependencias
npm install

# 3. Copia el archivo de configuración
cp .env.example .env

# 4. Configura las variables de entorno
# Edita .env con tus configuraciones locales

# 5. Ejecuta el proyecto en modo desarrollo
npm run dev

# 6. Ejecuta los tests para verificar que todo funciona
npm test
```

### **Configuración de IDE**

#### **VS Code (Recomendado)**

Instala las siguientes extensiones:

- **ESLint** - Linting de JavaScript/TypeScript
- **Prettier** - Formateo de código
- **GitLens** - Mejor integración con Git
- **Auto Rename Tag** - Renombrado automático de tags HTML
- **Bracket Pair Colorizer** - Coloreo de brackets
- **IntelliCode** - Sugerencias de código con IA

#### **Configuración de Settings.json**

```json
{
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "emmet.includeLanguages": {
    "javascript": "javascriptreact"
  }
}
```

---

## **Tipos de Contribuciones**

### **Bug Reports**

Usa el template de **Bug Report** cuando encuentres un error:

```markdown
**Descripción del Bug**
Descripción clara y concisa del problema.

**Pasos para Reproducir**
1. Ve a '...'
2. Haz clic en '....'
3. Desplázate hacia abajo hasta '....'
4. Ver error

**Comportamiento Esperado**
Descripción clara de lo que esperabas que sucediera.

**Screenshots**
Si es aplicable, agrega screenshots.

**Información del Entorno**
- OS: [e.g. macOS, Windows, Linux]
- Browser: [e.g. Chrome, Firefox, Safari]
- Version: [e.g. 22]
```

### **Feature Requests**

Usa el template de **Feature Request** para proponer nuevas características:

```markdown
**¿Tu feature request está relacionado con un problema?**
Descripción clara y concisa del problema.

**Describe la solución que te gustaría**
Descripción clara y concisa de lo que quieres que suceda.

**Describe alternativas que hayas considerado**
Descripción clara y concisa de soluciones alternativas.

**Contexto adicional**
Agrega cualquier otro contexto o screenshots sobre el feature request.
```

### **Documentación**

- Correcciones de typos
- Mejoras en la claridad
- Ejemplos adicionales
- Traducciones
- Actualización de dependencias

### **Código**

- **Hotfixes**: Correcciones críticas
- **Features**: Nuevas funcionalidades
- **Refactoring**: Mejoras en el código existente
- **Performance**: Optimizaciones
- **Security**: Mejoras de seguridad

---

## **Flujo de Trabajo con Git**

### **Branching Strategy**

Utilizamos **GitFlow** modificado:

```
main
├── develop
│   ├── feature/nueva-funcionalidad
│   ├── feature/mejora-ui
│   └── hotfix/correccion-critica
└── release/v1.2.0
```

### **Convención de Nombres de Ramas**

```bash
# Features
feature/nombre-descriptivo
feature/login-social
feature/dashboard-analytics

# Hotfixes
hotfix/descripcion-problema
hotfix/memory-leak-fix
hotfix/security-patch

# Releases
release/v1.2.0
release/v2.0.0-beta
```

### **Workflow Completo**

```bash
# 1. Actualiza tu fork
git checkout develop
git pull upstream develop

# 2. Crea una nueva rama
git checkout -b feature/nueva-funcionalidad

# 3. Realiza tus cambios
git add .
git commit -m "feat: add new authentication system"

# 4. Push a tu fork
git push origin feature/nueva-funcionalidad

# 5. Crea un Pull Request
# Usa la interfaz web de GitHub
```

### **Convenciones de Commit**

Seguimos **Conventional Commits**:

```bash
# Tipos de commit
feat:     nueva funcionalidad
fix:      corrección de bug
docs:     cambios en documentación
style:    formateo, comas, etc.
refactor: refactoring de código
test:     agregar tests
chore:    tareas de mantenimiento

# Ejemplos
git commit -m "feat: add user authentication"
git commit -m "fix: resolve memory leak in data processing"
git commit -m "docs: update API documentation"
git commit -m "style: format code with prettier"
git commit -m "refactor: improve error handling"
git commit -m "test: add unit tests for auth service"
git commit -m "chore: update dependencies"
```

### **Mensajes de Commit Detallados**

```bash
# Formato completo
tipo(scope): descripción corta

Descripción más detallada explicando qué y por qué,
no cómo.

- Bullet point con cambios específicos
- Otro cambio importante

Fixes #123
Closes #456
```

---

## **Estándares de Código**

### **JavaScript/TypeScript**

#### **Naming Conventions**

```javascript
// Variables y funciones: camelCase
const userName = 'john_doe';
const calculateTotalPrice = () => {};

// Constantes: UPPER_SNAKE_CASE
const API_BASE_URL = 'https://api.example.com';
const MAX_RETRY_ATTEMPTS = 3;

// Clases: PascalCase
class UserService {}
class ApiClient {}

// Interfaces (TypeScript): PascalCase con prefijo I
interface IUserData {}
interface IApiResponse {}

// Tipos (TypeScript): PascalCase
type UserRole = 'admin' | 'user' | 'guest';
type ApiStatus = 'loading' | 'success' | 'error';
```

#### **Estructura de Archivos**

```javascript
// Orden de imports
// 1. Node modules
import React from 'react';
import axios from 'axios';

// 2. Internal modules
import { UserService } from '../services/UserService';
import { validateInput } from '../utils/validation';

// 3. Relative imports
import './Component.css';

// 4. Types (al final)
import type { UserData, ApiResponse } from '../types';
```

#### **Funciones**

```javascript
// Función pura preferida
const calculateTotal = (items: Item[]): number => {
  return items.reduce((sum, item) => sum + item.price, 0);
};

// Función con documentación JSDoc
/**
 * Calcula el precio total de los items
 * @param items - Array de items con precio
 * @param discount - Descuento a aplicar (0-1)
 * @returns Precio total con descuento aplicado
 */
const calculateTotalWithDiscount = (
  items: Item[],
  discount: number = 0
): number => {
  const total = calculateTotal(items);
  return total * (1 - discount);
};
```

### **React Components**

#### **Functional Components**

```typescript
// Componente funcional con TypeScript
interface UserCardProps {
  user: User;
  onEdit?: (user: User) => void;
  isEditable?: boolean;
}

const UserCard: React.FC<UserCardProps> = ({
  user,
  onEdit,
  isEditable = false
}) => {
  const [isLoading, setIsLoading] = useState(false);
  
  const handleEdit = useCallback(() => {
    if (!onEdit || !isEditable) return;
    setIsLoading(true);
    onEdit(user);
  }, [user, onEdit, isEditable]);

  return (
    <div className="user-card">
      <h3>{user.name}</h3>
      {isEditable && (
        <button onClick={handleEdit} disabled={isLoading}>
          {isLoading ? 'Guardando...' : 'Editar'}
        </button>
      )}
    </div>
  );
};

export default UserCard;
```

#### **Custom Hooks**

```typescript
// Custom hook para manejo de estado
const useUserData = (userId: string) => {
  const [user, setUser] = useState<User | null>(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState<string | null>(null);

  useEffect(() => {
    const fetchUser = async () => {
      try {
        setLoading(true);
        const userData = await UserService.getById(userId);
        setUser(userData);
        setError(null);
      } catch (err) {
        setError(err instanceof Error ? err.message : 'Error desconocido');
        setUser(null);
      } finally {
        setLoading(false);
      }
    };

    if (userId) {
      fetchUser();
    }
  }, [userId]);

  return { user, loading, error };
};
```

### **CSS/SCSS**

#### **Nomenclatura BEM**

```scss
// Block Element Modifier
.user-card {
  padding: 1rem;
  border: 1px solid #ddd;
  
  &__header {
    display: flex;
    justify-content: space-between;
    margin-bottom: 1rem;
  }
  
  &__title {
    font-size: 1.2rem;
    font-weight: bold;
    color: #333;
  }
  
  &__actions {
    display: flex;
    gap: 0.5rem;
  }
  
  &--highlighted {
    border-color: #007bff;
    background-color: #f8f9fa;
  }
  
  &--loading {
    opacity: 0.6;
    pointer-events: none;
  }
}
```

#### **Variables CSS**

```scss
// Variables globales
:root {
  // Colores
  --color-primary: #007bff;
  --color-secondary: #6c757d;
  --color-success: #28a745;
  --color-danger: #dc3545;
  --color-warning: #ffc107;
  
  // Espaciado
  --spacing-xs: 0.25rem;
  --spacing-sm: 0.5rem;
  --spacing-md: 1rem;
  --spacing-lg: 1.5rem;
  --spacing-xl: 3rem;
  
  // Tipografía
  --font-family-base: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
  --font-size-xs: 0.75rem;
  --font-size-sm: 0.875rem;
  --font-size-base: 1rem;
  --font-size-lg: 1.125rem;
  --font-size-xl: 1.25rem;
  
  // Sombras
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05);
  --shadow-md: 0 4px 6px rgba(0, 0, 0, 0.1);
  --shadow-lg: 0 10px 15px rgba(0, 0, 0, 0.1);
}
```

---

## **Testing y Calidad**

### **Tipos de Tests**

#### **Unit Tests**

```typescript
// user.service.test.ts
import { UserService } from '../UserService';
import { mockUser, mockApiResponse } from '../__mocks__/user.mocks';

describe('UserService', () => {
  describe('getById', () => {
    it('should return user data when API call succeeds', async () => {
      // Arrange
      const userId = '123';
      const expectedUser = mockUser;
      jest.spyOn(global, 'fetch').mockResolvedValueOnce(
        mockApiResponse(expectedUser)
      );

      // Act
      const result = await UserService.getById(userId);

      // Assert
      expect(result).toEqual(expectedUser);
      expect(fetch).toHaveBeenCalledWith(`/api/users/${userId}`);
    });

    it('should throw error when user not found', async () => {
      // Arrange
      const userId = 'nonexistent';
      jest.spyOn(global, 'fetch').mockRejectedValueOnce(
        new Error('User not found')
      );

      // Act & Assert
      await expect(UserService.getById(userId)).rejects.toThrow('User not found');
    });
  });
});
```

#### **Integration Tests**

```typescript
// user-card.integration.test.tsx
import { render, screen, fireEvent, waitFor } from '@testing-library/react';
import { UserCard } from '../UserCard';
import { UserService } from '../../services/UserService';

jest.mock('../../services/UserService');

describe('UserCard Integration', () => {
  it('should display user data and handle edit action', async () => {
    // Arrange
    const mockUser = { id: '1', name: 'John Doe', email: 'john@example.com' };
    const mockOnEdit = jest.fn();
    
    (UserService.getById as jest.Mock).mockResolvedValue(mockUser);

    // Act
    render(<UserCard userId="1" onEdit={mockOnEdit} isEditable />);

    // Assert
    await waitFor(() => {
      expect(screen.getByText('John Doe')).toBeInTheDocument();
    });

    // Act - click edit button
    fireEvent.click(screen.getByText('Editar'));

    // Assert
    expect(mockOnEdit).toHaveBeenCalledWith(mockUser);
  });
});
```

#### **E2E Tests**

```typescript
// user-management.e2e.test.ts
import { test, expect } from '@playwright/test';

test.describe('User Management', () => {
  test('should create, edit, and delete user', async ({ page }) => {
    // Navigate to user management
    await page.goto('/admin/users');
    
    // Create user
    await page.click('[data-testid="add-user-btn"]');
    await page.fill('[data-testid="user-name"]', 'Test User');
    await page.fill('[data-testid="user-email"]', 'test@example.com');
    await page.click('[data-testid="save-user-btn"]');
    
    // Verify user was created
    await expect(page.locator('[data-testid="user-list"]')).toContainText('Test User');
    
    // Edit user
    await page.click('[data-testid="edit-user-btn"]');
    await page.fill('[data-testid="user-name"]', 'Updated User');
    await page.click('[data-testid="save-user-btn"]');
    
    // Verify user was updated
    await expect(page.locator('[data-testid="user-list"]')).toContainText('Updated User');
    
    // Delete user
    await page.click('[data-testid="delete-user-btn"]');
    await page.click('[data-testid="confirm-delete-btn"]');
    
    // Verify user was deleted
    await expect(page.locator('[data-testid="user-list"]')).not.toContainText('Updated User');
  });
});
```

### **Configuración de Testing**

#### **Jest Configuration**

```javascript
// jest.config.js
module.exports = {
  testEnvironment: 'jsdom',
  setupFilesAfterEnv: ['<rootDir>/src/setupTests.ts'],
  moduleNameMapping: {
    '^@/(.*)$': '<rootDir>/src/$1',
    '\\.(css|less|scss|sass)$': 'identity-obj-proxy',
  },
  collectCoverageFrom: [
    'src/**/*.{ts,tsx}',
    '!src/**/*.d.ts',
    '!src/index.tsx',
    '!src/reportWebVitals.ts',
  ],
  coverageThreshold: {
    global: {
      branches: 80,
      functions: 80,
      lines: 80,
      statements: 80,
    },
  },
  testMatch: [
    '<rootDir>/src/**/__tests__/**/*.{ts,tsx}',
    '<rootDir>/src/**/*.{test,spec}.{ts,tsx}',
  ],
};
```

### **Comandos de Testing**

```bash
# Ejecutar todos los tests
npm test

# Ejecutar tests en modo watch
npm run test:watch

# Ejecutar tests con coverage
npm run test:coverage

# Ejecutar solo tests unitarios
npm run test:unit

# Ejecutar solo tests de integración
npm run test:integration

# Ejecutar tests E2E
npm run test:e2e

# Ejecutar tests específicos
npm test -- --testNamePattern="UserService"
npm test -- --testPathPattern="user"
```

---

## **Documentación**

### **JSDoc**

```typescript
/**
 * Servicio para manejo de usuarios
 * @class UserService
 */
class UserService {
  /**
   * Obtiene un usuario por su ID
   * @param {string} id - ID único del usuario
   * @returns {Promise<User>} Datos del usuario
   * @throws {Error} Cuando el usuario no existe
   * @example
   * ```typescript
   * const user = await UserService.getById('123');
   * console.log(user.name);
   * ```
   */
  static async getById(id: string): Promise<User> {
    // Implementation
  }

  /**
   * Actualiza los datos de un usuario
   * @param {string} id - ID del usuario a actualizar
   * @param {Partial<User>} updates - Datos a actualizar
   * @returns {Promise<User>} Usuario actualizado
   * @since 1.2.0
   * @deprecated Use updateUser instead
   */
  static async update(id: string, updates: Partial<User>): Promise<User> {
    // Implementation
  }
}
```

### **README Sections**

Cada componente/módulo debe tener documentación:

```markdown
# UserCard Component

## Descripción
Componente para mostrar información de usuario con capacidades de edición.

## Props
| Prop | Tipo | Requerido | Default | Descripción |
|------|------|-----------|---------|-------------|
| user | User | ✅ | - | Datos del usuario |
| onEdit | Function | ❌ | undefined | Callback para editar usuario |
| isEditable | boolean | ❌ | false | Habilita modo edición |

## Ejemplos de Uso

### Básico
```tsx
<UserCard user={userData} />
```

### Con edición
```tsx
<UserCard 
  user={userData} 
  isEditable 
  onEdit={(user) => console.log('Editing:', user)} 
/>
```

## Notas
- El componente maneja automáticamente los estados de loading
- Implementa lazy loading para imágenes de perfil
- Compatible con temas dark/light
```

### **Changelog**

```markdown
# Changelog

## [2.1.0] - 2024-01-15

### Added
- Nueva funcionalidad de autenticación social
- Soporte para temas personalizados
- Integración con API de notificaciones

### Changed
- Mejorada la performance del dashboard
- Actualizada la UI del formulario de usuario
- Refactorizado el sistema de routing

### Fixed
- Corregido el memory leak en el WebSocket
- Solucionado el problema de scroll infinito
- Arreglado el bug en la validación de email

### Deprecated
- `UserService.update()` será removido en v3.0.0
- Componente `OldButton` será reemplazado

### Removed
- Eliminado soporte para IE11
- Removidas las dependencias no utilizadas

### Security
- Actualizado el sistema de autenticación
- Parcheadas las vulnerabilidades de seguridad
```

---

## **Proceso de Code Review**

### **Checklist del Reviewer**

#### **Funcionalidad**
- [ ] El código hace lo que debe hacer
- [ ] Los edge cases están cubiertos
- [ ] No hay lógica duplicada
- [ ] Los errores se manejan apropiadamente

#### **Código**
- [ ] El código es limpio y legible
- [ ] Las variables tienen nombres descriptivos
- [ ] Las funciones son pequeñas y enfocadas
- [ ] Se siguen los patrones establecidos

#### **Performance**
- [ ] No hay bucles innecesarios
- [ ] Las consultas a la base de datos son eficientes
- [ ] Se usan lazy loading donde es apropiado
- [ ] La memoria se libera correctamente

#### **Seguridad**
- [ ] Los inputs están validados
- [ ] No hay información sensible expuesta
- [ ] Se usan HTTPS y tokens seguros
- [ ] Las dependencias están actualizadas

#### **Testing**
- [ ] Los tests existentes pasan
- [ ] Se agregaron tests para nuevo código
- [ ] El coverage es adecuado
- [ ] Los tests son significativos

### **Tipos de Comentarios**

#### **Comentarios Constructivos**

```markdown
# ✅ Bueno
"Considera usar `useMemo` aquí para optimizar el rendering cuando `items` es grande."

# ✅ Bueno
"Este patrón es excelente. ¿Podríamos extraerlo a un custom hook reutilizable?"

# ❌ Evitar
"Esto está mal."

# ❌ Evitar
"No me gusta este approach."
```

#### **Prioridades de Comentarios**

```markdown
# 🔴 MUST FIX - Bloquea el merge
- Bugs de seguridad
- Funcionalidad rota
- Tests fallando

# 🟡 SHOULD FIX - Importante pero no bloquea
- Mejoras de performance
- Refactoring sugerido
- Documentación faltante

# 🟢 COULD FIX - Sugerencias opcionales
- Optimizaciones menores
- Preferencias de estilo
- Ideas para el futuro
```

### **Proceso de Approval**

1. **Auto-review**: El autor revisa su propio código
2. **Peer review**: Al menos 2 reviewers aprueban
3. **Automated checks**: Tests y linting pasan
4. **Final approval**: Lead developer da el visto bueno

---

## **Despliegue y CI/CD**

### **Pipeline de CI/CD**

```yaml
# .github/workflows/ci-cd.yml
name: CI/CD Pipeline

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main, develop ]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    
    - name: Setup Node.js
      uses: actions/setup-node@v3
      with:
        node-version: '18'
        cache: 'npm'
    
    - name: Install dependencies
      run: npm ci
    
    - name: Run linting
      run: npm run lint
    
    - name: Run tests
      run: npm run test:coverage
    
    - name: Upload coverage
      uses: codecov/codecov-action@v3

  build:
    needs: test
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    
    - name: Setup Node.js
      uses: actions/setup-node@v3
      with:
        node-version: '18'
        cache: 'npm'
    
    - name: Install dependencies
      run: npm ci
    
    - name: Build application
      run: npm run build
    
    - name: Upload build artifacts
      uses: actions/upload-artifact@v3
      with:
        name: build-files
        path: dist/

  deploy:
    needs: build
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/main'
    steps:
    - name: Deploy to production
      run: echo "Deploying to production..."
```

### **Ambientes**

```bash
# Desarrollo
npm run dev
# http://localhost:3000

# Staging
npm run build:staging
npm run deploy:staging
# https://staging.example.com

# Production
npm run build:production
npm run deploy:production
# https://example.com
```

### **Monitoreo y Logs**

```typescript
// logger.ts
import winston from 'winston';

const logger = winston.createLogger({
  level: process.env.LOG_LEVEL || 'info',
  format: winston.format.combine(
    winston.format.timestamp(),
    winston.format.errors({ stack: true }),
    winston.format.json()
  ),
  transports: [
    new winston.transports.File({ filename: 'error.log', level: 'error' }),
    new winston.transports.File({ filename: 'combined.log' }),
  ],
});

if (process.env.NODE_ENV !== 'production') {
  logger.add(new winston.transports.Console({
    format: winston.format.simple()
  }));
}

export default logger;
```

---

## **Comunidad y Comunicación**

### **Canales de Comunicación**

- **GitHub Issues**: Para bugs y feature requests
- **GitHub Discussions**: Para preguntas generales
- **Discord**: Para chat en tiempo real
- **Email**: Para temas privados o sensibles

### **Meetings y Eventos**

- **Daily Standups**: Lunes a Viernes 9:00 AM
- **Code Review Sessions**: Martes y Jueves 2:00 PM
- **Sprint Planning**: Primer lunes de cada mes
- **Tech Talks**: Viernes 4:00 PM (opcional)

### **Onboarding para Nuevos Contributors**

1. **Semana 1**: Configuración del entorno y primeros issues
2. **Semana 2**: Primer PR y code review
3. **Semana 3**: Feature mediana y pair programming
4. **Semana 4**: Evaluación y feedback

### **Mentorship Program**

- **Mentores disponibles**: Lista de contributors experimentados
- **Programa de buddy**: Asignación de mentor para nuevos contributors
- **Sesiones de pair programming**: Semanales para aprendizaje

---

## **Troubleshooting**

### **Problemas Comunes**

#### **Error: Cannot resolve module**

```bash
# Limpiar cache y reinstalar
rm -rf node_modules package-lock.json
npm install

# Verificar versiones
node --version
npm --version
```

#### **Tests fallando después de cambios**

```bash
# Limpiar cache de Jest
npm test -- --clearCache

# Actualizar snapshots
npm test -- --updateSnapshot

# Ejecutar tests específicos
npm test -- --testNamePattern="UserService"
```

#### **Build fallando en producción**

```bash
# Verificar variables de entorno
cat .env.production

# Build con logs detallados
npm run build -- --verbose

# Verificar bundle size
npm run analyze
```

#### **Problemas de Performance**

```bash
# Analizar bundle
npm run analyze

# Profiling con React DevTools
npm run dev

# Lighthouse audit
npm run lighthouse
```

### **Comandos Útiles**

```bash
# Desarrollo
npm run dev              # Servidor de desarrollo
npm run dev:debug        # Desarrollo con debugging
npm run storybook        # Storybook para componentes

# Testing
npm test                 # Todos los tests
npm run test:watch       # Tests en modo watch
npm run test:debug       # Tests con debugging
npm run test:e2e         # Tests end-to-end

# Linting y Formateo
npm run lint             # ESLint