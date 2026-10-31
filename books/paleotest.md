# 🦖 PaleoTest: Prehistoric Rebirth

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/paleotest
- **Mod Name**: `paleotest`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: Adds Prehistoric Fauna and Flora to Minetest Game

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`, `walls`, `stairs`, `mobkit`, `mob_core`, `mcl_core`, `mcl_sounds`, `mcl_fences`, `mcl_stairs`, `mcl_farming`, `mcl_wool`, `mcl_mobitems`, `mcl_books`, `mcl_buckets`, `mcl_copper`, `mcl_bronze`
- **Asset Structure**: `LICENSE`, `README.md`, `api`, `crafting.lua`, `craftitems.lua`, `dna_cultivator.lua`, `feeders.lua`, `fossil_analyzer.lua`

### System Description
The `paleotest` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- Automated deployment and registration of `paleotest` components.
- Native Luanti entity/node state handling with zero external overhead.
- Interactive controls, placement nodes, and realistic behaviors in the world.

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `paleotest`
- Registered Nodes/Entities: Derived from `paleotest` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `paleotest` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `paleotest` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity paleotest:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
