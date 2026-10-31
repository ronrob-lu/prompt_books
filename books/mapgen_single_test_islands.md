# 🏝️ Island Gen 🏝️

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/mapgen-single-test-islands
- **Mod Name**: `mapgen-single-test-islands`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: A Minetest/Luanti mod that generates a specific island map configuration when the world starts! 🌊

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: `default`, `biomegen`
- **Optional Dependencies**: `default`
- **Asset Structure**: `.gitignore`, `LICENSE.md`, `init.lua`, `mod.conf`, `readme.md`, `source_mods`, `test_plan.sh`

### System Description
The `mapgen-single-test-islands` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- Automated deployment and registration of `mapgen-single-test-islands` components.
- Native Luanti entity/node state handling with zero external overhead.
- Interactive controls, placement nodes, and realistic behaviors in the world.

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `mapgen-single-test-islands`
- Registered Nodes/Entities: Derived from `mapgen-single-test-islands` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `mapgen-single-test-islands` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `mapgen-single-test-islands` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity mapgen-single-test-islands:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
