# Menotics Light Drone (Theater Spot)

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/menotics_light_drone
- **Mod Name**: `menotics_light_drone`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: A **Luanti / Minetest** mod that creates a floating theater spotlight block that follows a **configurable target** (players, NPCs, or mobs) from **12 blocks above**, emitting light level **14** using dynamic glowing air and overhead spotlight blocks.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`, `mcl_core`, `ronrob_npc`, `glow_air`
- **Asset Structure**: `LICENSE`, `README.md`, `init.lua`, `mod.conf`, `settingtypes.txt`, `textures`

### System Description
The `menotics_light_drone` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- **Real Floating Spotlight Block**: A textured, glowing theater spotlight block (`menotics_spot_top.png`, `menotics_spot_bottom.png`, `menotics_spot_side.png`) floats 12 blocks directly over the actor with a bright spotlight lens shining downward.
- **True Stage Illumination (Light Level 14)**:
  - Illuminates overhead at the floating spotlight block (light 14).
  - Illuminates directly onto the actor/stage below (light 14), overcoming Luanti's distance light attenuation so the target is brightly lit in the spotlight beam.
- **Configurable Target Tracking**: Follows players, specific usernames, NPCs, or mobs with automatic detection and smooth aerial flight.
- **Destroyable with Pickaxe**: Hit the floating drone with any pickaxe to dismantle it, cleanly clearing its light and dropping a Spawn Egg item.
- **Spawn Egg**: Spawns the spotlight using the custom **Spot Spawn Egg** item.
- **C...

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `menotics_light_drone`
- Registered Nodes/Entities: Derived from `menotics_light_drone` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `menotics_light_drone` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `menotics_light_drone` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity menotics_light_drone:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
