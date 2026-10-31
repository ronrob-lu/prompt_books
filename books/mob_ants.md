# Mob Ants (`mob_ants`)

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/mob_ants
- **Mod Name**: `mob_ants`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: An emergent ant colony and stigmergy simulation mod for **Minetest / Luanti**, built on top of the `mobs_redo` framework.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: `mobs`
- **Optional Dependencies**: `default`, `mcl_core`
- **Asset Structure**: `ant.lua`, `brain.lua`, `colony.lua`, `debug.lua`, `init.lua`, `licence.md`, `mod.conf`, `models`

### System Description
The `mob_ants` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
### 🐜 Living Ant Colonies
- **Nest Core** (`mob_ants:nest_core`): The underground heart of each colony, tracking stored food, brood, and worker counts.
- **Surface Anthills** (`mob_ants:nest_mound`): Workers construct natural dome-shaped earth mounds around colony entrances.
- **Organic Colony Founding**: Colonies form organically across various biomes (grasslands, forests, savannas, deserts; cold/frozen biomes excluded).
- **Nuptial Flights & Swarming**: When a colony amasses enough food and workers, the queen triggers a nuptial flight, founding a daughter colony in distant territory.

### 👥 Castes & AI (Finite State Machine)
- **Worker Ant** (`mob_ants:ant`):
  - **Foraging & Harvesting**: Searches for flora, crops, flowers, fungi, and leaves to bring back to the nest.
  - **Excavation & Building**: Digs underground chambers and carries excavated material to build the surface mound.
  ...

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `mob_ants`
- Registered Nodes/Entities: Derived from `mob_ants` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `mob_ants` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `mob_ants` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity mob_ants:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
