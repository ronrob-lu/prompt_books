# Mobs Chaos NPCs

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/mobs_chaos_npcs
- **Mod Name**: `mobs_chaos_npcs`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: A Luanti (Minetest) mod built on the `mobs` API. This mod introduces Human and Orc NPC factions.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: `mobs`
- **Optional Dependencies**: `default`
- **Asset Structure**: `ANIMATION_GUIDE.txt`, `LICENSE`, `README.md`, `init.lua`, `minetest_anim_calc.py`, `mod.conf`, `models`, `textures`

### System Description
The `mobs_chaos_npcs` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- **Human Faction**: Friendly toward players and other Humans. They will aggressively attack non-humans.
- **Orc Faction**: Hostile to players, Humans, and other non-orc mobs. Only friendly to other Orcs.

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `mobs_chaos_npcs`
- Registered Nodes/Entities: Derived from `mobs_chaos_npcs` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `mobs_chaos_npcs` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `mobs_chaos_npcs` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity mobs_chaos_npcs:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
