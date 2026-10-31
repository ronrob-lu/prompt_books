# Menotics Landscaper Drone

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/menotics_landscaper
- **Mod Name**: `menotics_landscaper`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: A Luanti (Minetest) mod that introduces automated, autonomous landscaping drones. Once crafted and deployed, these drones fly around within a 50-block radius and shape the local terrain. The mod features two types of drones: a **Blue Landscaper Drone** for biome-specific terrain/plants/trees, and a **Yellow Lake Landscaper Drone** for carving lakes, placing sand beaches, and building sand dunes.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`
- **Asset Structure**: `LICENSE`, `README.md`, `init.lua`, `mod.conf`, `textures`

### System Description
The `menotics_landscaper` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- **Autonomous Flight**: Drones fly smoothly, adapting their height (5–12 blocks) to follow the contours of the terrain.
- **Biomes & Lakes**:
  - **Blue Drone**: Queries the local biome and places matching top soil, filler blocks, stone, plants, and trees.
  - **Yellow Drone**: Carves a deep lake basin centered on its spawn point, fills it with water (level with the spawn point), creates a flat sandy beach transition, and mounds wavy sand dunes with beach grass further out.
- **Overcrowding Protection**: Blue drones plant trees with built-in spacing protection (minimum 5-block distance between trees) to prevent overcrowding.
- **High-Quality Visual Effects**: Custom pixel-art textures (blue/yellow themed solar panels, thrusters, camera lenses, and chassis lights) and glowing, neon-colored scanning laser beams.
- **Multi-Drone Capability**: Spawn multiple drones in the same area to shap...

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `menotics_landscaper`
- Registered Nodes/Entities: Derived from `menotics_landscaper` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `menotics_landscaper` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `menotics_landscaper` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity menotics_landscaper:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
