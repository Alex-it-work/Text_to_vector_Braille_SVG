# Project Context for Claude

## Overview
Single-page web app (HTML + inline CSS/JS) that converts text to vector Braille in SVG format.
Target audience: designers working with accessibility and inclusive design.

## Architecture
- **Single file**: `braille_converter.html` — all logic, styles, and markup in one file
- No build tools, no dependencies, no frameworks — pure vanilla HTML/CSS/JS
- Opens directly in browser, no server needed

## Key Components
- `brailleMap` — dictionary mapping characters to 6-dot Braille patterns (arrays of 0/1)
- `specialPrefixes` — capital letter prefix (dots 4,5) and number prefix (dots 3,4,5,6)
- `convertToBraille()` — main conversion function, generates SVG markup
- `downloadSVG()` / `copyToClipboard()` — export functions
- Live event listeners on all inputs for real-time preview

## Supported Alphabets
- Ukrainian (primary): а-я + ґ, є, і, ї
- Russian: additional ё, ъ, ы, э
- English: a-z
- Numbers: 0-9 (with automatic number prefix)
- Punctuation: . , ! ? : ; - — № " ' ( )

## UI Language
Interface is in **Ukrainian**. Keep all UI text in Ukrainian.

## Development Notes
- When adding new features, keep everything in the single HTML file unless there's a strong reason to split
- SVG output uses classes: `.braille-dot`, `.braille-empty`, `.letter-label`, `.prefix-label`
- Dot positions follow the standard 6-dot Braille cell layout (1-4, 2-5, 3-6)
