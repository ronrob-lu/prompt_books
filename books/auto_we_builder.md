# Auto WE Builder NPC Mod

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/auto_we_builder
- **Mod Name**: `auto_we_builder`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: ========================

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: `default`
- **Optional Dependencies**: `default`
- **Asset Structure**: `.gitignore`, `README.md`, `init.lua`, `mod.conf`, `models`, `schema`, `textures`

### System Description
The `auto_we_builder` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- NPC follows behind the player with realistic walking physics (gravity, ground collision)
- Right-click to open building selection menu
- Selects from `.we` files in the `schema/` folder
- Builds layer by layer, moving upward as needed
- Realistic player-like appearance with walking and building animations
- Uses custom `auto_we_builder.b3d` model and texture

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `auto_we_builder`
- Registered Nodes/Entities: Derived from `auto_we_builder` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `auto_we_builder` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `auto_we_builder` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity auto_we_builder:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
