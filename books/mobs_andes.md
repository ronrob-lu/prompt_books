# Mobs Andes 🦙

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/mobs_andes
- **Mod Name**: `mobs_andes`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: **Bring the vibrant, rugged spirit of the South American Andes to your Luanti (Minetest) world!**

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: `mobs`
- **Optional Dependencies**: `default`, `ethereal`, `mcl_core`, `mcl_flowers`
- **Asset Structure**: `LICENCE.md`, `README.md`, `alpaca.lua`, `capybara.lua`, `dog.lua`, `donkey.lua`, `init.lua`, `locale`

### System Description
The `mobs_andes` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- Automated deployment and registration of `mobs_andes` components.
- Native Luanti entity/node state handling with zero external overhead.
- Interactive controls, placement nodes, and realistic behaviors in the world.

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `mobs_andes`
- Registered Nodes/Entities: Derived from `mobs_andes` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `mobs_andes` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `mobs_andes` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity mobs_andes:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
