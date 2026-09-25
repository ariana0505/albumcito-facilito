@AGENTS.md

# Albumcito Facilito — App

Aplicación frontend de Albumcito Facilito. Permite al usuario ver sus álbumes de figuritas, marcar cuáles tiene, cuáles le faltan y cuáles tiene repetidas, y hacer seguimiento de su progreso de colección.

Consume la API backend ubicada en `services/albumcito-facilito-api`. Ver el `CLAUDE.md` de la raíz del repo para la visión general del producto.

Cuando necesites install/develop software usa context7 mcp.

## Stack

- **Framework**: [Next.js](https://nextjs.org/) 16 (App Router, Turbopack)
- **Lenguaje**: TypeScript
- **Estilos**: [Tailwind CSS](https://tailwindcss.com/) v4 (vía `@tailwindcss/postcss`)
- **React**: 19
- **Runtime**: Node.js >= 18
- **Gestor de paquetes**: pnpm (workspace del monorepo)
- **Linter**: ESLint 9 (`eslint-config-next`), configurado en `eslint.config.mjs`
- **Testing**: [Vitest](https://vitest.dev/) + [React Testing Library](https://testing-library.com/react) + jsdom, configurado en `vitest.config.mts`

Este es un scaffold inicial (`create-next-app`) sin features de dominio todavía — solo la página de bienvenida por defecto.

> **Importante — Next.js 16**: esta versión tiene cambios de ruptura respecto a versiones anteriores de Next.js. Antes de escribir código, revisar la guía relevante en `node_modules/next/dist/docs/` y prestar atención a los avisos de deprecación (ver `AGENTS.md`).

## Comandos

Ejecutar desde la raíz del monorepo con el filtro de pnpm, o directamente dentro de `apps/albumcito-facilito-app`:

```bash
# desde la raíz
pnpm --filter "@albumcito-facilito/app" run dev
pnpm --filter "@albumcito-facilito/app" run build
pnpm --filter "@albumcito-facilito/app" run lint
pnpm --filter "@albumcito-facilito/app" run test
pnpm --filter "@albumcito-facilito/app" run test:watch

# o vía turbo, para todo el monorepo
pnpm dev
pnpm build
pnpm lint
pnpm test
```

## Estructura

```
app/
  layout.tsx     # layout raíz
  page.tsx        # página de inicio
  globals.css      # estilos globales / Tailwind
__tests__/
  page.test.tsx   # test de ejemplo con Vitest + Testing Library
public/            # assets estáticos
```

## Convenciones

- App Router: organizar rutas y componentes de dominio (álbumes, figuritas, colección) dentro de `app/`, colocando componentes junto a la ruta que los usa cuando sea posible.
- Usar Tailwind utility classes; evitar CSS custom salvo excepciones en `globals.css`.
- Tests con Vitest + Testing Library, colocados en `__tests__/` o junto al componente (`*.test.tsx`).
- No se ha configurado aún cliente HTTP ni manejo de estado global — pendiente de definir al integrar con `services/albumcito-facilito-api`.
- Mantener el linter (`eslint`) y los tests en verde antes de cada commit.

Este archivo se irá completando con decisiones de arquitectura, componentes de dominio y convenciones adicionales a medida que el proyecto avance.
