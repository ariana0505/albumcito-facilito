# Albumcito Facilito — API

API backend de Albumcito Facilito. Expone los endpoints para gestionar álbumes, figuritas y el estado de colección del usuario (obtenidas, repetidas, faltantes).

Consumida por la app frontend ubicada en `apps/albumcito-facilito-app`. Ver el `CLAUDE.md` de la raíz del repo para la visión general del producto.

## Stack

- **Framework**: [NestJS](https://nestjs.com/) v12 (TypeScript)
- **Runtime**: Node.js >= 18
- **Gestor de paquetes**: pnpm (workspace del monorepo)
- **Linter**: [oxlint](https://oxc.rs/docs/guide/usage/linter.html) (type-aware), configurado en `.oxlintrc.json`
- **Formateo**: Prettier (`.prettierrc`)
- **Testing**: [Vitest](https://vitest.dev/) (unit + e2e), configurado en `vitest.config.ts` y `vitest.config.e2e.ts`

Este es un scaffold inicial (`nest new`) sin módulos de dominio todavía — solo el `AppModule` por defecto.

## Comandos

Ejecutar desde la raíz del monorepo con el filtro de pnpm, o directamente dentro de `services/albumcito-facilito-api`:

```bash
# desde la raíz
pnpm --filter "@albumcito-facilito/api" run start:dev
pnpm --filter "@albumcito-facilito/api" run build
pnpm --filter "@albumcito-facilito/api" run lint
pnpm --filter "@albumcito-facilito/api" run test
pnpm --filter "@albumcito-facilito/api" run test:e2e

# o vía turbo, para todo el monorepo
pnpm dev
pnpm build
pnpm lint
pnpm test
```

## Estructura

```
src/
  app.controller.ts    # controlador raíz
  app.service.ts        # servicio raíz
  app.module.ts          # módulo raíz
  main.ts                 # bootstrap de la aplicación
test/
  app.e2e-spec.ts        # test e2e de ejemplo
```

## Convenciones

- Seguir la estructura modular de Nest (`*.module.ts`, `*.controller.ts`, `*.service.ts`) por dominio a medida que se agreguen features (álbumes, figuritas, colección, usuarios).
- Usar DTOs con `class-validator`/`class-transformer` para validar entradas cuando se agreguen endpoints (aún no instalados; agregar al introducir el primer endpoint real).
- Mantener el linter (`oxlint --type-aware`) y los tests en verde antes de cada commit.
- No se ha configurado aún base de datos ni ORM — pendiente de definir según los requerimientos del dominio (álbumes, figuritas, colección).

Este archivo se irá completando con decisiones de arquitectura, módulos de dominio y convenciones adicionales a medida que el proyecto avance.
