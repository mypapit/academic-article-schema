# Academic Article & Dataset Schema Generator (LLM Agent Skill)

[![Version](https://img.shields.io/badge/Version-1.0.0-informational.svg)](#)
[![Date Published](https://img.shields.io/badge/Published-2026--08--14-blueviolet.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Author](https://img.shields.io/badge/Author-Mohammad%20Hafiz%20bin%20Ismail-blue.svg)](https://mypapit.net)
[![Schema.org](https://img.shields.io/badge/Schema.org-ScholarlyArticle%20%7C%20Dataset-green.svg)](https://schema.org)
[![Google Scholar](https://img.shields.io/badge/Google%20Scholar-Inclusion%20Ready-orange.svg)](https://scholar.google.com/intl/en/scholar/inclusion.html)

**Version:** 1.0.0  
**Date Published:** 2026-08-14  
**Author:** Mohammad Hafiz bin Ismail ([mypapit@gmail.com](mailto:mypapit@gmail.com) | [https://mypapit.net](https://mypapit.net))  
**License:** [MIT License](./LICENSE)

---

A modular, production-ready **LLM Agent Skill** designed to generate complete, validated academic metadata and Schema.org JSON-LD structured data. It maximizes the indexing, citation capture, open-data discoverability, and semantic comprehension of academic papers and datasets across **Google Scholar**, **Google Dataset Search**, **Google Search**, **Reference Managers (Zotero, Mendeley)**, and **AI Research Engines (Perplexity, ChatGPT Search, Gemini, Claude, Semantic Scholar)**.

---

## 🌟 Key Features

1. **Google Scholar / Highwire Press Meta Tags (`citation_*`)**:
   - Strictly conforms to the official [Google Scholar Inclusion Guidelines](https://scholar.google.com/intl/en/scholar/inclusion.html#indexing).
   - Generates formatted `citation_title`, `citation_author`, `citation_publication_date`, `citation_pdf_url`, `citation_journal_title`, `citation_doi`, etc.
2. **Dublin Core (`DC.*`) & Open Graph / Twitter Cards**:
   - DCMI-compliant metadata for Zotero, Mendeley, and repository harvesters (OAI-PMH).
   - Social cards with graphical abstract images for social networks and messaging link unfurlers.
3. **Primary `ScholarlyArticle` JSON-LD**:
   - Features **one corresponding author** with structured ORCID and direct nested `EducationalOrganization` affiliation.
   - Enriches institutional affiliation with **`PostalAddress`** (`streetAddress`, `addressLocality`, `addressRegion`, `postalCode`, `addressCountry`).
   - Ensures mandatory fields (`headline`, `datePublished`, `dateModified`) are always present.
4. **Separate `Dataset` JSON-LD (Google Dataset Search Compatible)**:
   - Separate modular JSON-LD block for research datasets with `distribution` (`DataDownload`), open data license, and **bidirectional linking to the article via `"isBasedOn"`**.
5. **Configurable Defaults (`academic-config.json`)**:
   - Store default author profiles, ORCID IDs, institutional addresses, and publisher settings once to reuse across all papers.

---

## 📁 Repository Structure

```text
academic-article-schema/
├── SKILL.md                 # Primary LLM Agent skill definition & instructions (v1.0.0)
├── academic-config.json     # User configuration for author & affiliation defaults
├── README.md                # Documentation, version info & multi-agent guide
├── LICENSE                  # MIT License
├── references/              # Detailed specifications & tag dictionaries
│   └── google-scholar-tags.md
└── examples/                # Complete reference templates
    ├── journal-article-complete.html
    ├── dataset-and-article-linking.html
    └── preprint-and-thesis-examples.md
```

---

## 🚀 Installation & Setup

You can install and use this skill across multiple AI platforms and agents:

### 1. Google Antigravity (Gemini Agent / IDE)

Antigravity automatically discovers skills located in `.agents/skills/` or `.agent/skills/`.

#### Option A: Install in your Current Project Workspace
Clone or copy this repository into your project's `.agents/skills/` directory:
```bash
# From your project root:
mkdir -p .agents/skills
git clone https://github.com/mypapit/academic-article-schema.git .agents/skills/academic-article-schema
```

#### Option B: Global Discovery
Place the skill inside your global Antigravity config directory:
```bash
# Windows:
xcopy /E /I academic-article-schema %USERPROFILE%\.gemini\config\skills\academic-article-schema

# Linux / macOS:
cp -r academic-article-schema ~/.gemini/config/skills/academic-article-schema
```

---

### 2. ChatGPT Desktop / Codex App

ChatGPT and Codex support standalone skills as directories containing a `SKILL.md` file. Install the complete repository so the skill can also use `academic-config.json`, `references/`, and `examples/`.

#### Option A: Install in the Current Project

From the project root, clone the repository into `.agents/skills/`:

```bash
mkdir -p .agents/skills
git clone https://github.com/mypapit/academic-article-schema.git .agents/skills/academic-article-schema
```

Windows PowerShell equivalent:

```powershell
New-Item -ItemType Directory -Force .agents\skills
git clone https://github.com/mypapit/academic-article-schema.git .agents\skills\academic-article-schema
```

#### Option B: Install for Your User Account

Place the repository at `$HOME/.agents/skills/academic-article-schema` so it is available across projects:

```bash
mkdir -p "$HOME/.agents/skills"
git clone https://github.com/mypapit/academic-article-schema.git "$HOME/.agents/skills/academic-article-schema"
```

```powershell
New-Item -ItemType Directory -Force "$HOME\.agents\skills"
git clone https://github.com/mypapit/academic-article-schema.git "$HOME\.agents\skills\academic-article-schema"
```

Codex detects new and changed skills automatically. Restart the app if the skill does not appear.

#### Use the Skill

- In the ChatGPT desktop app, open **Skills** in the sidebar and select `academic-article-schema`, or type `@academic-article-schema` in Chat.
- In Codex CLI or the IDE extension, type `$academic-article-schema` to invoke it explicitly. Codex can also select it automatically when your request matches the skill description.

Example:

```text
$academic-article-schema Generate complete Google Scholar meta tags and separate
ScholarlyArticle and Dataset JSON-LD for the attached manuscript.
```

See the official [ChatGPT and Codex skills documentation](https://developers.openai.com/codex/skills).

---

### 3. Open WebUI

Open WebUI supports Markdown skills with YAML frontmatter, so this repository's `SKILL.md` can be imported directly.

#### Install

1. Download or clone this repository.
2. In Open WebUI, go to **Workspace > Skills**.
3. Click **Import** and select [`SKILL.md`](./SKILL.md). Its `name` and `description` are populated from the YAML frontmatter.
4. If other users need the skill, grant them read access or make the skill public according to your Open WebUI access policy.

#### Use

- **One message:** type `$academic-article-schema` in the chat input and select the skill.
- **Entire chat:** open the **+** menu, choose **Skills**, and enable `academic-article-schema`.
- **Reusable model:** go to **Workspace > Models**, edit a model, select this skill under **Skills**, and save.

Model-bound skills use lazy loading through the `view_skill` tool and require native function calling. If the selected model does not support native function calling, use a `$` mention or the per-chat Skills toggle so Open WebUI injects the full instructions.

To give the model access to the repository's supporting files, add `academic-config.json`, `references/`, and `examples/` to an Open WebUI Knowledge collection and attach that collection to the model or chat.

See the official [Open WebUI Skills documentation](https://docs.openwebui.com/features/workspace/skills/).

---

### 4. Anthropic Claude (Claude Projects & Artifacts)

To use this skill in **Claude 3.5 Sonnet / Claude Projects**:

1. Open **Claude** and create a new **Project** (e.g., *Academic Publishing Assistant*).
2. Click **Set Project Instructions** and paste the contents of [`SKILL.md`](./SKILL.md).
3. Under **Project Knowledge**, upload:
   - `SKILL.md`
   - `academic-config.json`
   - `references/google-scholar-tags.md`
   - `examples/journal-article-complete.html`
4. Prompt Claude:
   ```text
   Generate academic metadata and separate JSON-LD schemas for my manuscript and dataset.
   ```
   Claude will output the HTML and JSON-LD as copyable Artifacts.

---

### 5. OpenCode / Open-Source Coding Agents

To use this skill with **OpenCode Interpreter**, **Aider**, **Cursor**, or custom open-source LLM agents:

#### In Cursor / OpenCode Workspace Rules:
Add a workspace rule pointing to the skill instructions:
1. Create `.cursorrules` or `.opencode/rules.md` in your repository root.
2. Add:
   ```markdown
   When generating academic metadata, Schema.org JSON-LD, or Google Scholar tags for web pages, 
   follow the instructions defined in `.agents/skills/academic-article-schema/SKILL.md`.
   ```
3. Place this repository in `.agents/skills/academic-article-schema/`.

---

## ⚙️ Customizing Defaults (`academic-config.json`)

Edit [`academic-config.json`](./academic-config.json) to set your default author profile and institutional address:

```json
{
  "correspondingAuthor": {
    "name": "Mohammad Hafiz bin Ismail",
    "givenName": "Mohammad Hafiz",
    "familyName": "Ismail",
    "jobTitle": "Researcher & Systems Engineer",
    "identifier": "https://orcid.org/0000-0002-1825-0097",
    "email": "mypapit@gmail.com",
    "sameAs": [
      "https://mypapit.net"
    ],
    "affiliation": {
      "@type": "EducationalOrganization",
      "name": "University Name / Institute",
      "department": "Department of Computer Science",
      "url": "https://example.edu",
      "address": {
        "@type": "PostalAddress",
        "streetAddress": "123 Academic Way",
        "addressLocality": "City",
        "addressRegion": "State",
        "postalCode": "12345",
        "addressCountry": "MY"
      }
    }
  },
  "defaultPublisher": {
    "@type": "Organization",
    "name": "Academic Publisher Name",
    "url": "https://publisher.example.org"
  }
}
```

---

## 💬 Example Prompt Invocations

Once installed, trigger the skill with natural prompts:

- *"Generate complete Google Scholar meta tags and Schema.org JSON-LD for this research paper."*
- *"Create a ScholarlyArticle schema with my corresponding author details and link it to our Zenodo dataset."*
- *"Format Dublin Core, Open Graph, and Dataset JSON-LD for this publication."*

---

## 📄 License

This project is open-source and distributed under the **[MIT License](./LICENSE)**.

---

## 👤 Author

**Mohammad Hafiz bin Ismail**
- 🌐 Website: [https://mypapit.net](https://mypapit.net)
- ✉️ Email: [mypapit@gmail.com](mailto:mypapit@gmail.com)
