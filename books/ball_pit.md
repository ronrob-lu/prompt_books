# Mine Test Ball Pit (Bällebad)

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/ball_pit
- **Mod Name**: `ball_pit`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: A relaxing ball pit mod with physics-based rainbow balls and a spawner.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`
- **Asset Structure**: `LICENSE.md`, `README.md`, `build_assets.py`, `init.lua`, `mod.conf`, `models`, `readme.md`, `textures`

### System Description
The `ball_pit` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- Physics-based balls that are exactly 1/4 of a standard block size.
- 7 different rainbow colors (Red, Orange, Yellow, Green, Blue, Indigo, Violet).
- Balls naturally stack and spread out (simulating a real ball pit).
- Both the spawner and the balls are destroyable.
- Balls can be grabbed and spawned manually anywhere.
- completely silent, NO sound effects.

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `ball_pit`
- Registered Nodes/Entities: Derived from `ball_pit` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `ball_pit` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `ball_pit` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity ball_pit:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
