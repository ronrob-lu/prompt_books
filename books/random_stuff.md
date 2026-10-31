# Random Stuff

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/random_stuff
- **Mod Name**: `random_stuff`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: **Note: This mod is just in development and nobody knows if it is needed.**

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`
- **Asset Structure**: `LICENSE`, `README.md`, `init.lua`, `minetest_anim_calc.py`, `mod.conf`, `models`, `org_files`, `patch_chest.lua`

### System Description
The `random_stuff` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- **Falling Blocks**: Adds physical structural blocks (Barrels, Chairs, Tables, Wood Structures) that behave like sand and will fall if unsupported. They can be broken by hand and are colorable.
- **Chaos Chest**: An animated storage chest with a 0.05s buffered continuous timeline animation, capable of storing items including the falling blocks.

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `random_stuff`
- Registered Nodes/Entities: Derived from `random_stuff` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `random_stuff` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `random_stuff` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity random_stuff:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
