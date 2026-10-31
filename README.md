# 📚 prompt_books Mod for Luanti / Minetest

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE.md)

Transform your Minetest / Luanti worlds into an AI-driven, interactive architectural and mechanical library! The **`prompt_books`** mod serves as the official in-game Luanti documentation repository for all published mods created by **ronrob-lu**.

Every book in `books/` is crafted with structured, highly detailed guides, node and entity definitions, schematics, and autonomous prompt instructions. These books allow both players and **Luanti AI NPCs** (such as `llm_npc_core` or `auto_we_builder`) to read documentation in-game and autonomously build, spawn, configure, and maintain the contents of the mods in the world!

---

## ✨ Features

- 🤖 **AI NPC Blueprint & Prompt Manuals**: Books provide exact node IDs, entity names, parameters, building recipes, and step-by-step assembly instructions optimized for autonomous LLM NPCs.
- 📖 **Complete ronrob-lu Mod Library**: Contains specialized documentation books for every published mod repository by ronrob-lu.
- 📝 **Markdown-Powered Engine**: Automatically parses `.md` files directly from the `books/` directory into interactive in-game craftitem books.
- 📑 **Multi-Page Reader GUI**: Clean, interactive book reading interface with custom page formatting and seamless `< Previous` / `Next >` navigation.
- ✂️ **Selectable & Copyable Text**: Text inside the books can be easily selected, inspected, or ingested by LLM agents.
- 🛠️ **Fully Extensible**: Adding new in-game documentation or AI prompts is as simple as dropping a new `.md` file into the `books/` folder!

---

## 🚀 Installation

1. Download or clone this repository into your mods directory:
   ```bash
   git clone https://github.com/ronrob-lu/prompt_books.git prompt_books
   ```
2. Place the `prompt_books` folder into your Minetest/Luanti `mods/` directory.
3. Enable `prompt_books` in your world configuration or `world.mt`:
   ```text
   load_mod_prompt_books = true
   ```

---

## 📖 How to Use

### For Players
- **Reading Books**: Hold any prompt book in your hand and **left-click (use)** or **right-click** to open the reading GUI.
- **Page Navigation**: Click **`< Previous`** and **`Next >`** buttons at the bottom of the book interface to navigate through chapters and pages.

### For Luanti AI NPCs
- AI NPCs equipped with inventory inspection or text reading tools can read `prompt_books:<mod_name>` items.
- The books are structured with:
  1. **Mod Overview & Identifiers**: Mod name, craftitems, nodes, and entities.
  2. **Assembly & Construction Blueprints**: Exact dimensions, block layouts, and placement coordinates.
  3. **Configuration & Control Instructions**: Operating parameters, chat commands, and event triggers.
  4. **AI NPC Direct Action Instructions**: Machine-actionable steps for autonomous reconstruction.

---

## 🏗️ Technical Details & API

- **Mod Name**: `prompt_books`
- **Dependencies**: None (Optional: `default`)
- **Structure**:
  - `init.lua`: Core Lua code for loading books, parsing Markdown, registering craftitems, and managing formspecs.
  - `books/`: Contains Markdown books for each ronrob-lu repository.
  - `textures/`: Contains PNG cover textures (`Book1_Closed.png` through `Book8_Closed.png`) and reader background (`books_bg.png`).

---

## 📜 License

This project is licensed under the **MIT License** - see the [LICENSE.md](LICENSE.md) file for details.

Copyright (c) 2026 **ronrob-lu**
