# Frontend para el API de Música

## Descripción

En este taller generarás el frontend para el API de Música desarrollada en el lpa2-taller3 usando la herramienta [v0.app](https://v0.app/) y un *prompt* especializado.

## Prerrequisitos

- API del lpa2-taller3 funcionando localmente
- Node.js 18+ instalado
- Cuenta en [v0.app](https://v0.app)

## Preparar la información de tu API

Antes de usar el *prompt*, recopila esta información de tu API de Música, para cada *endpoint*:

```json
{
  "endpoint": "http://localhost:3000/api/tu-endpoint",
  "método": "GET/POST/PUT/DELETE",
  "body_request": {"clave": "valor"},
  "body_response": {"data": [], "message": "string"},
  "errores": {"400": "Bad Request", "500": "Server Error"}
}
```

## Usar el *Prompt* en v0.app

1. Accede a [v0.app](https://v0.app)
2. Copia y adapta el siguiente *prompt*:

    ---
    
    Eres un ingeniero de frontend senior especializado en React, TypeScript y Tailwind CSS. Tu tarea es diseñar interfaces web responsivas y eficientes que consuman APIs existentes.

    Crea un frontend web que interactúe con la siguiente API:  

    > pega el JSON con los detalles de tu API 

    Requisitos funcionales:  

    1. **Interfaz de usuario**:  

        - [ESPECIFICA: Diseño esperado (ej: formulario de login, dashboard de datos, tabla editable)]  
        - [ESPECIFICA: Estados de carga/éxito/error]  
        - [ESPECIFICA: Comportamientos interactivos (ej: validación en tiempo real, paginación)]

    2. **Lógica de integración**:  

        - Implementa manejo de errores robusto  
        - Optimiza el rendimiento (ej: caching, lazy loading)  
        - [ESPECIFICA: Validaciones de datos necesarias]

    ---

## Generar y Descargar el Código

1. Ejecuta el *prompt* en [v0.app](https://v0.app)
2. Revisa el *preview* y realiza los ajustes necesarios
3. Descarga el `ZIP` con la aplicación
4. Ve al proyecto: `cd proyectos/lpa2-taller4`
5. Descomprime el `ZIP` en este directorio
6. Configurar Node v20: `curl -sL https://deb.nodesource.com/setup_20.x | sudo -E bash -`
7. Instalar Node/NPM: `sudo apt install nodejs -y`
8. Instalar PNPM: `sudo npm install -g pnpm`
9. Instalar las dependencias del proyecto: `pnpm install`
10. Ejecutar en modo desarrollo: `pnpm dev`
11. Abrir la aplicación en: [localhost:3000](http://localhost:3000/)
12. Revisa y ajusta la configuración del API
13. Para ejecutar en modo producción: `pnpm build` y luego: `pnpm start`


---

## Implementación

El frontend se generó con **Claude Code** (el profesor permitió usar cualquier herramienta de IA). En [`PROMPT.md`](PROMPT.md) está el JSON con los *endpoints* de la API y el *prompt* completo, por si se quiere reproducir en v0.app.

**Tecnologías:** Next.js 16 (App Router), React 19, TypeScript, Tailwind CSS 4 y TanStack Query.

**Funcionalidades:**

- **Panel:** totales de usuarios, canciones y favoritos, y estado de la API (`/health`).
- **Canciones:** listado paginado, búsqueda por título, artista y género, y crear, editar y eliminar.
- **Usuarios:** listado paginado, crear, editar y eliminar, y página de detalle con sus favoritos.
- **Favoritos:** listado general, registrar y eliminar.
- **Usuario activo:** se elige en la barra superior y permite marcar favoritos con ♡ desde el catálogo.
- **Validación en tiempo real:** usa las mismas reglas que el backend y muestra los errores de la API (422 y 400) junto a cada campo.
- **Estados de la interfaz:** carga, vacío y error con reintento, y notificaciones de éxito.

### Ejecutar en Windows

1. Tener la API del lpa2-taller3 corriendo en `http://127.0.0.1:8000`:
   ```bash
   uvicorn main:app --reload
   ```
2. Instalar Node 20 o superior (desde [nodejs.org](https://nodejs.org) o con `winget install OpenJS.NodeJS.LTS`) y PNPM:
   ```bash
   npm install -g pnpm
   ```
3. En este directorio, instalar las dependencias:
   ```bash
   pnpm install
   ```
4. Si la API está en otra URL, copiar `.env.example` como `.env.local` y ajustar `NEXT_PUBLIC_API_URL`.
5. Modo desarrollo: `pnpm dev`, y abrir [localhost:3000](http://localhost:3000/).
6. Modo producción: `pnpm build` y luego `pnpm start`.
7. *Linter*: `pnpm lint`.
