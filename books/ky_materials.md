# KY Materials (`ky_materials`)

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/ky_materials
- **Mod Name**: `ky_materials`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: A modular building materials and supply box mod for **Luanti** (formerly Minetest).

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`, `mcl_core`, `mcl_sounds`, `mcl_formspec`, `mcl_chests`, `screwdriver`
- **Asset Structure**: `init.lua`, `licence.md`, `mod.conf`, `models`, `readme.md`, `textures`

### System Description
The `ky_materials` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
### 1. Material Supply Chest (`ky_materials:box`)
- **3D Mesh Appearance**: Custom box model using Kenney's prototype palette (`colormap.png`).
- **Prefilled Supply**: When placed in the world, the box is automatically stocked with a full stack (99 items) of every building material in the mod.
- **Chest Functionality**: Acts as a regular interactive chest allowing players to take materials out, store items, and organize inventory.

### 2. Connected Fences
- `ky_materials:fence_wood` (Wood Fence)
- `ky_materials:fence_stone` (Stone Fence)
- Real 3D connected nodebox structure (thin posts and rails) that smoothly connects to other fences, walls, wood, stone, and tree nodes.

### 3. Rotatable Trunks (Top & Side Textures)
- `ky_materials:trunk` (Standard Trunk)
- `ky_materials:trunk_white` (White Trunk)
- Features directional rotation (`paramtype2 = "facedir"` and `on_place = minetest.rotate...

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `ky_materials`
- Registered Nodes/Entities: Derived from `ky_materials` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `ky_materials` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `ky_materials` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity ky_materials:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
