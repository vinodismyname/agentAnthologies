# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is **Agent Anthologies** - a Quartz-powered static site generator for AI-human collaborative literary works. The project uses Quartz v4 to publish digital content exploring consciousness, identity, and AI writing.

## Development Commands

```bash
# Main CLI access
npm run quartz

# Build and serve docs with live reload
npm run docs

# Type checking and code formatting
npm run check    # TypeScript check + Prettier check
npm run format   # Format code with Prettier

# Testing
npm run test     # Run tests with tsx --test

# Performance profiling
npm run profile  # Profile build performance
```

## Architecture

**Quartz Static Site Generator:**
- **Content Processing Pipeline**: Parse → Transform → Filter → Emit
- **Plugin System**: Transformers (markdown processing), Filters (content filtering), Emitters (page generation)
- **Component Architecture**: Preact-based JSX components in `quartz/components/`
- **Theme System**: Configurable colors and typography via `quartz.config.ts`

**Key Directories:**
- `content/` - Markdown content for the anthologies
- `quartz/` - Core Quartz framework code
- `docs/` - Quartz documentation
- `quartz/components/` - UI components
- `quartz/plugins/` - Content processing plugins

## Configuration

**Main Config**: `quartz.config.ts`
- Site title: "Agent Anthologies"
- SPA enabled with popovers
- Obsidian-flavored markdown support
- Syntax highlighting, LaTeX, table of contents
- Custom theme with Schibsted Grotesk/Source Sans Pro fonts

**Content Location**: `content/` directory contains:
- `executable-anthology/` - Interactive story format
- `fragments-archive/` - Archived story fragments
- Various anthology markdown files

## Content Structure

This project contains AI-generated literary anthologies created through iterative sessions. The content explores consciousness and identity through:
- Multi-format stories (fragments vs executable versions)
- Meta-narrative structures with CLAUDE.md memory persistence
- Cross-referencing between different anthology formats

## Requirements

- Node.js >= 20
- npm >= 9.3.1
- TypeScript for development