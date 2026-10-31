# Plutonium's Ships

## Overview & Architecture
- **Repository**: https://github.com/ronrob-lu/plutoniumships
- **Mod Name**: `plutoniumships`
- **Classification**: Luanti / Minetest World Asset & Functional System
- **Core Function**: Turn your constructions into boats or blimps and set off on the adventure aboard the ship of your dreams.

### Mod Manifest & Dependencies
- **Mandatory Dependencies**: `default`, `wool`
- **Optional Dependencies**: `xdecor`
- **Asset Structure**: `README.md`, `description.txt`, `init.lua`, `license.txt`, `mod.conf`, `models`, `screenshot.png`, `settingtypes.txt`

### System Description
The `plutoniumships` package provides specialized Luanti mechanics, entities, nodes, or structures designed for high-performance integration and procedural world expansion.
---
## System Mechanics & Components

### Key Capabilities & Mechanics
& Highlights

- **Complete Creative Freedom**: Build your ship however you like using a wide range of blocks. If you can build it, you can pilot it!
- **Sea & Sky**: Create majestic sailing ships, steampunk airships, or speedy modern boats.
- **Simple Controls**: Place a helm, board your creation, and steer it through the world with ease.
- **Dynamic Physics & Entities**: The mod transforms your block-based structures into moving entities, allowing smooth travel across the map.

### Key Nodes, Entities & Inventory Items
- Mod Identifier: `plutoniumships`
- Registered Nodes/Entities: Derived from `plutoniumships` assets and definition tables.
- Collision & Physics: Standard Luanti voxel collision and physics controller integration.
- Custom Properties: Interactive activation, state synchronization, and persistent storage.
---
## AI NPC Construction & Operational Blueprint

### Protocol for Luanti AI NPC Workers
Luanti AI NPCs (e.g., `llm_npc_core`, `auto_we_builder`, or automated worker bots) must follow these operational steps to build and integrate the `plutoniumships` contents in the world:

1. **Workspace Verification & Preparation**:
   - Locate a suitable build site. Clear obstacles within bounding radius.
   - Verify required node materials in inventory or spawn dependencies (`default:dirt`, `default:stone`, `default:wood`, or mod-specific items).

2. **Placement & Assembly Sequence**:
   - Align construction orientation according to player or target vector `(x, y, z)`.
   - Place foundation nodes layer-by-layer starting at ground level `y = 0`.
   - If `plutoniumships` defines entities (vehicles, mobs, drones, NPCs), spawn entity using `/spawnentity plutoniumships:<entity_id>` or place spawn nodes.
   - Initialize internal node metadata, timers, and formspec triggers as specified in the mod API.

3. **Autonomous Verification & Maintenance**:
   - Check collision boxes and ensure entities/nodes are unblocked.
   - Run activation routines or trigger test interactions (right-click / `on_rightclick`).
   - Log completed construction status to AI NPC memory and coordinate registry.
