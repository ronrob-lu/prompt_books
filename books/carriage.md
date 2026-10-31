# Carriage Mod

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/carriage
- **Mod Name**: `carriage`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: a luanti mod with a carriage

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`, `mobs`, `mob_horse`, `mobs_andes`, `mcl_core`, `mcl_wool`, `mobs_mc`, `mcl_formspec`
- **Asset Structure**: `LICENSE.md`, `README.md`, `fix_optical_problems.txt`, `init.lua`, `locale`, `mod.conf`, `models`, `textures`

### System Description
The `carriage` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- Craft the desired carriage.
- Place it down and ride it! Requires a horse, donkey, or dog to be near the front to attach automatically.
- Press `W` to increase speed (speeds 1, 2, 3), and `S` to decrease speed (speeds 3, 2, 1, 0). Steer with `A` and `D`. (Controls do not apply to the autonomous Transport Carriage).

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `carriage`
- Registered Nodes/Entities: Derived from `carriage` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `carriage` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `carriage` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity carriage:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
