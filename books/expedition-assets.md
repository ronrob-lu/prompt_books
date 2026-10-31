# 🧭 Expedition Assets

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/expedition-assets
- **Mod Name**: `expedition-assets`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: ---

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`, `wool`, `stairs`, `doors`, `farming`, `player_api`, `creative`, `mobs`, `mcl_core`, `mcl_sounds`, `mcl_wool`, `mcl_mobs`, `mcl_player`, `mcl_stairs`, `mcl_doors`, `mcl_torches`, `mcl_fences`, `mcl_furnaces`, `mcl_books`, `mcl_copper`, `mcl_deepslate`, `mcl_farming`
- **Asset Structure**: `LICENSE.md`, `README.md`, `dev`, `init.lua`, `mod.conf`, `models`, `reference_images`, `source`

### System Description
The `expedition-assets` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- Automated deployment and registration of `expedition-assets` components.
- Native Luanti entity/node state handling with zero external overhead.
- Interactive controls, placement nodes, and realistic behaviors in the world.

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `expedition-assets`
- Registered Nodes/Entities: Derived from `expedition-assets` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `expedition-assets` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `expedition-assets` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity expedition-assets:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
