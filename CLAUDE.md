# Claude Code specific instructions

@Agents.md

## Repository Setup

For first-time setup, use the Claude command:

```sh
/setup_repo
```

This bootstraps the monorepo with dependencies, builds, tests, and dev server verification.

**Prerequisites:** Node.js >= 24, Git repository, available ports for dev server, storybook, etc.

## Development Workflow

1. **First-time setup**: Run `/setup_repo` Claude command
2. Make code changes
3. Run tests (see subdirectory CLAUDE.md files)
4. Run typecheck, lint, format
5. Check README updates
6. Consider docs.comfy.org updates

## Git Conventions

- Use `prefix:` format: `feat:`, `fix:`, `test:`
- Add "Fixes #n" to PR descriptions
- Never mention Claude/AI in commits

## Flutter Port (apps/flutter/)

A Flutter implementation of the ComfyUI frontend, designed to work with the ComfyUI backend.

### Key Files

- `core/nodes/` - Node definitions, registry, and slot types
- `core/graph/` - Graph container, validation, and topological sort
- `core/serialization/` - Workflow and API format serialization
- `test/` - Unit tests for all core functionality

### Testing Flutter

Tests are run from the xyflow example directory:
```bash
cd /path/to/xyflow/packages/xyflow_flutter/example
flutter test test/comfyui/
```

### Implementation Status

- **Core Data Models**: Complete (SlotType, NodeDefinition, NodeRegistry)
- **Graph Core**: Complete (ComfyGraph, validation, topological sort)
- **Serialization**: Complete (workflow JSON, API format)
- **UI Components**: In progress
- **Backend Integration**: Pending

See `apps/flutter/IMPLEMENTATION_PLAN.md` for detailed roadmap.
