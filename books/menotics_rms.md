# RMS Menotics Cruise Ship Mod (`rms_menotics`) for Luanti / Minetest

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/menotics_rms
- **Mod Name**: `menotics_rms`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: **RMS Menotics** is a complete, standalone, ocean liner mod for Luanti / Minetest (supporting **Minetest Game**, **Mineclonia**, and **VoxeLibre**).

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`, `mcl_core`, `mcl_sounds`, `mcl_sounds_core`, `mcl_tools`, `mcl_chests`, `mcl_furnaces`, `mcl_beds`, `mcl_crafting_table`, `mcl_fences`, `mcl_doors`, `mcl_stairs`
- **Asset Structure**: `ANIMATION_RESEARCH.md`, `README.md`, `check_bug.lua`, `check_lua_0.lua`, `check_minus_zero.lua`, `commands.lua`, `compat.lua`, `entity.lua`

### System Description
The `menotics_rms` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- Automated deployment and registration of `menotics_rms` components.
- Native Luanti entity/node state handling with zero external overhead.
- Interactive controls, placement nodes, and realistic behaviors in the world.

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `menotics_rms`
- Registered Nodes/Entities: Derived from `menotics_rms` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `menotics_rms` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `menotics_rms` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity menotics_rms:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
