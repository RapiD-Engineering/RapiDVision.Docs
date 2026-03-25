# RapiD Vision Documentation

This is the MkDocs documentation site for RapiD Engineering products.

## Setup

1. Install dependencies:
   ```bash
   pip install mkdocs-material
   ```

2. Run development server:
   ```bash
   mkdocs serve
   ```
   The site will be available at http://127.0.0.1:8000

3. Build static site:
   ```bash
   mkdocs build
   ```
   The built site will be in the `site/` directory.

## Project Structure

```
docs/
├── mkdocs.yml                  # MkDocs configuration
├── docs/                       # Documentation source files
│   ├── assets/                 # Static assets (images, icons, etc.)
│   ├── index.md                # Home page
│   ├── rapid-vision/           # RapiD Vision documentation
│   ├── rapid-vision-explorer/  # RapiD Vision Explorer documentation
│   └── rapid-vision-api/       # RapiD Vision API documentation
└── site/                       # Built site (generated, not in git)
```

## Features

- **Material Theme**: Modern, responsive design
- **Light/Dark Mode**: Automatic theme switching based on system preference
- **Search**: Full-text search across all documentation
- **Code Highlighting**: Syntax highlighting for code blocks
- **Navigation**: Tabbed navigation with sections

## Documentation Sections

- **RapiD Vision**: Main vision processing application
- **RapiD Vision Explorer**: Data exploration and analysis tool
- **RapiD Vision API**: RESTful API
