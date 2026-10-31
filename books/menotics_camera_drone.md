# Menotics Camera Drone

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/menotics_camera_drone
- **Mod Name**: `menotics_camera_drone`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: A **Luanti / Minetest** mod that adds an attachable stone block camera drone engineered for smooth, cinematic viewing with zero chat window spam.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`, `player_api`, `menotics_llm_city_builder_drone`
- **Asset Structure**: `.gitignore`, `LICENSE`, `README.md`, `config.lua`, `init.lua`, `logic.lua`, `menotics_camera_drone_stone.png`, `menotics_camera_drone_transparent.png`

### System Description
The `menotics_camera_drone` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- Automated deployment and registration of `menotics_camera_drone` components.
- Native Luanti entity/node state handling with zero external overhead.
- Interactive controls, placement nodes, and realistic behaviors in the world.

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `menotics_camera_drone`
- Registered Nodes/Entities: Derived from `menotics_camera_drone` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `menotics_camera_drone` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `menotics_camera_drone` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity menotics_camera_drone:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
