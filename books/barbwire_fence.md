# Barbwire Fence Mod for Luanti/Minetest

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/barbwire_fence
- **Mod Name**: `barbwire_fence`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: a luanti mod for barbwire fence

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: `default`
- **Optional Dependencies**: `default`
- **Asset Structure**: `.gitignore`, `LICENSE.md`, `README.md`, `init.lua`, `mod.conf`, `textures`

### System Description
The `barbwire_fence` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- **2-Blocks High**: All fences stand 2 blocks tall upon placement, meaning you only need to place one node to create a secure perimeter.
- **See-Through Design**: Allows visibility, light, and projectiles (such as arrows) to pass through while keeping mobs and players out.
- **Collision Physics**: Fully prevents players and mobs from walking through the fence.
- **Facedir Rotatable**: Fences automatically face the direction you are looking when placed, and support rotation using the Screwdriver tool.
- **Craftable**: Made using standard survival items (Steel Ingots and Sticks).

---

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `barbwire_fence`
- Registered Nodes/Entities: Derived from `barbwire_fence` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `barbwire_fence` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `barbwire_fence` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity barbwire_fence:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
