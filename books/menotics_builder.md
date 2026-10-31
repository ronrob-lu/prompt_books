# Menotics Builder

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/menotics_builder
- **Mod Name**: `menotics_builder`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: A unified Luanti (Minetest) mod that combines automated, autonomous landscaping drones with cooperative, terminal-controlled schematic building drones.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: `default`
- **Optional Dependencies**: `default`
- **Asset Structure**: `README.md`, `init.lua`, `mod.conf`, `schema`, `textures`

### System Description
The `menotics_builder` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- **Cooperative Schematic Building (Green Builder Drone)**:
  - Place a **Terminal Block** and select from `.we` schematic files in the `schema/` directory.
  - Set the build speed (1x, 2x, 3x) and start construction.
  - Place one or more **Builder Drones** near the terminal. They will cooperatively build the structure layer-by-layer in front of the terminal, aligned with the terminal's placement orientation.
  - When idle (no build in progress), the drones will patrol/orbit around the terminal block.
  - Glowing neon green thrusters and construction scan lasers.
- **Autonomous Landscaping (Blue Landscaper Drone)**:
  - Queries local biomes and shapes terrain by placing top soil, filler, stone, plants, and trees.
  - Features overcrowding protection to keep trees spaced out naturally.
  - Glowing neon green scanning laser beams.
- **Autonomous Lake Excavation (Yellow Lake Drone)**:
  - ...

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `menotics_builder`
- Registered Nodes/Entities: Derived from `menotics_builder` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `menotics_builder` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `menotics_builder` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity menotics_builder:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
