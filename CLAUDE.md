# Albumcito Facilito

Aplicación para coleccionar álbumes de figuritas (stickers), permitiendo llevar el control de qué figuritas se tienen, cuáles faltan y cuáles están repetidas dentro de cada álbum.

## Estructura del monorepo

El proyecto está dividido en dos partes principales:

- **API backend** — `services/albumcito-facilito-api`
  Expone los endpoints para gestionar álbumes, figuritas y el estado de colección del usuario. Construida con NestJS v12 + TypeScript, linteada con oxlint y testeada con Vitest. Ver `services/albumcito-facilito-api/CLAUDE.md`.

- **Aplicación frontend** — `apps/albumcito-facilito-app`
  Interfaz donde el usuario visualiza sus álbumes, marca figuritas como obtenidas/repetidas y consulta su progreso. Construida con Next.js 16 (App Router) + TypeScript + Tailwind CSS v4, linteada con ESLint y testeada con Vitest + React Testing Library. Ver `apps/albumcito-facilito-app/CLAUDE.md`.

Cada parte mantiene su propio `CLAUDE.md` con detalles específicos de stack, convenciones y comandos.
