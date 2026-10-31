# sfstreets

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/city-cars
- **Mod Name**: `city-cars`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: A Luanti Mod that spawns non-controllable NPC cars in the world.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`
- **Asset Structure**: `Preview.png`, `init.lua`, `license.md`, `mod.conf`, `models`, `readme.md`, `textures`

### System Description
The `city-cars` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
* Adds 23 different vehicle models.
* Spawns cars dynamically around online players.
* Cars move autonomously along horizontal axes, avoiding obstacles and falling into deep holes.
* Lightweight simulation with a configurable limit of max cars.

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `city-cars`
- Registered Nodes/Entities: Derived from `city-cars` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `city-cars` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `city-cars` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity city-cars:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
