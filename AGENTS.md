# AGENTS

Guia de contexto y directrices operativas para agentes IA que trabajen en este repositorio (`client-template`).

---

## 🎯 Regla Fundamental de Activación de Skills

El proyecto incluye una colección de **skills locales especializadas** en la carpeta `skills/`.

> ⚠️ **REGLA OBLIGATORIA:** Antes de escribir, modificar o refactorizar código, diseñar interfaces o ejecutar diagnósticos, el agente **DEBE verificar la acción que va a realizar** y consultar el archivo `SKILL.md` correspondiente (`skills/<nombre-skill>/SKILL.md`) para aplicar estrictamente sus patrones y mejores prácticas.

---

## 🗺️ Matriz de Decisión: ¿Qué acción estás realizando?

Usa esta tabla para determinar qué skill(s) activar según la tarea:

| Si la acción del agente o usuario es... | Skill a activar | Ruta del manual |
| :--- | :--- | :--- |
| **Crear o modificar componentes, páginas, layouts, providers, estilos o consumo de APIs (MUI, Emotion, React Query)** | `create-component` | `skills/create-component/SKILL.md` |
| **Diseñar arquitectura de componentes, compound components, render props o refactorizar boolean props** | `composition-patterns` | `skills/composition-patterns/SKILL.md` |
| **Optimizar rendimiento en React, re-renders innecesarios, bundle size o data fetching eficiente** | `react-best-practices` | `skills/react-best-practices/SKILL.md` |
| **Diseñar interfaces de alta calidad visual, tipografía, microinteracciones y evitar estéticas genéricas ("AI slop")** | `frontend-design` | `skills/frontend-design/SKILL.md` |
| **Auditar o corregir accesibilidad web (a11y), cumplimiento WCAG 2.2, contraste, navegación por teclado o ARIA** | `accessibility` | `skills/accessibility/SKILL.md` |
| **Tipado avanzado en TypeScript, genéricos, mapped types, conditional types, utility types o resolver errores de tipos** | `typescript-advanced-types` | `skills/typescript-advanced-types/SKILL.md` |
| **Escribir o corregir pruebas unitarias con Vitest y React Testing Library en `src/test/`, mocks con `vi` o spies** | `vitest` | `skills/vitest/SKILL.md` |
| **Configurar `vite.config.ts`, plugins de Vite/Babel/Rolldown, variables `import.meta.env` o problemas de build** | `vite` | `skills/vite/SKILL.md` |
| **Optimizar SEO, meta tags, OpenGraph, Twitter Cards, datos estructurados (JSON-LD) o sitemap** | `seo` | `skills/seo/SKILL.md` |
| **Integrar patrones de backend en Node.js, flujos de autenticación, WebSockets o consumo de microservicios** | `nodejs-backend-patterns` | `skills/nodejs-backend-patterns/SKILL.md` |
| **Tomar decisiones arquitectónicas en Node.js, tooling, async handling, gestión de variables de entorno y seguridad** | `nodejs-best-practices` | `skills/nodejs-best-practices/SKILL.md` |

---

## 📚 Catálogo Detallado de Skills y Cuándo Usarlas

### 1. `create-component` (Obligatoria para UI en este repositorio)
* **Ruta:** `skills/create-component/SKILL.md`
* **Propósito:** Guía oficial y obligatoria del repositorio para crear o modificar componentes con React 19, MUI 9, Emotion, traducciones (i18next), hooks, rutas y acceso a datos (Axios + TanStack Query).
* **Cuándo activarla:**
  - Siempre que se cree o modifique un componente, página, layout o provider.
  - Al estructurar archivos de componentes (`Component.tsx`, `Component.types.ts`, `Component.styles.ts`, `useComponent.ts`).
  - Al conectar componentes con `mainInstance` o TanStack Query.
  - Si existe conflicto entre la skill y las convenciones del repositorio, priorizar siempre las convenciones del repositorio.

### 2. `composition-patterns`
* **Ruta:** `skills/composition-patterns/SKILL.md`
* **Propósito:** Patrones de composición en React que escalan (Vercel), evitando la proliferación excesiva de boolean props (`isHeader`, `hasFooter`, etc.).
* **Cuándo activarla:**
  - Al refactorizar componentes monolíticos con demasiadas props de configuración.
  - Al diseñar componentes compuestos (Compound Components, ej. `<Select><Select.Option /></Select>`).
  - Al implementar render props, context providers o slots de composición.
  - Al aprovechar las nuevas APIs y patrones de React 19 (`action`, `use`, `Context` nativo sin `.Provider`).

