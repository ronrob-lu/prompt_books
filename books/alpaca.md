# Alpaca Mod

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/alpaca
- **Mod Name**: `alpaca`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: A Minetest/Luanti mod that adds alpacas to the game!

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`, `wool`, `mcl_core`, `mcl_wool`
- **Asset Structure**: `LICENSE.md`, `README.md`, `init.lua`, `mod.conf`, `models`, `textures`

### System Description
The `alpaca` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- Alpacas spawn in the world.
- 4 different types of alpacas: White, Light Fawn, Dark Brown, and True Black.
- Each type has distinct genetics including speed, grass detection radius, drops, and energy drain.
- Reproduction and mutation mechanics.
- Alpacas drop wool when killed.

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `alpaca`
- Registered Nodes/Entities: Derived from `alpaca` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `alpaca` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `alpaca` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity alpaca:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
