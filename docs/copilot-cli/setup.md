# My Copilot CLI Setup: How I Get Things Done on Windows & macOS

I've been using GitHub Copilot CLI as part of my daily workflow for a while now, and it's genuinely changed how productive I feel — especially in a corporate environment with Work IQ. This guide documents exactly how I set things up on both my Windows desktop and my Mac. It's not an official manual; it's just what works for me. Hopefully it saves you the trial-and-error I went through.

> **Note:** While most of these steps work anywhere, the Work IQ integration gives you the most value when you're on your corporate network. That said, Copilot CLI itself is useful regardless of where you're working from.

---

## Prerequisites

Before diving in, make sure you have the following on your machine. I use [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/) on Windows and [Homebrew](https://brew.sh/) on macOS to keep installs clean and repeatable.

### 1. Git

**Windows (winget):**
```powershell
winget install -e --id Git.Git
```

**macOS (Homebrew):**
```bash
brew install git
```

If you're reading this wiki, you probably already have Git — but just in case, this ensures you're on the exact stable release.

### 2. Node.js

Node.js is only required if you plan to install Copilot CLI via `npm`. If you're using Homebrew on macOS or WinGet on Windows, you can skip this step.

**Windows (winget):**
```powershell
winget install -e --id OpenJS.NodeJS
```

**macOS (Homebrew):**
```bash
brew install node
```

After installation, open a new terminal and confirm:

```bash
node --version
npm --version
```

### 3. Azure CLI

Required if you're working with Azure-backed services or authenticating through your corporate identity.

**Windows (winget):**
```powershell
winget install -e --id Microsoft.AzureCLI
```

**macOS (Homebrew):**
```bash
brew install azure-cli
```

---

## Installing GitHub Copilot CLI

Once your prerequisites are in place, install the Copilot CLI itself:

**Windows (winget):**
```powershell
winget install GitHub.Copilot
```

**macOS (Homebrew):**
```bash
brew install copilot-cli
```

**All platforms (npm):**
```bash
npm install -g @github/copilot
```

After installation, restart your terminal. You should now have access to the `copilot` command.

> **Official docs:** For the full list of install methods (install script, direct download, prerelease versions), see the [GitHub Copilot CLI installation guide](https://docs.github.com/en/copilot/how-tos/copilot-cli/set-up-copilot-cli/install-copilot-cli).

---

## Logging In

On first launch, Copilot CLI will prompt you to authenticate. Run:

```
/login
```

This opens a browser window where you sign in with your **GitHub account**. Once authenticated, you're ready to start chatting.

### Choosing a Model

After logging in, you can switch the underlying AI model to match your task. Use the `/model` command:

```
/model
```

This presents a list of available models (e.g., GPT-4o, Claude Sonnet, o3-mini). Select the one you want and Copilot will use it for all subsequent interactions in that session.

> **Tip:** Your model choice persists across sessions, so you only need to set it once unless you want to change it.

---

## Setting Up Work IQ (Corporate Integration)

This is the part that took me the most time to figure out. Work IQ is what makes Copilot genuinely powerful in a corporate environment — it integrates with internal knowledge bases and company-specific context so your AI assistant actually knows your stack.

### Add the Copilot Plugins Marketplace

```
/plugin marketplace add github/copilot-plugins
```

### Install the Work IQ Plugin

```
/plugin install workiq@copilot-plugins
```

### Accept the EULA

Before Work IQ starts working, you'll need to accept the End User License Agreement:

```
/workiq accept-eula
```

Once this is done, Copilot will have access to Work IQ features. In my experience, the difference is immediately noticeable — the responses become much more contextually aware of our internal tooling.

---

## Bonus: Speech-to-Text with Handy

I like talking through problems more than typing them, so I installed [Handy](https://handy.computer/) for speech-to-text input. It integrates seamlessly with any text field, so I can just speak my prompts to Copilot. Highly recommended if you do a lot of exploratory querying.

---

## Want to Go Deeper?

This guide covers the basics of my setup — enough to get you productive. But if you want to go further with advanced configuration, custom plugins, or more nuanced workflows, check out the community guide by Nish Anil:

👉 **[nishanil.github.io/copilot-guide](https://nishanil.github.io/copilot-guide/)**

It's a much more comprehensive reference for everything Copilot CLI can do.

---

## Quick Reference

| Tool | Windows (winget) | macOS (Homebrew) |
|---|---|---|
| Git | `winget install -e --id Git.Git` | `brew install git` |
| Node.js | `winget install -e --id OpenJS.NodeJS` | `brew install node` |
| Azure CLI | `winget install -e --id Microsoft.AzureCLI` | `brew install azure-cli` |
| GitHub CLI | `winget install GitHub.Copilot` | `brew install gh` |
| Copilot CLI extension | *(bundled)* | `gh extension install github/gh-copilot` |
| Handy (speech-to-text) | [handy.computer](https://handy.computer/) | [handy.computer](https://handy.computer/) |

| Plugin Command | Purpose |
|---|---|
| `/plugin marketplace add github/copilot-plugins` | Add the plugins marketplace |
| `/plugin install workiq@copilot-plugins` | Install Work IQ plugin |
| `/workiq accept-eula` | Accept Work IQ license |

---

*Last updated: March 2026 — feel free to open a PR if anything's changed or you've found a better way to do something!*