### 3. `react-best-practices`
* **Ruta:** `skills/react-best-practices/SKILL.md`
* **Propósito:** Directrices de optimización de rendimiento de ingeniería de Vercel (70 reglas prioritarias).
* **Cuándo activarla:**
  - Al optimizar componentes con re-renders lentos o innecesarios (`rerender-`).
  - Al eliminar waterfalls asíncronos en la carga de datos (`async-`).
  - Al reducir el bundle size y optimizar imports de librerías grandes como MUI (`bundle-`).
  - Al implementar virtualización de listas o memorización estratégica.

### 4. `frontend-design`
* **Ruta:** `skills/frontend-design/SKILL.md`
* **Propósito:** Creación de interfaces web memorables, con dirección estética definida y libres del patrón visual genérico de IA ("AI slop").
* **Cuándo activarla:**
  - Al diseñar o estilizar nuevas vistas, landing pages, dashboards o componentes visuales.
  - Al seleccionar combinaciones tipográficas intencionales y jerarquías visuales.
  - Al añadir microinteracciones, animaciones de entrada, efectos visuales y estados hover/focus atractivos.
  - Al componer espacios asimétricos o layouts distintivos respetando la identidad del producto.

### 5. `accessibility` (a11y)
* **Ruta:** `skills/accessibility/SKILL.md`
* **Propósito:** Cumplimiento de pautas WCAG 2.2 (principios POUR) y optimización de auditorías Lighthouse.
* **Cuándo activarla:**
  - Al diseñar o modificar formularios, botones, modales y navegación.
  - Al asegurar soporte completo para lectores de pantalla mediante atributos `aria-*` adecuados y semántica HTML.
  - Al verificar contraste de colores, estados de focus visibles y navegación 100% operable por teclado.

### 6. `typescript-advanced-types`
* **Ruta:** `skills/typescript-advanced-types/SKILL.md`
* **Propósito:** Dominio del sistema de tipos de TypeScript (genéricos, conditional types, mapped types, utility types).
* **Cuándo activarla:**
  - Al crear tipos genéricos reutilizables para respuestas de API, hooks o componentes.
  - Al definir tipos estrictos para estados en Zustand o configuraciones de React Query.
  - Siempre que haya tentación de recurrir a `any` (para reemplazarlo por tipos estrictos y seguros).
  - Al resolver errores complejos de compilación en `tsc -b`.

### 7. `vitest`
* **Ruta:** `skills/vitest/SKILL.md`
* **Propósito:** Testing rápido basado en Vite (Jest-compatible, soporte nativo ESM y TypeScript).
* **Cuándo activarla:**
  - Al crear o mantener pruebas unitarias e integración en `src/test/`.
  - Al mockear llamadas HTTP de Axios o queries de TanStack Query con `vi.fn()` o `vi.spyOn()`.
  - Al configurar cobertura (`npm run test:coverage`) o hooks de prueba (`beforeEach`, `afterEach`).

### 8. `vite`
* **Ruta:** `skills/vite/SKILL.md`
* **Propósito:** Configuración y optimización de Vite 8, plugins de Rollup/Rolldown/Babel y tooling de compilación.
* **Cuándo activarla:**
  - Al modificar `vite.config.ts`, configurar plugins de Babel (como React Compiler) o alias de rutas.
  - Al resolver problemas de importaciones de assets, variables `import.meta.env` o errores de build de Vite.
  - Al optimizar el tiempo de inicio del dev server o la generación de bundles de producción.

### 9. `seo`
* **Ruta:** `skills/seo/SKILL.md`
* **Propósito:** Optimización técnica y semántica para motores de búsqueda y redes sociales.
* **Cuándo activarla:**
  - Al configurar meta etiquetas en `index.html` o dinámicamente por ruta (OpenGraph, Twitter Cards).
  - Al estructurar encabezados semánticos (`h1`-`h6`), enlaces crawlables y datos estructurados (JSON-LD).
  - Al preparar `robots.txt` o sitemaps para producción.

### 10. `nodejs-backend-patterns`
* **Ruta:** `skills/nodejs-backend-patterns/SKILL.md`
* **Propósito:** Patrones backend para entender la arquitectura del servidor con el que interactúa el cliente.
* **Cuándo activarla:**
  - Al diseñar el consumo de APIs RESTful, flujos de autenticación basados en refresh tokens / cookies `HttpOnly` o RBAC.
  - Al configurar clientes de WebSocket o Server-Sent Events (SSE).

