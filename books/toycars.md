# Toy Cars Mod (`toy_cars`)

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/toycars
- **Mod Name**: `toycars`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: a luanti toy cars mod

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`
- **Asset Structure**: `init.lua`, `license.md`, `mod.conf`, `models`, `readme.md`, `textures`

### System Description
The `toycars` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- **Large Vehicle Scale**: Toy cars are scaled to 5.0 × 5.0 × 5.0 nodes (`visual_size = {x = 5.0, y = 5.0, z = 5.0}`, `collisionbox = {-2.5, 0.0, -2.5, 2.5, 3.5, 2.5}`).
- **Step Height & Terrain Navigation**: `stepheight = 2.0` allows cars to step up terrain obstacles up to 2 nodes high smoothly without flying or getting stuck.
- **Randomized Models**: Automatically selects randomly from 8 provided 3D vehicle models (`vehicle-drag-racer.obj`, `vehicle-monster-truck.obj`, `vehicle-racer-low.obj`, `vehicle-racer.obj`, `vehicle-speedster.obj`, `vehicle-suv.obj`, `vehicle-truck.obj`, `vehicle-vintage-racer.obj`) using shared color textures (`colormap.png`).
- **Autonomous AI & Forward Movement**:
  - Moves forward along cardinal horizontal axes in the direction the model is facing.
  - **Traffic Avoidance**: Stops and waits when players or other toy cars are directly ahead.
  - **Terrain Ob...

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `toycars`
- Registered Nodes/Entities: Derived from `toycars` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `toycars` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `toycars` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity toycars:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
