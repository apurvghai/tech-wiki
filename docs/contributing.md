---
layout: default
title: Contribute
nav_order: 99
description: "How to contribute to Tech Wiki"
permalink: /contributing/
---

# Contributing to Tech Wiki
{: .fs-9 }

Thank you for your interest in making this wiki better!
{: .fs-6 .fw-300 }

---

## How to Contribute

This wiki is open source and welcomes contributions from the community. Here's how you can help:

### 1. Report Issues

Found an error or outdated information?

{: .highlight }
> [Open an issue](https://github.com/apurvghai/tech-wiki/issues/new) on GitHub describing what needs to be fixed.

### 2. Submit Pull Requests

Have improvements or new content to add?

1. Fork the repository
2. Create a new branch for your changes
3. Make your edits
4. Submit a pull request

---

## Content Guidelines

When contributing content, please follow these guidelines:

### Writing Style

- **Be concise**: Get to the point quickly
- **Be practical**: Include working examples
- **Be accurate**: Test all commands before documenting them
- **Be specific**: Mention versions, platforms, and prerequisites

### Formatting

| Element | Format |
|:--------|:-------|
| Commands | Use code blocks with language hints |
| Important notes | Use callout blocks (`{: .note }`) |
| File paths | Use inline code |
| Links | Use descriptive link text |

### Code Examples

```bash
# Good example: includes comments and context
# Install GitHub Copilot CLI on macOS
brew install copilot-cli
```

---

## File Structure

The wiki follows this structure:

```
docs/
├── _config.yml          # Jekyll configuration
├── index.md             # Home page
├── contributing.md      # This page
└── copilot-cli/         # Topic folder
    ├── index.md         # Topic overview
    └── setup.md         # Specific guide
```

### Adding a New Topic

1. Create a new folder under `docs/`
2. Add an `index.md` with front matter:

```markdown
---
layout: default
title: Your Topic
nav_order: 3
has_children: true
permalink: /your-topic/
---
```

3. Add child pages with `parent: Your Topic` in front matter

---

## Local Development

To preview your changes locally:

```bash
# Install Jekyll (one-time setup)
gem install bundler jekyll

# Navigate to docs directory
cd docs

# Install dependencies
bundle install

# Start local server
bundle exec jekyll serve
```

Then open [http://localhost:4000](http://localhost:4000) in your browser.

---

## Code of Conduct

- Be respectful and constructive
- Focus on improving the content
- Credit original sources when applicable

---

## Questions?

If you have questions about contributing, feel free to:

- [Open a discussion](https://github.com/apurvghai/tech-wiki/discussions)
- [Check existing issues](https://github.com/apurvghai/tech-wiki/issues)

Thank you for helping make Tech Wiki better for everyone!
