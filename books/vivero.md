# Vivero (Tree Nursery) Mod for Luanti / Minetest

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/vivero
- **Mod Name**: `vivero`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: a mod to plant random trees in a luanti world

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`, `mcl_core`, `mcl_sounds`
- **Asset Structure**: `LICENSE.md`, `README.md`, `init.lua`, `mod.conf`, `models`, `textures`

### System Description
The `vivero` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- **Game-Independent Sapling Detection**:
  Dynamically scans registered nodes for any node containing `"sapling"` in its name (e.g. `default:sapling`, `default:acacia_sapling`, `mcl_core:oak_sapling`, etc.), making it work out-of-the-box across Minetest Game, MineClone 2 / VoxeLibre, and custom games.

- **Smart Planting Conditions**:
  Before placing a sapling, the NPC checks:
  1. Soil or dirt underneath (`group:soil`, `group:crumbly`, or dirt/grass nodes).
  2. Sunlight/light level (at least light level 8).
  3. At least 3x3 horizontal open area and vertical clearance for proper tree growth.

- **Natural Movement & AI**:
  - State machine with idle/standing, walking, running, and planting states.
  - Auto-jumps over 1-block high terrain obstacles.
  - Changes direction smoothly when encountering tall walls or drop-offs.
  - Uses full 3D keyframe mesh animations (`vivero_char.b3d`).

...

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `vivero`
- Registered Nodes/Entities: Derived from `vivero` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `vivero` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `vivero` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity vivero:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
