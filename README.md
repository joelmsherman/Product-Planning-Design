# Product Planning & Design Template

A GitHub template for quickly designing screen mocks and front-end components using [Design OS](https://buildermethods.com/design-os), the structured product planning and design tool created by [Brian Casel](https://buildermethods.com) at Builder Methods.

## Introduction

Design OS guides you through a structured conversation where you define your vision, design your UI, and generate production-ready React components — all before implementation begins.

The result is a complete handoff package: screen designs, data shapes, design tokens, and implementation instructions that any coding agent can follow to build exactly what you envisioned.

This template gives you a ready-to-go starting point. Clone it, run a few commands, and start designing.

## Requirements

### Node.js v18+

Design OS runs as a local development tool on Node.js.

**Check your installed version:**

```bash
node -v
```

If you see `v18.x.x` or higher, you're good. If not, install or update Node.js:

- **macOS/Linux (via nvm):**
  ```bash
  curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash
  nvm install 18
  nvm use 18
  ```

- **Windows:** Download the installer from [nodejs.org](https://nodejs.org/)

npm is included with Node.js — no separate install needed.

### React & Tailwind CSS (for exported components)

The components Design OS generates are production-ready React elements styled with Tailwind CSS utility classes. Your implementation project will need:

- **React** v18 or higher
- **Tailwind CSS** v4

Your backend can be anything — Rails, Laravel, Next.js API routes, Python, Go, or whatever you prefer. Design OS only handles the frontend design layer.

## Workflow

Design OS follows a three-phase process. Each phase uses slash commands inside Claude Code that run as interactive conversations — the AI asks questions, you provide direction, and together you shape the product.

### Phase 1: Product Planning

Establish the foundation before any design work begins.

| Command | Purpose |
|---------|---------|
| `/product-vision` | Define your product concept, break it into sections, and structure the data model |
| `/design-tokens` | Select your color palette and typography system |
| `/design-shell` | Build your application's navigation and layout structure |

### Phase 2: Section Design

Work through each product section iteratively. Repeat this cycle for every section in your roadmap:

| Command | Purpose |
|---------|---------|
| `/shape-section` | Define the scope and requirements for a section |
| `/sample-data` | Generate realistic sample data and TypeScript type definitions |
| `/design-screen` | Build the React screen components |
| `/screenshot-design` | Capture screenshots of your designs (optional) |

Supporting commands available at any time:
- `/product-roadmap` — Update the product roadmap
- `/data-shape` — Modify the data structure

### Phase 3: Export

When you're ready — even if not every section is complete — generate a handoff package:

| Command | Purpose |
|---------|---------|
| `/export-product` | Generate the complete handoff package with implementation instructions, design assets, and test specs |

The export produces a `product-plan/` directory containing pre-written prompts, implementation instructions, CSS tokens, TypeScript interfaces, sample data, shell templates, and per-section component deliverables with behavioral test specs.

## Implementation (Incremental Approach)

The export generates two implementation paths. The **incremental approach** is recommended — it breaks the build into milestones so you can validate as you go rather than debugging a monolithic output.

### How it works

1. **Start with the foundation milestone.** The export includes a `section-prompt.md` template and milestone-by-milestone instructions. The first milestone sets up your project scaffold, installs dependencies, and configures your design tokens (colors, typography, Tailwind config).

2. **Build the shell.** The second milestone implements your application shell — navigation, layout structure, and routing scaffolding — using the shell component templates from the export.

3. **Implement one section at a time.** Each subsequent milestone corresponds to a product section. For each one, the export provides:
   - React components (props-based, fully styled with Tailwind, dark mode support)
   - TypeScript type definitions
   - Sample data for development
   - Behavioral test specifications
   - Screenshots for visual reference

4. **Wire up and integrate.** The exported components are presentation-ready but intentionally decoupled from your backend. Your responsibilities after each milestone:
   - Connect callbacks to your routing
   - Replace sample data with backend API calls
   - Add error handling and loading states
   - Write tests aligned with the provided specs

### Using the prompts

Each milestone comes with a pre-written prompt you can feed directly to your coding agent (Claude Code, Cursor, Copilot, etc.). Open the milestone instructions, copy the prompt, and let your agent build that slice. Review, adjust, then move to the next milestone.

## Getting Started

```bash
# Clone from this template
git clone https://github.com/joelmsherman/Product-Planning-Design.git my-product-design
cd my-product-design

# Remove the template remote
git remote remove origin

# Install dependencies
npm install

# Start the dev server
npm run dev

# Open Claude Code and begin
claude
```

Then run `/product-vision` to start defining your product.

## Support & Community

For support, training, and community access, consider joining [Builder Methods Pro](https://buildermethods.com/pro) — connect directly with Brian Casel and other builders using Design OS.

- [Builder Briefing newsletter](https://buildermethods.com)
- [YouTube](https://youtube.com/@briancasel)
- [Changelog](CHANGELOG.md)