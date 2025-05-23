# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Common Commands

### Development
- `npm run quartz build` - Build the site
- `npm run quartz build --serve` - Build and serve the site locally with hot reload
- `npm run docs` - Build and serve the documentation site
- `npm run check` - Run TypeScript type checking and Prettier format checking
- `npm run format` - Auto-format code with Prettier
- `npm run test` - Run tests using tsx

### Quartz CLI
- `npx quartz create` - Create a new Quartz site
- `npx quartz build` - Build the site
- `npx quartz build --serve` - Build and serve with hot reload
- `npx quartz sync` - Sync content and push to GitHub
- `npx quartz update` - Update Quartz to latest version

## Architecture Overview

### Core Build Pipeline
Quartz uses a three-stage build pipeline (`quartz/build.ts`):
1. **Parse** - Markdown files are parsed into AST using unified/remark
2. **Filter** - Content is filtered based on drafts, private pages, etc.
3. **Emit** - Processed content is emitted as HTML files

### Plugin System
Quartz has three types of plugins:
- **Transformers** (`quartz/plugins/transformers/`) - Modify markdown AST during parsing
- **Filters** (`quartz/plugins/filters/`) - Filter which content gets published
- **Emitters** (`quartz/plugins/emitters/`) - Generate output files (HTML, RSS, etc.)

### Component Architecture
- Components are Preact-based and located in `quartz/components/`
- Layout is defined in `quartz.layout.ts` with separate layouts for content and list pages
- Components can be client-side interactive (scripts in `quartz/components/scripts/`)

### Content Structure
- Content lives in `content/` directory
- Supports Obsidian-flavored markdown with wikilinks
- Configuration in `quartz.config.ts` controls site behavior and theme

### Key Files
- `quartz.config.ts` - Main configuration file
- `quartz.layout.ts` - Page layout definitions
- `quartz/build.ts` - Core build logic
- `quartz/cli/handlers.js` - CLI command implementations
- `quartz/util/path.ts` - Path and slug handling utilities