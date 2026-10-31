# Winkers Mod

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/winkers
- **Mod Name**: `winkers`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: This project features characters that simply stand there and wink. Sometimes, the simplest actions make the biggest impression.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: None (Independent)
- **Optional Dependencies**: `default`
- **Asset Structure**: `.gitignore`, `LICENSE.md`, `README.md`, `init.lua`, `mod.conf`, `models`, `textures`

### System Description
The `winkers` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
This project features characters that simply stand there and wink. Sometimes, the simplest actions make the biggest impression.

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `winkers`
- Registered Nodes/Entities: Derived from `winkers` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `winkers` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `winkers` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity winkers:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
