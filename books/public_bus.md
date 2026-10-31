# Autonomous Public Bus Mod

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/public_bus
- **Mod Name**: `public_bus`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: This is a Luanti (Minetest) mod that implements an autonomous public bus (`public_bus:bus`) which drives on specific road materials, picks up players dynamically, and follows strict pathfinding rules.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: `default`
- **Optional Dependencies**: `mg_villages`
- **Asset Structure**: `.gitignore`, `LICENSE.md`, `README.md`, `adjust_bus_size.txt`, `init.lua`, `manual-visuel-fixes.txt`, `mod.conf`, `models`

### System Description
The `public_bus` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- Automated deployment and registration of `public_bus` components.
- Native Luanti entity/node state handling with zero external overhead.
- Interactive controls, placement nodes, and realistic behaviors in the world.

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `public_bus`
- Registered Nodes/Entities: Derived from `public_bus` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `public_bus` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `public_bus` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity public_bus:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
