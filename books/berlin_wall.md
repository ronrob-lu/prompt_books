# Berlin Wall Mod for Luanti/Minetest

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/berlin_wall
- **Mod Name**: `berlin_wall`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: a luanti mod resembling the berlin wall

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`
- **Asset Structure**: `.gitignore`, `LICENSE.md`, `README.md`, `init.lua`, `mod.conf`, `screenshot-berlin-wall.png`, `textures`

### System Description
The `berlin_wall` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
& Blocks Included

| Block / Item | Description | Light Level | Command to Give |
| :--- | :--- | :--- | :--- |
| **Search Light**<br>`berlin_wall:search_light` | A powerful wall-mounted or freestanding light source to illuminate your border posts. | 10 | `/giveme berlin_wall:search_light` |
| **Fence Site**<br>`berlin_wall:fence_site` | A mesh fence block designed for placement on tower tops or perimeter barriers. | None | `/giveme berlin_wall:fence_site` |
| **Grenzmauer 75 Top**<br>`berlin_wall:grenzmauer_top` | The wall cap fitted with a smooth, semi-circular concrete pipe to prevent climbers from gaining a foothold. Automatically aligns based on player rotation. | None | `/giveme berlin_wall:grenzmauer_top` |
| **Berlin Wall Block**<br>`berlin_wall:wall_block` | The standard solid wall block showing concrete/stone textures on all sides. | None | `/giveme berlin_wall:wall_block` |

-...

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `berlin_wall`
- Registered Nodes/Entities: Derived from `berlin_wall` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `berlin_wall` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `berlin_wall` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity berlin_wall:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
