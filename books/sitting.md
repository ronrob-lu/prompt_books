# Sit on Beds Mod

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/sitting
- **Mod Name**: `sitting`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: A Luanti/Minetest mod that allows players to sit on beds (or any registered bed-like object) during daytime.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `beds`, `player_api`, `mcl_player`
- **Asset Structure**: `.gitignore`, `LICENSE.md`, `README.md`, `init.lua`, `mod.conf`, `textures`, `textures_file_backup.png`

### System Description
The `sitting` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- Sit on beds during daytime without sleeping
- Full 360-degree rotation while sitting
- Look around freely while seated
- Compatible with any object registered as a bed
- Easy to extend for other sit-able objects

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `sitting`
- Registered Nodes/Entities: Derived from `sitting` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `sitting` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `sitting` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity sitting:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
