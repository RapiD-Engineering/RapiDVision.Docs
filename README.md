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

## Contributing Documentation

Use this workflow when adding or updating docs content.

### 1. Choose the right section

- RapiD Vision pages: `docs/rapid-vision/*.md`
- RapiD Vision Explorer pages: `docs/rapid-vision-explorer/*.md`
- RapiD Vision API pages: `docs/rapid-vision-api/*.md`

### 2. Add or edit text

- Open the target `.md` file and write in standard Markdown.
- Use clear headings and short sections.
- Keep terminology consistent with existing docs.

Example:

```markdown
## Camera Exposure

Use exposure values between `1000` and `8000` for most indoor production lines.

### Recommended Starting Point

- Start at `3000`
- Increase only if images are too dark
```

### 3. Add images

- Store source images in `docs/assets/images/`.
- Recommended: create a subfolder per product area, for example:
   - `docs/assets/images/rapid-vision/`
   - `docs/assets/images/rapid-vision-explorer/`
   - `docs/assets/images/rapid-vision-api/`
- Use lowercase filenames with hyphens, for example: `camera-exposure-panel.png`.

From files inside `docs/rapid-vision/`, `docs/rapid-vision-explorer/`, or `docs/rapid-vision-api/`, reference images like this:

```markdown
![Camera settings panel](../assets/images/rapid-vision/camera-exposure-panel.png)
```

### 4. Add a new page to navigation (if creating a new file)

- Create the new file under the correct section folder.
- Add it to `mkdocs.yml` under the matching `nav` group:
   - `RapiD Vision`
   - `RapiD Vision Explorer`
   - `RapiD Vision API`

Example `mkdocs.yml` entry:

```yaml
   - RapiD Vision:
      - Overview: rapid-vision/index.md
      - New Topic: rapid-vision/new-topic.md
```

### 5. Preview before committing

```bash
mkdocs serve
```

Check that:

- The page appears in left navigation
- Headings and spacing render correctly
- Images load and are sized appropriately
- Links work

### 6. Important

- Edit files in `docs/` and `mkdocs.yml` only.
- Do not edit generated files in `site/` directly.
