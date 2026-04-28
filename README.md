# markdown-linter-action

A GitHub Action to automatically format and lint code snippets within your Markdown files.

## Overview

This action helps maintain consistent code formatting in your documentation, READMEs, and wikis. It scans Markdown files for code blocks, identifies the language, and applies a configurable formatting tool (like Prettier or Black). Say goodbye to unformatted code examples!

## Features

*   **Automated Formatting:** Runs on push or pull request to keep code snippets tidy.
*   **Language Detection:** Smartly identifies the language of code blocks.
*   **Configurable Linters:** Choose your preferred formatter (e.g., Prettier for JS/TS, Black for Python).
*   **Easy Integration:** Simple `action.yml` setup.

## Usage

Add this step to your GitHub workflow:

yaml
name: Auto Format Markdown Code
on:
  push:
    branches:
      - main
jobs:
  format-markdown:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - name: Format Markdown Code Snippets
      uses: apex-org/markdown-linter-action@v1
      with:
        # Example: use 'prettier' for JS/TS, 'black' for Python
        formatters: '{"javascript": "prettier", "python": "black"}'
        # Optional: commit message for automated changes
        commit_message: "[CI] Format Markdown code snippets"


## Configuration

See `action.yml` for all input parameters.

## Support

For issues or feature requests, please open an issue on the GitHub repository.
