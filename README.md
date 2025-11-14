# SDLC1 CRUD API

NestJS CRUD API with automated AI standards enforcement via pre-commit hooks and CI/CD.

## Quick Start

```bash
npm install          # Auto-configures husky hooks
npm start            # Runs on http://localhost:3000
```

## Step-by-Step Setup

1. **Install dependencies**
   ```bash
   npm install
   ```
   - Installs all packages
   - Auto-configures Husky git hooks
   - Builds the project

2. **Start development server**
   ```bash
   npm run start:dev
   ```
   - Runs on `http://localhost:3000`
   - Auto-reloads on file changes

3. **Run tests**
   ```bash
   npm test
   ```

## Validation Options

### Manual Validation (Before Commit/Push)

**Validate everything:**
```bash
npm run validate
```
Runs linting + tests with coverage

**Individual checks:**
```bash
npm run lint:check      # Check linting
npm run format:check    # Check formatting
npm run test:cov        # Run tests with coverage
npm run build           # Verify build
```

### Automatic Validation (Git Hooks)

**Pre-commit hook** (runs automatically on `git commit`):
- Lints staged files
- Formats staged files
- Runs related tests
- Blocks commit if validation fails

**Pre-push hook** (runs automatically on `git push`):
- Runs full test suite with coverage
- Checks coverage threshold (80% minimum)
- Builds project
- Blocks push if validation fails

**Skip hooks (if needed):**
```bash
git commit --no-verify   # Skip pre-commit hook
git push --no-verify     # Skip pre-push hook
```

## API Endpoints

- `POST /items` - Create item
- `GET /items` - List all items
- `GET /items/:id` - Get item by ID
- `PATCH /items/:id` - Update item
- `DELETE /items/:id` - Delete item

## AI Standards Enforcement

- **Cursor IDE**: `.cursor/rules/*.mdc` files
- **Claude Code**: `claude.md`
- **GitHub Copilot**: `.github/copilot-instructions.md`
- **CI/CD**: GitHub Actions validates on push/PR
