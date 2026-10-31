# Menotics Water, Lava & Fire Drones

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/menotics_water_lava_fire
- **Mod Name**: `menotics_water_lava_fire`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: **Mod name:** `menotics_water_lava_fire`

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`, `fire`, `mcl_core`, `mcl_fire`
- **Asset Structure**: `LICENSE`, `README.md`, `init.lua`, `mod.conf`, `textures`

### System Description
The `menotics_water_lava_fire` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
1. Craft the desired drone spawner.
2. Place the block anywhere — it immediately converts into a flying drone entity.
3. The drone flies within a 50-block horizontal radius of its placement point.
4. Punch the drone to retrieve it as an item.

---

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `menotics_water_lava_fire`
- Registered Nodes/Entities: Derived from `menotics_water_lava_fire` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `menotics_water_lava_fire` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `menotics_water_lava_fire` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity menotics_water_lava_fire:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
