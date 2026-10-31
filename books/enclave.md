# Enclave (Unified Fortification Mod for Luanti/Minetest)

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/enclave
- **Mod Name**: `enclave`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: An advanced, unified fortification and tactical defense mod for **Luanti (Minetest)**. Combining the historical architecture of the Berlin Wall, industrial security of barbed wire fences, and tactical hostile mob behaviors, **Enclave** allows players to generate a massive, fully fortified, closed-loop border base that dynamically adapts to world terrain.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`, `stairs`, `xpanes`, `mcl_core`, `mcl_sounds`, `mcl_books`, `mcl_stairs`, `mcl_panes`, `mcl_flowers`, `mcl_torches`, `mcl_glass`
- **Asset Structure**: `README.md`, `generator.lua`, `init.lua`, `mobs.lua`, `mod.conf`, `models`, `nodes.lua`, `schematics`

### System Description
The `enclave` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- 🏗️ **Adaptive Base Generation**: Placing the **Enclave Generator Core** triggers the construction of a massive $244 \times 244$ block base centered on the core.
- ⛰️ **Contour-Adaptive Snapping**: Fences, straight concrete walls, and perimeter lines snap exactly to the local terrain heights (including seabed surfaces underwater) column-by-column, ensuring no gaps or floating blocks on hills or valleys.
- 🏰 **Flat Watchtowers**: Watchtowers generate perfectly flat at their center ground coordinates, dynamically building concrete/sandstone foundations downwards to bridge any gaps on slopes.
- 🌿 **Automatic Foliage Excavation**: Clears column vegetation, trees, and dirt from `gy + 1` up to `gy + 25` prior to building, preventing plants or tree leaves from clipping through the fortifications.
- 🛡️ **Guarded Patrol Corridor**: Hostile perimeter guards spawn inside the boundary corridors, pa...

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `enclave`
- Registered Nodes/Entities: Derived from `enclave` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `enclave` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `enclave` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity enclave:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
