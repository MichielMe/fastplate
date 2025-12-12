# 🚀 Fastplate

[![PyPI version](https://badge.fury.io/py/fastplate.svg)](https://badge.fury.io/py/fastplate)
[![Python 3.12+](https://img.shields.io/badge/python-3.12+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**Fastplate** is a CLI tool that scaffolds production-ready FastAPI projects with Tailwind CSS, DaisyUI, and Jinja2 templates in seconds.

## ✨ Features

- 🏗️ **FastAPI** backend with async support and automatic OpenAPI docs
- 🎨 **Tailwind CSS v4** + **DaisyUI** for beautiful, responsive UIs
- 📄 **Jinja2** server-side templating with component-based structure
- 📦 **uv** for fast Python dependency management
- 🐳 **Docker** & **docker-compose** ready for deployment
- ⚡ **Hot reload** for both backend and CSS during development
- 🔧 **Makefile** with common development commands

## 📦 Installation

### With uv (recommended)

```bash
uv tool install fastplate
```

### With pip

```bash
pip install fastplate
```

### With pipx

```bash
pipx install fastplate
```

## 🚀 Quick Start

```bash
# Create a new project in the current directory
mkdir my-app && cd my-app
fastplate init --name "My App"

# Or create in a new directory
fastplate init ./my-app --name "My App"

# Start development
make dev          # FastAPI server at http://localhost:8000
make npm-watch    # Tailwind CSS watcher (in another terminal)
```

## 📖 Usage

```bash
fastplate init [OPTIONS] [PATH]
```

### Arguments

| Argument | Description | Default |
|----------|-------------|---------|
| `PATH` | Directory to create the project in | `.` (current directory) |

### Options

| Option | Description |
|--------|-------------|
| `-n, --name TEXT` | Project name (defaults to directory name) |
| `--skip-install` | Skip dependency installation |
| `-f, --force` | Overwrite existing project files |
| `--help` | Show help message |

### Examples

```bash
# Interactive mode (prompts for project name)
fastplate init

# Specify project name
fastplate init --name "My Awesome App"

# Create in a specific directory
fastplate init ./projects/my-app --name my-app

# Skip dependency installation
fastplate init --skip-install

# Overwrite existing project
fastplate init --force
```

## 📁 Generated Project Structure

```
my-app/
├── app/
│   ├── __init__.py
│   ├── main.py              # FastAPI application
│   ├── api/                  # API routes
│   ├── core/
│   │   ├── config.py        # Settings & configuration
│   │   └── middleware.py
│   ├── models/              # Database models
│   ├── schemas/             # Pydantic schemas
│   ├── services/            # Business logic
│   └── views/               # HTML view routes
│       └── index.py
├── frontend/
│   ├── static/
│   │   └── css/
│   │       ├── input.css    # Tailwind source
│   │       └── output.css   # Compiled CSS
│   └── templates/
│       ├── base.html        # Base template
│       ├── components/      # Reusable components
│       │   ├── card.html
│       │   └── navbar.html
│       └── pages/           # Page templates
│           └── index.html
├── Dockerfile
├── docker-compose.yml
├── Makefile
├── pyproject.toml
└── README.md
```

## 🛠️ Development Commands

The generated project includes a `Makefile` with these commands:

```bash
make dev          # Start FastAPI dev server with hot reload
make run          # Start production server
make npm-watch    # Watch & compile Tailwind CSS
make npm-build    # Build minified CSS for production
make docker-up    # Start with Docker Compose
make docker-down  # Stop Docker containers
make clean        # Remove generated files
```

## 🎨 Styling with Tailwind & DaisyUI

The template uses [Tailwind CSS v4](https://tailwindcss.com/) with [DaisyUI](https://daisyui.com/) components.

Edit `frontend/static/css/input.css` to customize your styles:

```css
@import "tailwindcss";
@plugin "daisyui";

/* Your custom styles here */
```

Run `make npm-watch` during development to auto-compile CSS changes.

## 🐳 Docker Deployment

```bash
# Build and run with Docker Compose
make docker-up

# Or manually
docker build -t my-app .
docker run -p 8000:8000 my-app
```

## 📋 Requirements

- **Python 3.12+**
- **Node.js 18+** (for Tailwind CSS)
- **uv** (recommended) or pip

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

MIT License - see [LICENSE](LICENSE) for details.
