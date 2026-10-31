# LLM City Builder

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/llm_city_builder
- **Mod Name**: `llm_city_builder`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: Autonomous city-building NPC mod for **Luanti / Minetest** (MineClone2 / Mineclonia compatible).

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `mcl_sounds`, `mcl_core`, `mcl_formspec`, `default`, `player_api`, `screwdriver`
- **Asset Structure**: `README.md`, `init.lua`, `licence.md`, `mod.conf`, `models`, `nodes.lua`, `openrouter.example.json`, `structures.json`

### System Description
The `llm_city_builder` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- **Zero external mod dependencies** — Complete `ky_materials` nodes and textures are bundled inside this mod.
- **Autonomous NPC lifecycle** — Wander → Plan → Build → Lay streets → Rest → Repeat.
- **AI city planning** — OpenRouter designs every structure procedurally and explains its placement in chat.
- **Rich structure catalogue** — 10 distinct structure types included out of the box (Houses, Two-Story Houses, Shops, Churches, Parks, Watchtowers, Sand Dunes, Skyscrapers, Houses with Gardens, Two-Story Houses with Gardens). Easily extendable via `structures.json`.
- **Realistic multi-story floors & gardens** — Automatic intermediate floor slabs every 4 layers for tall buildings, perimeter fences, and open gardens with dirt paths.
- **Terrain & Water-aware** — Builds on dry land on slopes and plains. Detects and avoids underwater plots (oceans, lakes, rivers). Fills foundation gaps wit...

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `llm_city_builder`
- Registered Nodes/Entities: Derived from `llm_city_builder` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `llm_city_builder` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `llm_city_builder` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity llm_city_builder:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
