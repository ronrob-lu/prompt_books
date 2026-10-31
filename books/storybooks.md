# 📚 Books Mod for Minetest / Luanti

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/storybooks
- **Mod Name**: `storybooks`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: if this is not my final luanti minetest mod, it would be a never ending story

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`
- **Asset Structure**: `LICENSE.md`, `README.md`, `books`, `init.lua`, `mod.conf`, `test_books.py`, `textures`

### System Description
The `storybooks` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
- Automated deployment and registration of `storybooks` components.
- Native Luanti entity/node state handling with zero external overhead.
- Interactive controls, placement nodes, and realistic behaviors in the world.

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `storybooks`
- Registered Nodes/Entities: Derived from `storybooks` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `storybooks` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `storybooks` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity storybooks:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
