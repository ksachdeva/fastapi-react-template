# FastAPI + React Template

A full-stack starter with a FastAPI backend and a React, TypeScript, and Vite frontend. It includes a configured Dev Container and shared development tooling so you can start building without first wiring the workspace together.

## Included

- **Backend:** Python 3.14, FastAPI, Pydantic Settings, and Dishka dependency injection. CORS is configured for local frontend development, and the interactive API docs are available outside production.
- **Frontend:** React 19, TypeScript, and Vite, with hot module replacement, ESLint, and the `@` alias for `frontend/src`.
- **Dev Container:** Python, Node.js 24, pnpm, uv, and Docker access are provisioned. On creation, the container syncs Python dependencies, configures Zsh history and completions for uv/uvx, Poe, and Docker, installs pre-commit hooks, and sets up OpenCode and APM. Zsh history and OpenCode data use persistent volumes.
- **Workspace tooling:** Poe tasks provide common backend/frontend run and build commands. Ruff, mypy, pytest, and pre-commit are configured for Python; ESLint and TypeScript are configured for the frontend.

## Getting Started

Open the repository in its Dev Container. Python dependencies are synced during container setup. Install the frontend dependencies once:

```sh
pnpm install --frozen-lockfile
```

Start the backend and frontend in separate terminals:

```sh
poe dev-run-backend
poe dev-run-frontend
```

The frontend is served at `http://localhost:5173`; the backend runs at `http://localhost:8000`. In the Dev Container, `poe` is a shell wrapper for `uv run poe`, so Poe tasks run in the uv-managed environment. Zsh completions are configured for the wrapper.

## Useful Commands

| Command | Description |
| --- | --- |
| `poe dev-run-backend` | Run the FastAPI development server |
| `poe dev-run-frontend` | Run the Vite development server |
| `poe frontend-build` | Type-check and build the frontend for production |
| `poe fmt` | Format Python code with Ruff |
| `uv run pre-commit run --all-files` | Run all pre-commit checks |
| `pnpm --filter frontend run lint` | Lint the frontend |

## Starter Endpoints

- `GET /health` returns a basic health status.
- `GET /api/v1/dummy` is an example API route; replace it with application functionality.
- `GET /docs` serves the interactive OpenAPI docs in development and staging.

The frontend is the Vite starter screen. Replace it along with the example endpoint as you build your application. Backend settings are loaded from the root `.env` file when present and use the `BACKEND_` environment prefix; defaults are set for local development.
