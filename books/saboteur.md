# 🧨 Saboteur NPC

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/saboteur
- **Mod Name**: `saboteur`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: A persistent, AI-driven NPC mod for Luanti/Minetest. Saboteurs roam your world and make independent decisions every in-game day. Will they place TNT today? Will they flee or stay to watch the explosion? Survivors persist indefinitely, creating dynamic, emergent tension in survival and building servers.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `tnt`, `protector`, `areas`
- **Asset Structure**: `README.md`, `init.lua`, `mod.conf`, `models`, `saboteur`, `textures`

### System Description
The `saboteur` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- Automated deployment and registration of `saboteur` components.
- Native Luanti entity/node state handling with zero external overhead.
- Interactive controls, placement nodes, and realistic behaviors in the world.

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `saboteur`
- Registered Nodes/Entities: Derived from `saboteur` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `saboteur` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `saboteur` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity saboteur:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
