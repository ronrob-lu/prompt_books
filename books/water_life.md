# water_life

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/water_life
- **Mod Name**: `water_life`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: water mobs for mobkit/minetest

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: `mobkit`, `default`
- **Optional Dependencies**: `bucket`, `petz`, `unified_inventory`, `farming`, `vessels`, `flowers`, `fireflies`, `mobs`
- **Asset Structure**: `README.md`, `animals`, `api.lua`, `behaviors.lua`, `bio.lua`, `chatcommands.lua`, `compat.lua`, `crafts.lua`

### System Description
The `water_life` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- Automated deployment and registration of `water_life` components.
- Native Luanti entity/node state handling with zero external overhead.
- Interactive controls, placement nodes, and realistic behaviors in the world.

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `water_life`
- Registered Nodes/Entities: Derived from `water_life` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `water_life` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `water_life` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity water_life:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