### 11. `nodejs-best-practices`
* **Ruta:** `skills/nodejs-best-practices/SKILL.md`
* **Propósito:** Principios de desarrollo, arquitectura y patrones asíncronos en Node.js.
* **Cuándo activarla:**
  - Al crear o modificar scripts en `package.json` o utilidades en Node.
  - Al evaluar buenas prácticas en manejo de variables de entorno y validaciones previas al arranque.

---

## 🏛️ Contexto General del Proyecto

- **Proyecto:** Frontend template con React 19 + TypeScript + Vite 8.
- **UI:** MUI (Material UI 9) + Emotion.
- **Estado:** Zustand.
- **Datos remotos:** Axios + TanStack React Query.
- **Ruteo:** React Router con `Guard` (rutas protegidas) y `NoGuard` (rutas públicas).
- **Traducciones:** i18next + react-i18next en `src/translate`.

---

## 🏗️ Arquitectura Base (Resumen)

- **Auth centralizada:**
  - `src/store/authStore.tsx`
  - `src/hooks/useAuth.tsx`
- **API:**
  - `src/config/axiosInstance.ts`
  - `mainInstance` como base común
  - `createApiInstance(...)` para APIs derivadas
- **Query client:**
  - `src/config/reactQuery.ts`
- **Tema MUI:**
  - `src/providers/MUIProvider.tsx` crea el theme con `createTheme(...)`
  - Tokens en `src/theme/*`
  - Modo via `src/hooks/useThemeType.tsx` (`configStore`)
- **Rutas:**
  - `src/routes/index.tsx`
  - `src/routes/Guard.tsx`
  - `src/routes/NoGuard.tsx`
- **Errores globales:**
  - `src/modules/core/components/AppErrorBoundary/AppErrorBoundary.tsx`
  - `src/modules/core/pages/RouteError/RouteError.tsx`

---

## 📋 Reglas Operativas Obligatorias

1. **No duplicar auth:** La lógica de autenticación no debe replicarse fuera de `authStore` + `useAuth`.
2. **Instancias Axios:** No crear instancias Axios aisladas; usar `mainInstance` o `createApiInstance`.
3. **Internacionalización total:** Todo texto visible debe usar traducción `t("namespace:key")`.
4. **Traducciones completas:** Toda key nueva de traducción debe existir obligatoriamente tanto en `src/translate/es/*` como en `src/translate/en/*`.
5. **Guardas de navegación:** Respetar `Guard`/`NoGuard` al agregar o modificar rutas.
6. **Tipado estricto:** Mantener tipado estricto en TypeScript; evitar `any` innecesario.
7. **Tema centralizado:** No crear themes MUI en componentes de módulo; la composición del theme debe permanecer en `MUIProvider`.
8. **Tests de componentes:** Todo componente que contenga lógica debe tener un archivo de test correspondiente en `src/test`.
9. **Estructura espejo de tests:** `src/test` debe replicar la estructura de directorios de `src` (ej. el test de `src/modules/auth/pages/Login/Login.tsx` debe ubicarse en `src/test/modules/auth/pages/Login/Login.test.tsx`).
10. **Creación de tests espejo:** Si `src/test` o la ruta espejo no existen al crear o modificar un componente con lógica, se deben crear junto con su archivo `*.test.tsx`.

---

## 🧪 Pruebas (Testing)

- **Runner:** Vitest con entorno `jsdom`.
- **Librerías:** React Testing Library, `@testing-library/jest-dom` y `@testing-library/user-event`.
- **Ubicación obligatoria:** `src/test/**/*.test.{ts,tsx}`.
- **Imports explícitos:** Los tests deben importar las APIs de Vitest explícitamente (`describe`, `it`, `expect`, `vi`) para conservar el tipado y las reglas de lint.
- **Comandos:**
  ```bash
  npm run test          # Ejecución única
  npm run test:watch    # Modo watch interactivo
  npm run test:coverage # Reporte de cobertura
  ```

---

## ✅ Checklist Antes de Finalizar Cualquier Tarea

Antes de entregar cualquier cambio, ejecutar y asegurar que no haya errores:

```bash
npm run test        # 1. Pruebas unitarias de Vitest en verde
npm run typecheck   # 2. Verificación de tipos con TypeScript (tsc -b)
npm run lint        # 3. Reglas de ESLint cumplidas
```

Si se tocan variables de entorno:
1. Actualizar `.env.example`.
2. Verificar consistencia con `src/config/.envs.ts`.
