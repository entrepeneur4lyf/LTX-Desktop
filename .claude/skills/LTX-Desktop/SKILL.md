```markdown
# LTX-Desktop Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you the core development patterns, coding conventions, and common workflows for contributing to the **LTX-Desktop** project. The repository is a cross-platform desktop application with a Python backend and a Vite-powered frontend. It uses modern TypeScript/React for UI, and follows clear conventions for file organization, code style, and workflow automation. This guide will help you quickly get up to speed with the project's structure and best practices.

## Coding Conventions

### File Naming

- **Python files:** Use `snake_case`, e.g., `api_types.py`, `app_state_types.py`
- **TypeScript/JSX files:** Use `PascalCase` for React components, e.g., `MainView.tsx`, but `snake_case` for utility files if present.

### Import Style

- **Python:** Use relative imports within the backend.
  ```python
  from .services.my_service import do_something
  ```
- **TypeScript:** Use relative imports for local modules.
  ```typescript
  import { MyComponent } from '../components/MyComponent';
  ```

### Export Style

- **Python:** Use named exports (functions/classes).
  ```python
  def my_function():
      pass
  ```
- **TypeScript:** Use named exports.
  ```typescript
  export function useCustomHook() { ... }
  export type User = { ... };
  ```

### Commit Patterns

- Freeform commit messages, often with a short prefix (e.g., `fix:`, `feat:`), but not strictly enforced.
- Average commit message length: ~47 characters.

## Workflows

### Update NPM Dependencies

**Trigger:** When you need to upgrade or update JavaScript/TypeScript dependencies.

**Command:** `/upgrade-npm`

1. Edit `package.json` to update dependency versions.
2. Regenerate `pnpm-lock.yaml` to reflect new versions.
3. Update `pnpm-workspace.yaml` if the workspace structure changes.

**Example:**
```bash
pnpm install some-package@latest
pnpm install
```

### Add or Update Linux Support

**Trigger:** When adding or enhancing Linux compatibility (icons, installer scripts, docs).

**Command:** `/add-linux-support`

1. Edit `electron-builder.yml` to add Linux targets or update config.
2. Add/update Linux icons in `resources/icons/*.png`.
3. Update installer/build scripts: `scripts/create-installer.sh`, `scripts/Dockerfile.linux-build`.
4. Update documentation: `README.md`, `docs/INSTALLER.md`.
5. Modify `electron/python-setup.ts` if Python setup changes are needed.

**Example:**
```yaml
# electron-builder.yml
linux:
  target:
    - AppImage
    - deb
```

### Feature or Breaking Backend Change

**Trigger:** When implementing a backend feature, refactor, or breaking change.

**Command:** `/feature-backend`

1. Edit/add backend handlers: `backend/handlers/*.py`.
2. Edit/add backend services: `backend/services/**/*.py`.
3. Update types: `backend/api_types.py`, `backend/state/app_state_types.py`.
4. Update/add tests: `backend/tests/*.py`, `backend/tests/fakes/services.py`.
5. Update frontend components/hooks if needed for integration.

**Example:**
```python
# backend/handlers/new_feature.py
def handle_new_feature(request):
    ...
```

### Frontend Feature or UI Enhancement

**Trigger:** When adding or enhancing a frontend/UI feature.

**Command:** `/feature-frontend`

1. Edit/add UI components: `frontend/components/*.tsx`.
2. Edit views: `frontend/views/*.tsx`.
3. Edit contexts/hooks: `frontend/contexts/*.tsx`, `frontend/hooks/*.ts`.
4. Update types: `frontend/types/*.ts`.
5. Update styles: `frontend/index.css` if needed.

**Example:**
```tsx
// frontend/components/NewButton.tsx
export function NewButton() {
  return <button>Click me</button>;
}
```

### Documentation Update

**Trigger:** When updating documentation (README, install/contribution guides, telemetry).

**Command:** `/update-docs`

1. Edit `README.md` for general docs.
2. Edit `docs/INSTALLER.md` or `docs/CONTRIBUTING.md` for install/contribution instructions.
3. Edit `docs/TELEMETRY.md` for telemetry/privacy info.

**Example:**
```markdown
## How to Install
Follow the steps in `docs/INSTALLER.md`.
```

### Sync Upstream with Origin

**Trigger:** When synchronizing upstream/main with origin/main.

**Command:** `/sync-upstream`

1. Merge changes from `origin/main` into `upstream/main`.
2. Update backend handlers, state, tests, and `package.json` as needed.

**Example:**
```bash
git checkout upstream/main
git merge origin/main
```

## Testing Patterns

- **Test Framework:** Unknown (likely Jest or Vitest for frontend, pytest for backend).
- **Frontend Test Files:** Use the pattern `*.test.ts`.
- **Backend Test Files:** Located in `backend/tests/*.py`.

**Example (frontend):**
```typescript
// frontend/components/__tests__/MyComponent.test.ts
import { render } from '@testing-library/react';
import { MyComponent } from '../MyComponent';

test('renders correctly', () => {
  render(<MyComponent />);
});
```

**Example (backend):**
```python
# backend/tests/test_my_service.py
def test_my_service_behavior():
    assert my_service.do_something() == expected
```

## Commands

| Command             | Purpose                                                      |
|---------------------|--------------------------------------------------------------|
| /upgrade-npm        | Update npm dependencies and lockfiles                        |
| /add-linux-support  | Add or update Linux build support and documentation          |
| /feature-backend    | Implement or update backend features and tests               |
| /feature-frontend   | Add or enhance frontend features or UI                       |
| /update-docs        | Update documentation files                                   |
| /sync-upstream      | Synchronize upstream/main with origin/main                   |
```